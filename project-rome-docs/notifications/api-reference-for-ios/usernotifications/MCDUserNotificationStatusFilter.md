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
# <a name="enum-mcdusernotificationstatusfilter"></a>열거형 `MCDUserNotificationStatusFilter`

```
typedef NS_ENUM(NSInteger, MCDUserNotificationStatusFilter)
```

알림 판독기를 만들 때 읽기 상태 필터를 나타내는 값을 포함 합니다. 높은 읽기만 앱 모든 알림을 수신 하려는 지 여부를 결정 하거나 읽지 않은 것만 합니다. 

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|   MCDUserNotificationStatusFilterAny | 0| 상태 값에 관계 없이 모든 알림이 포함 됩니다. |
|   MCDUserNotificationStatusFilterActive |1| 연결 된 장치 플랫폼 알림 저장소에서 활성 상태이 고 지속형 수 있는 알림이 포함 됩니다. |
|   MCDUserNotificationStatusFilterDeleted | 2| 삭제 된 알림이 포함 됩니다.|