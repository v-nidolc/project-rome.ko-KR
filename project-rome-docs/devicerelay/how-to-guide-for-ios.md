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
# <a name="implementing-device-relay-for-ios"></a><span data-ttu-id="f1866-104">IOS에 대 한 장치 릴레이 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-104">Implementing device relay for iOS</span></span>

<span data-ttu-id="f1866-105">프로젝트 로마 장치 릴레이 기능의 두 가지 주요 기능을 지 원하는 Api의 집합으로 구성: 원격 시작 (라고도 명령) 및 앱 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-105">The Device Relay functionality of Project Rome consists of a set of APIs that support two main features: remote launching (also known as commanding) and app services.</span></span>

<span data-ttu-id="f1866-106">원격 시작 Api를 로컬 장치에서 원격 장치에서 프로세스가 시작 되는 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-106">Remote Launching APIs support scenarios where a process on a remote device is started from a local device.</span></span> <span data-ttu-id="f1866-107">예를 들어 사용자 자동차에서 휴대폰에 라디오를 수신할 수도 있지만 홈을 받으면를 사용 하 여 전화를 홈 스테레오로 후크 되어 있는 해당 Xbox 재생 전송할 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-107">For example, a user might be listening to the radio on their phone in the car, but when they get home they use their phone to transfer playback to their Xbox which is hooked up to the home stereo.</span></span>

<span data-ttu-id="f1866-108">앱 서비스 Api는 임의의 콘텐츠를 포함 하는 메시지를 보낼 수 있습니다 하는 두 장치 간에 영구 파이프라인을 설정 하는 응용 프로그램을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-108">App Services APIs allow an application to establish a persistent pipeline between two devices through which messages containing any arbitrary content can be sent.</span></span> <span data-ttu-id="f1866-109">예, 사진 모바일 장치에서 실행 되는 앱을 공유 사진을 검색 하기 위해 사용자의 PC 사용 하 여 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-109">For example, a photo sharing app running on a mobile device could establish a connection with the user's PC in order to retrieve photos.</span></span>

<span data-ttu-id="f1866-110">프로젝트 로마 기능의 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-110">The features of Project Rome are supported by an underlying platform called the Connected Devices Platform.</span></span> <span data-ttu-id="f1866-111">이 가이드는 연결 된 장치 플랫폼을 사용 하 여 시작 하는 데 필요한 단계를 제공 하 고 다음을 구현 하는 플랫폼을 사용 하는 방법에 설명 릴레이 장치 관련 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-111">This guide provides the necessary steps to get started using the Connected Devices Platform, and then explains how to use the platform to implement device relay related features.</span></span>

<span data-ttu-id="f1866-112">이 단계 아래에서 코드 참조는 [프로젝트 로마 iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) GitHub에서 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-112">This steps below will reference code from the [Project Rome iOS sample app](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) that is available on GitHub.</span></span>  

## <a name="setting-up-the-connected-devices-platform-and-notifications"></a><span data-ttu-id="f1866-113">연결 된 장치 플랫폼 및 알림 설정</span><span class="sxs-lookup"><span data-stu-id="f1866-113">Setting up the Connected Devices Platform and Notifications</span></span>

[!INCLUDE [ios/preliminary-setup](../includes/ios/preliminary-setup.md)]

[!INCLUDE [auth-scopesiOS](../includes/auth-scopesiOS.md)]

[!INCLUDE [ios/dev-center-onboarding](../includes/ios/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a><span data-ttu-id="f1866-114">플랫폼을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="f1866-114">Using the platform</span></span>

[!INCLUDE [ios/create-setup-events-start-platform](../includes/ios/create-setup-events-start-platform.md)]

### <a name="discover-remote-devices-and-apps"></a><span data-ttu-id="f1866-115">원격 장치 및 앱 검색</span><span class="sxs-lookup"><span data-stu-id="f1866-115">Discover remote devices and apps</span></span>

<span data-ttu-id="f1866-116">**MCDRemoteSystemWatcher** 인스턴스는이 섹션의 핵심 기능을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-116">An **MCDRemoteSystemWatcher** instance will handle the core functionality of this section.</span></span> <span data-ttu-id="f1866-117">원격 시스템을 검색 하는 클래스에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-117">Declare it in the class which is to discover remote systems.</span></span>

`MCDRemoteSystemWatcher* _watcher;`

<span data-ttu-id="f1866-118">감시자를 만들고 장치 검색을 시작 하기 전에 어떤 종류의 장치에 앱의 대상이 될 확인 하려면 검색 필터를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-118">Before you create a watcher and start discovering devices, you may wish to add discovery filters to determine which kinds of devices your app will target.</span></span> <span data-ttu-id="f1866-119">이러한 사용자 입력 또는 사용 사례에 따라 앱에 하드 코딩 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-119">These can be determined by user input or hard-coded into the app, depending on your use case.</span></span>

<span data-ttu-id="f1866-120">샘플 앱에서 다음 코드를 만들고 앱을 구문 분석 하 고 검색 되는 장치와 상호 작용할 수 있도록 감시자 인스턴스를 시작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-120">The following code from the sample app demonstrates how to create and start a watcher instance allowing your app to parse and interact with the devices that are discovered.</span></span>

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

<span data-ttu-id="f1866-121">이벤트 처리기 메서드를 여기에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-121">The event handler methods are defined here.</span></span>

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

<span data-ttu-id="f1866-122">앱에 검색 된 장치 집합을 유지 관리 하는 것이 좋습니다 (나타내는 **MCDRemoteSystem** 인스턴스) 및 UI에서 사용할 수 있는 장치 및 앱 (예: 표시 이름 및 장치 유형)에 대 한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-122">We recommend that your app maintain a set of discovered devices (represented by **MCDRemoteSystem** instances) and display information about available devices and their apps (such as display name and device type) on the UI.</span></span> 

<span data-ttu-id="f1866-123">한 번 `[_watcher start]` 은 원격 시스템 작업에 대 한 감시 시작 되 고 연결 된 장치 검색, 업데이트 또는 검색 된 장치 집합에서 제거 될 때 이벤트 발생을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-123">Once `[_watcher start]` is called, it will begin watching for remote system activity and will raise events when connected devices are discovered, updated, or removed from the set of detected devices.</span></span> <span data-ttu-id="f1866-124">검사 지속적으로 백그라운드에서 하므로 감시자를 중지 하는 것이 좋습니다 (사용 하 여 `[_watcher stop]`) 더 이상 필요할 때 불필요 한 네트워크 통신 및 배터리 드레이닝 하지 않으려면입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-124">It will scan continuously in the background, so it is recommended that you stop the watcher (with `[_watcher stop]`) when you no longer need it to avoid unnecessary network communication and battery drain.</span></span>

## <a name="example-use-case-implementing-remote-launching-and-remote-app-services"></a><span data-ttu-id="f1866-125">예제 사용 사례: 원격 시작 하 고 원격 앱 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-125">Example use case: implementing remote launching and remote app services</span></span>
<span data-ttu-id="f1866-126">이 시점에서 코드 있어야 작업 목록이 **MCDRemoteSystem** 사용 가능한 장치를 참조 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-126">At this point in your code, you should have a working list of **MCDRemoteSystem** objects that refer to available devices.</span></span> <span data-ttu-id="f1866-127">이러한 장치를 사용 하 여 수행할 앱의 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-127">What you do with these devices will depend on the function of your app.</span></span> <span data-ttu-id="f1866-128">기본 상호 작용 유형은 원격 시작 하 고 원격 앱 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-128">The main types of interaction are remote launching and remote app services.</span></span> <span data-ttu-id="f1866-129">다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-129">They are explained in the following sections.</span></span>

### <a name="a-remote-launching"></a><span data-ttu-id="f1866-130">A) 원격 시작</span><span class="sxs-lookup"><span data-stu-id="f1866-130">A) Remote launching</span></span>

<span data-ttu-id="f1866-131">다음 코드 중 하나를 선택 하는 방법을 보여 줍니다 합니다 **MCDRemoteSystem** (이상적으로 이렇게 UI 컨트롤을 통해) 하는 개체 및 사용 하 여 **MCDRemoteLauncher** 앱 호환을 전달 하 여 앱을 시작 하려면 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-131">The following code shows how to select one of the **MCDRemoteSystem** objects (ideally this is done through a UI control) and then use **MCDRemoteLauncher** to launch an app on it by passing an app-compatible URI.</span></span>

<span data-ttu-id="f1866-132">원격 시작이 (이 경우 호스트 장치 시작 됩니다 해당 URI 체계는 기본 앱을 사용 하 여 지정된 된 URI) 원격 장치를 대상 수를 확인 해야 _또는_ 해당 장치에서 특정 원격 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-132">It's important to note that a remote launch can target a remote device (in which case the host device will launch the given URI with its default app for that URI scheme) _or_ a specific remote application on that device.</span></span>

<span data-ttu-id="f1866-133">이전 섹션에서 볼 수 있듯이 검색 발생 하는 장치 수준에서 먼저 (을 **MCDRemoteSystem** 장치를 나타냅니다), 호출할 수 있지만 `getApplications` 메서드를 **MCDRemoteSystem** 배열을 가져올 인스턴스입니다 **MCDRemoteSystemApp** (처럼 준비 단계에서 사용자 고유의 앱을 등록할 연결 된 장치 플랫폼을 사용 하려면 등록 된 원격 장치에서 앱을 나타내는 개체를 위의 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="f1866-133">As the previous section demonstrated, discovery happens at the device level first (an **MCDRemoteSystem** represents a device), but you can call the `getApplications` method on an **MCDRemoteSystem** instance to get an array of **MCDRemoteSystemApp** objects, which represent apps on the remote device that have been registered to use the Connected Devices Platform (just as you registered your own app in the preliminary steps above).</span></span> <span data-ttu-id="f1866-134">둘 다 **MCDRemoteSystem** 및 **MCDRemoteSystemApp** 만드는 데 사용할 수는 **MCDRemoteSystemConnectionRequest**, URI를 시작 하는 데 필요한 사항을 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-134">Both **MCDRemoteSystem** and **MCDRemoteSystemApp** can be used to construct a **MCDRemoteSystemConnectionRequest**, which is what is needed to launch a URI.</span></span>

<span data-ttu-id="f1866-135">다음 코드 샘플에서 원격을 실행 하는 URI를 통해 연결 요청을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-135">The following code from the sample shows the remote launching of a URI over a connection request.</span></span>

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

<span data-ttu-id="f1866-136">전송 되는 URI에 따라 특정 상태 또는 원격 장치 구성에서 앱을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-136">Depending on the URI that is sent, you can launch an app in a specific state or configuration on a remote device.</span></span> <span data-ttu-id="f1866-137">이렇게 하면 중단 없이 다른 장치에서 동영상을 시청 같은 사용자 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-137">This allows for the ability to continue a user task, like watching a movie, on a different device without interruption.</span></span>

<span data-ttu-id="f1866-138">사용에 따라 대상된 시스템에 앱이 없습니다 URI를 처리할 수 있는 경우를 처리 하기 위해 해야 할 수 있습니다 하거나 여러 앱에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-138">Depending on your use, you may need to cover the cases in which no apps on the targeted system can handle the URI, or multiple apps can handle it.</span></span> <span data-ttu-id="f1866-139">합니다 **[MCDRemoteLauncher](../objectivec-api/remotesystems.commanding/MCDRemoteLauncher.md)** 클래스 및 **[MCDRemoteLauncherOptions](../objectivec-api/remotesystems.commanding/MCDRemoteLauncherOptions.md)** 클래스에는이 작업을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-139">The **[MCDRemoteLauncher](../objectivec-api/remotesystems.commanding/MCDRemoteLauncher.md)** class and **[MCDRemoteLauncherOptions](../objectivec-api/remotesystems.commanding/MCDRemoteLauncherOptions.md)** class describe how to do this.</span></span>

### <a name="b-remote-app-services"></a><span data-ttu-id="f1866-140">B) 원격 앱 서비스</span><span class="sxs-lookup"><span data-stu-id="f1866-140">B) Remote app services</span></span>

<span data-ttu-id="f1866-141">IOS 앱 연결 장치 포털을 사용 하 여 다른 장치에서 앱 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-141">Your iOS app can use the Connected Devices Portal to interact with app services on other devices.</span></span> <span data-ttu-id="f1866-142">다른 장치와 통신 하는 여러 방법을 제공&mdash;모든 하지 않고도 앱 호스트 장치 포그라운드로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-142">This provides many ways to communicate with other devices&mdash;all without needing to bring an app to the foreground of the host device.</span></span>

#### <a name="set-up-the-app-service-on-the-target-device"></a><span data-ttu-id="f1866-143">대상 장치에서 앱 서비스 설정</span><span class="sxs-lookup"><span data-stu-id="f1866-143">Set up the app service on the target device</span></span>
<span data-ttu-id="f1866-144">이 가이드를 사용 합니다 [Roman 테스트 앱에 대 한 Windows](http://aka.ms/romeapp) 해당 대상 앱 서비스로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-144">This guide will use the [Roman Test App for Windows](http://aka.ms/romeapp) as its target app service.</span></span> <span data-ttu-id="f1866-145">따라서 아래 코드를 사용 하면 iOS 앱이 지정된 된 원격 시스템에서 해당 특정 앱 서비스에 대 한 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-145">Therefore, the code below will cause an iOS app to look for that specific app service on the given remote system.</span></span> <span data-ttu-id="f1866-146">이 시나리오를 테스트 하려는 경우 Windows 장치의 Roman 테스트 앱을 다운로드 하 고 같은 MSA 또는 위의 예비 단계에서 사용한 AAD 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-146">If you wish to test this scenario, download the Roman Test App on a Windows device and make sure you are signed in with the same MSA or AAD that you used in the preliminary steps above.</span></span>

<span data-ttu-id="f1866-147">사용자 고유의 UWP 앱 서비스를 작성 하는 방법에 대 한 지침을 참조 하세요 [만들기 (UWP) 앱 서비스를 사용 하 고](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-147">For instructions on how to write your own UWP app service, see [Create and consume an app service (UWP)](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span> <span data-ttu-id="f1866-148">서비스를 연결 된 장치와 호환 되도록 하기 위해 몇 가지 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-148">You will need to make a few changes in order to make the service compatible with Connected Devices.</span></span> <span data-ttu-id="f1866-149">참조 된 [remoteapp 서비스에 대 한 UWP 가이드](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) 이 작업을 수행 하는 방법에 대 한 지침은 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-149">See the [UWP guide for remote app services](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service) for instructions on how to do this.</span></span> 

#### <a name="open-an-app-service-connection-on-the-client-device"></a><span data-ttu-id="f1866-150">클라이언트 장치에서 앱 서비스 연결을 열려면</span><span class="sxs-lookup"><span data-stu-id="f1866-150">Open an app service connection on the client device</span></span>
<span data-ttu-id="f1866-151">IOS 앱을 원격 장치 또는 응용 프로그램에 대 한 참조를 획득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-151">Your iOS app must acquire a reference to a remote device or application.</span></span> <span data-ttu-id="f1866-152">이 시나리오의 시작 섹션에서와 같은 사용 해야 합니다는 **MCDRemoteSystemConnectionRequest**에서 생성할 수 있습니다는 **MCDRemoteSystem** 또는 **MCDRemoteSystemApp**  시스템에서 사용 가능한 앱을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-152">Like the launch section, this scenario requires the use of a **MCDRemoteSystemConnectionRequest**, which can be constructed from either a **MCDRemoteSystem** or a **MCDRemoteSystemApp** representing an available app on the system.</span></span>

<span data-ttu-id="f1866-153">두 문자열에서 해당 대상된 앱 서비스를 식별 하려면 앱에 필요 하는 또한: 합니다 *app service 이름* 하 고 *패키지 식별자*합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-153">Additionally, your app will need to identify its targeted app service by two strings: the *app service name* and *package identifier*.</span></span> <span data-ttu-id="f1866-154">App service 공급자의 소스 코드에서 발견 되는 이러한 (참조 [만들기 (UWP) 앱 서비스를 사용 하 고](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) 세부 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="f1866-154">These are found in the source code of the app service provider (see [Create and consume an app service (UWP)](https://msdn.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) for details).</span></span> <span data-ttu-id="f1866-155">함께 이러한 문자열 구성 합니다 **MCDAppServiceDescription**에 공급 되는 **MCDAppServiceConnection** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f1866-155">Together these strings construct the **MCDAppServiceDescription**, which is fed into an **MCDAppServiceConnection** instance.</span></span>

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


#### <a name="create-a-message-to-send-to-the-app-service"></a><span data-ttu-id="f1866-156">App service에 보낼 메시지를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f1866-156">Create a message to send to the app service</span></span>

<span data-ttu-id="f1866-157">보낼 메시지를 저장 하는 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-157">Declare a variable to store the message to send.</span></span> <span data-ttu-id="f1866-158">IOS에서 원격 앱 서비스에 보내는 메시지의 수를 **NSDictionary** 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-158">On iOS, the messages that you send to remote app services will be of the **NSDictionary** type.</span></span>

> [!NOTE]
> <span data-ttu-id="f1866-159">앱을 다른 플랫폼에서 앱 서비스와 통신 하는 경우 연결 된 장치 플랫폼을 변환 합니다 **NSDictionary** 수신 플랫폼에서 해당 구문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-159">When your app communicates with app services on other platforms, the Connected Devices Platform translates the **NSDictionary** into the equivalent construct on the receiving platform.</span></span> <span data-ttu-id="f1866-160">예를 들어를 **[NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary)** app service로 변환 하는 Windows에이 앱에서 보낸를 [ **ValueSet** ](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) (의.NET 개체 프레임 워크), app service에서 다음 해석 될 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-160">For example, a **[NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary)** sent from this app to a Windows app service gets translated into a [**ValueSet**](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.valueset) object (of the .NET Framework), which can then be interpreted by the app service.</span></span> <span data-ttu-id="f1866-161">다른 방향으로 전달 되는 정보는 역변환을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-161">Information passed in the other direction undergoes the reverse translation.</span></span>

<span data-ttu-id="f1866-162">다음 메서드는 Windows에 대 한 Roman 테스트 앱의 app service에서 해석할 수 있는 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-162">The following method crafts a message that can be interpreted by the Roman Test App's app service for Windows.</span></span>

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
> <span data-ttu-id="f1866-163">합니다 **NSDictionary** 원격 앱 서비스 시나리오에서 앱 및 서비스 간에 전달 되는 개체는 다음 형식을 준수 해야 합니다. 키 이어야 합니다 **NSString**및 값이 될 수 있습니다. **NSString**boxed 숫자 형식 (정수 또는 부동 소수점), 부울, boxed **NSDate**합니다 **NSUUID**, 이러한 형식 또는 다른 유형이 같은 배열 **NSDictionary**  이 사양을 충족 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-163">The **NSDictionary** objects that are passed between apps and services in the remote app services scenario must adhere to the following format: Keys must be **NSString**s, and the values may be: **NSString**, boxed numeric types (integers or floating points), boxed booleans, **NSDate**, **NSUUID**, homogeneous arrays of any of these types, or other **NSDictionary** objects that meet this specification.</span></span> 

#### <a name="send-messages-to-the-app-service"></a><span data-ttu-id="f1866-164">App service에 메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="f1866-164">Send messages to the app service</span></span>

<span data-ttu-id="f1866-165">앱 서비스 연결이 설정 된 메시지를 작성 하 고 간단 하 고 작업을 수행 하려면에서 아무 곳 이나 연결 인스턴스 및 메시지에 대 한 참조가 있는 앱 app service에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-165">Once the app service connection is established and the message is created, sending it to the app service is simple and can be done from anywhere in the app that has a reference to the connection instance and the message.</span></span>

<span data-ttu-id="f1866-166">다음 코드 샘플에서 app service 및 응답 처리에 메시지를 보내는 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-166">The following code from the sample shows the sending of a message to an app service and the handling of the response.</span></span>

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

<span data-ttu-id="f1866-167">로마 앱의 경우 응답 메시지 응답의 총 전송 시간 날짜를 비교할 것이 매우 간단한 사용 사례에 있도록 만들어진 날짜를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-167">In the Roman App case, the response contains the date it was created, so in this very simple use case, we can compare the dates to get the total transit time of the message response.</span></span>

<span data-ttu-id="f1866-168">원격 앱 서비스를 사용 하 여 단일 메시지 교환이 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-168">That concludes a single message exchange with a remote app service.</span></span>

#### <a name="finish-app-service-communication"></a><span data-ttu-id="f1866-169">앱 서비스 통신을 완료</span><span class="sxs-lookup"><span data-stu-id="f1866-169">Finish app service communication</span></span>

<span data-ttu-id="f1866-170">앱 완료 되 면 두 장치 간에 연결을 닫습니다 대상 장치의 앱 서비스와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-170">When your app is finished interacting with the target device's app service, close the connection between the two devices.</span></span>

```ObjectiveC
- (void)appServiceConnection:(__unused MCDAppServiceConnection*)connection closedWithStatus:(MCDAppServiceClosedStatus)status
{
    NSLog(@"AppService closed with status %d", (int)status);
    dispatch_async(
        dispatch_get_main_queue(), ^{ self.appServiceStatusLabel.text = [NSString stringWithFormat:@"disconnected (%d)", (int)status]; });
}
```

## <a name="related-topics"></a><span data-ttu-id="f1866-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f1866-171">Related topics</span></span>
* [<span data-ttu-id="f1866-172">API 참조 페이지</span><span class="sxs-lookup"><span data-stu-id="f1866-172">API reference page</span></span>](api-reference-for-ios.md) 
* [<span data-ttu-id="f1866-173">iOS 샘플 앱</span><span class="sxs-lookup"><span data-stu-id="f1866-173">iOS sample app</span></span>](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) 
* [<span data-ttu-id="f1866-174">원격 앱 서비스 (UWP)와 통신</span><span class="sxs-lookup"><span data-stu-id="f1866-174">Communicate with a remote app service (UWP)</span></span>](https://docs.microsoft.com/windows/uwp/launch-resume/communicate-with-a-remote-app-service)
* <span data-ttu-id="f1866-175">[만들기 및 app service (UWP) 사용](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1866-175">[Create and consume an app service (UWP)](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service).</span></span>
