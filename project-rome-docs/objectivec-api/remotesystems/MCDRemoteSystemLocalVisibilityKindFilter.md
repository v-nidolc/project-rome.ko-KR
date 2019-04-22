---
title: MCDRemoteSystemLocalVisibilityKindFilter
description: 원격 시스템을 검색 하는 경우 로컬 (호출) 응용 프로그램 표시 기본 설정을 설정 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b54614c1ee0a820e605df05768c164d07a5a9464
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800675"
---
# <a name="class-mcdremotesystemlocalvisibilitykindfilter"></a><span data-ttu-id="ebe2d-104">클래스 `MCDRemoteSystemLocalVisibilityKindFilter`</span><span class="sxs-lookup"><span data-stu-id="ebe2d-104">class `MCDRemoteSystemLocalVisibilityKindFilter`</span></span> 

```
@interface MCDRemoteSystemLocalVisibilityKindFilter : NSObject <MCDRemoteSystemFilter>
```  

<span data-ttu-id="ebe2d-105">원격 시스템을 검색 하는 경우 로컬 (호출) 응용 프로그램 표시 기본 설정을 설정 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-105">A class used to set the local (calling) application visibility preference when discovering remote systems.</span></span>

## <a name="properties"></a><span data-ttu-id="ebe2d-106">속성</span><span class="sxs-lookup"><span data-stu-id="ebe2d-106">Properties</span></span>

### <a name="kind"></a><span data-ttu-id="ebe2d-107">kind</span><span class="sxs-lookup"><span data-stu-id="ebe2d-107">kind</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemLocalVisibilityKind kind;`

<span data-ttu-id="ebe2d-108">사용 하 여 필터링에 표시 유형 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-108">The visibility setting to filter with.</span></span>

## <a name="constructors"></a><span data-ttu-id="ebe2d-109">생성자</span><span class="sxs-lookup"><span data-stu-id="ebe2d-109">Constructors</span></span>

### <a name="filterwithkind"></a><span data-ttu-id="ebe2d-110">filterWithKind</span><span class="sxs-lookup"><span data-stu-id="ebe2d-110">filterWithKind</span></span>
`+ (nullable instancetype)filterWithKind:(MCDRemoteSystemLocalVisibilityKind)localVisibilityKind;`

<span data-ttu-id="ebe2d-111">페이지를 만들고이 클래스의 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-111">Creates and initializes an instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ebe2d-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebe2d-112">Parameters</span></span>
* `localVisibilityKind` 

<span data-ttu-id="ebe2d-113">사용 하 여 필터링 하는 로컬 앱 표시 설정을 나타내는 MCDRemoteSystemLocalVisibilityKind 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-113">An MCDRemoteSystemLocalVisibilityKind value indicating the local app visibility setting to filter with.</span></span>

#### <a name="returns"></a><span data-ttu-id="ebe2d-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="ebe2d-114">Returns</span></span>
<span data-ttu-id="ebe2d-115">종류별로 필터링 MCDRemoteSystemLocalVisibilityKind 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-115">Returns an MCDRemoteSystemLocalVisibilityKind object filtered by kind.</span></span>

### <a name="initwithkind"></a><span data-ttu-id="ebe2d-116">initWithKind</span><span class="sxs-lookup"><span data-stu-id="ebe2d-116">initWithKind</span></span>
`- (nullable instancetype)initWithKind:(MCDRemoteSystemLocalVisibilityKind)localVisibilityKind;`

<span data-ttu-id="ebe2d-117">페이지를 만들고이 클래스의 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-117">Creates and initializes an instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ebe2d-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebe2d-118">Parameters</span></span>
* `localVisibilityKind` 

<span data-ttu-id="ebe2d-119">사용 하 여 필터링 하는 로컬 앱 표시 설정을 나타내는 MCDRemoteSystemLocalVisibilityKind 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-119">An MCDRemoteSystemLocalVisibilityKind value indicating the local app visibility setting to filter with.</span></span>

#### <a name="returns"></a><span data-ttu-id="ebe2d-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="ebe2d-120">Returns</span></span>
<span data-ttu-id="ebe2d-121">종류를 사용 하 여 초기화 MCDRemoteSystemLocalVisibilityKind 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-121">Returns an MCDRemoteSystemLocalVisibilityKind object initialized with kind.</span></span>