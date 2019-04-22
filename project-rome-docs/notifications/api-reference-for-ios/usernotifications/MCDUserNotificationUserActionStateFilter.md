---
title: MCDUserNotificationUserActionStateFilter
description: 알림을 상태별 사용자 작업 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 41719d76e03fd6def57c8f77f9ab6956811e8803
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800565"
---
# <a name="enum-mcdusernotificationuseractionstatefilter"></a><span data-ttu-id="12e1e-104">열거형 `MCDUserNotificationUserActionStateFilter`</span><span class="sxs-lookup"><span data-stu-id="12e1e-104">enum `MCDUserNotificationUserActionStateFilter`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationUserActionStateFilter)
```

<span data-ttu-id="12e1e-105">알림을 상태별 사용자 작업 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-105">Contains values that categorize notifications by user action state (for filtered notification retrieval).</span></span>

|<span data-ttu-id="12e1e-106">이름</span><span class="sxs-lookup"><span data-stu-id="12e1e-106">Name</span></span> | <span data-ttu-id="12e1e-107">값</span><span class="sxs-lookup"><span data-stu-id="12e1e-107">Value</span></span> | <span data-ttu-id="12e1e-108">설명</span><span class="sxs-lookup"><span data-stu-id="12e1e-108">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="12e1e-109">MCDUserNotificationUserActionStateFilterAny</span><span class="sxs-lookup"><span data-stu-id="12e1e-109">MCDUserNotificationUserActionStateFilterAny</span></span>|<span data-ttu-id="12e1e-110">0</span><span class="sxs-lookup"><span data-stu-id="12e1e-110">0</span></span>| <span data-ttu-id="12e1e-111">사용자 작업 상태에 관계 없이 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-111">Include notifications regardless of user action state.</span></span>|
|   <span data-ttu-id="12e1e-112">MCDUserNotificationUserActionStateFilterNoInteraction</span><span class="sxs-lookup"><span data-stu-id="12e1e-112">MCDUserNotificationUserActionStateFilterNoInteraction</span></span> |<span data-ttu-id="12e1e-113">1</span><span class="sxs-lookup"><span data-stu-id="12e1e-113">1</span></span>| <span data-ttu-id="12e1e-114">가 된 작업을 하지 않은 사용자는 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-114">Include notifications that have not been acted on by the user.</span></span>|
|   <span data-ttu-id="12e1e-115">MCDUserNotificationUserActionStateFilterActivated</span><span class="sxs-lookup"><span data-stu-id="12e1e-115">MCDUserNotificationUserActionStateFilterActivated</span></span>|<span data-ttu-id="12e1e-116">2</span><span class="sxs-lookup"><span data-stu-id="12e1e-116">2</span></span>| <span data-ttu-id="12e1e-117">사용자가 활성화 된는 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-117">Include notifications that have been activated by the user.</span></span>|
|   <span data-ttu-id="12e1e-118">MCDUserNotificationUserActionStateFilterDismissed</span><span class="sxs-lookup"><span data-stu-id="12e1e-118">MCDUserNotificationUserActionStateFilterDismissed</span></span>|<span data-ttu-id="12e1e-119">3</span><span class="sxs-lookup"><span data-stu-id="12e1e-119">3</span></span>| <span data-ttu-id="12e1e-120">사용자가 해제 된 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-120">Include notifications that have been dismissed by the user.</span></span>|
|   <span data-ttu-id="12e1e-121">MCDUserNotificationUserActionStateFilterSnoozed</span><span class="sxs-lookup"><span data-stu-id="12e1e-121">MCDUserNotificationUserActionStateFilterSnoozed</span></span>|<span data-ttu-id="12e1e-122">4</span><span class="sxs-lookup"><span data-stu-id="12e1e-122">4</span></span>| <span data-ttu-id="12e1e-123">사용자에 의해 연기 된 있어야 하는 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12e1e-123">Include notifications that have been snoozed by the user.</span></span>|