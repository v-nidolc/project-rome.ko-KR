---
title: MCDRemoteSystemAuthorizationKindFilter
description: 권한 부여 유형을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: da68c7a0eacd2018332d5e2fe5c8e3c906f473f8
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801255"
---
# <a name="class-mcdremotesystemauthorizationkindfilter"></a><span data-ttu-id="9fd8a-104">클래스 `MCDRemoteSystemAuthorizationKindFilter`</span><span class="sxs-lookup"><span data-stu-id="9fd8a-104">class `MCDRemoteSystemAuthorizationKindFilter`</span></span> 

```
@interface MCDRemoteSystemAuthorizationKindFilter : NSObject<MCDRemoteSystemFilter>
```  

<span data-ttu-id="9fd8a-105">권한 부여 유형을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-105">A class used to filter remote systems based on authorization type.</span></span>

## <a name="properties"></a><span data-ttu-id="9fd8a-106">속성</span><span class="sxs-lookup"><span data-stu-id="9fd8a-106">Properties</span></span>

### <a name="kind"></a><span data-ttu-id="9fd8a-107">kind</span><span class="sxs-lookup"><span data-stu-id="9fd8a-107">kind</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemAuthorizationKind kind;`

<span data-ttu-id="9fd8a-108">권한 부여 형식에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-108">The authorization type to filter for.</span></span>

## <a name="constructors"></a><span data-ttu-id="9fd8a-109">생성자</span><span class="sxs-lookup"><span data-stu-id="9fd8a-109">Constructors</span></span>

### <a name="filterwithkind"></a><span data-ttu-id="9fd8a-110">filterWithKind</span><span class="sxs-lookup"><span data-stu-id="9fd8a-110">filterWithKind</span></span>
`+ (nullable instancetype)filterWithKind:(MCDRemoteSystemAuthorizationKind)authorizationKind;`

<span data-ttu-id="9fd8a-111">MCDRemoteSystemAuthorizationKind 필터링이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-111">A new instance of this class filtered on MCDRemoteSystemAuthorizationKind.</span></span>

#### <a name="parameters"></a><span data-ttu-id="9fd8a-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fd8a-112">Parameters</span></span> 
* `authorizationKind` 

<span data-ttu-id="9fd8a-113">권한 부여 형식에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-113">The authorization type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="9fd8a-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="9fd8a-114">Returns</span></span>
<span data-ttu-id="9fd8a-115">제공 된 권한 부여 필터를 사용 하 여 MCDRemoteSystemAuthorizationKindFilter 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-115">Returns an MCDRemoteSystemAuthorizationKindFilter object with the provided authorization filter.</span></span>

### <a name="initwithkind"></a><span data-ttu-id="9fd8a-116">initWithKind</span><span class="sxs-lookup"><span data-stu-id="9fd8a-116">initWithKind</span></span>
`- (nullable instancetype)initWithKind:(MCDRemoteSystemAuthorizationKind)authorizationKind;`

<span data-ttu-id="9fd8a-117">MCDRemoteSystemAuthorizationKind 사용 하 여이 클래스의 새 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-117">A new instance of this class with MCDRemoteSystemAuthorizationKind.</span></span>

#### <a name="parameters"></a><span data-ttu-id="9fd8a-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9fd8a-118">Parameters</span></span> 
* `authorizationKind` 

<span data-ttu-id="9fd8a-119">권한 부여 형식에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-119">The authorization type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="9fd8a-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="9fd8a-120">Returns</span></span>
<span data-ttu-id="9fd8a-121">authorizationKind를 사용 하 여 초기화 MCDRemoteSystemAuthorizationKindFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd8a-121">Returns an MCDRemoteSystemAuthorizationKindFilter object initialized with the authorizationKind.</span></span>