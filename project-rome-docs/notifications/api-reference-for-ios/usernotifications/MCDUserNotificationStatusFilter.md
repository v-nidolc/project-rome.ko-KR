---
title: MCDUserNotificationStatusFilter
description: 알림 판독기를 만들 때 읽기 상태 필터를 나타내는 값을 포함 합니다. 높은 읽기만 앱 모든 알림을 수신 하려는 지 여부를 결정 하거나 읽지 않은 것만 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 09e165c98a557b16214d7c1103734d6e17407b6f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801495"
---
# <a name="enum-mcdusernotificationstatusfilter"></a><span data-ttu-id="a1bb7-105">열거형 `MCDUserNotificationStatusFilter`</span><span class="sxs-lookup"><span data-stu-id="a1bb7-105">enum `MCDUserNotificationStatusFilter`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationStatusFilter)
```

<span data-ttu-id="a1bb7-106">알림 판독기를 만들 때 읽기 상태 필터를 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bb7-106">Contains values that indicates a read state filter when creating a notification reader.</span></span> <span data-ttu-id="a1bb7-107">높은 읽기만 앱 모든 알림을 수신 하려는 지 여부를 결정 하거나 읽지 않은 것만 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bb7-107">This determines whether the app wants to receive all notifications, only read ones, or only unread ones.</span></span> 

|<span data-ttu-id="a1bb7-108">이름</span><span class="sxs-lookup"><span data-stu-id="a1bb7-108">Name</span></span> | <span data-ttu-id="a1bb7-109">값</span><span class="sxs-lookup"><span data-stu-id="a1bb7-109">Value</span></span> | <span data-ttu-id="a1bb7-110">설명</span><span class="sxs-lookup"><span data-stu-id="a1bb7-110">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="a1bb7-111">MCDUserNotificationStatusFilterAny</span><span class="sxs-lookup"><span data-stu-id="a1bb7-111">MCDUserNotificationStatusFilterAny</span></span> | <span data-ttu-id="a1bb7-112">0</span><span class="sxs-lookup"><span data-stu-id="a1bb7-112">0</span></span>| <span data-ttu-id="a1bb7-113">상태 값에 관계 없이 모든 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1bb7-113">Include all notifications regardless of status value.</span></span> |
|   <span data-ttu-id="a1bb7-114">MCDUserNotificationStatusFilterActive</span><span class="sxs-lookup"><span data-stu-id="a1bb7-114">MCDUserNotificationStatusFilterActive</span></span> |<span data-ttu-id="a1bb7-115">1</span><span class="sxs-lookup"><span data-stu-id="a1bb7-115">1</span></span>| <span data-ttu-id="a1bb7-116">연결 된 장치 플랫폼 알림 저장소에서 활성 상태이 고 지속형 수 있는 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1bb7-116">Include notifications that are active and persisted in Connected Devices Platform notification store.</span></span> |
|   <span data-ttu-id="a1bb7-117">MCDUserNotificationStatusFilterDeleted</span><span class="sxs-lookup"><span data-stu-id="a1bb7-117">MCDUserNotificationStatusFilterDeleted</span></span> | <span data-ttu-id="a1bb7-118">2</span><span class="sxs-lookup"><span data-stu-id="a1bb7-118">2</span></span>| <span data-ttu-id="a1bb7-119">삭제 된 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1bb7-119">Include deleted notifications only.</span></span>|