---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: dc4d7bbd-bc87-42b1-9924-52c7bfcd5b5f
ms.localizationpriority: medium
ms.openlocfilehash: f085486eece082366dddc00d86f0c4959d09a5cf
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907305"
---
### <a name="register-your-app-for-push-notifications"></a><span data-ttu-id="d353d-103">푸시 알림을 위해 앱 등록</span><span class="sxs-lookup"><span data-stu-id="d353d-103">Register your app for push notifications</span></span>

<span data-ttu-id="d353d-104">Google에 응용 프로그램 등록 [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/android/client) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-104">Register your application with Google for [Firebase Cloud Messaging](https://firebase.google.com/docs/cloud-messaging/android/client) support.</span></span> <span data-ttu-id="d353d-105">보낸 사람에 게 받은; ID 및 서버 키 기록해 해야 합니다. 나중에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-105">Be sure to make note of the sender ID and server key that you receive; you'll need them later.</span></span>

<span data-ttu-id="d353d-106">등록 되 면 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-106">Once registered, you must associate push notification functionality with the Connected Devices Platform in your app.</span></span>

```Java
mNotificationRegistration = new ConnectedDevicesNotificationRegistration();
mNotificationRegistration.setType(ConnectedDevicesNotificationType.FCM);
mNotificationRegistration.setToken(token);
mNotificationRegistration.setAppId(Secrets.FCM_SENDER_ID);
mNotificationRegistration.setAppDisplayName("SampleApp");
```

### <a name="register-your-app-in-microsoft-windows-dev-center-for-cross-device-experiences"></a><span data-ttu-id="d353d-107">장치 간 환경을 위한 Microsoft Windows 개발자 센터에서 앱 등록</span><span class="sxs-lookup"><span data-stu-id="d353d-107">Register your app in Microsoft Windows Dev Center for cross-device experiences</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d353d-108">이 단계는만 프로젝트 로마 기능에서 데이터를 액세스 하거나 비 Windows 장치에 대 한 요청을 사용 하려는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-108">This step is only required if you want to use Project Rome features to access data from or make requests of non-Windows devices.</span></span> <span data-ttu-id="d353d-109">만 Windows 장치를 대상으로 하는 경우이 단계를 완료할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-109">If you only target Windows devices, you do not need to complete this step.</span></span>

<span data-ttu-id="d353d-110">Dev Center 대시보드로 이동, 왼쪽 탐색 창에서 장치 간 환경을로 이동 하 고 아래와 같이 표시 된 새 장치 간 앱을 구성를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-110">Go to Dev Center Dashboard, navigate to Cross-Device Experiences from the left side navigation pane, and select configuring a new cross-device app, shown as below.</span></span>
<span data-ttu-id="d353d-111">![개발자 센터 대시보드 – 장치 간 환경](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-111">![Dev Center Dashboard – Cross-Device Experiences](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)</span></span>

<span data-ttu-id="d353d-112">개발자 센터 온 보 딩 프로세스에는 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-112">The Dev Center on-boarding process requires the following steps:</span></span>
* <span data-ttu-id="d353d-113">앱의 존재가 됩니다 및 장치 간 환경을 사용할 수 있는 플랫폼 선택 – 지원 되는 플랫폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-113">Select supported platforms – select the platforms where your app will have a presence and be enabled for cross-device experiences.</span></span> <span data-ttu-id="d353d-114">그래프 알림을 통합의 경우 Windows, Android 및/또는 iOS에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-114">In the case of Graph Notifications integration, you can select from Windows, Android, and/or iOS.</span></span>
<span data-ttu-id="d353d-115">![장치 간 환경을 – 지원 되는 플랫폼](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-115">![Cross-Device Experiences – Supported Platforms](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)</span></span>

* <span data-ttu-id="d353d-116">앱 Id를 제공 합니다.-각 앱을 현재 상태에 플랫폼에 대 한 앱 Id를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-116">Provide app IDs – provide app IDs for each of the platform where your app has a presence.</span></span> <span data-ttu-id="d353d-117">Android 앱에 대 한 프로젝트를 만들 때 앱에 할당 하는 패키지 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-117">For Android apps, this is the Package Name you assigned to your app when you created the project.</span></span> <span data-ttu-id="d353d-118">프로젝트 개요 아래에 있는 Firebase 콘솔에서 패키지 이름을 찾을 수 있습니다-> 일반입니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-118">The Package Name can be found in your Firebase console under Project Overview -> General.</span></span> <span data-ttu-id="d353d-119">플랫폼 당 10) (최대 서로 다른 Id를 추가할 수 있습니다 –이 여러 버전의 동일한 앱 또는 다른 앱과 동일한 사용자를 대상으로 하 여 응용 프로그램 서버에서 보낸 동일한 알림을 받을 수 있게 되기를 원하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-119">You may add different IDs (up to ten) per platform – this is in case you have multiple version of the same app, or even different apps, that want to be able to receive the same notifications sent by your app server targeted at the same user.</span></span> 
<span data-ttu-id="d353d-120">![장치 간 환경을-앱 Id](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-120">![Cross-Device Experiences – App IDs](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)</span></span>

* <span data-ttu-id="d353d-121">하거나 MSA 및/또는 AAD 앱 등록에서 앱 Id를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-121">Provide or select the app IDs from MSA and/or AAD app registrations.</span></span> <span data-ttu-id="d353d-122">MSA 또는 AAD 앱 등록에 해당 하는 이러한 클라이언트 Id는 위에서 이전 MSA/AAD 앱 등록 단계에서 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-122">These client IDs corresponding to MSA or AAD app registration were obtained in the previous MSA/AAD app registration steps from above.</span></span> 
<span data-ttu-id="d353d-123">![장치 간 환경을 – MSA 및 AAD 앱 등록](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-123">![Cross-Device Experiences – MSA and AAD App Registrations](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)</span></span>

* <span data-ttu-id="d353d-124">주요 플랫폼에서 클라이언트 끝점, 즉, 앱으로 알림을 보낼 WNS (Windows UWP)에 대 한 고 FCM (Android) 용 APNS (iOS)에 대 한 기본 알림 플랫폼의 각 그래프 알림 및 기타 연결 된 장치 플랫폼 기능 활용 .</span><span class="sxs-lookup"><span data-stu-id="d353d-124">Graph Notifications and other Connected Devices Platform capabilities leverage each of the native notification platforms on major platforms to send notifications down to the app client endpoints, namely, WNS (for Windows UWP), FCM (for Android) and APNS (for iOS).</span></span> <span data-ttu-id="d353d-125">알림을 배달 하기 위해 앱 서버에 대해 사용자를 대상으로 알림을 게시할 때 그래프 알림을 사용 하도록이 알림 플랫폼을 위한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-125">Provide your credentials for these notification platforms to enable Graph Notifications to deliver the notifications for your app server, when you publish user-targeted notifications.</span></span> <span data-ttu-id="d353d-126">Android 용 [클라우드 메시징 서비스를 사용 하도록 설정 하면](https://firebase.google.com/docs/cloud-messaging/android/client) Microsoft Graph 알림을 사용 하 여 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-126">For Android, [enabling the Cloud Messaging service](https://firebase.google.com/docs/cloud-messaging/android/client) is a prerequisite to using Microsoft Graph Notifications.</span></span> <span data-ttu-id="d353d-127">또한 필요한 보낸 사람 ID를 Firebase 클라우드 메시징 발신자 ID 및 API 키에 해당 하는 참고 레거시 서버 키에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-127">Also, note that the required Sender ID corresponds to the Firebase Cloud Messaging Sender ID, and the API key corresponds to the Legacy Server Key.</span></span> <span data-ttu-id="d353d-128">Firebase 콘솔에서 모두를 확인할 수 있습니다-> 프로젝트-> 설정, 클라우드 메시징 탭 아래 스크린샷에 표시 된 것과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-128">Both can be found in Firebase Console -> Project -> Settings, under the Cloud Messaging tab, as shown in the screenshot.</span></span>
<span data-ttu-id="d353d-129">![장치 간 환경을 – 푸시 자격 증명](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-129">![Cross-Device Experiences – Push Credentials](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)</span></span>

* <span data-ttu-id="d353d-130">마지막 단계는 확인 프로세스는 앱에이 도메인의 소유권을 컴퓨터에 등록 된 장치 간 앱 id 앱 처럼 작동 하는 증명으로 사용 되는 장치 간 앱 도메인을 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d353d-130">The last step is to verify your cross-device app domain, which serves as a verification process to prove that your app has the ownership of this domain which acts like a cross-device app identity for the app you registered.</span></span>
<span data-ttu-id="d353d-131">![장치 간 환경을 – 도메인 확인](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)</span><span class="sxs-lookup"><span data-stu-id="d353d-131">![Cross-Device Experiences – Domain Verification](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png)</span></span>
