---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: dc4d7bbd-bc87-42b1-9924-52c7bfcd5b5f
ms.localizationpriority: medium
ms.openlocfilehash: d8e94884c742015b08d87e83a9384cbb577695c4
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907925"
---
## <a name="preliminary-setup-for-push-notifications"></a><span data-ttu-id="d102f-103">푸시 알림에 대 한 예비 설치</span><span class="sxs-lookup"><span data-stu-id="d102f-103">Preliminary setup for push notifications</span></span>

### <a name="register-your-app-for-push-notifications"></a><span data-ttu-id="d102f-104">푸시 알림을 위해 앱 등록</span><span class="sxs-lookup"><span data-stu-id="d102f-104">Register your app for push notifications</span></span>

<span data-ttu-id="d102f-105">Google에 응용 프로그램 등록 [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/android/client) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-105">Register your application with Google for [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/android/client) support.</span></span> <span data-ttu-id="d102f-106">보낸 사람에 게 받은; ID 및 서버 키 기록해 해야 합니다. 나중에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-106">Be sure to make note of the sender ID and server key that you receive; you'll need them later.</span></span> 

<span data-ttu-id="d102f-107">등록 되 면 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-107">Once registered, you must associate push notification functionality with the Connected Devices Platform in your app.</span></span>

```Java
notificationRegistration = new ConnectedDevicesNotificationRegistration();
notificationRegistration.setType(ConnectedDevicesNotificationType.FCM);
notificationRegistration.setToken(token);
notificationRegistration.setAppId(Secrets.FCM_SENDER_ID);
notificationRegistration.setAppDisplayName("SampleApp");

mConnectedDevicesPlatform.getNotificationRegistrationManager().registerForAccountAsync(mConnectedDevicesAccount).whenComplete(() -> {
  // Now that notifications are registered, this account can receive replies to commands and incoming commands.
});
```

### <a name="register-your-app-in-microsoft-windows-dev-center-for-cross-device-experiences"></a><span data-ttu-id="d102f-108">장치 간 환경을 위한 Microsoft Windows 개발자 센터에서 앱 등록</span><span class="sxs-lookup"><span data-stu-id="d102f-108">Register your app in Microsoft Windows Dev Center for cross-device experiences</span></span>
<span data-ttu-id="d102f-109">에 대 한 앱을 등록 해야 하는 Android 장치에서 통신 해야 하는 경우는 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-109">If you require communication to your Android device, you need to register your app for the [cross-device experiences feature of the Microsoft Developer Dashboard](https://developer.microsoft.com/dashboard/crossplatform/web).</span></span> <span data-ttu-id="d102f-110">위의 MSA 및 AAD 앱 등록에서 다른 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-110">This is a different procedure from MSA and AAD app registration above.</span></span>  <span data-ttu-id="d102f-111">이 프로세스에 대 한 주요 목표는 연결 된 장치 플랫폼에서 인식 되 고 동시에 네이티브 푸시 알림을 사용 하 여 알림을 보낼 플랫폼에 권한을 부여 하는 플랫폼 간 앱 id 사용 하 여 플랫폼 특정 앱 id를 매핑할 각 모바일 플랫폼에 해당 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-111">The main goal for this process is to map the platform specific app identities with a cross-platform app identity that is recognized by Connected Devices Platform, and at the same time authorizes the Platform to send notifications using the native push notification services corresponding to each mobile platform.</span></span> <span data-ttu-id="d102f-112">이 경우 해당 있도록 Firebase Cloud Messaging을 통해 iOS 앱 끝점을 통신을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-112">In this case, it enables it enables communication to iOS app endpoints via Firebase Cloud Messaging.</span></span>

<span data-ttu-id="d102f-113">Dev Center 대시보드로 이동, 왼쪽 탐색 창에서 장치 간 환경을로 이동 하 고 아래와 같이 표시 된 새 장치 간 앱을 구성를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-113">Go to Dev Center Dashboard, navigate to Cross-Device Experiences from the left side navigation pane, and select configuring a new cross-device app, shown as below.</span></span>
<span data-ttu-id="d102f-114">![개발자 센터 대시보드 – 장치 간 환경](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-114">![Dev Center Dashboard – Cross-Device Experiences](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span></span>

<span data-ttu-id="d102f-115">개발자 센터 온 보 딩 프로세스에는 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-115">The Dev Center on-boarding process requires the following steps:</span></span>
* <span data-ttu-id="d102f-116">앱의 존재가 됩니다 및 장치 간 환경을 사용할 수 있는 플랫폼 선택 – 지원 되는 플랫폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-116">Select supported platforms – select the platforms where your app will have a presence and be enabled for cross-device experiences.</span></span> <span data-ttu-id="d102f-117">Windows, Android 및/또는 iOS에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-117">You can select from Windows, Android, and/or iOS.</span></span>
<span data-ttu-id="d102f-118">![장치 간 환경을 – 지원 되는 플랫폼](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-118">![Cross-Device Experiences – Supported Platforms](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)</span></span>

* <span data-ttu-id="d102f-119">앱 Id를 제공 합니다.-각 앱을 현재 상태에 플랫폼에 대 한 앱 Id를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-119">Provide app IDs – provide app IDs for each of the platform where your app has a presence.</span></span> 
<span data-ttu-id="d102f-120">![장치 간 환경을-앱 Id](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-120">![Cross-Device Experiences – App IDs](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)</span></span>
> [!NOTE]
> <span data-ttu-id="d102f-121">플랫폼 당 10) (최대 서로 다른 Id를 추가할 수 있습니다 –이 여러 버전의 동일한 앱 또는 다른 앱과 동일한 사용자를 대상으로 하 여 응용 프로그램 서버에서 보낸 동일한 알림을 받을 수 있게 되기를 원하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-121">You may add different IDs (up to ten) per platform – this is in case you have multiple version of the same app, or even different apps, that want to be able to receive the same notifications sent by your app server targeted at the same user.</span></span> 
> [!TIP] 
> <span data-ttu-id="d102f-122">Android 앱에 대 한 프로젝트를 만들 때 앱에 할당 하는 패키지 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-122">For Android apps, this is the Package Name you assigned to your app when you created the project.</span></span> <span data-ttu-id="d102f-123">프로젝트 개요 아래에 있는 Firebase 콘솔에서 패키지 이름을 찾을 수 있습니다-> 일반입니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-123">The Package Name can be found in your Firebase console under Project Overview -> General.</span></span>
<span data-ttu-id="d102f-124">![Firebase 콘솔-프로젝트 개요](../../notifications/media/dev_center_portal/firebase_overview.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-124">![Firebase Console – Project Overview](../../notifications/media/dev_center_portal/firebase_overview.png)</span></span>

* <span data-ttu-id="d102f-125">하거나 MSA 및/또는 AAD 앱 등록에서 앱 Id를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-125">Provide or select the app IDs from MSA and/or AAD app registrations.</span></span> <span data-ttu-id="d102f-126">MSA 또는 AAD 앱 등록에 해당 하는 이러한 클라이언트 Id는 위에서 이전 MSA/AAD 앱 등록 단계에서 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-126">These client IDs corresponding to MSA or AAD app registration were obtained in the previous MSA/AAD app registration steps from above.</span></span> 
<span data-ttu-id="d102f-127">![장치 간 환경을 – MSA 및 AAD 앱 등록](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-127">![Cross-Device Experiences – MSA and AAD App Registrations](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)</span></span>

* <span data-ttu-id="d102f-128">장치 플랫폼 기능 활용 하 여 각 주요 플랫폼에서 앱 클라이언트 알림 끝점, 즉, 보내기 WNS (Windows UWP)에 대 한 고 GCM (Android) 용 APNS (iOS)에 대 한 기본 알림 플랫폼을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-128">Connected Devices Platform capabilities leverage each of the native notification platforms on major platforms to send notifications down to the app client endpoints, namely, WNS (for Windows UWP), GCM (for Android) and APNS (for iOS).</span></span> <span data-ttu-id="d102f-129">알림을 배달 하기 위해 앱 서버에 대해 사용자를 대상으로 알림을 게시할 때 플랫폼을 사용 하도록 설정 하려면 이러한 알림 플랫폼을 위한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-129">Provide your credentials for these notification platforms to enable the Platform to deliver the notifications for your app server, when you publish user-targeted notifications.</span></span>
<span data-ttu-id="d102f-130">![장치 간 환경을 – 푸시 자격 증명](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-130">![Cross-Device Experiences – Push Credentials](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)</span></span>
> [!NOTE] 
> <span data-ttu-id="d102f-131">Android에 대 한 Android 장치를 사용 하 여 통신을 위한 필수 조건은 클라우드 메시징 서비스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-131">For Android, enabling Cloud Messaging service is a prerequisite to communicate with an Android device.</span></span> <span data-ttu-id="d102f-132">참조 [설정 하는 Firebase 클라우드 메시징 클라이언트 Android에서 앱](https://firebase.google.com/docs/cloud-messaging/android/client) 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-132">See [Set Up a Firebase Cloud Messaging Client App on Android](https://firebase.google.com/docs/cloud-messaging/android/client) for more details.</span></span> <span data-ttu-id="d102f-133">온 보 딩을 완료 하면 연결 된 장치 플랫폼에 Windows 개발자 센터를 통해 푸시 자격 증명을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-133">Once you complete the onboarding, you can then provide the push credentials via Windows Dev Center to the Connected Device Platform.</span></span> 
> [!TIP] 
> <span data-ttu-id="d102f-134">필수 보낸 사람 ID Firebase 클라우드 메시징 보낸 사람 ID에 해당 하 고 API 키 레거시 서버 키에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-134">The required Sender ID is corresponding to Firebase Cloud Messaging Sender ID, and the API key is corresponding to Legacy Server Key.</span></span> <span data-ttu-id="d102f-135">Firebase 콘솔에서 모두를 확인할 수 있습니다-> 프로젝트-> 설정, 클라우드 메시징 탭 아래 스크린샷에 표시 된 것과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-135">Both can be found in Firebase Console -> Project -> Settings, under the Cloud Messaging tab, as shown in the screenshot.</span></span>
<span data-ttu-id="d102f-136">![Firebase 콘솔 – Android 푸시 자격 증명](../../notifications/media/dev_center_portal/firebase_push_creds.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-136">![Firebase Console – Android Push Credentials](../../notifications/media/dev_center_portal/firebase_push_creds.png)</span></span>

* <span data-ttu-id="d102f-137">마지막 단계는 확인 프로세스는 앱에이 도메인의 소유권을 컴퓨터에 등록 된 장치 간 앱 id 앱 처럼 작동 하는 증명으로 사용 되는 장치 간 앱 도메인을 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-137">The last step is to verify your cross-device app domain, which serves as a verification process to prove that your app has the ownership of this domain which acts like a cross-device app identity for the app you registered.</span></span>
<span data-ttu-id="d102f-138">![장치 간 환경을 – 도메인 확인](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)</span><span class="sxs-lookup"><span data-stu-id="d102f-138">![Cross-Device Experiences – Domain Verification](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)</span></span>

### <a name="process-notifications-as-they-are-received-by-the-app"></a><span data-ttu-id="d102f-139">앱에서 받은 알림을 처리합니다</span><span class="sxs-lookup"><span data-stu-id="d102f-139">Process notifications as they are received by the app</span></span>

<span data-ttu-id="d102f-140">Microsoft Windows 개발자 센터 내에서 장치 간 환경을 확인 되 면 앱 오면 알림을 처리할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d102f-140">Once the Cross-Device experience within the Microsoft Windows Dev Center has been validated, make sure your app can process the notifications as they come in.</span></span> 

```Java
    ensurePlatformInitialized().thenAccept((ConnectedDevicesPlatform platform) -> {
            ConnectedDevicesProcessNotificationOperation operation = platform.processNotification(data);
        });
```
