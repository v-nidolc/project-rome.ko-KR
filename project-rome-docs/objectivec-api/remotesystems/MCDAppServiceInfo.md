---
title: MCDAppServiceInfo
description: 이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5cb01d664a07653387b523eeec68ebd50bbc2798
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801165"
---
# <a name="class-mcdappserviceinfo"></a><span data-ttu-id="baeeb-104">클래스 `MCDAppServiceInfo`</span><span class="sxs-lookup"><span data-stu-id="baeeb-104">class `MCDAppServiceInfo`</span></span> 

```
@interface MCDAppServiceInfo : NSObject<NSCopying>
```  

<span data-ttu-id="baeeb-105">이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-105">This class describes an app service that belongs to a remote device or application.</span></span>

## <a name="properties"></a><span data-ttu-id="baeeb-106">속성</span><span class="sxs-lookup"><span data-stu-id="baeeb-106">Properties</span></span>

### <a name="name"></a><span data-ttu-id="baeeb-107">NAME</span><span class="sxs-lookup"><span data-stu-id="baeeb-107">name</span></span>
`@property(nonatomic, readonly, nullable) NSString* name;`

<span data-ttu-id="baeeb-108">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-108">The name of the app service being described.</span></span>

### <a name="packageid"></a><span data-ttu-id="baeeb-109">packageId</span><span class="sxs-lookup"><span data-stu-id="baeeb-109">packageId</span></span>
`@property(nonatomic, readonly, nullable) NSString* packageId;`

<span data-ttu-id="baeeb-110">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-110">The package ID of the app service being described.</span></span>

## <a name="constructors"></a><span data-ttu-id="baeeb-111">생성자</span><span class="sxs-lookup"><span data-stu-id="baeeb-111">Constructors</span></span>

### <a name="infowithname"></a><span data-ttu-id="baeeb-112">infoWithName</span><span class="sxs-lookup"><span data-stu-id="baeeb-112">infoWithName</span></span>
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name;`

<span data-ttu-id="baeeb-113">App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-113">Initialize the class with information and name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="baeeb-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baeeb-114">Parameters</span></span> 
* `name` 

<span data-ttu-id="baeeb-115">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-115">The name of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="baeeb-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="baeeb-116">Returns</span></span>
<span data-ttu-id="baeeb-117">제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-117">Returns an MCDAppServiceInfo object containing the provided name.</span></span>

### <a name="initwithname"></a><span data-ttu-id="baeeb-118">initWithName</span><span class="sxs-lookup"><span data-stu-id="baeeb-118">initWithName</span></span>
`- (nullable instancetype)initWithName:(nonnull NSString*)name;`

<span data-ttu-id="baeeb-119">App service의 이름 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-119">Initialize the class with the name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="baeeb-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baeeb-120">Parameters</span></span> 
* `name` 

<span data-ttu-id="baeeb-121">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-121">The name of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="baeeb-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="baeeb-122">Returns</span></span>
<span data-ttu-id="baeeb-123">제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-123">Returns an MCDAppServiceInfo object initialized with the provided name.</span></span>

### <a name="infowithname"></a><span data-ttu-id="baeeb-124">infoWithName</span><span class="sxs-lookup"><span data-stu-id="baeeb-124">infoWithName</span></span>
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

<span data-ttu-id="baeeb-125">App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-125">Initialize the class with information and name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="baeeb-126">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baeeb-126">Parameters</span></span> 
* `name` 

<span data-ttu-id="baeeb-127">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-127">The name of the app service being described.</span></span>

* `packageId` 

<span data-ttu-id="baeeb-128">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-128">The package ID of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="baeeb-129">반환 값</span><span class="sxs-lookup"><span data-stu-id="baeeb-129">Returns</span></span>
<span data-ttu-id="baeeb-130">제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-130">Returns an MCDAppServiceInfo object containing the provided name.</span></span>

### <a name="initwithname"></a><span data-ttu-id="baeeb-131">initWithName</span><span class="sxs-lookup"><span data-stu-id="baeeb-131">initWithName</span></span>
`- (nullable instancetype)initWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

<span data-ttu-id="baeeb-132">App service의 이름 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-132">Initialize the class with the name of the app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="baeeb-133">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baeeb-133">Parameters</span></span> 
* `name` 

<span data-ttu-id="baeeb-134">설명 하 고 app service의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-134">The name of the app service being described.</span></span>

* `packageId` 

<span data-ttu-id="baeeb-135">설명 하 고 app service의 패키지 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-135">The package ID of the app service being described.</span></span>

#### <a name="returns"></a><span data-ttu-id="baeeb-136">반환 값</span><span class="sxs-lookup"><span data-stu-id="baeeb-136">Returns</span></span>
<span data-ttu-id="baeeb-137">제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="baeeb-137">Returns an MCDAppServiceInfo object initialized with the provided name.</span></span>
