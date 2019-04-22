---
title: MCDRemoteSystemDiscoveryType
description: 포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: dc94b92311cb666fd2ffd3949b3d4d66a49e6e5b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800505"
---
# <a name="enum-mcdremotesystemdiscoverytype"></a><span data-ttu-id="aa4fe-104">열거형 `MCDRemoteSystemDiscoveryType`</span><span class="sxs-lookup"><span data-stu-id="aa4fe-104">enum `MCDRemoteSystemDiscoveryType`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemDiscoveryType)
```  

<span data-ttu-id="aa4fe-105">포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4fe-105">Contains values that describe how remote systems are able to be discovered.</span></span> 

## <a name="fields"></a><span data-ttu-id="aa4fe-106">필드</span><span class="sxs-lookup"><span data-stu-id="aa4fe-106">Fields</span></span>

| <span data-ttu-id="aa4fe-107">이름</span><span class="sxs-lookup"><span data-stu-id="aa4fe-107">Name</span></span>                              | <span data-ttu-id="aa4fe-108">값</span><span class="sxs-lookup"><span data-stu-id="aa4fe-108">Value</span></span> | <span data-ttu-id="aa4fe-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa4fe-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="aa4fe-110">MCDRemoteSystemDiscoveryTypeAny</span><span class="sxs-lookup"><span data-stu-id="aa4fe-110">MCDRemoteSystemDiscoveryTypeAny</span></span>   | <span data-ttu-id="aa4fe-111">0</span><span class="sxs-lookup"><span data-stu-id="aa4fe-111">0</span></span>     | <span data-ttu-id="aa4fe-112">원격 시스템 모든 연결을 통해 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4fe-112">Remote systems are discoverable through any connection.</span></span>  |
| <span data-ttu-id="aa4fe-113">MCDRemoteSystemDiscoveryTypeProximal</span><span class="sxs-lookup"><span data-stu-id="aa4fe-113">MCDRemoteSystemDiscoveryTypeProximal</span></span> | <span data-ttu-id="aa4fe-114">1</span><span class="sxs-lookup"><span data-stu-id="aa4fe-114">1</span></span>     | <span data-ttu-id="aa4fe-115">원격 시스템은 로컬 같은 proximal 연결을 통해 검색할 수만</span><span class="sxs-lookup"><span data-stu-id="aa4fe-115">Remote systems are only discoverable through a proximal connection, such as a local</span></span>
<span data-ttu-id="aa4fe-116">네트워크 또는 Bluetooth 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa4fe-116">network or Bluetooth connection.</span></span> |
| <span data-ttu-id="aa4fe-117">MCDRemoteSystemDiscoveryTypeCloud</span><span class="sxs-lookup"><span data-stu-id="aa4fe-117">MCDRemoteSystemDiscoveryTypeCloud</span></span> | <span data-ttu-id="aa4fe-118">2</span><span class="sxs-lookup"><span data-stu-id="aa4fe-118">2</span></span>     | <span data-ttu-id="aa4fe-119">원격 시스템은 클라우드 연결을 통해 검색할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa4fe-119">Remote systems are only discoverable through cloud connection.</span></span> |
| <span data-ttu-id="aa4fe-120">MCDRemoteSystemDiscoveryTypeSpatiallyProximal</span><span class="sxs-lookup"><span data-stu-id="aa4fe-120">MCDRemoteSystemDiscoveryTypeSpatiallyProximal</span></span> | <span data-ttu-id="aa4fe-121">3</span><span class="sxs-lookup"><span data-stu-id="aa4fe-121">3</span></span>     | <span data-ttu-id="aa4fe-122">원격 시스템 proximal 연결을 통해 검색할 수 고 할 수 있어야</span><span class="sxs-lookup"><span data-stu-id="aa4fe-122">Remote systems are discoverable through a proximal connection and are expected to be</span></span>
<span data-ttu-id="aa4fe-123">Bluetooth 범위에서 예를 들어 클라이언트 장치 곧이 공간적으로입니다.</span><span class="sxs-lookup"><span data-stu-id="aa4fe-123">spatially near to the client device (in Bluetooth range, for example).</span></span>  |

