---
title: MCDAppServiceClosedStatus
description: 원격 앱 서비스에 닫힌된 연결을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9a56ee489175cb065fde281acb4ae8a345fb851b
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907725"
---
# <a name="enum-mcdappserviceclosedstatus"></a><span data-ttu-id="8625e-104">열거형 `MCDAppServiceClosedStatus`</span><span class="sxs-lookup"><span data-stu-id="8625e-104">enum `MCDAppServiceClosedStatus`</span></span>

```
typedef NS_ENUM(NSInteger, MCDAppServiceClosedStatus)
```

<span data-ttu-id="8625e-105">원격 앱 서비스에 닫힌된 연결을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8625e-105">Contains values that describe a closed connection to a remote app service.</span></span>

|<span data-ttu-id="8625e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8625e-106">Member</span></span>   |<span data-ttu-id="8625e-107">값</span><span class="sxs-lookup"><span data-stu-id="8625e-107">Value</span></span>   |<span data-ttu-id="8625e-108">설명</span><span class="sxs-lookup"><span data-stu-id="8625e-108">Description</span></span>   |
|--------|-------|-------------|
|<span data-ttu-id="8625e-109">MCDAppServiceClosedStatusCompleted</span><span class="sxs-lookup"><span data-stu-id="8625e-109">MCDAppServiceClosedStatusCompleted</span></span> |<span data-ttu-id="8625e-110">0</span><span class="sxs-lookup"><span data-stu-id="8625e-110">0</span></span>| <span data-ttu-id="8625e-111">App service에 대 한 끝점을 정상적으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="8625e-111">The endpoint for the app service closed gracefully.</span></span>|
|<span data-ttu-id="8625e-112">MCDAppServiceClosedStatusCanceled</span><span class="sxs-lookup"><span data-stu-id="8625e-112">MCDAppServiceClosedStatusCanceled</span></span> |<span data-ttu-id="8625e-113">1</span><span class="sxs-lookup"><span data-stu-id="8625e-113">1</span></span>| <span data-ttu-id="8625e-114">App service에 대 한 끝점은 클라이언트 또는 시스템에서 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="8625e-114">The endpoint for the app service was closed by the client or the system.</span></span>|
|<span data-ttu-id="8625e-115">MCDAppServiceClosedStatusResourceLimitsExceeded</span><span class="sxs-lookup"><span data-stu-id="8625e-115">MCDAppServiceClosedStatusResourceLimitsExceeded</span></span> |<span data-ttu-id="8625e-116">2</span><span class="sxs-lookup"><span data-stu-id="8625e-116">2</span></span>| <span data-ttu-id="8625e-117">App service에 대 한 끝점은 끝점 리소스가 부족 하기 때문에 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8625e-117">The endpoint for the app service was closed because the endpoint ran out of resources.</span></span>|
|<span data-ttu-id="8625e-118">MCDAppServiceClosedStatusUnknown</span><span class="sxs-lookup"><span data-stu-id="8625e-118">MCDAppServiceClosedStatusUnknown</span></span> |<span data-ttu-id="8625e-119">3</span><span class="sxs-lookup"><span data-stu-id="8625e-119">3</span></span>| <span data-ttu-id="8625e-120">알 수 없는 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="8625e-120">An unknown error occurred.</span></span>|