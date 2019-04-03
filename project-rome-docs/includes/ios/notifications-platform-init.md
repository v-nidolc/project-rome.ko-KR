---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: cf4bc236-1a9c-4192-b3fe-2d78331316c0
ms.localizationpriority: medium
ms.openlocfilehash: 6de00cdfd4595f67a655a672dc46fea75806a51f
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908925"
---
### <a name="add-the-sdk"></a><span data-ttu-id="edb8c-103">SDK를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-103">Add the SDK</span></span>

<span data-ttu-id="edb8c-104">사용 하 여 iOS 앱에 연결 된 장치 플랫폼을 추가 하는 가장 간단한 방법은는 [CocoaPods](https://cocoapods.org/) 종속성 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-104">The simplest way to add the Connected Devices Platform to your iOS app is by using the [CocoaPods](https://cocoapods.org/) dependency manager.</span></span> <span data-ttu-id="edb8c-105">IOS 프로젝트의 이동 *Podfile* 하 고 다음 항목을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-105">Go to your iOS project's *Podfile* and insert the following entry:</span></span>

```ObjectiveC
platform :ios, "10.0"
workspace 'iOSSample'

target 'iOSSample' do
  # Uncomment the next line if you're using Swift or would like to use dynamic frameworks
  # use_frameworks!

    pod 'ProjectRomeSdk'

  # Pods for iOSSample
```

> [!NOTE]
> <span data-ttu-id="edb8c-106">CocoaPod를 사용 하려면 사용 해야 합니다 _.xcworkspace 인_ 프로젝트의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-106">In order to consume CocoaPod, you must use the _.xcworkspace_ file in your project.</span></span>

## <a name="initialize-the-connected-devices-platform"></a><span data-ttu-id="edb8c-107">연결 된 장치 플랫폼 초기화</span><span class="sxs-lookup"><span data-stu-id="edb8c-107">Initialize the Connected Devices platform</span></span>

<span data-ttu-id="edb8c-108">모든 연결 된 장치 기능을 사용할 수 있습니다, 전에 플랫폼 앱 내에서 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-108">Before any Connected Devices features can be used, the platform must be initialized within your app.</span></span> 

<span data-ttu-id="edb8c-109">인스턴스화해야 합니다 **MCDPlatform** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-109">You must instantiate the **MCDPlatform** class.</span></span> <span data-ttu-id="edb8c-110">합니다 **MCDPlatform**의 `platformWithAccountProvider:` 메서드는 두 매개 변수:를 **MCDUserAccountProvider** 와 **MCDNotificationProvider**합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-110">The **MCDPlatform**'s `platformWithAccountProvider:` method takes two parameters: a **MCDUserAccountProvider** and a **MCDNotificationProvider**.</span></span> <span data-ttu-id="edb8c-111">합니다 **MCDNotificationProvider** 매개 변수는 원격 앱 호스팅 및이 가이드에서 다루지 않는 사용자 작업에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-111">The **MCDNotificationProvider** parameter is only needed for remote app hosting and User Activities, which are not covered in this guide.</span></span> <span data-ttu-id="edb8c-112">유지할 수 있습니다 `nil` 지금은 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-112">It can be left `nil` for now.</span></span>

<span data-ttu-id="edb8c-113">합니다 **MCDUserAccountProvider** 연결 된 장치 플랫폼에 현재 사용자의 액세스를 위한 OAuth 2.0 액세스 토큰을 제공 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-113">The **MCDUserAccountProvider** is needed to deliver an OAuth 2.0 access token for the current user's access to the Connected Devices Platform.</span></span> <span data-ttu-id="edb8c-114">처음으로 앱 실행 되 고 새로 고침 토큰을 플랫폼에서 관리 하는 만료 되 면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-114">It will be called the first time the app is run and upon the expiration of a platform-managed refresh token.</span></span> 

<span data-ttu-id="edb8c-115">위해 온 보 딩 개발자 플랫폼을 사용 하 여 보다 쉽게 하기 위해 제공 했습니다 계정 공급자 구현에서 Android 및 iOS 용.</span><span class="sxs-lookup"><span data-stu-id="edb8c-115">In order to help developers onboard with the platform more easily, we have provided account provider implementations for Android and iOS.</span></span> <span data-ttu-id="edb8c-116">이러한 구현에는 [인증 공급자 샘플](https://github.com/Microsoft/project-rome/tree/master/iOS/samples/account-provider-sample), OAuth 2.0 액세스 토큰을 가져오고 앱에 대 한 토큰 새로 고침을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-116">These implementations, found in the [authentication provider sample](https://github.com/Microsoft/project-rome/tree/master/iOS/samples/account-provider-sample), can be used to obtain the OAuth 2.0 access token and refresh token for your app.</span></span>

[!INCLUDE [auth-scopes](../auth-scopes.md)]

<span data-ttu-id="edb8c-117">샘플 앱에서 다음 코드를 플랫폼의 초기화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edb8c-117">The following code from the sample app shows the initialization of the platform.</span></span>

```ObjectiveC
- (void)initializePlatform
{
    // Only register for APNs if this app is enabled for push notifications
    NotificationProvider* notificationProvider;
    if ([[UIApplication sharedApplication] isRegisteredForRemoteNotifications])
    {
        notificationProvider = [AppDataSource sharedInstance].notificationProvider;
    }
    else
    {
        NSLog(@"Initializing platform without a notification provider!");
        notificationProvider = nil;
    }

    // Initialize platform
    [AppDataSource sharedInstance].platform = [MCDPlatform platformWithAccountProvider:[AppDataSource sharedInstance].accountProvider notificationProvider:notificationProvider];

    // ...
}
```

<span data-ttu-id="edb8c-118">앱에 호출 하 여 포그라운드 종료 될 때 플랫폼 종료는 `shutdownAsync:` 메서드.</span><span class="sxs-lookup"><span data-stu-id="edb8c-118">Shut down the platform when your app exits the foreground by calling the `shutdownAsync:` method.</span></span>
