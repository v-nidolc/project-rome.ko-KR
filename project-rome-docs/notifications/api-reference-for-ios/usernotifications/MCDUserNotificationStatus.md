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
# <a name="enum-mcdusernotificationstatus"></a>열거형 `MCDUserNotificationStatus`

```
typedef NS_ENUM(NSInteger, MCDUserNotificationStatus)
```

알림을 삭제 여부를 결정 하는 값을 포함 합니다. 삭제 된 알림 알림 저장소 됩니다 및 플랫폼 정리를 수행 하기 전에 판독기에서 반환 합니다. 이러한 알림은 알림 판독기에서 표시 하지 않으려면 해당 UserNotificationStatusFilter 판독기 필터를 적용할 수 있습니다. 

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|   MCDUserNotificationStatusActive |0| 알림 여전히 활성 상태이 고 연결 된 장치 플랫폼 저장소 내에서 지속형입니다. |
|   MCDUserNotificationStatusDeleted | 1| 알림이 삭제 되었습니다.|