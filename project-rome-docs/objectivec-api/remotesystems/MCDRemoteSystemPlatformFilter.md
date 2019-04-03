---
title: MCDRemoteSystemPlatformFilter
description: 실행 중인 OS 플랫폼을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 1b82d7b3a1626489a83196bf949567b3ce7b94f0
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908755"
---
# <a name="class-mcdremotesystemplatformfilter"></a><span data-ttu-id="f923a-104">클래스 `MCDRemoteSystemPlatformFilter`</span><span class="sxs-lookup"><span data-stu-id="f923a-104">class `MCDRemoteSystemPlatformFilter`</span></span> 

```
@interface MCDRemoteSystemPlatformFilter : NSObject<MCDRemoteSystemFilter> 
```  

<span data-ttu-id="f923a-105">실행 중인 OS 플랫폼을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-105">A class used to filter remote systems based on the OS platform they are running.</span></span>

## <a name="properties"></a><span data-ttu-id="f923a-106">속성</span><span class="sxs-lookup"><span data-stu-id="f923a-106">Properties</span></span>

### <a name="platform"></a><span data-ttu-id="f923a-107">플랫폼</span><span class="sxs-lookup"><span data-stu-id="f923a-107">platform</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemPlatform platform;`

<span data-ttu-id="f923a-108">플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-108">A MCDRemoteSystemPlatform value indicating the platform to filter for.</span></span>

## <a name="constructors"></a><span data-ttu-id="f923a-109">생성자</span><span class="sxs-lookup"><span data-stu-id="f923a-109">Constructors</span></span>

### <a name="filterwithplatform"></a><span data-ttu-id="f923a-110">filterWithPlatform</span><span class="sxs-lookup"><span data-stu-id="f923a-110">filterWithPlatform</span></span>
`+ (nullable instancetype)filterWithPlatform:(MCDRemoteSystemPlatform)platform;`

#### <a name="parameters"></a><span data-ttu-id="f923a-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f923a-111">Parameters</span></span> 
* `platform` 

<span data-ttu-id="f923a-112">플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-112">A MCDRemoteSystemPlatform value indicating the platform to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="f923a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="f923a-113">Returns</span></span>
<span data-ttu-id="f923a-114">플랫폼별으로 필터링 MCDRemoteSystemPlatformFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-114">Returns an MCDRemoteSystemPlatformFilter object filtered by platform.</span></span>

### <a name="initwithplatform"></a><span data-ttu-id="f923a-115">initWithPlatform</span><span class="sxs-lookup"><span data-stu-id="f923a-115">initWithPlatform</span></span>
`- (nullable instancetype)initWithPlatform:(MCDRemoteSystemPlatform)platform;`

#### <a name="parameters"></a><span data-ttu-id="f923a-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f923a-116">Parameters</span></span> 
* `platform` 

<span data-ttu-id="f923a-117">플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-117">A MCDRemoteSystemPlatform value indicating the platform to filter for.</span></span>

#### <a name="returns"></a><span data-ttu-id="f923a-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="f923a-118">Returns</span></span>
<span data-ttu-id="f923a-119">필터를 사용 하 여 플랫폼별 초기화 MCDRemoteSystemPlatformFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f923a-119">Returns an MCDRemoteSystemPlatformFilter object initialized with a filter by platform.</span></span>