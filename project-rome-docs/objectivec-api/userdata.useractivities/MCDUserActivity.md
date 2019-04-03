---
title: MCDUserActivity
description: 이 클래스는 단일 사용자 활동 인스턴스를 나타냅니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: f01889f5e41c761fe359ed1fa90befee4a8aca46
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907425"
---
# <a name="class-mcduseractivity"></a><span data-ttu-id="95153-104">클래스 `MCDUserActivity`</span><span class="sxs-lookup"><span data-stu-id="95153-104">class `MCDUserActivity`</span></span>

```
@interface MCDUserActivity : NSObject
```

<span data-ttu-id="95153-105">이 클래스는 단일 사용자 활동 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95153-105">This class represents a single user activity instance.</span></span> <span data-ttu-id="95153-106">사용자 작업을 동일한 장치에 다른 시간에 또는 다른 장치에서 계속 될 수 있는 사용자 작업 스트림의 시스템에 알리기 위해 실행 하는 동안 앱에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95153-106">A user activity is created by an app during its execution to notify the system of a user work stream that can be continued on another device or at another time on the same device.</span></span> <span data-ttu-id="95153-107">사용자에 참여 하는 작업에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-107">It provides information about a task the user is engaged in.</span></span>

><span data-ttu-id="95153-108">**참고:** MCDUserActivity 인스턴스는 크기 제한이 100kb, 기준이 되는 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95153-108">**Note:** MCDUserActivity instances have a size limit of 100KB, above which they cannot be published.</span></span>

## <a name="properties"></a><span data-ttu-id="95153-109">속성</span><span class="sxs-lookup"><span data-stu-id="95153-109">Properties</span></span>

### <a name="activityid"></a><span data-ttu-id="95153-110">activityId</span><span class="sxs-lookup"><span data-stu-id="95153-110">activityId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* activityId;`

<span data-ttu-id="95153-111">이 작업에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-111">The unique ID for this activity.</span></span>

### <a name="state"></a><span data-ttu-id="95153-112">state</span><span class="sxs-lookup"><span data-stu-id="95153-112">state</span></span>
`@property(nonatomic, readonly) MCDUserActivityState state;`

<span data-ttu-id="95153-113">이 작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-113">The state of this activity.</span></span>

### <a name="activationuri"></a><span data-ttu-id="95153-114">activationUri</span><span class="sxs-lookup"><span data-stu-id="95153-114">activationUri</span></span>
`@property(nonatomic, copy, nonnull) NSString* activationUri;`

<span data-ttu-id="95153-115">이 사용자 활동이 활성화 될 때 이동할 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-115">The URI to follow when this user activity is activated.</span></span>

### <a name="fallbackuri"></a><span data-ttu-id="95153-116">fallbackUri</span><span class="sxs-lookup"><span data-stu-id="95153-116">fallbackUri</span></span>
`@property(nonatomic, copy, nullable) NSString* fallbackUri;`

<span data-ttu-id="95153-117">웹용 URI이이 작업을 소유 기본 URI에 실패 하는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-117">The web-friendly URI held by this activity, to be used if the primary URI fails.</span></span>

### <a name="contenturi"></a><span data-ttu-id="95153-118">contentUri</span><span class="sxs-lookup"><span data-stu-id="95153-118">contentUri</span></span>
`@property(nonatomic, copy, nullable) NSString* contentUri;`

<span data-ttu-id="95153-119">이 작업 (다른 장치에서 작업을 나타내는 데 사용할 이미지의 URI)에 대 한 콘텐츠 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-119">The content URI for this activity (the URI of the image that will be used to represent the activity on another device).</span></span>

### <a name="contenttype"></a><span data-ttu-id="95153-120">contentType</span><span class="sxs-lookup"><span data-stu-id="95153-120">contentType</span></span>
`@property(nonatomic, copy, nullable) NSString* contentType;`

<span data-ttu-id="95153-121">MIME (Multipurpose Internet Mail Extensions) 형식에 저장 된 콘텐츠의 **contentUri**합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-121">the MIME (Multipurpose Internet Mail Extensions) type of the content stored in **contentUri**.</span></span> <span data-ttu-id="95153-122">예를 들어, "텍스트/plain"입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-122">For example, "text/plain".</span></span>

### <a name="contentinfojson"></a><span data-ttu-id="95153-123">contentInfoJson</span><span class="sxs-lookup"><span data-stu-id="95153-123">contentInfoJson</span></span>
`@property(nonatomic, copy, nullable) NSString* contentInfoJson;`

<span data-ttu-id="95153-124">이 작업에 대 한 기본 콘텐츠 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-124">The basic content info for this activity.</span></span> <span data-ttu-id="95153-125">예를 들어, 활동이 RSS 피드를 읽고, 콘텐츠 문자열에 문서 및 해당 작성자의 이름을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95153-125">For example, if your activity was reading an RSS feed, the content string might include the name of the article and its author.</span></span>

### <a name="appdisplayname"></a><span data-ttu-id="95153-126">appDisplayName</span><span class="sxs-lookup"><span data-stu-id="95153-126">appDisplayName</span></span>
`@property(nonatomic, readonly, nullable) NSString* appDisplayName;`

<span data-ttu-id="95153-127">이 작업에 대 한 앱 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-127">The app display name for this activity.</span></span>

### <a name="visualelements"></a><span data-ttu-id="95153-128">VisualElements</span><span class="sxs-lookup"><span data-stu-id="95153-128">visualElements</span></span>
`@property(nonatomic, retain, nonnull) MCDUserActivityVisualElements* visualElements`

<span data-ttu-id="95153-129">이 활동 (활동의 "세부 정보" 타일에 대해 사용할 수 있는 정보)에 대 한 시각적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-129">The visual elements for this activity (information that can be used for the "details" tile of the activity).</span></span>

### <a name="roamable"></a><span data-ttu-id="95153-130">있는 로밍 가능한</span><span class="sxs-lookup"><span data-stu-id="95153-130">roamable</span></span>
`@property(nonatomic, assign, getter = isRoamable) BOOL roamable;`

<span data-ttu-id="95153-131">이 작업은 다른 끝점에 로밍 여부를 나타내는 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-131">Gets or sets whether this activity is roamed to other endpoints.</span></span>

## <a name="constructors"></a><span data-ttu-id="95153-132">생성자</span><span class="sxs-lookup"><span data-stu-id="95153-132">Constructors</span></span>

### <a name="activitywithactivityid"></a><span data-ttu-id="95153-133">activityWithActivityId</span><span class="sxs-lookup"><span data-stu-id="95153-133">activityWithActivityId</span></span>
`+ (nullable instancetype)activityWithActivityId:(nonnull NSString*)activityId;`

<span data-ttu-id="95153-134">지정 된 ID를 사용 하 여이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95153-134">Creates an instance of this class with a given ID.</span></span>

#### <a name="parameters"></a><span data-ttu-id="95153-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95153-135">Parameters</span></span>
* `activityId` 

<span data-ttu-id="95153-136">(고유한 문자열 이어야 함)이이 작업에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-136">The identifier for this Activity (should be a unique string).</span></span>

#### <a name="returns"></a><span data-ttu-id="95153-137">반환 값</span><span class="sxs-lookup"><span data-stu-id="95153-137">Returns</span></span>
<span data-ttu-id="95153-138">이 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-138">Returns an instance of this class.</span></span>

### <a name="initwithactivityid"></a><span data-ttu-id="95153-139">initWithActivityId</span><span class="sxs-lookup"><span data-stu-id="95153-139">initWithActivityId</span></span>
`- (nullable instancetype)initWithActivityId:(nonnull NSString*)activityId;`

<span data-ttu-id="95153-140">지정 된 ID를 사용 하 여이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95153-140">Creates an instance of this class with a given ID.</span></span>

#### <a name="parameters"></a><span data-ttu-id="95153-141">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95153-141">Parameters</span></span>
* `activityId`

<span data-ttu-id="95153-142">(고유한 문자열 이어야 함)이이 작업에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-142">The identifier for this Activity (should be a unique string).</span></span>

#### <a name="returns"></a><span data-ttu-id="95153-143">반환 값</span><span class="sxs-lookup"><span data-stu-id="95153-143">Returns</span></span>
<span data-ttu-id="95153-144">이 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-144">Returns an instance of this class.</span></span>

## <a name="methods"></a><span data-ttu-id="95153-145">메서드</span><span class="sxs-lookup"><span data-stu-id="95153-145">Methods</span></span>

### <a name="createsession"></a><span data-ttu-id="95153-146">createSession</span><span class="sxs-lookup"><span data-stu-id="95153-146">createSession</span></span>
`- (nonnull MCDUserActivitySession*)createSession;`

<span data-ttu-id="95153-147">이 MCDUserActivity와 연결 된 사용자 활동 세션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="95153-147">Creates a user activity session that this MCDUserActivity will be associated with.</span></span> <span data-ttu-id="95153-148">연결된 MCDUserActivitySession는 사용자는 현재 활동에 포함 됩니다 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95153-148">An associated MCDUserActivitySession indicates that the user is currently engaged in the activity.</span></span>

#### <a name="returns"></a><span data-ttu-id="95153-149">반환 값</span><span class="sxs-lookup"><span data-stu-id="95153-149">Returns</span></span>
<span data-ttu-id="95153-150">만든된 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-150">The created session.</span></span>

### <a name="saveasync"></a><span data-ttu-id="95153-151">saveAsync</span><span class="sxs-lookup"><span data-stu-id="95153-151">saveAsync</span></span>
`- (void)saveAsync:(nonnull void (^)(NSError* _Nullable))completionBlock;`

<span data-ttu-id="95153-152">사용자 활동을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-152">Publishes the user activity.</span></span> <span data-ttu-id="95153-153">MCDUserActivity이이 메서드가 호출 되기 전에 활성화 하는 URI 및 텍스트를 표시 하는 집합을 사용 하 여 VisualElements 멤버인 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-153">The MCDUserActivity must have an activation URI and a VisualElements member with set display text before this method is called.</span></span> <span data-ttu-id="95153-154">앱 (하기 위해 업데이트를 게시)를 MCDUserActivity의 속성을 수정 될 때마다이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-154">This method should be called whenever the app modifies a property of the MCDUserActivity (in order to publish the update).</span></span>

#### <a name="parameters"></a><span data-ttu-id="95153-155">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95153-155">Parameters</span></span>
* <span data-ttu-id="95153-156">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-156">`completionBlock` The code block to execute upon completion.</span></span>