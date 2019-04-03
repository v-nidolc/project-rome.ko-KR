---
title: MCDAppServiceInfo
description: 이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5cb01d664a07653387b523eeec68ebd50bbc2798
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907115"
---
# <a name="class-mcdappserviceinfo"></a><span data-ttu-id="3ef66-104">클래스 `MCDAppServiceInfo`</span><span class="sxs-lookup"><span data-stu-id="3ef66-104">class `MCDAppServiceInfo`</span></span> 

```
@interface MCDAppServiceInfo : NSObject<NSCopying>
```  

<span data-ttu-id="3ef66-105">이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-105">This class describes an app service that belongs to a remote device or application.</span></span>

## <a name="properties"></a><span data-ttu-id="3ef66-106">속성</span><span class="sxs-lookup"><span data-stu-id="3ef66-106">Properties</span></span>

### <a name="name"></a><span data-ttu-id="3ef66-107">NAME</span><span class="sxs-lookup"><span data-stu-id="3ef66-107">name</span></span>
`@property(nonatomic, readonly, nullable) NSString* name;`

<span data-ttu-id="3ef66-108">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-108">The name of the app service being described.</span></span>

### <a name="packageid"></a><span data-ttu-id="3ef66-109">packageId</span><span class="sxs-lookup"><span data-stu-id="3ef66-109">packageId</span></span>
`@property(nonatomic, readonly, nullable) NSString* packageId;`

<span data-ttu-id="3ef66-110">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-110">The package ID of the app service being described.</span></span>

## <a name="constructors"></a><span data-ttu-id="3ef66-111">생성자</span><span class="sxs-lookup"><span data-stu-id="3ef66-111">Constructors</span></span>

### <a name="infowithname"></a><span data-ttu-id="3ef66-112">infoWithName</span><span class="sxs-lookup"><span data-stu-id="3ef66-112">infoWithName</span></span>
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name;`

<span data-ttu-id="3ef66-113">App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-113">Initialize the class with information and name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="3ef66-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ef66-114">Parameters</span></span> 
* `name` 

<span data-ttu-id="3ef66-115">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-115">The name of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="3ef66-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="3ef66-116">Returns</span></span>
<span data-ttu-id="3ef66-117">제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-117">Returns an MCDAppServiceInfo object containing the provided name.</span></span>

### <a name="initwithname"></a><span data-ttu-id="3ef66-118">initWithName</span><span class="sxs-lookup"><span data-stu-id="3ef66-118">initWithName</span></span>
`- (nullable instancetype)initWithName:(nonnull NSString*)name;`

<span data-ttu-id="3ef66-119">App service의 이름 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-119">Initialize the class with the name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="3ef66-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ef66-120">Parameters</span></span> 
* `name` 

<span data-ttu-id="3ef66-121">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-121">The name of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="3ef66-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="3ef66-122">Returns</span></span>
<span data-ttu-id="3ef66-123">제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-123">Returns an MCDAppServiceInfo object initialized with the provided name.</span></span>

### <a name="infowithname"></a><span data-ttu-id="3ef66-124">infoWithName</span><span class="sxs-lookup"><span data-stu-id="3ef66-124">infoWithName</span></span>
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

<span data-ttu-id="3ef66-125">App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-125">Initialize the class with information and name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="3ef66-126">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ef66-126">Parameters</span></span> 
* `name` 

<span data-ttu-id="3ef66-127">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-127">The name of the app service being described.</span></span>

* `packageId` 

<span data-ttu-id="3ef66-128">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-128">The package ID of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="3ef66-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="3ef66-129">Returns</span></span>
<span data-ttu-id="3ef66-130">제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-130">Returns an MCDAppServiceInfo object containing the provided name.</span></span>

### <a name="initwithname"></a><span data-ttu-id="3ef66-131">initWithName</span><span class="sxs-lookup"><span data-stu-id="3ef66-131">initWithName</span></span>
`- (nullable instancetype)initWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

<span data-ttu-id="3ef66-132">App service의 이름 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-132">Initialize the class with the name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="3ef66-133">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3ef66-133">Parameters</span></span> 
* `name` 

<span data-ttu-id="3ef66-134">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-134">The name of the app service being described.</span></span>

* `packageId` 

<span data-ttu-id="3ef66-135">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-135">The package ID of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="3ef66-136">반환 값</span><span class="sxs-lookup"><span data-stu-id="3ef66-136">Returns</span></span>
<span data-ttu-id="3ef66-137">제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ef66-137">Returns an MCDAppServiceInfo object initialized with the provided name.</span></span>
