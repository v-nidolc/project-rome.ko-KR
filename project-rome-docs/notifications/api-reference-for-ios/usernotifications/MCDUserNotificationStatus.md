---
title: MCDUserNotificationStatus
description: 알림을 삭제 여부를 결정 하는 값을 포함 합니다. 삭제 된 알림 알림 저장소 됩니다 및 플랫폼 정리를 수행 하기 전에 판독기에서 반환 합니다. 이러한 알림은 알림 판독기에서 표시 하지 않으려면 해당 UserNotificationStatusFilter 판독기 필터를 적용할 수 있습니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 2d2ce28b08442c51ecdb4652ba33cb96f091b8ce
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907245"
---
# <a name="enum-mcdusernotificationstatus"></a><span data-ttu-id="ea831-106">열거형 `MCDUserNotificationStatus`</span><span class="sxs-lookup"><span data-stu-id="ea831-106">enum `MCDUserNotificationStatus`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserNotificationStatus)
```

<span data-ttu-id="ea831-107">알림을 삭제 여부를 결정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea831-107">Contains values that determines whether the notification is deleted or not.</span></span> <span data-ttu-id="ea831-108">삭제 된 알림 알림 저장소 됩니다 및 플랫폼 정리를 수행 하기 전에 판독기에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea831-108">Deleted notifications will still be in the notification store and be returned by the reader before the platform cleanup happens.</span></span> <span data-ttu-id="ea831-109">이러한 알림은 알림 판독기에서 표시 하지 않으려면 해당 UserNotificationStatusFilter 판독기 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea831-109">A corresponding reader filter UserNotificationStatusFilter can be applied to prevent these notifications from showing up in notification reader.</span></span> 

|<span data-ttu-id="ea831-110">이름</span><span class="sxs-lookup"><span data-stu-id="ea831-110">Name</span></span> | <span data-ttu-id="ea831-111">값</span><span class="sxs-lookup"><span data-stu-id="ea831-111">Value</span></span> | <span data-ttu-id="ea831-112">설명</span><span class="sxs-lookup"><span data-stu-id="ea831-112">Description</span></span> |
|:-- |:-- |:-- |
|   <span data-ttu-id="ea831-113">MCDUserNotificationStatusActive</span><span class="sxs-lookup"><span data-stu-id="ea831-113">MCDUserNotificationStatusActive</span></span> |<span data-ttu-id="ea831-114">0</span><span class="sxs-lookup"><span data-stu-id="ea831-114">0</span></span>| <span data-ttu-id="ea831-115">알림 여전히 활성 상태이 고 연결 된 장치 플랫폼 저장소 내에서 지속형입니다.</span><span class="sxs-lookup"><span data-stu-id="ea831-115">The notification is still active and persisted inside Connected Devices Platform store.</span></span> |
|   <span data-ttu-id="ea831-116">MCDUserNotificationStatusDeleted</span><span class="sxs-lookup"><span data-stu-id="ea831-116">MCDUserNotificationStatusDeleted</span></span> | <span data-ttu-id="ea831-117">1</span><span class="sxs-lookup"><span data-stu-id="ea831-117">1</span></span>| <span data-ttu-id="ea831-118">알림이 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea831-118">The notification has been deleted.</span></span>|