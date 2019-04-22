---
title: MCDUserNotificationUserActionState
description: 알림 사용자가 수행 하는 동작을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 2baebeff7ccd43c7a5259c178434162908ee84c9
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800805"
---
# <a name="enum-mcdusernotificationuseractionstate"></a>열거형 `MCDUserNotificationUserActionState`

```
typedef NS_ENUM(NSInteger, MCDUserNotificationUserActionState)
```

알림 사용자가 수행 하는 동작을 설명 하는 값을 포함 합니다.

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|   MCDUserNotificationUserActionStateNoInteraction |0| 사용자는 모든 조치를 취하지 않았습니다.|
|   MCDUserNotificationUserActionStateActivated|1|사용자가 알림을 활성화 합니다.|
|   MCDUserNotificationUserActionStateDismissed|2| 사용자가 알림을 해제 됩니다.|
|   MCDUserNotificationUserActionStateSnoozed|3| 사용자가 알림을 연기 합니다.|
