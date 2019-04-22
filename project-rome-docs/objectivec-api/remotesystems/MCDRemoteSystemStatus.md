---
title: MCDRemoteSystemStatus
description: 원격 시스템의 가용성을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4a69961b12def736733e1b6a78d376d57b2fa33f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801375"
---
# <a name="enum-mcdremotesystemstatus"></a><span data-ttu-id="86cb8-104">열거형 `MCDRemoteSystemStatus`</span><span class="sxs-lookup"><span data-stu-id="86cb8-104">enum `MCDRemoteSystemStatus`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemStatus)
```  
<span data-ttu-id="86cb8-105">원격 시스템의 가용성을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="86cb8-105">Contains values that describe the availability of a remote system.</span></span> <span data-ttu-id="86cb8-106">IOS 앱의 값에 **MCDRemoteSystemStatusUnknown** 항상 발생할 수, 다른 값은 Windows 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86cb8-106">On iOS apps, a value of **MCDRemoteSystemStatusUnknown** will always be encountered; other values are only available on Windows systems.</span></span>

## <a name="fields"></a><span data-ttu-id="86cb8-107">필드</span><span class="sxs-lookup"><span data-stu-id="86cb8-107">Fields</span></span>

| <span data-ttu-id="86cb8-108">이름</span><span class="sxs-lookup"><span data-stu-id="86cb8-108">Name</span></span>                              | <span data-ttu-id="86cb8-109">값</span><span class="sxs-lookup"><span data-stu-id="86cb8-109">Value</span></span> | <span data-ttu-id="86cb8-110">설명</span><span class="sxs-lookup"><span data-stu-id="86cb8-110">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="86cb8-111">MCDRemoteSystemStatusUnavailable</span><span class="sxs-lookup"><span data-stu-id="86cb8-111">MCDRemoteSystemStatusUnavailable</span></span> | <span data-ttu-id="86cb8-112">0</span><span class="sxs-lookup"><span data-stu-id="86cb8-112">0</span></span> | <span data-ttu-id="86cb8-113">원격 시스템을 사용할 수 없는 상태로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86cb8-113">The remote system is reported as unavailable.</span></span> |
| <span data-ttu-id="86cb8-114">MCDRemoteSystemStatusDiscoveringAvailablilty</span><span class="sxs-lookup"><span data-stu-id="86cb8-114">MCDRemoteSystemStatusDiscoveringAvailablilty</span></span> | <span data-ttu-id="86cb8-115">1</span><span class="sxs-lookup"><span data-stu-id="86cb8-115">1</span></span> | <span data-ttu-id="86cb8-116">원격 시스템의 상태를 결정 하는 (검색 프로세스 중에 발생).</span><span class="sxs-lookup"><span data-stu-id="86cb8-116">The status of the remote system is being determined (occurs during the discovery process).</span></span> |
| <span data-ttu-id="86cb8-117">MCDRemoteSystemStatusAvailable</span><span class="sxs-lookup"><span data-stu-id="86cb8-117">MCDRemoteSystemStatusAvailable</span></span> | <span data-ttu-id="86cb8-118">2</span><span class="sxs-lookup"><span data-stu-id="86cb8-118">2</span></span> | <span data-ttu-id="86cb8-119">원격 시스템은 사용 가능한 것으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86cb8-119">The remote system is reported as available.</span></span> |
| <span data-ttu-id="86cb8-120">MCDRemoteSystemStatusUnknown</span><span class="sxs-lookup"><span data-stu-id="86cb8-120">MCDRemoteSystemStatusUnknown</span></span> | <span data-ttu-id="86cb8-121">3</span><span class="sxs-lookup"><span data-stu-id="86cb8-121">3</span></span> | <span data-ttu-id="86cb8-122">상태를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86cb8-122">The status is unknown.</span></span> |
