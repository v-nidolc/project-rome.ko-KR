---
title: MCDUserDataFeed
description: 이 클래스는 연결 된 장치 플랫폼 백 엔드를 사용 하 여 사용자 고유의 데이터를 동기화 하는 일을 담당 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 66898563bdad8adb2f1ebfe75f010cd5ef1d9ca2
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58908995"
---
# <a name="class-mcduserdatafeed"></a><span data-ttu-id="c083d-104">클래스 `MCDUserDataFeed`</span><span class="sxs-lookup"><span data-stu-id="c083d-104">class `MCDUserDataFeed`</span></span>

```
@interface MCDUserDataFeed : NSObject
```

<span data-ttu-id="c083d-105">이 클래스는 연결 된 장치 플랫폼 백 엔드를 사용 하 여 사용자 고유의 데이터를 동기화 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-105">This class is responsible for synchronizing user-specific data with the Connected Devices Platform backend.</span></span> <span data-ttu-id="c083d-106">동기화 되는 데이터는 종속 **[MCDUserDataFeedSyncScope](MCDUserDataFeedSyncScope.md)** 인스턴스 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-106">The data that is synchronized depends on which **[MCDUserDataFeedSyncScope](MCDUserDataFeedSyncScope.md)** instances are contained.</span></span>

## <a name="properties"></a><span data-ttu-id="c083d-107">속성</span><span class="sxs-lookup"><span data-stu-id="c083d-107">Properties</span></span>

### <a name="syncstatus"></a><span data-ttu-id="c083d-108">syncStatus</span><span class="sxs-lookup"><span data-stu-id="c083d-108">syncStatus</span></span>
`@property(nonatomic, readonly) MCDUserDataSyncStatus syncStatus;`

<span data-ttu-id="c083d-109">사용자 데이터 동기화의 현재 상태를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-109">Describes the current status of user data synchronization.</span></span>

### <a name="syncstatuschanged"></a><span data-ttu-id="c083d-110">syncStatusChanged</span><span class="sxs-lookup"><span data-stu-id="c083d-110">syncStatusChanged</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDUserDataFeed*, MCDUserDataFeedSyncStatusChangedEventArgs*>* syncStatusChanged;`

<span data-ttu-id="c083d-111">UserDataFeed의 동기화 상태를 변경 하는 경우에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-111">Event for when the sync status of the UserDataFeed changes.</span></span>

### <a name="daystosync"></a><span data-ttu-id="c083d-112">daysToSync</span><span class="sxs-lookup"><span data-stu-id="c083d-112">daysToSync</span></span>
`@property(nonatomic, readwrite) NSInteger daysToSync;`

<span data-ttu-id="c083d-113">30 개 미만인 해야 하는 데이터 동기화의 일 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-113">The number of days of data to sync, which should be fewer than 30.</span></span>  <span data-ttu-id="c083d-114">서버에 의해 결정 됩니다는 기본값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-114">It represents the default value, which will be determined by the server.</span></span>

## <a name="constructors"></a><span data-ttu-id="c083d-115">생성자</span><span class="sxs-lookup"><span data-stu-id="c083d-115">Constructors</span></span>

### <a name="getforaccount"></a><span data-ttu-id="c083d-116">getForAccount</span><span class="sxs-lookup"><span data-stu-id="c083d-116">getForAccount</span></span>
`+ (nullable instancetype)getForAccount:(nonnull MCDConnectedDevicesAccount*)userAccount
                                   platform:(nonnull MCDConnectedDevicesPlatform*)platform
                         activitySourceHost:(nonnull NSString*)activitySourceHost;`

<span data-ttu-id="c083d-117">만들고 사용자 계정, 플랫폼 인스턴스 및 플랫폼 간 앱 ID를 사용 하 여이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-117">Creates and initializes a new instance of this class with a user account, platform instance, and the cross-platform app ID.</span></span>

#### <a name="parameters"></a><span data-ttu-id="c083d-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c083d-118">Parameters</span></span>
* `userAccount` 

<span data-ttu-id="c083d-119">이 데이터와 연결 된 사용자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-119">The user account that this data will be associated with.</span></span>

* `platform` 

<span data-ttu-id="c083d-120">합니다 **MCDPlatform** 이 앱의 연결 된 장치 기능에 대 한 초기화 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c083d-120">The **MCDPlatform** instance that has been initialized for this app's Connected Devices functionality.</span></span>

* `activitySourceHost` 

<span data-ttu-id="c083d-121">플랫폼 간 앱 id입니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-121">The cross-platform app ID.</span></span> <span data-ttu-id="c083d-122">이 Microsoft 개발자 대시보드 등록을 통해 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-122">This is retrieved through the Microsoft Developer Dashboard registration.</span></span>

#### <a name="returns"></a><span data-ttu-id="c083d-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="c083d-123">Returns</span></span>
<span data-ttu-id="c083d-124">이 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-124">Returns an instance of this class.</span></span>

## <a name="methods"></a><span data-ttu-id="c083d-125">메서드</span><span class="sxs-lookup"><span data-stu-id="c083d-125">Methods</span></span>

### <a name="subscribetosyncscopesasync"></a><span data-ttu-id="c083d-126">subscribeToSyncScopesAsync</span><span class="sxs-lookup"><span data-stu-id="c083d-126">subscribeToSyncScopesAsync</span></span>
`- (void)subscribeToSyncScopesAsync:(NSArray<MCDUserDataFeedSyncScope*>* _Nonnull) syncScopes callback:(nonnull void (^)(BOOL, NSError* _Nullable)) callback;`

<span data-ttu-id="c083d-127">추가 **MCDUserDataFeedSyncScope** 이 MCDUserDataFeed 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c083d-127">Adds **MCDUserDataFeedSyncScope** instances to this MCDUserDataFeed.</span></span>  <span data-ttu-id="c083d-128">이 MCDUserDataFeed에 따라 동기화 되는 **MCDUserDataFeedSyncScope** 지정 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c083d-128">This MCDUserDataFeed is synchronized according to the **MCDUserDataFeedSyncScope** instances specified.</span></span>

#### <a name="parameters"></a><span data-ttu-id="c083d-129">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c083d-129">Parameters</span></span>

* <span data-ttu-id="c083d-130">`syncScopes` 배열을 **MCDSyncScope** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c083d-130">`syncScopes` An array of **MCDSyncScope** instances.</span></span>

* `callback`

<span data-ttu-id="c083d-131">콜백 결과 구독 인지 성공 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-131">The callback result indicates if subscription is successful, or not.</span></span> 

### <a name="startsync"></a><span data-ttu-id="c083d-132">startSync</span><span class="sxs-lookup"><span data-stu-id="c083d-132">startSync</span></span>
`- (void)startSync;`

<span data-ttu-id="c083d-133">연결 된 장치 플랫폼을 사용 하 여 동기화 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-133">Starts the synchronization process with the Connected Devices Platform.</span></span> <span data-ttu-id="c083d-134">이 작업을이 수행 하는 동안 합니다 **syncStatus** 속성은 업데이트 되 고 변경 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c083d-134">During this operation, the **syncStatus** property will be updated and change events will be raised.</span></span>