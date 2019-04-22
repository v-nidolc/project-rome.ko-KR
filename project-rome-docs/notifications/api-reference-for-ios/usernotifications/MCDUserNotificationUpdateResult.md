---
title: MCDUserNotificationUpdateResult
description: 이 클래스는 업데이트 알림을 시도의 상태를 설명 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 814d4373c47c8af00d3e003f730db804f48c5fb0
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801485"
---
# <a name="class-mcdusernotificationupdateresult"></a><span data-ttu-id="edd8e-104">클래스 `MCDUserNotificationUpdateResult`</span><span class="sxs-lookup"><span data-stu-id="edd8e-104">class `MCDUserNotificationUpdateResult`</span></span>

```
@interface MCDUserNotificationUpdateResult : NSObject
```

<span data-ttu-id="edd8e-105">이 클래스는 업데이트 알림을 시도의 상태를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="edd8e-105">This class describes the status of an attempt to update a notification.</span></span>

## <a name="properties"></a><span data-ttu-id="edd8e-106">속성</span><span class="sxs-lookup"><span data-stu-id="edd8e-106">Properties</span></span>

### <a name="notificationid"></a><span data-ttu-id="edd8e-107">notificationId</span><span class="sxs-lookup"><span data-stu-id="edd8e-107">notificationId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* notificationId;`

<span data-ttu-id="edd8e-108">알림의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="edd8e-108">The ID of the notification.</span></span>

### <a name="succeeded"></a><span data-ttu-id="edd8e-109">성공</span><span class="sxs-lookup"><span data-stu-id="edd8e-109">succeeded</span></span>
`@property(nonatomic, readonly) Succeeded succeeded;`

<span data-ttu-id="edd8e-110">작업의 성공 여부.</span><span class="sxs-lookup"><span data-stu-id="edd8e-110">Whether the operation succeeded.</span></span> 