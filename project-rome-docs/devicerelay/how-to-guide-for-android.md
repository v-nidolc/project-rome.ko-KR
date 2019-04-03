---
title: 명령을 원격 장치 및 앱 (Android)
description: 이 가이드에서는 원격 장치 및 앱을 검색 한 다음 앱을 시작 및 앱 서비스와 상호 작용 하는 방법을 보여줍니다.
ms.topic: article
keywords: microsoft, windows, 로마, 명령, android 프로젝트
ms.assetid: 2fd14dd0-0f1f-49ee-83e3-468737810c81
ms.localizationpriority: medium
ms.openlocfilehash: 78cb712d3b1cbbd3d613a45cd42af491eaa33afc
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907765"
---
# <a name="implementing-device-relay-for-android"></a><span data-ttu-id="f40ff-104">Android에 대 한 장치 릴레이 구현</span><span class="sxs-lookup"><span data-stu-id="f40ff-104">Implementing device relay for Android</span></span>

<span data-ttu-id="f40ff-105">프로젝트 로마 장치 릴레이 기능의 두 가지 주요 기능을 지 원하는 Api의 집합으로 구성: 원격 시작 (라고도 명령) 및 앱 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-105">The Device Relay functionality of Project Rome consists of a set of APIs that support two main features: remote launching (also known as commanding) and app services.</span></span>

<span data-ttu-id="f40ff-106">원격 시작 Api를 로컬 장치에서 원격 장치에서 프로세스가 시작 되는 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-106">Remote Launching APIs support scenarios where a process on a remote device is started from a local device.</span></span> <span data-ttu-id="f40ff-107">예를 들어 사용자 자동차에서 휴대폰에 라디오를 수신할 수도 있지만 홈을 받으면를 사용 하 여 전화를 홈 스테레오로 후크 되어 있는 해당 Xbox 재생 전송할 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-107">For example, a user might be listening to the radio on their phone in the car, but when they get home they use their phone to transfer playback to their Xbox which is hooked up to the home stereo.</span></span>

<span data-ttu-id="f40ff-108">앱 서비스 Api는 임의의 콘텐츠를 포함 하는 메시지를 보낼 수 있습니다 하는 두 장치 간에 영구 파이프라인을 설정 하는 응용 프로그램을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-108">App Services APIs allow an application to establish a persistent pipeline between two devices through which messages containing any arbitrary content can be sent.</span></span> <span data-ttu-id="f40ff-109">예, 사진 모바일 장치에서 실행 되는 앱을 공유 사진을 검색 하기 위해 사용자의 PC 사용 하 여 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-109">For example, a photo sharing app running on a mobile device could establish a connection with the user's PC in order to retrieve photos.</span></span>

<span data-ttu-id="f40ff-110">프로젝트 로마 기능의 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-110">The features of Project Rome are supported by an underlying platform called the Connected Devices Platform.</span></span> <span data-ttu-id="f40ff-111">이 가이드는 연결 된 장치 플랫폼을 사용 하 여 시작 하는 데 필요한 단계를 제공 하 고 다음 장치 릴레이 구현 하는 플랫폼을 사용 하는 방법에 설명 관련 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-111">This guide provides the necessary steps to get started using the Connected Devices Platform, and then explains how to use the platform to implement Device Relay related features.</span></span>

<span data-ttu-id="f40ff-112">이 단계 아래에서 코드 참조는 [프로젝트 로마 Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples)합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-112">This steps below will reference code from the [Project Rome Android sample app](https://github.com/Microsoft/project-rome/tree/master/Android/samples).</span></span>

[!INCLUDE [android/dev-reqs](../includes/android/dev-reqs.md)]

[!INCLUDE [android/preliminary-setup](../includes/android/preliminary-setup.md)]

[!INCLUDE [android/auth-scopes](../includes/auth-scopes.md)]

[!INCLUDE [android/dev-center-onboarding](../includes/android/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a><span data-ttu-id="f40ff-113">플랫폼을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="f40ff-113">Using the platform</span></span>

[!INCLUDE [android/create-setup-events-start-platform](../includes/android/create-setup-events-start-platform.md)]

### <a name="discover-remote-devices-and-apps"></a><span data-ttu-id="f40ff-114">원격 장치 및 앱 검색</span><span class="sxs-lookup"><span data-stu-id="f40ff-114">Discover remote devices and apps</span></span>

<span data-ttu-id="f40ff-115">A **RemoteSystemWatcher** 인스턴스는이 섹션의 핵심 기능을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-115">A **RemoteSystemWatcher** instance will handle the core functionality of this section.</span></span> <span data-ttu-id="f40ff-116">원격 시스템을 검색 하는 클래스에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-116">Declare it in the class which is to discover remote systems.</span></span>

```Java
private RemoteSystemWatcher mWatcher = null;
```

<span data-ttu-id="f40ff-117">감시자를 만들고 장치 검색을 시작 하기 전에 어떤 종류의 장치에 앱의 대상이 될 확인 하려면 검색 필터를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-117">Before you create a watcher and start discovering devices, you may wish to add discovery filters to determine which kinds of devices your app will target.</span></span> <span data-ttu-id="f40ff-118">이러한 사용자 입력 또는 사용 사례에 따라 앱에 하드 코딩 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-118">These can be determined by user input or hard-coded into the app, depending on your use case.</span></span>

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

<span data-ttu-id="f40ff-119">이 시점에서 앱을 앱은 구문 분석 하 고 검색 되는 장치와 상호 작용 하는 방법을 결정 하는 감시자 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-119">At this point, the app can initialize the watcher object which determine how your app will parse and interact with devices that are discovered.</span></span>

```Java
    // ...

    // Create a RemoteSystemWatcher
    mWatcher = new RemoteSystemWatcher(filters.toArray(new RemoteSystemFilter[filters.size()]));
    }

    // ...
```

<span data-ttu-id="f40ff-120">앱에 검색 된 장치 집합을 유지 관리 하는 것이 좋습니다 (나타내는 **RemoteSystem** 인스턴스) 및 UI에서 사용할 수 있는 장치 및 앱 (예: 표시 이름 및 장치 유형)에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-120">It is recommended that your app maintain a set of discovered devices (represented by **RemoteSystem** instances) and display information about available devices and their apps (such as display name and device type) on the UI.</span></span> 

<span data-ttu-id="f40ff-121">다음 클래스 스텁 watcher 인스턴스에 대 한 이벤트 수신기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-121">The following class stubs can be used as event listeners for the watcher instance.</span></span>

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

<span data-ttu-id="f40ff-122">한 번 `mWatcher.start` 은 원격 시스템 작업에 대 한 감시 시작 되 고 장치 검색, 업데이트 또는 검색 된 장치 집합에서 제거 될 때 이벤트 발생을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-122">Once `mWatcher.start` is called, it will begin watching for remote system activity and will raise events when devices are discovered, updated, or removed from the set of discovered devices.</span></span> <span data-ttu-id="f40ff-123">검사 지속적으로 백그라운드에서 되므로 불필요 한 네트워크 통신 및 배터리 드레이닝 하지 않으려면 더 이상 필요할 때 감시자를 중지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-123">It will scan continuously in the background, so it is recommended that you stop the watcher when you no longer need it to avoid unnecessary network communication and battery drain.</span></span>

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
## <a name="example-use-case-implementing-remote-launching-and-remote-app-services"></a><span data-ttu-id="f40ff-124">예제 사용 사례: 원격 시작 하 고 원격 앱 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-124">Example use case: implementing remote launching and remote app services</span></span>

<span data-ttu-id="f40ff-125">이 시점에서 코드 있어야 작업 목록이 **RemoteSystem** 사용 가능한 장치를 참조 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-125">At this point in your code, you should have a working list of **RemoteSystem** objects that refer to available devices.</span></span> <span data-ttu-id="f40ff-126">이러한 장치를 사용 하 여 수행할 앱의 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-126">What you do with these devices will depend on the function of your app.</span></span> <span data-ttu-id="f40ff-127">기본 상호 작용 유형은 원격 시작 하 고 원격 앱 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-127">The main types of interaction are remote launching and remote app services.</span></span> <span data-ttu-id="f40ff-128">다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-128">They are explained in the following sections.</span></span>

### <a name="a-remote-launching"></a><span data-ttu-id="f40ff-129">A) 원격 시작</span><span class="sxs-lookup"><span data-stu-id="f40ff-129">A) Remote launching</span></span>

<span data-ttu-id="f40ff-130">다음 코드 (이상적으로 이렇게 UI 컨트롤을 통해) 이러한 장치 중 하나를 선택 하 고 사용 하는 방법을 보여 줍니다 **RemoteLauncher** 앱-호환 되는 URI를 전달 하 여에 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-130">The following code shows how to select one of these devices (ideally this is done through a UI control) and then use **RemoteLauncher** to launch an app on it by passing an app-compatible URI.</span></span> 

<span data-ttu-id="f40ff-131">원격 시작이 (이 경우 호스트 장치 시작 됩니다 해당 URI 체계는 기본 앱을 사용 하 여 지정된 된 URI) 원격 장치를 대상 수를 확인 해야 _또는_ 해당 장치에서 특정 원격 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-131">It's important to note that a remote launch can target a remote device (in which case the host device will launch the given URI with its default app for that URI scheme) _or_ a specific remote application on that device.</span></span> 

<span data-ttu-id="f40ff-132">이전 섹션에서 알 수 있듯이, 검색에서 발생 하는 장치 수준 먼저 (을 **RemoteSystem** 장치를 나타냅니다), 호출할 수 있지만 `getApplications` 메서드를 **RemoteSystem** 가져올 인스턴스입니다는 배열을 **RemoteSystemApp** (처럼 위의 예비 단계에서 사용자 고유의 앱을 등록할) 연결 된 장치 플랫폼을 사용 하려면 등록 된 원격 장치에서 앱을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-132">As the previous section demonstrated, discovery happens at the device level first (a **RemoteSystem** represents a device), but you can call the `getApplications` method on a **RemoteSystem** instance to get an array of **RemoteSystemApp** objects, which represent apps on the remote device that have been registered to use the Connected Devices Platform (just as you registered your own app in the preliminary steps above).</span></span> <span data-ttu-id="f40ff-133">둘 다 **RemoteSystem** 및 **RemoteSystemApp** 만드는 데 사용할 수는 **RemoteSystemConnectionRequest**, URI를 시작 하는 데 필요한 사항을 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-133">Both **RemoteSystem** and **RemoteSystemApp** can be used to construct a **RemoteSystemConnectionRequest**, which is what is needed to launch a URI.</span></span>

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
<span data-ttu-id="f40ff-134">사용 하 여 반환 된 **AsyncOperation** 시작 시도의 결과 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-134">Use the returned **AsyncOperation** to handle the result of the launch attempt.</span></span>

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
<span data-ttu-id="f40ff-135">전송 되는 URI에 따라 특정 상태 또는 원격 장치 구성에서 앱을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-135">Depending on the URI that is sent, you can launch an app in a specific state or configuration on a remote device.</span></span> <span data-ttu-id="f40ff-136">이렇게 하면 중단 없이 다른 장치에서 동영상을 시청 같은 사용자 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-136">This allows for the ability to continue a user task, like watching a movie, on a different device without interruption.</span></span> 

<span data-ttu-id="f40ff-137">해당 사용 사례에 따라 대상된 시스템에 앱이 없습니다 URI를 처리할 수 있는 경우를 처리 하기 위해 해야 할 수 있습니다 하거나 여러 앱에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-137">Depending on your use case, you may need to cover the cases in which no apps on the targeted system can handle the URI, or multiple apps can handle it.</span></span> <span data-ttu-id="f40ff-138">합니다 **[RemoteLauncher](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher)** 클래스 및 **[RemoteLauncherOptions](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher_options)** 클래스에는이 작업을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-138">The **[RemoteLauncher](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher)** class and **[RemoteLauncherOptions](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.commanding._remote_launcher_options)** class describe how to do this.</span></span>

### <a name="b-remote-app-services"></a><span data-ttu-id="f40ff-139">B) 원격 앱 서비스</span><span class="sxs-lookup"><span data-stu-id="f40ff-139">B) Remote app services</span></span>

<span data-ttu-id="f40ff-140">Android 앱 연결 장치 포털을 사용할 수 다른 장치에서 앱 서비스와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-140">Your Android app can use the Connected Devices Portal interact with app services on other devices.</span></span> <span data-ttu-id="f40ff-141">다른 장치와 통신 하는 여러 방법을 제공&mdash;모든 하지 않고도 앱 호스트 장치 포그라운드로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-141">This provides many ways to communicate with other devices&mdash;all without needing to bring an app to the foreground of the host device.</span></span> 

#### <a name="set-up-the-app-service-on-the-target-device"></a><span data-ttu-id="f40ff-142">대상 장치에서 앱 서비스 설정</span><span class="sxs-lookup"><span data-stu-id="f40ff-142">Set up the app service on the target device</span></span>
<span data-ttu-id="f40ff-143">이 가이드를 사용 합니다 [Roman 테스트 앱에 대 한 Windows](http://aka.ms/romeapp) 해당 대상 앱 서비스로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-143">This guide will use the [Roman Test App for Windows](http://aka.ms/romeapp) as its target app service.</span></span> <span data-ttu-id="f40ff-144">따라서 아래 코드를 사용 하면 Android 앱이 지정된 된 원격 시스템에서 해당 특정 앱 서비스에 대 한 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-144">Therefore, the code below will cause an Android app to look for that specific app service on the given remote system.</span></span> <span data-ttu-id="f40ff-145">이 시나리오를 테스트 하려는 경우 Windows 장치의 Roman 테스트 앱을 다운로드 하 고 같은 MSA 또는 위의 예비 단계에서 사용한 AAD 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-145">If you wish to test this scenario, download the Roman Test App on a Windows device and make sure you are signed in with the same MSA or AAD that you used in the preliminary steps above.</span></span> 

<span data-ttu-id="f40ff-146">사용자 고유의 UWP 앱 서비스를 작성 하는 방법에 대 한 지침을 참조 하세요 [만들기 (UWP) 앱 서비스를 사용 하 고](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-146">For instructions on how to write your own UWP app service, see [Create and consume an app service (UWP)](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span> <span data-ttu-id="f40ff-147">서비스를 연결 된 장치와 호환 되도록 하기 위해 몇 가지 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-147">You will need to make a few changes in order to make the service compatible with Connected Devices.</span></span> <span data-ttu-id="f40ff-148">참조 된 [remoteapp 서비스에 대 한 UWP 가이드](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) 이 작업을 수행 하는 방법에 대 한 지침은 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-148">See the [UWP guide for remote app services](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) for instructions on how to do this.</span></span> 

#### <a name="open-an-app-service-connection-on-the-client-device"></a><span data-ttu-id="f40ff-149">클라이언트 장치에서 앱 서비스 연결을 열려면</span><span class="sxs-lookup"><span data-stu-id="f40ff-149">Open an app service connection on the client device</span></span>
<span data-ttu-id="f40ff-150">Android 앱을 원격 장치 또는 응용 프로그램에 대 한 참조를 획득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-150">Your Android app must acquire a reference to a remote device or application.</span></span> <span data-ttu-id="f40ff-151">이 시나리오의 시작 섹션에서와 같은 사용 해야 합니다는 **RemoteSystemConnectionRequest**에서 생성할 수 있습니다는 **RemoteSystem** 또는 **RemoteSystemApp**시스템에서 사용 가능한 앱을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-151">Like the launch section, this scenario requires the use of a **RemoteSystemConnectionRequest**, which can be constructed from either a **RemoteSystem** or a **RemoteSystemApp** representing an available app on the system.</span></span>


```Java
// this could be a RemoteSystemApp instead. Either way, it 
// must be defined somewhere in the application before the app service
// connection is opened.
private RemoteSystem target = null;
```
<span data-ttu-id="f40ff-152">두 문자열을 사용 하 여 해당 대상된 앱 서비스를 식별 하려면 앱에 필요 하는 또한: 합니다 *app service 이름* 하 고 *패키지 식별자*합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-152">Additionally, your app will need to identify its targeted app service using two strings: the *app service name* and *package identifier*.</span></span> <span data-ttu-id="f40ff-153">App service 공급자의 소스 코드에서 발견 되는 이러한 (참조 [만들기 (UWP) 앱 서비스를 사용 하 고](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) 이 Windows 앱 서비스에 대 한 문자열을 가져오는 방법에 대 한 세부 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="f40ff-153">These are found in the source code of the app service provider (see [Create and consume an app service (UWP)](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) for details on how to get this strings for Windows app services).</span></span> <span data-ttu-id="f40ff-154">함께 이러한 문자열 구성 합니다 **AppServiceDescription**에 공급 되는 **AppServiceConnection** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f40ff-154">Together these strings construct the **AppServiceDescription**, which is fed into an **AppServiceConnection** instance.</span></span>

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

#### <a name="create-a-message-to-send-to-the-app-service"></a><span data-ttu-id="f40ff-155">App service에 보낼 메시지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f40ff-155">Create a message to send to the app service</span></span>

<span data-ttu-id="f40ff-156">보낼 메시지를 저장 하는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-156">Declare a variable to store the message to send.</span></span> <span data-ttu-id="f40ff-157">Android에서 원격 앱 서비스에 보내는 메시지의 수를 **지도** 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-157">On Android, the messages that you send to remote app services will be of the **Map** type.</span></span>

```Java
private Map<String, Object> mMessagePayload = null;
```
> [!NOTE]
> <span data-ttu-id="f40ff-158">앱을 다른 플랫폼에서 앱 서비스와 통신 하는 경우 연결 된 장치 플랫폼을 변환 합니다 **지도** 수신 플랫폼에서 일치 하는 구문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-158">When your app communicates with app services on other platforms, the Connected Devices Platform translates the **Map** into the matching construct on the receiving platform.</span></span> <span data-ttu-id="f40ff-159">예를 들어를 **[맵](https://developer.android.com/reference/java/util/Map)** app service로 변환 하는 Windows에이 앱에서 보낸를 [ **ValueSet** ](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) (.NET Framework)의 개체 다음 해석 될 수 있는 app service에서.</span><span class="sxs-lookup"><span data-stu-id="f40ff-159">For example, a **[Map](https://developer.android.com/reference/java/util/Map)** sent from this app to a Windows app service gets translated into a [**ValueSet**](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) object (of the .NET Framework), which can then be interpreted by the app service.</span></span> <span data-ttu-id="f40ff-160">다른 방향으로 전달 되는 정보는 역변환을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-160">Information passed in the other direction undergoes the reverse translation.</span></span>

<span data-ttu-id="f40ff-161">다음 메서드는 Windows에 대 한 Roman 테스트 앱의 app service에서 해석할 수 있는 메시지를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-161">The following method composes a message that can be interpreted by the Roman Test App's app service for Windows.</span></span>

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
> <span data-ttu-id="f40ff-162">합니다 **지도**s 원격 앱 서비스 시나리오에서 앱 및 서비스 간에 전달 되는 다음 형식을 준수 해야 합니다. 키 문자열 이어야 합니다. 하 고 값이 될 수 있습니다. 문자열, boxed 숫자 형식 (정수 또는 부동 소수점) 박스형 부울, android.graphics.Point, android.graphics.Rect, java.util.Date, java.util.UUID, 이러한 형식 또는 다른 유형이 같은 배열 **지도** 개체 이 사양을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-162">The **Map**s that are passed between apps and services in the remote app services scenario must adhere to the following format: Keys must be Strings, and the values may be: Strings, boxed numeric types (integers or floating points), boxed booleans, android.graphics.Point, android.graphics.Rect, java.util.Date, java.util.UUID, homogeneous arrays of any of these types, or other **Map** objects that meet this specification.</span></span>

#### <a name="send-message-to-the-app-service"></a><span data-ttu-id="f40ff-163">App service에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="f40ff-163">Send message to the app service</span></span>

<span data-ttu-id="f40ff-164">앱 서비스 연결이 설정 된 메시지를 작성 하 고 간단 하 고 작업을 수행 하려면에서 아무 곳 이나 앱 서비스 연결 인스턴스 메시지에 대 한 참조를 가진 앱 app service에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-164">Once the app service connection is established and the message is created, sending it to the app service is simple and can be done from anywhere in the app that has a reference to the app service connection instance and the message.</span></span>


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

<span data-ttu-id="f40ff-165">App service의 응답을 수신 하 고 같은 방법으로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-165">The app service's response will be received and interpreted by the following method.</span></span>

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
<span data-ttu-id="f40ff-166">로마 앱의 경우 응답 메시지 응답의 총 전송 시간 날짜를 비교할 것이 매우 간단한 사용 사례에 있도록 만들어진 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-166">In the Roman App case, the response contains the date it was created, so in this very simple use case, we can compare the dates to get the total transit time of the message response.</span></span>

<span data-ttu-id="f40ff-167">원격 앱 서비스를 사용 하 여 단일 메시지 교환이 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-167">This concludes a single message exchange with a remote app service.</span></span>

#### <a name="finish-app-service-communication"></a><span data-ttu-id="f40ff-168">앱 서비스 통신을 완료</span><span class="sxs-lookup"><span data-stu-id="f40ff-168">Finish app service communication</span></span>

<span data-ttu-id="f40ff-169">앱 완료 되 면 두 장치 간에 연결을 닫습니다 대상 장치의 앱 서비스와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-169">When your app is finished interacting with the target device's app service, close the connection between the two devices.</span></span>

```java
// Close the given AppService connection
private void closeAppServiceConnection()
{
    connection.close();
}
```

### <a name="related-topics"></a><span data-ttu-id="f40ff-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f40ff-170">Related topics</span></span>
* [<span data-ttu-id="f40ff-171">API 참조 페이지</span><span class="sxs-lookup"><span data-stu-id="f40ff-171">API reference page</span></span>](api-reference-for-android.md) 
* [<span data-ttu-id="f40ff-172">Android 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="f40ff-172">Android sample app</span></span>](https://github.com/Microsoft/project-rome/tree/master/Android/samples) 
* [<span data-ttu-id="f40ff-173">원격 앱 서비스 (UWP)와 통신</span><span class="sxs-lookup"><span data-stu-id="f40ff-173">Communicate with a remote app service (UWP)</span></span>](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service)
* <span data-ttu-id="f40ff-174">[만들기 및 app service (UWP) 사용](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)합니다.</span><span class="sxs-lookup"><span data-stu-id="f40ff-174">[Create and consume an app service (UWP)](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
