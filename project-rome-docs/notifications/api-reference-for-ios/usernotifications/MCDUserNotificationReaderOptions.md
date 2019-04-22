---
title: MCDUserNotificationReaderOptions
description: 이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다.
keywords: microsoft, windows, 그래프 알림, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: d5ea9072af0f35f614557192ef782754c4054b22
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907985"
---
# <a name="class-mcdusernotificationreaderoptions"></a>클래스 `MCDUserNotificationReaderOptions`

```
@interface MCDUserNotificationReaderOptions : NSObject
```

이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다. 

## <a name="properties"></a>속성

### <a name="startposition"></a>startPosition
`@property(nonatomic, assign) MCDUserNotificationReaderStartPosition startPosition;` 가져오거나 UserNotificationReaderOptions의이 인스턴스에 대 한 시작 위치를 설정 합니다.

### <a name="statusfilter"></a>statusFilter
`@property(nonatomic, assign) MCDUserNotificationStatusFilter statusFilter;` 가져오거나 만들 하려는이 사용자 알림 판독기에 대 한 상태 필터를 설정 합니다.

### <a name="readstatefilter"></a>readStateFilter
`@property(nonatomic, assign) MCDUserNotificationReadStateFilter readStateFilter;` Get 또는 set UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 읽기 상태 필터

### <a name="useractionstatefilter"></a>userActionStateFilter
`@property(nonatomic, assign) MCDUserNotificationUserActionStateFilter userActionStateFilter;` Getor는 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 사용자 동작 상태 필터를 설정 합니다.

## <a name="constructors"></a>생성자

### <a name="options"></a>옵션
`+ (nullable instancetype)options;` 만들고 사용자 알림에 대 한 옵션의 새 인스턴스를 초기화 합니다.