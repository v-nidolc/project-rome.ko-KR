---
title: MCDRemoteSystemDiscoveryType
description: 포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: dc94b92311cb666fd2ffd3949b3d4d66a49e6e5b
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907035"
---
# <a name="enum-mcdremotesystemdiscoverytype"></a><span data-ttu-id="736e6-104">열거형 `MCDRemoteSystemDiscoveryType`</span><span class="sxs-lookup"><span data-stu-id="736e6-104">enum `MCDRemoteSystemDiscoveryType`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemDiscoveryType)
```  

<span data-ttu-id="736e6-105">포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736e6-105">Contains values that describe how remote systems are able to be discovered.</span></span> 

## <a name="fields"></a><span data-ttu-id="736e6-106">필드</span><span class="sxs-lookup"><span data-stu-id="736e6-106">Fields</span></span>

| <span data-ttu-id="736e6-107">이름</span><span class="sxs-lookup"><span data-stu-id="736e6-107">Name</span></span>                              | <span data-ttu-id="736e6-108">값</span><span class="sxs-lookup"><span data-stu-id="736e6-108">Value</span></span> | <span data-ttu-id="736e6-109">설명</span><span class="sxs-lookup"><span data-stu-id="736e6-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="736e6-110">MCDRemoteSystemDiscoveryTypeAny</span><span class="sxs-lookup"><span data-stu-id="736e6-110">MCDRemoteSystemDiscoveryTypeAny</span></span>   | <span data-ttu-id="736e6-111">0</span><span class="sxs-lookup"><span data-stu-id="736e6-111">0</span></span>     | <span data-ttu-id="736e6-112">원격 시스템 모든 연결을 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736e6-112">Remote systems are discoverable through any connection.</span></span>  |
| <span data-ttu-id="736e6-113">MCDRemoteSystemDiscoveryTypeProximal</span><span class="sxs-lookup"><span data-stu-id="736e6-113">MCDRemoteSystemDiscoveryTypeProximal</span></span> | <span data-ttu-id="736e6-114">1</span><span class="sxs-lookup"><span data-stu-id="736e6-114">1</span></span>     | <span data-ttu-id="736e6-115">원격 시스템은 로컬 같은 proximal 연결을 통해 검색할 수만</span><span class="sxs-lookup"><span data-stu-id="736e6-115">Remote systems are only discoverable through a proximal connection, such as a local</span></span>
<span data-ttu-id="736e6-116">네트워크 또는 Bluetooth 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="736e6-116">network or Bluetooth connection.</span></span> |
| <span data-ttu-id="736e6-117">MCDRemoteSystemDiscoveryTypeCloud</span><span class="sxs-lookup"><span data-stu-id="736e6-117">MCDRemoteSystemDiscoveryTypeCloud</span></span> | <span data-ttu-id="736e6-118">2</span><span class="sxs-lookup"><span data-stu-id="736e6-118">2</span></span>     | <span data-ttu-id="736e6-119">원격 시스템은 클라우드 연결을 통해 검색할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736e6-119">Remote systems are only discoverable through cloud connection.</span></span> |
| <span data-ttu-id="736e6-120">MCDRemoteSystemDiscoveryTypeSpatiallyProximal</span><span class="sxs-lookup"><span data-stu-id="736e6-120">MCDRemoteSystemDiscoveryTypeSpatiallyProximal</span></span> | <span data-ttu-id="736e6-121">3</span><span class="sxs-lookup"><span data-stu-id="736e6-121">3</span></span>     | <span data-ttu-id="736e6-122">원격 시스템 proximal 연결을 통해 검색할 수 고 할 수 있어야</span><span class="sxs-lookup"><span data-stu-id="736e6-122">Remote systems are discoverable through a proximal connection and are expected to be</span></span>
<span data-ttu-id="736e6-123">Bluetooth 범위에서 예를 들어 클라이언트 장치 곧이 공간적으로입니다.</span><span class="sxs-lookup"><span data-stu-id="736e6-123">spatially near to the client device (in Bluetooth range, for example).</span></span>  |

