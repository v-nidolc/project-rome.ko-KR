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
# <a name="enum-mcdusernotificationreadstatefilter"></a>열거형 `MCDUserNotificationReadStateFilter`

```
typedef NS_ENUM(NSInteger, MCDUserNotificationReadStateFilter)
```

알림을 상태별 읽기 (필터링 된 알림 검색)를 분류 하는 값을 포함 합니다.

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|   MCDUserNotificationReadStateFilterAny | 0 | 읽기 상태에 관계 없이 알림이 포함 됩니다.|
|   MCDUserNotificationReadStateFilterUnread | 1 | 읽지 않은 알림이 포함 됩니다.|
|   MCDUserNotificationReadStateFilterRead | 2 | 읽은 알림이 포함 됩니다. |