---
title: MCDUserActivityChannel
description: 이 클래스에 추가 하 고 응용 프로그램에 대 한 사용자 활동의 쿼리 처리 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b047af1da3ba79be88a53cf589c3894892b01ef4
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907805"
---
# <a name="class-mcduseractivitychannel"></a><span data-ttu-id="0c1ae-104">클래스 `MCDUserActivityChannel`</span><span class="sxs-lookup"><span data-stu-id="0c1ae-104">class `MCDUserActivityChannel`</span></span>

```
@interface MCDUserActivityChannel : NSObject
```

<span data-ttu-id="0c1ae-105">이 클래스에 추가 하 고 응용 프로그램에 대 한 사용자 활동의 쿼리 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-105">This class handles the adding and querying of user activities for the application.</span></span>

## <a name="properties"></a><span data-ttu-id="0c1ae-106">속성</span><span class="sxs-lookup"><span data-stu-id="0c1ae-106">Properties</span></span>

### <a name="syncscope"></a><span data-ttu-id="0c1ae-107">syncScope</span><span class="sxs-lookup"><span data-stu-id="0c1ae-107">syncScope</span></span>
`@property(class, readonly, nonnull) MCDUserDataFeedSyncScope* syncScope;`

<span data-ttu-id="0c1ae-108">사용자 활동에 대 한 사용자 데이터 동기화 범위 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-108">Gets the user data sync scope value for User Activities.</span></span>

### <a name="appdisplayname"></a><span data-ttu-id="0c1ae-109">appDisplayName</span><span class="sxs-lookup"><span data-stu-id="0c1ae-109">appDisplayName</span></span>
`@property(nonatomic, copy, nullable) NSString* appDisplayName;`

<span data-ttu-id="0c1ae-110">모든 활동에 대 한 앱의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-110">The display name of the app for all activities.</span></span>

## <a name="constructors"></a><span data-ttu-id="0c1ae-111">생성자</span><span class="sxs-lookup"><span data-stu-id="0c1ae-111">Constructors</span></span>

### <a name="channelwithuserdatafeed"></a><span data-ttu-id="0c1ae-112">channelWithUserDataFeed</span><span class="sxs-lookup"><span data-stu-id="0c1ae-112">channelWithUserDataFeed</span></span>
`+ (nullable instancetype)channelWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

<span data-ttu-id="0c1ae-113">사용자 데이터 피드를 사용 하 여이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-113">Creates an instance of this class with the user data feed.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-114">Parameters</span></span>
* <span data-ttu-id="0c1ae-115">`userDataFeed` 이 채널에서 작업과 관련 된 사용자 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-115">`userDataFeed` The user data associated with the activities on this channel.</span></span>

#### <a name="returns"></a><span data-ttu-id="0c1ae-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="0c1ae-116">Returns</span></span>
<span data-ttu-id="0c1ae-117">이 클래스의 새 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-117">Returns a new instance of this class.</span></span>

## <a name="methods"></a><span data-ttu-id="0c1ae-118">메서드</span><span class="sxs-lookup"><span data-stu-id="0c1ae-118">Methods</span></span>

### <a name="getorcreateuseractivityasync"></a><span data-ttu-id="0c1ae-119">getOrCreateUserActivityAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-119">getOrCreateUserActivityAsync</span></span>
`- (void)getOrCreateUserActivityAsync:(nonnull NSString*)activityId
                          completion:(nonnull void (^)(MCDUserActivity* _Nonnull, NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-120">지정 된 사용자 활동을 만들거나 이미 있는 경우에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-120">Creates the specified user activity, or gets a reference to it if it already exists.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-121">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-121">Parameters</span></span>
* <span data-ttu-id="0c1ae-122">`activityId` 이 작업의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-122">`activityId` The ID for this activity.</span></span>
* <span data-ttu-id="0c1ae-123">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-123">`completionBlock` The code block to execute upon completion.</span></span> <span data-ttu-id="0c1ae-124">이 검색된 작업에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-124">This provides access to the retrieved activity.</span></span>

### <a name="deleteactivityasync"></a><span data-ttu-id="0c1ae-125">deleteActivityAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-125">deleteActivityAsync</span></span>
`- (void)deleteActivityAsync:(nonnull NSString*)activityId completion:(nonnull void (^)(NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-126">지정 된 사용자 활동을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-126">Deletes the given user activity.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-127">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-127">Parameters</span></span>
* <span data-ttu-id="0c1ae-128">`activityId` 삭제 작업의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-128">`activityId` The ID of the activity to delete.</span></span>
* <span data-ttu-id="0c1ae-129">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-129">`completionBlock` The code block to execute upon completion.</span></span>

### <a name="deleteallactivitiesasync"></a><span data-ttu-id="0c1ae-130">deleteAllActivitiesAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-130">deleteAllActivitiesAsync</span></span>
`- (void)deleteAllActivitiesAsync:(nonnull void (^)(NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-131">모든 사용자 활동을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-131">Deletes all user activities.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-132">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-132">Parameters</span></span>
* <span data-ttu-id="0c1ae-133">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-133">`completionBlock` The code block to execute upon completion.</span></span>

### <a name="getrecentuseractivitiesasync"></a><span data-ttu-id="0c1ae-134">getRecentUserActivitiesAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-134">getRecentUserActivitiesAsync</span></span>
`- (void)getRecentUserActivitiesAsync:(NSInteger)maxUniqueActivities
                          completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull, NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-135">최근 사용자 활동의 기록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-135">Gets a history of recent user activities.</span></span> 

#### <a name="parameters"></a><span data-ttu-id="0c1ae-136">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-136">Parameters</span></span>
* <span data-ttu-id="0c1ae-137">`maxUniqueActivities` 검색할 사용자 작업의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-137">`maxUniqueActivities` The maximum number of user activities to retrieve.</span></span>
* <span data-ttu-id="0c1ae-138">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-138">`completionBlock` The code block to execute upon completion.</span></span> <span data-ttu-id="0c1ae-139">작업 기록에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-139">This provides access to the activity history.</span></span>

### <a name="getsessionhistoryitemsforuseractivityasync"></a><span data-ttu-id="0c1ae-140">getSessionHistoryItemsForUserActivityAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-140">getSessionHistoryItemsForUserActivityAsync</span></span>
`- (void)getSessionHistoryItemsForUserActivityAsync:(nonnull NSString*)activityId
                                     withStartTime:(nonnull NSDate*)startTime
                                        completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull, NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-141">지정된 된 활동에 대 한 세션 기록 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-141">Gets the session history entries for a given activity.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-142">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-142">Parameters</span></span>
* <span data-ttu-id="0c1ae-143">`activityId` 에 대 한 기록 가져오기 작업의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-143">`activityId` The ID of the activity to get history for.</span></span>
* <span data-ttu-id="0c1ae-144">`startTime` 세션 기록을 고려 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-144">`startTime` The time at which to consider session history.</span></span>
* <span data-ttu-id="0c1ae-145">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-145">`completionBlock` The code block to execute upon completion.</span></span> <span data-ttu-id="0c1ae-146">작업 기록에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-146">This provides access to the activity history.</span></span>

### <a name="getrecentsessionhistoryitemsfortimerangeasync"></a><span data-ttu-id="0c1ae-147">getRecentSessionHistoryItemsForTimeRangeAsync</span><span class="sxs-lookup"><span data-stu-id="0c1ae-147">getRecentSessionHistoryItemsForTimeRangeAsync</span></span>
`- (void)getRecentSessionHistoryItemsForTimeRangeAsync:(nonnull NSDate*)startTime
                                 endTime:(nonnull NSDate*)endTime
                                 maxActivities:(NSInteger)maxActivities
                                 completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull,
                                                       NSError* _Nullable))completionBlock;`

<span data-ttu-id="0c1ae-148">지정된 된 활동에 대 한 세션 기록 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-148">Gets the session history entries for a given activity.</span></span>

#### <a name="parameters"></a><span data-ttu-id="0c1ae-149">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c1ae-149">Parameters</span></span>
* <span data-ttu-id="0c1ae-150">`startTime` 세션 기록을 고려 시작 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-150">`startTime` The time at which to start considering session history.</span></span>
* <span data-ttu-id="0c1ae-151">`endTime` 세션 기록 고려 종료 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-151">`endTime` The time at which to end considering session history.</span></span>
* <span data-ttu-id="0c1ae-152">`maxActivities` 검색할 사용자 작업의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-152">`maxActivities` The maximum number of user activities to retrieve.</span></span>
* <span data-ttu-id="0c1ae-153">`completion` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-153">`completion` The code block to execute upon completion.</span></span>
* <span data-ttu-id="0c1ae-154">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-154">`completionBlock` The code block to execute upon completion.</span></span> <span data-ttu-id="0c1ae-155">작업 기록에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c1ae-155">This provides access to the activity history.</span></span>