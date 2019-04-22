---
title: IOS에 대 한 장치 릴레이 기능 구현
description: 이 가이드에서는 원격 장치 및 앱을 검색 한 다음 앱을 시작 및 앱 서비스와 상호 작용 하는 방법을 보여줍니다.
ms.topic: article
keywords: microsoft, windows, 로마, 명령, ios 프로젝트
ms.assetid: b5d426db-a0ca-4888-b2cb-cb7fdb1c6c0d
ms.localizationpriority: medium
ms.openlocfilehash: 11596720d9363f0ef29fd9c7bf0ccc5b4db62fae
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907735"
---
# <a name="implementing-device-relay-for-ios"></a>IOS에 대 한 장치 릴레이 구현합니다.

프로젝트 로마 장치 릴레이 기능의 두 가지 주요 기능을 지 원하는 Api의 집합으로 구성: 원격 시작 (라고도 명령) 및 앱 서비스입니다.

원격 시작 Api를 로컬 장치에서 원격 장치에서 프로세스가 시작 되는 시나리오를 지원 합니다. 예를 들어 사용자 자동차에서 휴대폰에 라디오를 수신할 수도 있지만 홈을 받으면를 사용 하 여 전화를 홈 스테레오로 후크 되어 있는 해당 Xbox 재생 전송할 합니다.

앱 서비스 Api는 임의의 콘텐츠를 포함 하는 메시지를 보낼 수 있습니다 하는 두 장치 간에 영구 파이프라인을 설정 하는 응용 프로그램을 허용 합니다. 예, 사진 모바일 장치에서 실행 되는 앱을 공유 사진을 검색 하기 위해 사용자의 PC 사용 하 여 연결을 설정할 수 있습니다.

프로젝트 로마 기능의 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼에서 지원 됩니다. 이 가이드는 연결 된 장치 플랫폼을 사용 하 여 시작 하는 데 필요한 단계를 제공 하 고 다음을 구현 하는 플랫폼을 사용 하는 방법에 설명 릴레이 장치 관련 기능입니다.

이 단계 아래에서 코드 참조는 [프로젝트 로마 iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) GitHub에서 사용할 수 있는 합니다.  

## <a name="setting-up-the-connected-devices-platform-and-notifications"></a>연결 된 장치 플랫폼 및 알림 설정

[!INCLUDE [ios/preliminary-setup](../includes/ios/preliminary-setup.md)]

[!INCLUDE [auth-scopesiOS](../includes/auth-scopesiOS.md)]

[!INCLUDE [ios/dev-center-onboarding](../includes/ios/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a>플랫폼을 사용 하 여

[!INCLUDE [ios/create-setup-events-start-platform](../includes/ios/create-setup-events-start-platform.md)]

### <a name="discover-remote-devices-and-apps"></a>원격 장치 및 앱 검색

**MCDRemoteSystemWatcher** 인스턴스는이 섹션의 핵심 기능을 처리 합니다. 원격 시스템을 검색 하는 클래스에서 선언 합니다.

`MCDRemoteSystemWatcher* _watcher;`

감시자를 만들고 장치 검색을 시작 하기 전에 어떤 종류의 장치에 앱의 대상이 될 확인 하려면 검색 필터를 추가할 수도 있습니다. 이러한 사용자 입력 또는 사용 사례에 따라 앱에 하드 코딩 하 여 확인할 수 있습니다.

샘플 앱에서 다음 코드를 만들고 앱을 구문 분석 하 고 검색 되는 장치와 상호 작용할 수 있도록 감시자 인스턴스를 시작 하는 방법을 보여 줍니다.

```ObjectiveC
// Start watcher with filter for transport types, form factors
- (void)startWatcherWithFilter:(NSMutableArray<NSObject<MCDRemoteSystemFilter>*>*)remoteSystemFilter
{
    _discoveredSystems = [[NSMutableArray alloc] init];
    _devicesAdded = 0;
    _devicesUpdated = 0;
    _devicesRemoved = 0;

    // add filters (not defined here)
    _watcher = (remoteSystemFilter.count > 0) ? [[MCDRemoteSystemWatcher alloc] initWithFilters:remoteSystemFilter] :
        [[MCDRemoteSystemWatcher alloc] init];

    // add event handlers
    RemoteSystemViewController* __weak weakSelf = self;
    [_watcher addRemoteSystemAddedListener:^(
        __unused MCDRemoteSystemWatcher* watcher, MCDRemoteSystem* system) { [weakSelf _onRemoteSystemAdded:system]; }];

    [_watcher addRemoteSystemUpdatedListener:^(
        __unused MCDRemoteSystemWatcher* watcher, MCDRemoteSystem* system) { [weakSelf _onRemoteSystemUpdated:system]; }];

    [_watcher addRemoteSystemRemovedListener:^(
        __unused MCDRemoteSystemWatcher* watcher, MCDRemoteSystem* system) { [weakSelf _onRemoteSystemRemoved:system]; }];

    // start watcher
    [_watcher start];
}
```

이벤트 처리기 메서드를 여기에서 정의 됩니다.

```ObjectiveC
// Handle when RemoteSystems are added
- (void)_onRemoteSystemAdded:(MCDRemoteSystem*)system
{
    @synchronized(self)
    {
        _devicesAdded++;
        [_discoveredSystems addObject:system];
        [_delegate remoteSystemsDidUpdate];
    }
}

// Handle when RemoteSystems are updated
- (void)_onRemoteSystemUpdated:(MCDRemoteSystem*)system
{
    @synchronized(self)
    {
        _devicesUpdated++;

        for (unsigned i = 0; i < _discoveredSystems.count; i++)
        {
            MCDRemoteSystem* cachedSystem = [_discoveredSystems objectAtIndex:i];
            if ([cachedSystem.displayName isEqualToString:system.displayName])
            {
                [_discoveredSystems replaceObjectAtIndex:i withObject:system];
                break;
            }
        }
    }
}

// Handle when RemoteSystems are removed
- (void)_onRemoteSystemRemoved:(MCDRemoteSystem*)system
{
    @synchronized(self)
    {
        _devicesRemoved++;

        for (unsigned i = 0; i < _discoveredSystems.count; i++)
        {
            MCDRemoteSystem* cachedSystem = [_discoveredSystems objectAtIndex:i];
            if ([cachedSystem.displayName isEqualToString:system.displayName])
            {
                [_discoveredSystems removeObjectAtIndex:i];
                break;
            }
        }
    }
}
```

앱에 검색 된 장치 집합을 유지 관리 하는 것이 좋습니다 (나타내는 **MCDRemoteSystem** 인스턴스) 및 UI에서 사용할 수 있는 장치 및 앱 (예: 표시 이름 및 장치 유형)에 대 한 정보를 표시 합니다. 

한 번 `[_watcher start]` 은 원격 시스템 작업에 대 한 감시 시작 되 고 연결 된 장치 검색, 업데이트 또는 검색 된 장치 집합에서 제거 될 때 이벤트 발생을 호출 합니다. 검사 지속적으로 백그라운드에서 하므로 감시자를 중지 하는 것이 좋습니다 (사용 하 여 `[_watcher stop]`) 더 이상 필요할 때 불필요 한 네트워크 통신 및 배터리 드레이닝 하지 않으려면입니다.

## <a name="example-use-case-implementing-remote-launching-and-remote-app-services"></a>예제 사용 사례: 원격 시작 하 고 원격 앱 서비스를 구현 합니다.
이 시점에서 코드 있어야 작업 목록이 **MCDRemoteSystem** 사용 가능한 장치를 참조 하는 개체입니다. 이러한 장치를 사용 하 여 수행할 앱의 기능에 따라 다릅니다. 기본 상호 작용 유형은 원격 시작 하 고 원격 앱 서비스입니다. 다음 섹션에서 설명 합니다.

### <a name="a-remote-launching"></a>A) 원격 시작

다음 코드 중 하나를 선택 하는 방법을 보여 줍니다 합니다 **MCDRemoteSystem** (이상적으로 이렇게 UI 컨트롤을 통해) 하는 개체 및 사용 하 여 **MCDRemoteLauncher** 앱 호환을 전달 하 여 앱을 시작 하려면 URI입니다.

원격 시작이 (이 경우 호스트 장치 시작 됩니다 해당 URI 체계는 기본 앱을 사용 하 여 지정된 된 URI) 원격 장치를 대상 수를 확인 해야 _또는_ 해당 장치에서 특정 원격 응용 프로그램입니다.

이전 섹션에서 볼 수 있듯이 검색 발생 하는 장치 수준에서 먼저 (을 **MCDRemoteSystem** 장치를 나타냅니다), 호출할 수 있지만 `getApplications` 메서드를 **MCDRemoteSystem** 배열을 가져올 인스턴스입니다 **MCDRemoteSystemApp** (처럼 준비 단계에서 사용자 고유의 앱을 등록할 연결 된 장치 플랫폼을 사용 하려면 등록 된 원격 장치에서 앱을 나타내는 개체를 위의 설명 참조). 둘 다 **MCDRemoteSystem** 및 **MCDRemoteSystemApp** 만드는 데 사용할 수는 **MCDRemoteSystemConnectionRequest**, URI를 시작 하는 데 필요한 사항을 인 합니다.

다음 코드 샘플에서 원격을 실행 하는 URI를 통해 연결 요청을 보여 줍니다.

```ObjectiveC
// Send a remote launch of a uri to RemoteSystemApplication
- (IBAction)launchUriButton:(id)sender
{
    NSString* uri = self.uriField.text;
    MCDRemoteLauncher* remoteLauncher = [[MCDRemoteLauncher alloc] init];
    MCDRemoteSystemConnectionRequest* connectionRequest =
        [MCDRemoteSystemConnectionRequest requestWithRemoteSystemApplication:self.selectedApplication];
    [remoteLauncher launchUriAsync:uri
        withConnectionRequest:connectionRequest
            completion:^(MCDRemoteLaunchUriStatus result, NSError* _Nullable error) {
                if (error)
                {
                    NSLog(@"LaunchURI [%@]: ERROR: %@", uri, error);
                    return;
                }

                if (result == MCDRemoteLaunchUriStatusSuccess)
                {
                    NSLog(@"LaunchURI [%@]: Success!", uri);
                }
                else
                {
                    NSLog(@"LaunchURI [%@]: Failed with code %d", uri, (int)result);
                }
            }];
}
```

전송 되는 URI에 따라 특정 상태 또는 원격 장치 구성에서 앱을 시작할 수 있습니다. 이렇게 하면 중단 없이 다른 장치에서 동영상을 시청 같은 사용자 작업을 계속할 수 있습니다.

사용에 따라 대상된 시스템에 앱이 없습니다 URI를 처리할 수 있는 경우를 처리 하기 위해 해야 할 수 있습니다 하거나 여러 앱에서 처리할 수 있습니다. 합니다 **[MCDRemoteLauncher](../objectivec-api/remotesystems.commanding/MCDRemoteLauncher.md)** 클래스 및 **[MCDRemoteLauncherOptions](../objectivec-api/remotesystems.commanding/MCDRemoteLauncherOptions.md)** 클래스에는이 작업을 수행 하는 방법을 설명 합니다.

### <a name="b-remote-app-services"></a>B) 원격 앱 서비스

IOS 앱 연결 장치 포털을 사용 하 여 다른 장치에서 앱 서비스와 상호 작용할 수 있습니다. 다른 장치와 통신 하는 여러 방법을 제공&mdash;모든 하지 않고도 앱 호스트 장치 포그라운드로 가져옵니다.

#### <a name="set-up-the-app-service-on-the-target-device"></a>대상 장치에서 앱 서비스 설정
이 가이드를 사용 합니다 [Roman 테스트 앱에 대 한 Windows](http://aka.ms/romeapp) 해당 대상 앱 서비스로 합니다. 따라서 아래 코드를 사용 하면 iOS 앱이 지정된 된 원격 시스템에서 해당 특정 앱 서비스에 대 한 확인 합니다. 이 시나리오를 테스트 하려는 경우 Windows 장치의 Roman 테스트 앱을 다운로드 하 고 같은 MSA 또는 위의 예비 단계에서 사용한 AAD 로그인 해야 합니다.

사용자 고유의 UWP 앱 서비스를 작성 하는 방법에 대 한 지침을 참조 하세요 [만들기 (UWP) 앱 서비스를 사용 하 고](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)입니다. 서비스를 연결 된 장치와 호환 되도록 하기 위해 몇 가지 변경 해야 합니다. 참조 된 [remoteapp 서비스에 대 한 UWP 가이드](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) 이 작업을 수행 하는 방법에 대 한 지침은 합니다. 

#### <a name="open-an-app-service-connection-on-the-client-device"></a>클라이언트 장치에서 앱 서비스 연결을 열려면
IOS 앱을 원격 장치 또는 응용 프로그램에 대 한 참조를 획득 해야 합니다. 이 시나리오의 시작 섹션에서와 같은 사용 해야 합니다는 **MCDRemoteSystemConnectionRequest**에서 생성할 수 있습니다는 **MCDRemoteSystem** 또는 **MCDRemoteSystemApp**  시스템에서 사용 가능한 앱을 나타내는입니다.

두 문자열에서 해당 대상된 앱 서비스를 식별 하려면 앱에 필요 하는 또한: 합니다 *app service 이름* 하 고 *패키지 식별자*합니다. App service 공급자의 소스 코드에서 발견 되는 이러한 (참조 [만들기 (UWP) 앱 서비스를 사용 하 고](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) 세부 정보에 대 한). 함께 이러한 문자열 구성 합니다 **MCDAppServiceDescription**에 공급 되는 **MCDAppServiceConnection** 인스턴스.

```ObjectiveC
// Step #1:  Establish an app service connection
- (IBAction)connectAppServiceButton:(id)sender
{
    MCDAppServiceConnection* connection = nil;
    @synchronized(self)
    {
        connection = _appServiceConnection;
        if (!connection)
        {
            connection = _appServiceConnection = [MCDAppServiceConnection new];
            connection.appServiceDescription =
                [MCDAppServiceDescription descriptionWithName:g_appServiceName packageId:g_packageIdentifier];
            _serviceClosedRegistration = [connection addServiceClosedListener:^(__unused MCDAppServiceConnection* connection,
                MCDAppServiceClosedStatus status) { [self appServiceConnection:connection closedWithStatus:status]; }];
        }
    }

    @try
    {
        MCDRemoteSystemConnectionRequest* connectionRequest =
            [MCDRemoteSystemConnectionRequest requestWithRemoteSystemApplication:self.selectedApplication];
        [connection openRemoteAsync:connectionRequest
            completion:^(MCDAppServiceConnectionStatus status, NSError* error) {
                if (error)
                {
                    NSLog(@"ConnectAppService: ERROR: %@", error);
                    return;
                }
                if (status != MCDAppServiceConnectionStatusSuccess)
                {
                    NSLog(@"ConnectAppService: Failed with code %d", (int)status);
                    return;
                }
                NSLog(@"Successfully connected!");
                dispatch_async(
                    dispatch_get_main_queue(), ^{ self.appServiceStatusLabel.text = @"App service connected! no ping sent"; });
            }];
    }
    @catch (NSException* ex)
    {
        NSLog(@"ConnectAppService: EXCEPTION! %@", ex);
    }
}
```


#### <a name="create-a-message-to-send-to-the-app-service"></a>App service에 보낼 메시지를 만들려면

보낼 메시지를 저장 하는 변수를 선언 합니다. IOS에서 원격 앱 서비스에 보내는 메시지의 수를 **NSDictionary** 형식입니다.

> [!NOTE]
> 앱을 다른 플랫폼에서 앱 서비스와 통신 하는 경우 연결 된 장치 플랫폼을 변환 합니다 **NSDictionary** 수신 플랫폼에서 해당 구문에 있습니다. 예를 들어를 **[NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary)** app service로 변환 하는 Windows에이 앱에서 보낸를 [ **ValueSet** ](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) (의.NET 개체 프레임 워크), app service에서 다음 해석 될 수 있는 합니다. 다른 방향으로 전달 되는 정보는 역변환을 거칩니다.

다음 메서드는 Windows에 대 한 Roman 테스트 앱의 app service에서 해석할 수 있는 메시지를 만듭니다.

```ObjectiveC
// Create a message to send
- (NSDictionary*)_createPingMessage
{
    return @{
        @"Type" : @"ping",
        @"CreationDate" : [_dateFormatter stringFromDate:[NSDate date]],
        @"TargetId" : _selectedApplication.applicationId
    };
}
```

> [!IMPORTANT]
> 합니다 **NSDictionary** 원격 앱 서비스 시나리오에서 앱 및 서비스 간에 전달 되는 개체는 다음 형식을 준수 해야 합니다. 키 이어야 합니다 **NSString**및 값이 될 수 있습니다. **NSString**boxed 숫자 형식 (정수 또는 부동 소수점), 부울, boxed **NSDate**합니다 **NSUUID**, 이러한 형식 또는 다른 유형이 같은 배열 **NSDictionary**  이 사양을 충족 하는 개체입니다. 

#### <a name="send-messages-to-the-app-service"></a>App service에 메시지 보내기

앱 서비스 연결이 설정 된 메시지를 작성 하 고 간단 하 고 작업을 수행 하려면에서 아무 곳 이나 연결 인스턴스 및 메시지에 대 한 참조가 있는 앱 app service에 전송 합니다.

다음 코드 샘플에서 app service 및 응답 처리에 메시지를 보내는 보여 줍니다.

```ObjectiveC
//  Send a message using the app service connection
- (IBAction)sendAppServiceButton:(id)sender
{
    if (!_appServiceConnection)
    {
        return;
    }

    // Send the message and get a response
    @try
    {
        [_appServiceConnection sendMessageAsync:[self _createPingMessage]
            completion:^(MCDAppServiceResponse* response, NSError* error) {
                if (error)
                {
                    NSLog(@"SendPing: ERROR: %@", error);
                    return;
                }

                if (response.status != MCDAppServiceResponseStatusSuccess)
                {
                    NSLog(@"SendPing: Response received with bad status code %d", (int)response.status);
                    return;
                }

                NSString* creationDateString = response.message[@"CreationDate"];
                if (creationDateString)
                {
                    NSDate* date = [_dateFormatter dateFromString:creationDateString];
                    if (date)
                    {
                        NSTimeInterval diff = [[NSDate date] timeIntervalSinceDate:date];
                        dispatch_async(dispatch_get_main_queue(),
                            ^{ self.appServiceStatusLabel.text = [NSString stringWithFormat:@"%g", diff]; });
                    }
                }
            }];
    }
    @catch (NSException* ex)
    {
        NSLog(@"SendPing: EXCEPTION! %@", ex);
    }
}
```

로마 앱의 경우 응답 메시지 응답의 총 전송 시간 날짜를 비교할 것이 매우 간단한 사용 사례에 있도록 만들어진 날짜를 포함 합니다.

원격 앱 서비스를 사용 하 여 단일 메시지 교환이 완료 했습니다.

#### <a name="finish-app-service-communication"></a>앱 서비스 통신을 완료

앱 완료 되 면 두 장치 간에 연결을 닫습니다 대상 장치의 앱 서비스와 상호 작용 합니다.

```ObjectiveC
- (void)appServiceConnection:(__unused MCDAppServiceConnection*)connection closedWithStatus:(MCDAppServiceClosedStatus)status
{
    NSLog(@"AppService closed with status %d", (int)status);
    dispatch_async(
        dispatch_get_main_queue(), ^{ self.appServiceStatusLabel.text = [NSString stringWithFormat:@"disconnected (%d)", (int)status]; });
}
```

## <a name="related-topics"></a>관련 항목
* [API 참조 페이지](api-reference-for-ios.md) 
* [iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) 
* [원격 앱 서비스 (UWP)와 통신](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service)
* [만들기 및 app service (UWP) 사용](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)합니다.
