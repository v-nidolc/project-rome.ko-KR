---
title: MCDRemoteSystemDiscoveryTypeFilter
description: 원격 시스템 검색 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 8054d378f203d5cde29af6b4452cc03e15e24828
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907525"
---
# <a name="class-mcdremotesystemdiscoverytypefilter"></a><span data-ttu-id="89f28-104">클래스 `MCDRemoteSystemDiscoveryTypeFilter`</span><span class="sxs-lookup"><span data-stu-id="89f28-104">class `MCDRemoteSystemDiscoveryTypeFilter`</span></span> 

```
@interface MCDRemoteSystemDiscoveryTypeFilter : NSObject<MCDRemoteSystemFilter>
```  

<span data-ttu-id="89f28-105">원격 시스템 검색 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-105">A class used to filter remote systems based upon discovery type.</span></span>

## <a name="properties"></a><span data-ttu-id="89f28-106">속성</span><span class="sxs-lookup"><span data-stu-id="89f28-106">Properties</span></span>

### <a name="type"></a><span data-ttu-id="89f28-107">유형</span><span class="sxs-lookup"><span data-stu-id="89f28-107">type</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemDiscoveryType type;`

<span data-ttu-id="89f28-108">필터링 할 검색 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-108">The discovery type to filter for.</span></span>

> <span data-ttu-id="89f28-109">참고: Android에서 연결 된 장치 플랫폼에만 사용할 수 Bluetooth Android 8.0 oreo (용)를 실행 하는 시스템 이상.</span><span class="sxs-lookup"><span data-stu-id="89f28-109">Note: On Android, the Connected Devices Platform can only use Bluetooth on systems running Android 8.0 (Oreo) or later.</span></span>

## <a name="constructors"></a><span data-ttu-id="89f28-110">생성자</span><span class="sxs-lookup"><span data-stu-id="89f28-110">Constructors</span></span>

### <a name="filterwithtype"></a><span data-ttu-id="89f28-111">filterWithType</span><span class="sxs-lookup"><span data-stu-id="89f28-111">filterWithType</span></span>
`+ (nullable instancetype)filterWithType:(MCDRemoteSystemDiscoveryType)discoveryType;`

#### <a name="parameters"></a><span data-ttu-id="89f28-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89f28-112">Parameters</span></span> 
* <span data-ttu-id="89f28-113">`discoveryType` 필터링 할 검색 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-113">`discoveryType` The discovery type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="89f28-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="89f28-114">Returns</span></span>
<span data-ttu-id="89f28-115">지정 된 형식 값을 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="89f28-115">A new instance of this class with the given type value.</span></span> <span data-ttu-id="89f28-116">값은 한 번에 여러 필터를 적용 하려면 함께 and 연산 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-116">Values can be AND'ed together to apply multiple filters at once.</span></span>

### <a name="initwithtype"></a><span data-ttu-id="89f28-117">initWithType</span><span class="sxs-lookup"><span data-stu-id="89f28-117">initWithType</span></span>
`- (nullable instancetype)initWithType:(MCDRemoteSystemDiscoveryType)discoveryType;`

#### <a name="parameters"></a><span data-ttu-id="89f28-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89f28-118">Parameters</span></span> 
* <span data-ttu-id="89f28-119">`discoveryType` 필터링 할 검색 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-119">`discoveryType` The discovery type to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="89f28-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="89f28-120">Returns</span></span>
<span data-ttu-id="89f28-121">지정 된 형식 값을 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="89f28-121">A new instance of this class with the given type value.</span></span> <span data-ttu-id="89f28-122">값은 한 번에 여러 필터를 적용 하려면 함께 and 연산 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89f28-122">Values can be AND'ed together to apply multiple filters at once.</span></span>