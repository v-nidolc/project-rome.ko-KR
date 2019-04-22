---
title: MCDRemoteSystemStatusTypeFilter
description: 원격 시스템 가용성 상태 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 201570c16a8eb9cf1a31e450b3408c8ab255fe1a
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907125"
---
# <a name="class-mcdremotesystemstatustypefilter"></a><span data-ttu-id="352d5-104">클래스 `MCDRemoteSystemStatusTypeFilter`</span><span class="sxs-lookup"><span data-stu-id="352d5-104">class `MCDRemoteSystemStatusTypeFilter`</span></span>

```
@interface MCDRemoteSystemStatusTypeFilter : NSObject <MCDRemoteSystemFilter>
```

<span data-ttu-id="352d5-105">원격 시스템 가용성 상태 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-105">A class used to filter remote systems based on availability status type.</span></span>

## <a name="properties"></a><span data-ttu-id="352d5-106">속성</span><span class="sxs-lookup"><span data-stu-id="352d5-106">Properties</span></span>

### <a name="type"></a><span data-ttu-id="352d5-107">유형</span><span class="sxs-lookup"><span data-stu-id="352d5-107">type</span></span>
<span data-ttu-id="352d5-108">`@property(nonatomic, readonly) MCDRemoteSystemStatusType type;` 이 필터 인스턴스의 원격 시스템 상태 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-108">`@property(nonatomic, readonly) MCDRemoteSystemStatusType type;` The remote system status type of this filter instance.</span></span>

## <a name="constructors"></a><span data-ttu-id="352d5-109">생성자</span><span class="sxs-lookup"><span data-stu-id="352d5-109">Constructors</span></span>

### <a name="filterwithtype"></a><span data-ttu-id="352d5-110">filterWithType</span><span class="sxs-lookup"><span data-stu-id="352d5-110">filterWithType</span></span>
`+ (nullable instancetype)filterWithType:(MCDRemoteSystemStatusType)statusType;`

#### <a name="parameters"></a><span data-ttu-id="352d5-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="352d5-111">Parameters</span></span> 
* <span data-ttu-id="352d5-112">`statusType` 가용성 상태 형식에 대 한 필터를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-112">`statusType` A value indicating the availability status type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="352d5-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="352d5-113">Returns</span></span>
<span data-ttu-id="352d5-114">유형별로 필터링 MCDRemoteSystemStatusTypeFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-114">Returns an MCDRemoteSystemStatusTypeFilter object filtered by type.</span></span>

### <a name="initwithtype"></a><span data-ttu-id="352d5-115">initWithType</span><span class="sxs-lookup"><span data-stu-id="352d5-115">initWithType</span></span>
`- (nullable instancetype)initWithType:(MCDRemoteSystemStatusType)statusType;`

#### <a name="parameters"></a><span data-ttu-id="352d5-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="352d5-116">Parameters</span></span> 
* `statusType` 

<span data-ttu-id="352d5-117">가용성 상태 형식에 대 한 필터를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-117">A value indicating the availability status type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="352d5-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="352d5-118">Returns</span></span>
<span data-ttu-id="352d5-119">형식을 사용 하 여 초기화 하는 MCDRemoteSystemStatusTypeFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="352d5-119">Returns an MCDRemoteSystemStatusTypeFilter object initialized with the type.</span></span>