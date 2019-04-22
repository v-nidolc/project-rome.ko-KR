---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: cf4bc236-1a9c-4192-b3fe-2d78331316c0
ms.localizationpriority: medium
ms.openlocfilehash: 6de00cdfd4595f67a655a672dc46fea75806a51f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801605"
---
### <a name="add-the-sdk"></a>SDK를 추가 합니다.

사용 하 여 iOS 앱에 연결 된 장치 플랫폼을 추가 하는 가장 간단한 방법은는 [CocoaPods](https://cocoapods.org/) 종속성 관리자입니다. IOS 프로젝트의 이동 *Podfile* 하 고 다음 항목을 삽입 합니다.

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
> CocoaPod를 사용 하려면 사용 해야 합니다 _.xcworkspace 인_ 프로젝트의 파일입니다.

## <a name="initialize-the-connected-devices-platform"></a>연결 된 장치 플랫폼 초기화

모든 연결 된 장치 기능을 사용할 수 있습니다, 전에 플랫폼 앱 내에서 초기화 되어야 합니다. 

인스턴스화해야 합니다 **MCDPlatform** 클래스입니다. 합니다 **MCDPlatform**의 `platformWithAccountProvider:` 메서드는 두 매개 변수:를 **MCDUserAccountProvider** 와 **MCDNotificationProvider**합니다. 합니다 **MCDNotificationProvider** 매개 변수는 원격 앱 호스팅 및이 가이드에서 다루지 않는 사용자 작업에만 필요 합니다. 유지할 수 있습니다 `nil` 지금은 합니다.

합니다 **MCDUserAccountProvider** 연결 된 장치 플랫폼에 현재 사용자의 액세스를 위한 OAuth 2.0 액세스 토큰을 제공 하는 데 필요한 합니다. 처음으로 앱 실행 되 고 새로 고침 토큰을 플랫폼에서 관리 하는 만료 되 면 호출 됩니다. 

위해 온 보 딩 개발자 플랫폼을 사용 하 여 보다 쉽게 하기 위해 제공 했습니다 계정 공급자 구현에서 Android 및 iOS 용. 이러한 구현에는 [인증 공급자 샘플](https://github.com/Microsoft/project-rome/tree/master/iOS/samples/account-provider-sample), OAuth 2.0 액세스 토큰을 가져오고 앱에 대 한 토큰 새로 고침을 사용할 수 있습니다.

[!INCLUDE [auth-scopes](../auth-scopes.md)]

샘플 앱에서 다음 코드를 플랫폼의 초기화를 보여 줍니다.

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

앱에 호출 하 여 포그라운드 종료 될 때 플랫폼 종료는 `shutdownAsync:` 메서드.
