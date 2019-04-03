---
title: MCDConnectedDevicesPlatform
description: 연결 된 장치 플랫폼을 나타내고 앱의 연결을 관리 하는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 33fdb6f7dfd7d11831da1f7710215e35306d79d1
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909745"
---
# <a name="class-mcdconnecteddevicesplatform"></a><span data-ttu-id="d4d07-104">클래스 `MCDConnectedDevicesPlatform`</span><span class="sxs-lookup"><span data-stu-id="d4d07-104">class `MCDConnectedDevicesPlatform`</span></span> 

```
@interface MCDConnectedDevicesPlatform : NSObject
```  
<span data-ttu-id="d4d07-105">이 클래스는 연결 된 장치 플랫폼을 나타내고 앱의 연결을 관리입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-105">This class to represent the Connected Devices Platform and manage the app's connection to it.</span></span>

## <a name="properties"></a><span data-ttu-id="d4d07-106">속성</span><span class="sxs-lookup"><span data-stu-id="d4d07-106">Properties</span></span>

### <a name="accountmanager"></a><span data-ttu-id="d4d07-107">accountManager</span><span class="sxs-lookup"><span data-stu-id="d4d07-107">accountManager</span></span>
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccountManager* accountManager;`

<span data-ttu-id="d4d07-108">플랫폼에서 보유 하 고 있는 MCDConnectedDevicesAccountManager 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d4d07-108">MCDConnectedDevicesAccountManager instance held by the platform.</span></span>

### <a name="notificationregistrationmanager"></a><span data-ttu-id="d4d07-109">notificationRegistrationManager</span><span class="sxs-lookup"><span data-stu-id="d4d07-109">notificationRegistrationManager</span></span>
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesNotificationRegistrationManager* notificationRegistrationManager;`

<span data-ttu-id="d4d07-110">플랫폼에서 보유 MCDConnectedDevicesNotificationRegistrationManager 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-110">MCDConnectedDevicesNotificationRegistrationManager instance held by platform.</span></span>

## <a name="constructors"></a><span data-ttu-id="d4d07-111">생성자</span><span class="sxs-lookup"><span data-stu-id="d4d07-111">Constructors</span></span>

### <a name="platformwithsettings"></a><span data-ttu-id="d4d07-112">platformWithSettings</span><span class="sxs-lookup"><span data-stu-id="d4d07-112">platformWithSettings</span></span>
`+ (nullable instancetype)platformWithSettings:(MCDConnectedDevicesPlatformSettings* _Nonnull)settings;`

<span data-ttu-id="d4d07-113">지정 된 플랫폼 설정 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d4d07-113">A new instance of this class with specified platform settings.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d4d07-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d07-114">Parameters</span></span> 
* `settings` 

<span data-ttu-id="d4d07-115">플랫폼의 응용 프로그램의 설정을 저장 하는 MCDConnectedDevicesPlatformSettings 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-115">The MCDConnectedDevicesPlatformSettings object which stores the app's settings of the platform.</span></span>

#### <a name="returns"></a><span data-ttu-id="d4d07-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4d07-116">Returns</span></span>

<span data-ttu-id="d4d07-117">앱의 플랫폼 설정을 포함 하는 MCDConnectedDevicesPlatform 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-117">Returns an MCDConnectedDevicesPlatform object containing the app's platform settings.</span></span>

### <a name="initwithsettings"></a><span data-ttu-id="d4d07-118">initWithSettings</span><span class="sxs-lookup"><span data-stu-id="d4d07-118">initWithSettings</span></span>
`- (nullable instancetype)initWithSettings:(MCDConnectedDevicesPlatformSettings* _Nonnull)settings;`

<span data-ttu-id="d4d07-119">플랫폼 설정 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d4d07-119">A new instance of this class with the platform settings.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d4d07-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d07-120">Parameters</span></span> 
* `settings` 

<span data-ttu-id="d4d07-121">플랫폼의 응용 프로그램의 설정을 저장 하는 MCDConnectedDevicesPlatformSettings 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-121">The MCDConnectedDevicesPlatformSettings object which stores the app's settings of the platform.</span></span>

#### <a name="returns"></a><span data-ttu-id="d4d07-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4d07-122">Returns</span></span>

<span data-ttu-id="d4d07-123">앱의 플랫폼 설정으로 초기화 하는 MCDConnectedDevicesPlatform 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-123">Returns an MCDConnectedDevicesPlatform object initialized with the app's platform settings.</span></span>

## <a name="methods"></a><span data-ttu-id="d4d07-124">메서드</span><span class="sxs-lookup"><span data-stu-id="d4d07-124">Methods</span></span>

### <a name="processnotification"></a><span data-ttu-id="d4d07-125">processNotification</span><span class="sxs-lookup"><span data-stu-id="d4d07-125">processNotification</span></span>
`- (MCDConnectedDevicesProcessNotificationOperation* _Nonnull)processNotification:(NSDictionary* _Nonnull)notification;`

<span data-ttu-id="d4d07-126">들어오는 APNs 알림을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-126">Process incoming APNs notification.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d4d07-127">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d07-127">Parameters</span></span> 
* `notification` 

<span data-ttu-id="d4d07-128">APNs 알림 처리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-128">Contains the APNs notification to process.</span></span>

#### <a name="returns"></a><span data-ttu-id="d4d07-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="d4d07-129">Returns</span></span>

<span data-ttu-id="d4d07-130">MCDConnectedDevicesProcessNotificationOperation 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-130">An instance of the MCDConnectedDevicesProcessNotificationOperation class.</span></span>

### <a name="start"></a><span data-ttu-id="d4d07-131">start</span><span class="sxs-lookup"><span data-stu-id="d4d07-131">start</span></span>
`- (void) start;`

<span data-ttu-id="d4d07-132">플랫폼을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-132">Start the platform.</span></span>

### <a name="shutdownasync"></a><span data-ttu-id="d4d07-133">shutdownAsync</span><span class="sxs-lookup"><span data-stu-id="d4d07-133">shutdownAsync</span></span>
`- (void)shutdownAsync:(void (^_Nonnull)(NSError* _Nullable))completionBlock;`

<span data-ttu-id="d4d07-134">연결 된 장치 플랫폼을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-134">Shuts down the Connected Devices Platform.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d4d07-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d07-135">Parameters</span></span> 
* `completionBlock` 

<span data-ttu-id="d4d07-136">블록 완료 시 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d07-136">The block to invoke upon completion.</span></span>