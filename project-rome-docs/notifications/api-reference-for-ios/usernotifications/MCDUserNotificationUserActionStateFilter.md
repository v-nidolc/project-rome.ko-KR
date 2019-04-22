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
# <a name="enum-mcdusernotificationuseractionstatefilter"></a>열거형 `MCDUserNotificationUserActionStateFilter`

```
typedef NS_ENUM(NSInteger, MCDUserNotificationUserActionStateFilter)
```

알림을 상태별 사용자 작업 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|   MCDUserNotificationUserActionStateFilterAny|0| 사용자 작업 상태에 관계 없이 알림이 포함 됩니다.|
|   MCDUserNotificationUserActionStateFilterNoInteraction |1| 가 된 작업을 하지 않은 사용자는 알림이 포함 됩니다.|
|   MCDUserNotificationUserActionStateFilterActivated|2| 사용자가 활성화 된는 알림이 포함 됩니다.|
|   MCDUserNotificationUserActionStateFilterDismissed|3| 사용자가 해제 된 알림이 포함 됩니다.|
|   MCDUserNotificationUserActionStateFilterSnoozed|4| 사용자에 의해 연기 된 있어야 하는 알림이 포함 됩니다.|