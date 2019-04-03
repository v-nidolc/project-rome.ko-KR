---
title: MCDUserNotificationUpdateResult
description: 이 클래스는 업데이트 알림을 시도의 상태를 설명 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 814d4373c47c8af00d3e003f730db804f48c5fb0
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907975"
---
# <a name="class-mcdusernotificationupdateresult"></a><span data-ttu-id="32c00-104">클래스 `MCDUserNotificationUpdateResult`</span><span class="sxs-lookup"><span data-stu-id="32c00-104">class `MCDUserNotificationUpdateResult`</span></span>

```
@interface MCDUserNotificationUpdateResult : NSObject
```

<span data-ttu-id="32c00-105">이 클래스는 업데이트 알림을 시도의 상태를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c00-105">This class describes the status of an attempt to update a notification.</span></span>

## <a name="properties"></a><span data-ttu-id="32c00-106">속성</span><span class="sxs-lookup"><span data-stu-id="32c00-106">Properties</span></span>

### <a name="notificationid"></a><span data-ttu-id="32c00-107">notificationId</span><span class="sxs-lookup"><span data-stu-id="32c00-107">notificationId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* notificationId;`

<span data-ttu-id="32c00-108">알림의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="32c00-108">The ID of the notification.</span></span>

### <a name="succeeded"></a><span data-ttu-id="32c00-109">성공</span><span class="sxs-lookup"><span data-stu-id="32c00-109">succeeded</span></span>
`@property(nonatomic, readonly) Succeeded succeeded;`

<span data-ttu-id="32c00-110">작업의 성공 여부.</span><span class="sxs-lookup"><span data-stu-id="32c00-110">Whether the operation succeeded.</span></span> 