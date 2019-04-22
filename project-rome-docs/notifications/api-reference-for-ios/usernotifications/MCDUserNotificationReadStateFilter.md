---
title: MCDUserNotificationReadStateFilter
description: 알림을 상태별 읽기 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 19da2f22e88dba5617ee60169c06552191aebe7d
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801345"
---
# <a name="enum-mcdusernotificationreadstatefilter"></a><span data-ttu-id="78c79-104">열거형 `MCDUserNotificationReadStateFilter`</span><span class="sxs-lookup"><span data-stu-id="78c79-104">enum `MCDUserNotificationReadStateFilter`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationReadStateFilter)
```

<span data-ttu-id="78c79-105">알림을 상태별 읽기 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c79-105">Contains values that categorize notifications by read state (for filtered notification retrieval).</span></span>

|<span data-ttu-id="78c79-106">이름</span><span class="sxs-lookup"><span data-stu-id="78c79-106">Name</span></span> | <span data-ttu-id="78c79-107">값</span><span class="sxs-lookup"><span data-stu-id="78c79-107">Value</span></span> | <span data-ttu-id="78c79-108">설명</span><span class="sxs-lookup"><span data-stu-id="78c79-108">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="78c79-109">MCDUserNotificationReadStateFilterAny</span><span class="sxs-lookup"><span data-stu-id="78c79-109">MCDUserNotificationReadStateFilterAny</span></span> | <span data-ttu-id="78c79-110">0</span><span class="sxs-lookup"><span data-stu-id="78c79-110">0</span></span> | <span data-ttu-id="78c79-111">읽기 상태에 관계 없이 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c79-111">Include notifications regardless of read state.</span></span>|
|   <span data-ttu-id="78c79-112">MCDUserNotificationReadStateFilterUnread</span><span class="sxs-lookup"><span data-stu-id="78c79-112">MCDUserNotificationReadStateFilterUnread</span></span> | <span data-ttu-id="78c79-113">1</span><span class="sxs-lookup"><span data-stu-id="78c79-113">1</span></span> | <span data-ttu-id="78c79-114">읽지 않은 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c79-114">Include notifications that haven't been read.</span></span>|
|   <span data-ttu-id="78c79-115">MCDUserNotificationReadStateFilterRead</span><span class="sxs-lookup"><span data-stu-id="78c79-115">MCDUserNotificationReadStateFilterRead</span></span> | <span data-ttu-id="78c79-116">2</span><span class="sxs-lookup"><span data-stu-id="78c79-116">2</span></span> | <span data-ttu-id="78c79-117">읽은 알림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c79-117">Include notifications that have been read.</span></span> |