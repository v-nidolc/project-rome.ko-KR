---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 0741073e-62de-4e31-8e3b-cd1a55027c1c
ms.localizationpriority: medium
ms.openlocfilehash: f302fa886cf342e5116b88f9b7474c0b3660ab18
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58909295"
---
### <a name="register-your-app-for-push-notifications"></a>푸시 알림을 위해 앱 등록

응용 프로그램에 대 한 Apple 등록 [Apple Push Notification](https://developer.apple.com/notifications/) 지원 합니다. 보낸 사람에 게 나중에 필요할 것으로 검색 하는 ID 및 서버 키 기록해 해야 합니다.

등록 되 면 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다.

```ObjectiveC
self.notificationRegistration = [[MCDConnectedDevicesNotificationRegistration alloc] init];
    if ([[UIApplication sharedApplication] isRegisteredForRemoteNotifications])
    {
        self.notificationRegistration.type = MCDNotificationTypeAPN;
    }
    else
    {
        self.notificationRegistration.type = MCDNotificationTypePolling;
    }
    self.notificationRegistration.appId = [[NSBundle mainBundle] bundleIdentifier];
    self.notificationRegistration.appDisplayName = (NSString*)[[NSBundle mainBundle] objectForInfoDictionaryKey:@"CFBundleDisplayName"];
    self.notificationRegistration.token = deviceToken;
    self.isRegisteredWithToken = YES;
```

### <a name="register-your-app-in-microsoft-windows-dev-center-for-cross-device-experiences"></a>장치 간 환경을 위한 Microsoft Windows 개발자 센터에서 앱 등록

> [!WARNING]
> 이 단계는만 프로젝트 로마 기능에서 데이터를 액세스 하거나 비 Windows 장치에 대 한 요청을 사용 하려는 경우 필요 합니다. 만 Windows 장치를 대상으로 하는 경우이 단계를 완료할 필요가 없습니다.

에 대 한 앱을 등록 합니다 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다. 위의 MSA 및 AAD 앱 등록에서 다른 프로시저입니다. 이 프로세스에 대 한 연결 된 장치 플랫폼에서 인식할 수 있는 플랫폼 간 앱 id 사용 하 여 플랫폼 특정 앱 id를 매핑할의 주 목적은입니다. 이 단계는 앱 활용 모바일 플랫폼에 해당 하는 네이티브 푸시 알림 서비스를 사용 하 여 알림을 보내는 통해 수도 있습니다. IOS에 대 한 알림을 APNS – Apple Push Notification Service를 통해 iOS 앱 끝점으로 보낼 수 있습니다.

Dev Center 대시보드로 이동, 왼쪽 탐색 창에서 장치 간 환경을로 이동 하 고 새 장치 간 앱을 구성를 선택 합니다.
![개발자 센터 대시보드 – 장치 간 환경](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)

개발자 센터 온 보 딩 프로세스에는 다음 단계를 필요 합니다.

* 앱의 존재가 됩니다 및 장치 간 환경을 사용할 수 있는 플랫폼 선택 – 지원 되는 플랫폼을 선택 합니다. 그래프 알림을 통합의 경우 Windows, Android 또는 iOS를 사용 하는 어떤 플랫폼에 따라 선택할 수 있습니다. ![장치 간 환경을 – 지원 되는 플랫폼](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)

* 앱 Id를 제공 합니다. – 사용 하는 각 플랫폼에 대 한 앱 Id를 제공 합니다. IOS 앱 용 프로젝트를 만들 때 앱에 할당 하는 패키지 이름입니다. 플랫폼 당 10) (최대 서로 다른 Id를 추가할 수 있습니다를 참고 하-여러 버전의 동일한 앱 또는 다른 앱과 동일한 사용자를 대상으로 하 여 응용 프로그램 서버에서 보낸 동일한 알림을 받을 수 있게 되기를 원하는 경우에이 합니다. ![장치 간 환경을-앱 Id](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)

* 하거나 이전 MSA/AAD 앱 등록이 위의 단계에서 얻은 MSA 및/또는 AAD 앱 등록에서 앱 Id를 선택 합니다. ![장치 간 환경을 – MSA 및 AAD 앱 등록](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)

* 사용자를 대상으로 알림을 게시할 때 앱 서버에서 알림 배달을 사용 하도록 설정 하려면 (예: WNS에 대 한 Windows, android의 경우 FCM 및/또는 iOS 용 APNS) 앱에 관련 알림 네이티브 플랫폼에 대 한 자격 증명을 제공 합니다. ![장치 간 환경을 – 푸시 자격 증명](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)

* 마지막으로, 응용 프로그램 도메인의 소유권을 가진다 고 사용할 수 있는 장치 간 id 앱에 대 한 장치 간 앱 도메인을 확인 합니다. ![장치 간 환경을 – 도메인 확인](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)
