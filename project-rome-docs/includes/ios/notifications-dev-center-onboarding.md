---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 0741073e-62de-4e31-8e3b-cd1a55027c1c
ms.localizationpriority: medium
ms.openlocfilehash: f302fa886cf342e5116b88f9b7474c0b3660ab18
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909295"
---
### <a name="register-your-app-for-push-notifications"></a><span data-ttu-id="26c95-103">푸시 알림을 위해 앱 등록</span><span class="sxs-lookup"><span data-stu-id="26c95-103">Register your app for push notifications</span></span>

<span data-ttu-id="26c95-104">응용 프로그램에 대 한 Apple 등록 [Apple Push Notification](https://developer.apple.com/notifications/) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-104">Register your application with Apple for [Apple Push Notification](https://developer.apple.com/notifications/) support.</span></span> <span data-ttu-id="26c95-105">보낸 사람에 게 나중에 필요할 것으로 검색 하는 ID 및 서버 키 기록해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-105">Be sure to make note of the sender ID and server key that you receive as you'll need them later.</span></span>

<span data-ttu-id="26c95-106">등록 되 면 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-106">Once registered, you must associate push notification functionality with the Connected Devices Platform in your app.</span></span>

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

### <a name="register-your-app-in-microsoft-windows-dev-center-for-cross-device-experiences"></a><span data-ttu-id="26c95-107">장치 간 환경을 위한 Microsoft Windows 개발자 센터에서 앱 등록</span><span class="sxs-lookup"><span data-stu-id="26c95-107">Register your app in Microsoft Windows Dev Center for cross-device experiences</span></span>

> [!WARNING]
> <span data-ttu-id="26c95-108">이 단계는만 프로젝트 로마 기능에서 데이터를 액세스 하거나 비 Windows 장치에 대 한 요청을 사용 하려는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-108">This step is only required if you want to use Project Rome features to access data from or make requests of non-Windows devices.</span></span> <span data-ttu-id="26c95-109">만 Windows 장치를 대상으로 하는 경우이 단계를 완료할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-109">If you only target Windows devices, you do not need to complete this step.</span></span>

<span data-ttu-id="26c95-110">에 대 한 앱을 등록 합니다 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-110">Register your app for the [cross-device experiences feature of the Microsoft Developer Dashboard](https://developer.microsoft.com/dashboard/crossplatform/web).</span></span> <span data-ttu-id="26c95-111">위의 MSA 및 AAD 앱 등록에서 다른 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-111">This is a different procedure from MSA and AAD app registration above.</span></span> <span data-ttu-id="26c95-112">이 프로세스에 대 한 연결 된 장치 플랫폼에서 인식할 수 있는 플랫폼 간 앱 id 사용 하 여 플랫폼 특정 앱 id를 매핑할의 주 목적은입니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-112">The main goal for this process is to map the platform specific app identities with a cross-platform app identity that is recognized by Connected Devices Platform.</span></span> <span data-ttu-id="26c95-113">이 단계는 앱 활용 모바일 플랫폼에 해당 하는 네이티브 푸시 알림 서비스를 사용 하 여 알림을 보내는 통해 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-113">This step will also enable sending notifications using the native push notification services corresponding to the mobile platform(s) your app utilizes.</span></span> <span data-ttu-id="26c95-114">IOS에 대 한 알림을 APNS – Apple Push Notification Service를 통해 iOS 앱 끝점으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-114">For iOS, it enables notifications to be sent to iOS app endpoints via APNS – Apple Push Notification Service.</span></span>

<span data-ttu-id="26c95-115">Dev Center 대시보드로 이동, 왼쪽 탐색 창에서 장치 간 환경을로 이동 하 고 새 장치 간 앱을 구성를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-115">Go to Dev Center Dashboard, navigate to Cross-Device Experiences from the left side navigation pane, and select configuring a new cross-device app.</span></span>
<span data-ttu-id="26c95-116">![개발자 센터 대시보드 – 장치 간 환경](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span><span class="sxs-lookup"><span data-stu-id="26c95-116">![Dev Center Dashboard – Cross-Device Experiences](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span></span>

<span data-ttu-id="26c95-117">개발자 센터 온 보 딩 프로세스에는 다음 단계를 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-117">The Dev Center on-boarding process require the following steps:</span></span>

* <span data-ttu-id="26c95-118">앱의 존재가 됩니다 및 장치 간 환경을 사용할 수 있는 플랫폼 선택 – 지원 되는 플랫폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-118">Select supported platforms – select the platforms where your app will have a presence and be enabled for cross-device experiences.</span></span> <span data-ttu-id="26c95-119">그래프 알림을 통합의 경우 Windows, Android 또는 iOS를 사용 하는 어떤 플랫폼에 따라 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-119">In the case of Graph Notifications integration, you can select from Windows, Android, and/or iOS, depending on what platforms you are using.</span></span> ![장치 간 환경을 – 지원 되는 플랫폼](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)

* <span data-ttu-id="26c95-121">앱 Id를 제공 합니다. – 사용 하는 각 플랫폼에 대 한 앱 Id를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-121">Provide app IDs – provide app IDs for each platform you are using.</span></span> <span data-ttu-id="26c95-122">IOS 앱 용 프로젝트를 만들 때 앱에 할당 하는 패키지 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-122">For iOS apps, this is the package name you assigned to your app when you created the project.</span></span> <span data-ttu-id="26c95-123">플랫폼 당 10) (최대 서로 다른 Id를 추가할 수 있습니다를 참고 하-여러 버전의 동일한 앱 또는 다른 앱과 동일한 사용자를 대상으로 하 여 응용 프로그램 서버에서 보낸 동일한 알림을 받을 수 있게 되기를 원하는 경우에이 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-123">Note that you may add different IDs (up to ten) per platform – this is in case you have multiple version of the same app, or even different apps, that want to be able to receive the same notifications sent by your app server targeted at the same user.</span></span> ![장치 간 환경을-앱 Id](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)

* <span data-ttu-id="26c95-125">하거나 이전 MSA/AAD 앱 등록이 위의 단계에서 얻은 MSA 및/또는 AAD 앱 등록에서 앱 Id를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-125">Provide or select the app IDs from MSA and/or AAD app registrations obtained in the previous MSA/AAD app registration steps above.</span></span> ![장치 간 환경을 – MSA 및 AAD 앱 등록](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)

* <span data-ttu-id="26c95-127">사용자를 대상으로 알림을 게시할 때 앱 서버에서 알림 배달을 사용 하도록 설정 하려면 (예: WNS에 대 한 Windows, android의 경우 FCM 및/또는 iOS 용 APNS) 앱에 관련 알림 네이티브 플랫폼에 대 한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-127">Provide your credentials for the native notification platforms relevant to your app (i.e. WNS for Windows, FCM for Android, and/or APNS for iOS) to enable delivery of notifications from your app server when you publish user-targeted notifications.</span></span> ![장치 간 환경을 – 푸시 자격 증명](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)

* <span data-ttu-id="26c95-129">마지막으로, 응용 프로그램 도메인의 소유권을 가진다 고 사용할 수 있는 장치 간 id 앱에 대 한 장치 간 앱 도메인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c95-129">Finally, verify your cross-device app domain to make sure your app has the ownership of the domain and can use it as a cross-device identity for your app.</span></span> ![장치 간 환경을 – 도메인 확인](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)
