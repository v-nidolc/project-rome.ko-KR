---
title: MCDRemoteSystemKindFilter
description: 원격 시스템 장치 종류에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 162e8f881b532fae50f6d301149b50c5ddf344b5
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801335"
---
# <a name="class-mcdremotesystemkindfilter"></a><span data-ttu-id="da0a4-104">클래스 `MCDRemoteSystemKindFilter`</span><span class="sxs-lookup"><span data-stu-id="da0a4-104">class `MCDRemoteSystemKindFilter`</span></span> 

```
@interface MCDRemoteSystemKindFilter : NSObject <MCDRemoteSystemFilter>
```  

<span data-ttu-id="da0a4-105">원격 시스템 장치 종류에 따라 필터링 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-105">A class used to filter remote systems based upon device kind.</span></span>

## <a name="properties"></a><span data-ttu-id="da0a4-106">속성</span><span class="sxs-lookup"><span data-stu-id="da0a4-106">Properties</span></span>

### <a name="kinds"></a><span data-ttu-id="da0a4-107">종류</span><span class="sxs-lookup"><span data-stu-id="da0a4-107">kinds</span></span>
`@property(nonatomic, readonly, copy, nonnull) NSArray<NSString*>* kinds;`

<span data-ttu-id="da0a4-108">배열에 대해 필터링 할 장치의 종류를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-108">An array of strings indicating the kinds of device to filter for.</span></span>

## <a name="constructors"></a><span data-ttu-id="da0a4-109">생성자</span><span class="sxs-lookup"><span data-stu-id="da0a4-109">Constructors</span></span>

### <a name="filterwithkinds"></a><span data-ttu-id="da0a4-110">filterWithKinds</span><span class="sxs-lookup"><span data-stu-id="da0a4-110">filterWithKinds</span></span>
`+ (nullable instancetype)filterWithKinds:(nonnull NSArray<NSString*>*)kinds;`

<span data-ttu-id="da0a4-111">종류의 필터링이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="da0a4-111">A new instance of this class filtered on kinds.</span></span>

#### <a name="parameters"></a><span data-ttu-id="da0a4-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da0a4-112">Parameters</span></span> 
* `kinds`

 <span data-ttu-id="da0a4-113">배열에 대해 필터링 할 장치 종류를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-113">An array of strings indicating the device kinds to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="da0a4-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="da0a4-114">Returns</span></span>
<span data-ttu-id="da0a4-115">종류를 사용 하 여 필터링 MCDRemoteSystemKindFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-115">Returns an MCDRemoteSystemKindFilter object filtered with kinds.</span></span>

### <a name="initwithkinds"></a><span data-ttu-id="da0a4-116">initWithKinds</span><span class="sxs-lookup"><span data-stu-id="da0a4-116">initWithKinds</span></span>
`- (nullable instancetype)initWithKinds:(nonnull NSArray<NSString*>*)kinds;`

<span data-ttu-id="da0a4-117">종류의 필터링이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="da0a4-117">A new instance of this class filtered on kinds.</span></span>

#### <a name="parameters"></a><span data-ttu-id="da0a4-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da0a4-118">Parameters</span></span> 
* `kinds` 

<span data-ttu-id="da0a4-119">배열에 대해 필터링 할 장치 종류를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-119">An array of strings indicating the device kinds to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="da0a4-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="da0a4-120">Returns</span></span>
<span data-ttu-id="da0a4-121">종류를 사용 하 여 초기화 MCDRemoteSystemKindFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da0a4-121">Returns an MCDRemoteSystemKindFilter object initialized with kinds.</span></span>