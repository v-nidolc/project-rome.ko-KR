---
title: 명령을 원격 장치 및 앱 (Android)
description: 이 가이드에서는 원격 장치 및 앱을 검색 한 다음 앱을 시작 및 앱 서비스와 상호 작용 하는 방법을 보여줍니다.
ms.topic: article
keywords: microsoft, windows, 로마, 명령, android 프로젝트
ms.assetid: 2fd14dd0-0f1f-49ee-83e3-468737810c81
ms.localizationpriority: medium
ms.openlocfilehash: 78cb712d3b1cbbd3d613a45cd42af491eaa33afc
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907765"
---
# <a name="implementing-device-relay-for-android"></a>Android에 대 한 장치 릴레이 구현

프로젝트 로마 장치 릴레이 기능의 두 가지 주요 기능을 지 원하는 Api의 집합으로 구성: 원격 시작 (라고도 명령) 및 앱 서비스입니다.

원격 시작 Api를 로컬 장치에서 원격 장치에서 프로세스가 시작 되는 시나리오를 지원 합니다. 예를 들어 사용자 자동차에서 휴대폰에 라디오를 수신할 수도 있지만 홈을 받으면를 사용 하 여 전화를 홈 스테레오로 후크 되어 있는 해당 Xbox 재생 전송할 합니다.

앱 서비스 Api는 임의의 콘텐츠를 포함 하는 메시지를 보낼 수 있습니다 하는 두 장치 간에 영구 파이프라인을 설정 하는 응용 프로그램을 허용 합니다. 예, 사진 모바일 장치에서 실행 되는 앱을 공유 사진을 검색 하기 위해 사용자의 PC 사용 하 여 연결을 설정할 수 있습니다.

프로젝트 로마 기능의 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼에서 지원 됩니다. 이 가이드는 연결 된 장치 플랫폼을 사용 하 여 시작 하는 데 필요한 단계를 제공 하 고 다음 장치 릴레이 구현 하는 플랫폼을 사용 하는 방법에 설명 관련 기능입니다.

이 단계 아래에서 코드 참조는 [프로젝트 로마 Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples)합니다.

[!INCLUDE [android/dev-reqs](../includes/android/dev-reqs.md)]

[!INCLUDE [android/preliminary-setup](../includes/android/preliminary-setup.md)]

[!INCLUDE [android/auth-scopes](../includes/auth-scopes.md)]

[!INCLUDE [android/dev-center-onboarding](../includes/android/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a>플랫폼을 사용 하 여

[!INCLUDE [android/create-setup-events-start-platform](../includes/android/create-setup-events-start-platform.md)]

### <a name="discover-remote-devices-and-apps"></a>원격 장치 및 앱 검색

A **RemoteSystemWatcher** 인스턴스는이 섹션의 핵심 기능을 처리 합니다. 원격 시스템을 검색 하는 클래스에서 선언 합니다.

```Java
private RemoteSystemWatcher mWatcher = null;
```

감시자를 만들고 장치 검색을 시작 하기 전에 어떤 종류의 장치에 앱의 대상이 될 확인 하려면 검색 필터를 추가할 수도 있습니다. 이러한 사용자 입력 또는 사용 사례에 따라 앱에 하드 코딩 하 여 확인할 수 있습니다.

```Java
private void onStartWatcherClicked() {
    // RemoteSystemWatcher cannot be started unless the platform is 
    // initialized and the user is logged in. It may be helpful to use
    // methods like these to track the state of the application.
    // See the sample app for their implementations.
    if (!getMainActivity().isSignedIn()) {
        return;
    }
    if (!getMainActivity().isPlatformInitialized()) {
        return;
    }

    // create and populate a list of filters. The filter choices below are arbitrary.
    ArrayList<RemoteSystemFilter> filters = new ArrayList<>();

    /*  RemoteSystemDiscoveryType filters can be used to filter the types of Remote Systems you discover.
    Possible values:
        ANY(0),
        PROXIMAL(1),
        CLOUD(2),
        SPATIALLY_PROXIMAL(3)
    */
    filters.add(new RemoteSystemDiscoveryTypeFilter(RemoteSystemDiscoveryType.ANY));

    /*  RemoteSystemStatusType filters can be used to filter the status of Remote Systems you discover.
    Possible values:
        ANY(0),
        AVAILABLE(1)
    */
    filters.add(new RemoteSystemStatusTypeFilter(RemoteSystemStatusType.AVAILABLE));


    /*  RemoteSystemKindFilter can filter the types of devices you want to discover.
    Possible values are members of the RemoteSystemKinds class.
    */
    String[] kinds = new String[] { RemoteSystemKinds.Phone(), RemoteSystemKinds.Tablet() };

    RemoteSystemKindFilter kindFilter = new RemoteSystemKindFilter(kinds);
    filters.add(kindFilter);

    /*  RemoteSystemAuthorizationKind determines the category of user whose system(s) you want to discover.
    Possible values:
        SAME_USER(0),
        ANONYMOUS(1)
    */
    filters.add(new RemoteSystemAuthorizationKindFilter(RemoteSystemAuthorizationKind.SAME_USER)); 
    // ...
```

이 시점에서 앱을 앱은 구문 분석 하 고 검색 되는 장치와 상호 작용 하는 방법을 결정 하는 감시자 개체를 초기화할 수 있습니다.

```Java
    // ...

    // Create a RemoteSystemWatcher
    mWatcher = new RemoteSystemWatcher(filters.toArray(new RemoteSystemFilter[filters.size()]));
    }

    // ...
```

앱에 검색 된 장치 집합을 유지 관리 하는 것이 좋습니다 (나타내는 **RemoteSystem** 인스턴스) 및 UI에서 사용할 수 있는 장치 및 앱 (예: 표시 이름 및 장치 유형)에 대 한 정보를 표시 합니다. 

다음 클래스 스텁 watcher 인스턴스에 대 한 이벤트 수신기로 사용할 수 있습니다.

```Java
private class RemoteSystemAddedListener implements EventListener<RemoteSystemWatcher, RemoteSystem> {
    @Override
    public void onEvent(RemoteSystemWatcher remoteSystemWatcher, RemoteSystem remoteSystem) {
        // add instance "remoteSystem" to program memory. See sample for full implementation.
    }
}

private class RemoteSystemUpdatedListener implements EventListener<RemoteSystemWatcher, RemoteSystem> {
    @Override
    public void onEvent(RemoteSystemWatcher remoteSystemWatcher, RemoteSystem remoteSystem) {
        // update instance "remoteSystem" in program memory. See sample for full implementation.
    }
}

private class RemoteSystemRemovedListener implements EventListener<RemoteSystemWatcher, RemoteSystem> {
    @Override
    public void onEvent(RemoteSystemWatcher remoteSystemWatcher, RemoteSystem remoteSystem) {
        // remove instance "remoteSystem" from program memory. See sample for full implementation.
    }
}

private class RemoteSystemWatcherErrorOccurredListener implements EventListener<RemoteSystemWatcher, RemoteSystemWatcherError> {
    @Override
    public void onEvent(RemoteSystemWatcher remoteSystemWatcher, RemoteSystemWatcherError remoteSystemWatcherError) {
        // handle the error
    }
}
```

한 번 `mWatcher.start` 은 원격 시스템 작업에 대 한 감시 시작 되 고 장치 검색, 업데이트 또는 검색 된 장치 집합에서 제거 될 때 이벤트 발생을 호출 합니다. 검사 지속적으로 백그라운드에서 되므로 불필요 한 네트워크 통신 및 배터리 드레이닝 하지 않으려면 더 이상 필요할 때 감시자를 중지 하는 것이 좋습니다.

```Java
// if you call this from the activity's onPause method, you ensure that
// it will stop when the activity exits the foreground.
public void stopWatcher() {
    if (mWatcher == null) {
        return;
    }
    mWatcher.stop();
}
```
## <a name="example-use-case-implementing-remote-launching-and-remote-app-services"></a>예제 사용 사례: 원격 시작 하 고 원격 앱 서비스를 구현 합니다.

이 시점에서 코드 있어야 작업 목록이 **RemoteSystem** 사용 가능한 장치를 참조 하는 개체입니다. 이러한 장치를 사용 하 여 수행할 앱의 기능에 따라 다릅니다. 기본 상호 작용 유형은 원격 시작 하 고 원격 앱 서비스입니다. 다음 섹션에서 설명 합니다.

### <a name="a-remote-launching"></a>A) 원격 시작

다음 코드 (이상적으로 이렇게 UI 컨트롤을 통해) 이러한 장치 중 하나를 선택 하 고 사용 하는 방법을 보여 줍니다 **RemoteLauncher** 앱-호환 되는 URI를 전달 하 여에 응용 프로그램을 실행 합니다. 

원격 시작이 (이 경우 호스트 장치 시작 됩니다 해당 URI 체계는 기본 앱을 사용 하 여 지정된 된 URI) 원격 장치를 대상 수를 확인 해야 _또는_ 해당 장치에서 특정 원격 응용 프로그램입니다. 

이전 섹션에서 알 수 있듯이, 검색에서 발생 하는 장치 수준 먼저 (을 **RemoteSystem** 장치를 나타냅니다), 호출할 수 있지만 `getApplications` 메서드를 **RemoteSystem** 가져올 인스턴스입니다는 배열을 **RemoteSystemApp** (처럼 위의 예비 단계에서 사용자 고유의 앱을 등록할) 연결 된 장치 플랫폼을 사용 하려면 등록 된 원격 장치에서 앱을 나타내는 개체입니다. 둘 다 **RemoteSystem** 및 **RemoteSystemApp** 만드는 데 사용할 수는 **RemoteSystemConnectionRequest**, URI를 시작 하는 데 필요한 사항을 인 합니다.

```java
// this could be a RemoteSystemApp instead. Either way, it 
// must be defined somewhere in the application before the launch operation
// is called.
private RemoteSystem target; 

// ...

/**
* Responsible for calling into the Rome API to launch the given URI and provides
* the logic to handle the RemoteLaunchUriStatus response.
* @param uri URI to launch
* @param target The target for the launch URI request
*/
private void launchUri(final String uri, final RemoteSystem target, final long messageId)
{
    RemoteLauncher remoteLauncher = new RemoteLauncher();

    AsyncOperation<RemoteLaunchUriStatus> resultOperation = remoteLauncher.launchUriAsync(new RemoteSystemConnectionRequest(target), uri);
    // ...
```
사용 하 여 반환 된 **AsyncOperation** 시작 시도의 결과 처리 하도록 합니다.

```Java
    // ...
    resultOperation.whenCompleteAsync(new AsyncOperation.ResultBiConsumer<RemoteLaunchUriStatus, Throwable>() {
        @Override
        public void accept(RemoteLaunchUriStatus status, Throwable throwable) throws Throwable {
            if (throwable != null) {
                // handle the exception, referencing "throwable"
            } else {
                if (status == RemoteLaunchUriStatus.SUCCESS) {
                    // report the success case
                } else {
                    // report the non-success case, referencing "status"
                }
            }
        }
    });
}
```
전송 되는 URI에 따라 특정 상태 또는 원격 장치 구성에서 앱을 시작할 수 있습니다. 이렇게 하면 중단 없이 다른 장치에서 동영상을 시청 같은 사용자 작업을 계속할 수 있습니다. 

해당 사용 사례에 따라 대상된 시스템에 앱이 없습니다 URI를 처리할 수 있는 경우를 처리 하기 위해 해야 할 수 있습니다 하거나 여러 앱에서 처리할 수 있습니다. 합니다 **[RemoteLauncher](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher)** 클래스 및 **[RemoteLauncherOptions](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher_options)** 클래스에는이 작업을 수행 하는 방법을 설명 합니다.

### <a name="b-remote-app-services"></a>B) 원격 앱 서비스

Android 앱 연결 장치 포털을 사용할 수 다른 장치에서 앱 서비스와 상호 작용 합니다. 다른 장치와 통신 하는 여러 방법을 제공&mdash;모든 하지 않고도 앱 호스트 장치 포그라운드로 가져옵니다. 

#### <a name="set-up-the-app-service-on-the-target-device"></a>대상 장치에서 앱 서비스 설정
이 가이드를 사용 합니다 [Roman 테스트 앱에 대 한 Windows](http://aka.ms/romeapp) 해당 대상 앱 서비스로 합니다. 따라서 아래 코드를 사용 하면 Android 앱이 지정된 된 원격 시스템에서 해당 특정 앱 서비스에 대 한 확인 합니다. 이 시나리오를 테스트 하려는 경우 Windows 장치의 Roman 테스트 앱을 다운로드 하 고 같은 MSA 또는 위의 예비 단계에서 사용한 AAD 로그인 해야 합니다. 

사용자 고유의 UWP 앱 서비스를 작성 하는 방법에 대 한 지침을 참조 하세요 [만들기 (UWP) 앱 서비스를 사용 하 고](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)입니다. 서비스를 연결 된 장치와 호환 되도록 하기 위해 몇 가지 변경 해야 합니다. 참조 된 [remoteapp 서비스에 대 한 UWP 가이드](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) 이 작업을 수행 하는 방법에 대 한 지침은 합니다. 

#### <a name="open-an-app-service-connection-on-the-client-device"></a>클라이언트 장치에서 앱 서비스 연결을 열려면
Android 앱을 원격 장치 또는 응용 프로그램에 대 한 참조를 획득 해야 합니다. 이 시나리오의 시작 섹션에서와 같은 사용 해야 합니다는 **RemoteSystemConnectionRequest**에서 생성할 수 있습니다는 **RemoteSystem** 또는 **RemoteSystemApp**시스템에서 사용 가능한 앱을 나타내는입니다.


```Java
// this could be a RemoteSystemApp instead. Either way, it 
// must be defined somewhere in the application before the app service
// connection is opened.
private RemoteSystem target = null;
```
두 문자열을 사용 하 여 해당 대상된 앱 서비스를 식별 하려면 앱에 필요 하는 또한: 합니다 *app service 이름* 하 고 *패키지 식별자*합니다. App service 공급자의 소스 코드에서 발견 되는 이러한 (참조 [만들기 (UWP) 앱 서비스를 사용 하 고](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) 이 Windows 앱 서비스에 대 한 문자열을 가져오는 방법에 대 한 세부 정보에 대 한). 함께 이러한 문자열 구성 합니다 **AppServiceDescription**에 공급 되는 **AppServiceConnection** 인스턴스.

```Java
// this is defined below
private AppServiceConnection connection = null; 


/**
* Creates an AppService connection with the current identifier and service name and opens the
* app service connection.
*/
private void onNewConnectionButtonClicked()
{
    connection = new AppServiceConnection();

    // these hard-coded strings must be defined elsewhere in the app
    connection.setAppServiceDescription(new AppServiceDescription(mAppServiceName, mPackageIdentifier));

    // this method is defined below
    openAppServiceConnection();
}
```
```Java
/**
* Establish an app service connection.
* Opens the given AppService connection using the connection request. Once the connection is
* opened, it adds the listeners for request-received and close. Catches all exceptions
* to show behavior of API surface exceptions.
*/
private void openAppServiceConnection()
{
    // optionally report outbound request
    // ...

    RemoteSystemConnectionRequest connectionRequest = new RemoteSystemConnectionRequest(target));

    /* Will asynchronously open the app service connection using the given connection request
    * When this is done, we log the traffic in the UI for visibility to the user (for sample purposes)
    * We can check the status of the connection to determine whether or not it was successful, and show 
    * some UI if it wasn't (in this case it is part of the list item).
    */
    connection.openRemoteAsync(connectionRequest)
        .thenAcceptAsync(new AsyncOperation.ResultConsumer<AppServiceConnectionStatus>() {
            @Override
            public void accept(AppServiceConnectionStatus appServiceConnectionStatus) throws Throwable {
                // optionally report inbound response
                // ...

                if (appServiceConnectionStatus != AppServiceConnectionStatus.SUCCESS) {
                    // report the error, referencing "appServiceConnectionStatus"
                    return;
                }
            }
        })
        .exceptionally(new AsyncOperation.ResultFunction<Throwable, Void>() {
            @Override
            public Void apply(Throwable throwable) throws Throwable {
                // report the exception
                return null;
            }
        });
}
```

#### <a name="create-a-message-to-send-to-the-app-service"></a>App service에 보낼 메시지를 만들려면

보낼 메시지를 저장 하는 변수를 선언 합니다. Android에서 원격 앱 서비스에 보내는 메시지의 수를 **지도** 형식입니다.

```Java
private Map<String, Object> mMessagePayload = null;
```
> [!NOTE]
> 앱을 다른 플랫폼에서 앱 서비스와 통신 하는 경우 연결 된 장치 플랫폼을 변환 합니다 **지도** 수신 플랫폼에서 일치 하는 구문에 있습니다. 예를 들어를 **[맵](https://developer.android.com/reference/java/util/Map)** app service로 변환 하는 Windows에이 앱에서 보낸를 [ **ValueSet** ](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) (.NET Framework)의 개체 다음 해석 될 수 있는 app service에서. 다른 방향으로 전달 되는 정보는 역변환을 거칩니다.

다음 메서드는 Windows에 대 한 Roman 테스트 앱의 app service에서 해석할 수 있는 메시지를 작성 합니다.

```Java
/**
* Send the current message payload through all selected AppService connections on a non-UI
* thread as to not block user interaction, a result of the delay between API calls.
*/
private void onMessageButtonClicked()
{
    mMessagePayload = new HashMap<>();
    // Add the required fields of RomanApp on Windows
    DateFormat df = new SimpleDateFormat(DATE_FORMAT);
    mMessagePayload.put("Type", "ping");
    mMessagePayload.put("CreationDate", df.format(new Date()));
    mMessagePayload.put("TargetId", "check if this field needs to be included");

    // this method is defined below.
    sendMessage(connection, mMessagePayload);
}
```

> [!IMPORTANT]
> 합니다 **지도**s 원격 앱 서비스 시나리오에서 앱 및 서비스 간에 전달 되는 다음 형식을 준수 해야 합니다. 키 문자열 이어야 합니다. 하 고 값이 될 수 있습니다. 문자열, boxed 숫자 형식 (정수 또는 부동 소수점) 박스형 부울, android.graphics.Point, android.graphics.Rect, java.util.Date, java.util.UUID, 이러한 형식 또는 다른 유형이 같은 배열 **지도** 개체 이 사양을 충족 합니다.

#### <a name="send-message-to-the-app-service"></a>App service에 메시지 보내기

앱 서비스 연결이 설정 된 메시지를 작성 하 고 간단 하 고 작업을 수행 하려면에서 아무 곳 이나 앱 서비스 연결 인스턴스 메시지에 대 한 참조를 가진 앱 app service에 전송 합니다.


```java

// When assigning message IDs, use an incremental counter
private AtomicInteger mMessageIdAppServices = new AtomicInteger(0);

// ...

/**
* Send a message using the app service connection
* Send the given Map object through the given AppServiceConnection. Uses an internal messageId
* for logging purposes.
* @param connection AppServiceConnection to send the Map payload
* @param message Payload to be translated to a ValueSet
*/
private void sendMessage(final AppServiceConnection connection, Map<String, Object> message)
{
    final long messageId = mMessageIdAppServices.incrementAndGet();

    connection.sendMessageAsync(message)
        .thenAcceptAsync(new AsyncOperation.ResultConsumer<AppServiceResponse>() {
            @Override
            public void accept(AppServiceResponse appServiceResponse) throws Throwable {
                // optionally report an inbound response

                // this method is defined below
                handleAppServiceResponse(appServiceResponse, messageId);
            }
        })
        .exceptionally(new AsyncOperation.ResultFunction<Throwable, Void>() {
            @Override
            public Void apply(Throwable throwable) throws Throwable {
                // report the exception, referencing "throwable"

                return null;
            }
        });

    // optionally log the outbound message request here, referencing 
    // connection.getAppServiceDescription().getName() as the recipient.
}
```

App service의 응답을 수신 하 고 같은 방법으로 해석 됩니다.

```Java
private void handleAppServiceResponse(AppServiceResponse appServiceResponse, long messageId)
{
    AppServiceResponseStatus status = appServiceResponse.getStatus();
    if (status == AppServiceResponseStatus.SUCCESS)
    {
        // the message was delivered successfully; interpret the response.
        Map<String, Object> response;
        response = appServiceResponse.getMessage();

        // in the Roman App case, the response contains the date it was created.
        String dateStr = (String)response.get("CreationDate");
        DateFormat df = new SimpleDateFormat(DATE_FORMAT, Locale.getDefault());

        // in this very simple use case, we compare the dates to get the total
        // transit time of the message response.
        try {
            Date startDate = df.parse(dateStr);
            Date nowDate = new Date();
            long diff = nowDate.getTime() - startDate.getTime();
            // do something with "diff"
        } catch (ParseException e) { e.printStackTrace(); }
    }
}
```
로마 앱의 경우 응답 메시지 응답의 총 전송 시간 날짜를 비교할 것이 매우 간단한 사용 사례에 있도록 만들어진 날짜를 포함 합니다.

원격 앱 서비스를 사용 하 여 단일 메시지 교환이 완료 했습니다.

#### <a name="finish-app-service-communication"></a>앱 서비스 통신을 완료

앱 완료 되 면 두 장치 간에 연결을 닫습니다 대상 장치의 앱 서비스와 상호 작용 합니다.

```java
// Close the given AppService connection
private void closeAppServiceConnection()
{
    connection.close();
}
```

### <a name="related-topics"></a>관련 항목
* [API 참조 페이지](api-reference-for-android.md) 
* [Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples) 
* [원격 앱 서비스 (UWP)와 통신](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service)
* [만들기 및 app service (UWP) 사용](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)합니다.
