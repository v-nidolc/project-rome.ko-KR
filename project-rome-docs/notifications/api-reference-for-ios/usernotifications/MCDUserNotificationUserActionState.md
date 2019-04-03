---
title: MCDUserNotificationUserActionState
description: 알림 사용자가 수행 하는 동작을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 2baebeff7ccd43c7a5259c178434162908ee84c9
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907785"
---
# <a name="enum-mcdusernotificationuseractionstate"></a><span data-ttu-id="46ca8-104">열거형 `MCDUserNotificationUserActionState`</span><span class="sxs-lookup"><span data-stu-id="46ca8-104">enum `MCDUserNotificationUserActionState`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationUserActionState)
```

<span data-ttu-id="46ca8-105">알림 사용자가 수행 하는 동작을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ca8-105">Contains values describing the action a user has taken on a notification.</span></span>

|<span data-ttu-id="46ca8-106">이름</span><span class="sxs-lookup"><span data-stu-id="46ca8-106">Name</span></span> | <span data-ttu-id="46ca8-107">값</span><span class="sxs-lookup"><span data-stu-id="46ca8-107">Value</span></span> | <span data-ttu-id="46ca8-108">설명</span><span class="sxs-lookup"><span data-stu-id="46ca8-108">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="46ca8-109">MCDUserNotificationUserActionStateNoInteraction</span><span class="sxs-lookup"><span data-stu-id="46ca8-109">MCDUserNotificationUserActionStateNoInteraction</span></span> |<span data-ttu-id="46ca8-110">0</span><span class="sxs-lookup"><span data-stu-id="46ca8-110">0</span></span>| <span data-ttu-id="46ca8-111">사용자는 모든 조치를 취하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="46ca8-111">The user hasn't taken any action.</span></span>|
|   <span data-ttu-id="46ca8-112">MCDUserNotificationUserActionStateActivated</span><span class="sxs-lookup"><span data-stu-id="46ca8-112">MCDUserNotificationUserActionStateActivated</span></span>|<span data-ttu-id="46ca8-113">1</span><span class="sxs-lookup"><span data-stu-id="46ca8-113">1</span></span>|<span data-ttu-id="46ca8-114">사용자가 알림을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ca8-114">The user has activated the notification.</span></span>|
|   <span data-ttu-id="46ca8-115">MCDUserNotificationUserActionStateDismissed</span><span class="sxs-lookup"><span data-stu-id="46ca8-115">MCDUserNotificationUserActionStateDismissed</span></span>|<span data-ttu-id="46ca8-116">2</span><span class="sxs-lookup"><span data-stu-id="46ca8-116">2</span></span>| <span data-ttu-id="46ca8-117">사용자가 알림을 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46ca8-117">The user has dismissed the notification.</span></span>|
|   <span data-ttu-id="46ca8-118">MCDUserNotificationUserActionStateSnoozed</span><span class="sxs-lookup"><span data-stu-id="46ca8-118">MCDUserNotificationUserActionStateSnoozed</span></span>|<span data-ttu-id="46ca8-119">3</span><span class="sxs-lookup"><span data-stu-id="46ca8-119">3</span></span>| <span data-ttu-id="46ca8-120">사용자가 알림을 연기 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ca8-120">The user has snoozed the notification.</span></span>|
