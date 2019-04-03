---
title: MCDConnectedDevicesNotificationRegistrationManager
description: 모든 계정에 대 한 로마 클라우드 알림 등록을 관리합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d4f5f7963514795e3e296d9bdb42b1811af4f7cc
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909905"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationmanager"></a><span data-ttu-id="a4b32-104">클래스 `MCDConnectedDevicesNotificationRegistrationManager`</span><span class="sxs-lookup"><span data-stu-id="a4b32-104">class `MCDConnectedDevicesNotificationRegistrationManager`</span></span> 

```
@interface MCDConnectedDevicesNotificationRegistrationManager : NSObject
```  
<span data-ttu-id="a4b32-105">모든 계정에 대 한 연결 된 장치 플랫폼 클라우드 알림에 대 한 등록을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-105">Manages the registration for the Connected Devices platform cloud notification for all accounts.</span></span>

<span data-ttu-id="a4b32-106">MCDConnectedDevicesNotificationRegistrationManager 각 계정에 대 한 등록 알림 정보를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-106">MCDConnectedDevicesNotificationRegistrationManager manages the notification information registered for each account.</span></span> <span data-ttu-id="a4b32-107">언제 든 지 앱의 알림 정보 (예를 들어 변경 될 때 APNS 토큰), 바꾸거나, 앱 정보를 다시 등록 해야 알림 정보를이 만료 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="a4b32-107">Any time an app's notification information changes (for example, when APNS changes its token), or when the notification information is expiring, an app should re-register its information.</span></span> <span data-ttu-id="a4b32-108">응용 프로그램은만 나가는 통신에 대 한 응답에 대 한 내용, 폴링 등록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-108">If an application only cares about responses to outgoing communication, a Polling registration may be used.</span></span>

> [!NOTE] 
> <span data-ttu-id="a4b32-109">알림 정보 ConnectedDevices 많지 성공적으로 작동 하기 전에 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-109">Notification information must be registered before many ConnectedDevices scenarios will work successfully.</span></span> 

## <a name="properties"></a><span data-ttu-id="a4b32-110">속성</span><span class="sxs-lookup"><span data-stu-id="a4b32-110">Properties</span></span>

### <a name="registrationstatechanged"></a><span data-ttu-id="a4b32-111">registrationStateChanged</span><span class="sxs-lookup"><span data-stu-id="a4b32-111">registrationStateChanged</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesNotificationRegistrationManager*, MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs*>* registrationStateChanged;`

<span data-ttu-id="a4b32-112">앱에는 계정에 대 한 알림 등록 상태가 변경 될 때 알립니다 수 있도록 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-112">Event to let the app know when notification registration state changes for an account.</span></span> 

## <a name="methods"></a><span data-ttu-id="a4b32-113">메서드</span><span class="sxs-lookup"><span data-stu-id="a4b32-113">Methods</span></span>

### <a name="registerforaccountasync"></a><span data-ttu-id="a4b32-114">registerForAccountAsync</span><span class="sxs-lookup"><span data-stu-id="a4b32-114">registerForAccountAsync</span></span>
`- (void) registerForAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account registration:(MCDConnectedDevicesNotificationRegistration* _Nonnull)notificationRegistration callback:(nonnull void (^)(BOOL, NSError* _Nullable))callback __attribute__((deprecated("Use registerAsync instead")));`

<span data-ttu-id="a4b32-115">주어진된 알림에 등록 정보를 사용 하 여 지정 된 계정을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-115">Register the given account with the given notification registration information.</span></span> <span data-ttu-id="a4b32-116">이이 응용 프로그램은이 계정에 대 한 새 연결 된 장치 정보에 대 한 알림을 받을 수 있도록 알림 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-116">This creates a notification channel so that this application can be notified about new Connected Devices information for this account.</span></span> <span data-ttu-id="a4b32-117">다른 응용 프로그램 MCDRemoteSystemAppRegistration 정보가 게시 될 때까지이 알림 채널을 사용 하 여이 앱과 통신 하지 수 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-117">Note that other applications can not communicate with this app using this notification channel until the MCDRemoteSystemAppRegistration information is published.</span></span>

> [!WARNING]
> <span data-ttu-id="a4b32-118">이 함수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-118">This function is deprecated.</span></span> <span data-ttu-id="a4b32-119">RegisterAsync를 대신 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4b32-119">Please use registerAsync instead.</span></span>

#### <a name="parameters"></a><span data-ttu-id="a4b32-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4b32-120">Parameters</span></span> 
* `account` 

<span data-ttu-id="a4b32-121">알림 정보를 등록 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-121">Account for which to register notification information.</span></span>

* `notificationRegistration` 

<span data-ttu-id="a4b32-122">알림 정보를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-122">Notification information to register.</span></span>

* `callback` 

<span data-ttu-id="a4b32-123">성공적으로 등록에 대 한 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-123">The callback result for if the registration completed successfully.</span></span>

### <a name="registerasync"></a><span data-ttu-id="a4b32-124">registerAsync</span><span class="sxs-lookup"><span data-stu-id="a4b32-124">registerAsync</span></span>
`- (void) registerAsync:(MCDConnectedDevicesAccount* _Nonnull)account registration:(MCDConnectedDevicesNotificationRegistration* _Nonnull)notificationRegistration completion:(nonnull void (^)(MCDConnectedDevicesNotificationRegistrationResult* _Nonnull, NSError* _Nullable))callback;`

<span data-ttu-id="a4b32-125">주어진된 알림에 등록 정보를 사용 하 여 지정 된 계정을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-125">Register the given account with the given notification registration information.</span></span> <span data-ttu-id="a4b32-126">이이 응용 프로그램은이 계정에 대 한 새 연결 된 장치 정보에 대 한 알림을 받을 수 있도록 알림 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-126">This creates a notification channel so that this application can be notified about new Connected Devices information for this account.</span></span> <span data-ttu-id="a4b32-127">다른 응용 프로그램 MCDRemoteSystemAppRegistration 정보가 게시 될 때까지이 알림 채널을 사용 하 여이 앱과 통신 하지 수 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-127">Note that other applications can not communicate with this app using this notification channel until the MCDRemoteSystemAppRegistration information is published.</span></span>

#### <a name="parameters"></a><span data-ttu-id="a4b32-128">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4b32-128">Parameters</span></span> 
* `account` 

<span data-ttu-id="a4b32-129">알림 정보를 등록 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-129">Account for which to register notification information.</span></span>

* `notificationRegistration` 

<span data-ttu-id="a4b32-130">알림 정보를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-130">Notification information to register.</span></span>

* `callback` 

<span data-ttu-id="a4b32-131">성공적으로 등록에 대 한 콜백이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-131">The callback result for if the registration completed successfully.</span></span>

### <a name="getnotificationregistrationstateforaccount"></a><span data-ttu-id="a4b32-132">getNotificationRegistrationStateForAccount</span><span class="sxs-lookup"><span data-stu-id="a4b32-132">getNotificationRegistrationStateForAccount</span></span>
`- (MCDConnectedDevicesNotificationRegistrationState) getNotificationRegistrationStateForAccount:(MCDConnectedDevicesAccount* _Nonnull)account;`

<span data-ttu-id="a4b32-133">지정된 된 계정에 대 한 현재 알림 등록 상태를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-133">Retrieve the current notification registration state for the given account.</span></span> <span data-ttu-id="a4b32-134">등록 된 알림 정보를 (앱 제거 되었거나 매우 오랫동안에서 실행 되지 하는 경우에 유용) 결국 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-134">The notification information that is registered will eventually expire (useful if the app is uninstalled or not run in a very long time).</span></span> <span data-ttu-id="a4b32-135">다시 앱 등록이 만료 됨 / 만료 된 경우 해당 알림 정보를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-135">An app should re-register its notification information when the registration is expiring / expired.</span></span> 

#### <a name="parameters"></a><span data-ttu-id="a4b32-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4b32-136">Parameters</span></span> 
* `account`

<span data-ttu-id="a4b32-137">등록 상태를 가져올 수 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-137">Account for which to get registration state.</span></span>

#### <a name="returns"></a><span data-ttu-id="a4b32-138">반환 값</span><span class="sxs-lookup"><span data-stu-id="a4b32-138">Returns</span></span>

<span data-ttu-id="a4b32-139">알림 등록의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b32-139">State of the notification registration.</span></span>
