---
title: MCDUserNotificationStatusFilter
description: 알림 판독기를 만들 때 읽기 상태 필터를 나타내는 값을 포함 합니다. 높은 읽기만 앱 모든 알림을 수신 하려는 지 여부를 결정 하거나 읽지 않은 것만 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 09e165c98a557b16214d7c1103734d6e17407b6f
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909145"
---
# <a name="enum-mcdusernotificationstatusfilter"></a><span data-ttu-id="c2f8c-105">열거형 `MCDUserNotificationStatusFilter`</span><span class="sxs-lookup"><span data-stu-id="c2f8c-105">enum `MCDUserNotificationStatusFilter`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationStatusFilter)
```

<span data-ttu-id="c2f8c-106">알림 판독기를 만들 때 읽기 상태 필터를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f8c-106">Contains values that indicates a read state filter when creating a notification reader.</span></span> <span data-ttu-id="c2f8c-107">높은 읽기만 앱 모든 알림을 수신 하려는 지 여부를 결정 하거나 읽지 않은 것만 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2f8c-107">This determines whether the app wants to receive all notifications, only read ones, or only unread ones.</span></span> 

|<span data-ttu-id="c2f8c-108">이름</span><span class="sxs-lookup"><span data-stu-id="c2f8c-108">Name</span></span> | <span data-ttu-id="c2f8c-109">값</span><span class="sxs-lookup"><span data-stu-id="c2f8c-109">Value</span></span> | <span data-ttu-id="c2f8c-110">설명</span><span class="sxs-lookup"><span data-stu-id="c2f8c-110">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="c2f8c-111">MCDUserNotificationStatusFilterAny</span><span class="sxs-lookup"><span data-stu-id="c2f8c-111">MCDUserNotificationStatusFilterAny</span></span> | <span data-ttu-id="c2f8c-112">0</span><span class="sxs-lookup"><span data-stu-id="c2f8c-112">0</span></span>| <span data-ttu-id="c2f8c-113">상태 값에 관계 없이 모든 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f8c-113">Include all notifications regardless of status value.</span></span> |
|   <span data-ttu-id="c2f8c-114">MCDUserNotificationStatusFilterActive</span><span class="sxs-lookup"><span data-stu-id="c2f8c-114">MCDUserNotificationStatusFilterActive</span></span> |<span data-ttu-id="c2f8c-115">1</span><span class="sxs-lookup"><span data-stu-id="c2f8c-115">1</span></span>| <span data-ttu-id="c2f8c-116">연결 된 장치 플랫폼 알림 저장소에서 활성 상태이 고 지속형 수 있는 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f8c-116">Include notifications that are active and persisted in Connected Devices Platform notification store.</span></span> |
|   <span data-ttu-id="c2f8c-117">MCDUserNotificationStatusFilterDeleted</span><span class="sxs-lookup"><span data-stu-id="c2f8c-117">MCDUserNotificationStatusFilterDeleted</span></span> | <span data-ttu-id="c2f8c-118">2</span><span class="sxs-lookup"><span data-stu-id="c2f8c-118">2</span></span>| <span data-ttu-id="c2f8c-119">삭제 된 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2f8c-119">Include deleted notifications only.</span></span>|