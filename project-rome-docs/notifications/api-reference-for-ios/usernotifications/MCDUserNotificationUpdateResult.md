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
# <a name="class-mcdusernotificationupdateresult"></a>클래스 `MCDUserNotificationUpdateResult`

```
@interface MCDUserNotificationUpdateResult : NSObject
```

이 클래스는 업데이트 알림을 시도의 상태를 설명 합니다.

## <a name="properties"></a>속성

### <a name="notificationid"></a>notificationId
`@property(nonatomic, readonly, nonnull) NSString* notificationId;`

알림의 ID입니다.

### <a name="succeeded"></a>성공
`@property(nonatomic, readonly) Succeeded succeeded;`

작업의 성공 여부. 