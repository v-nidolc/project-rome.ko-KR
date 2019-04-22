---
title: UserNotificationReaderOptions
description: 이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다.
keywords: microsoft, windows, 그래프 알림 및 방법 Windows
ms.openlocfilehash: dda9187dccd013f719d564f62b51fd9ac7be8444
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801385"
---
# <a name="class-usernotificationreaderoptions"></a>클래스 `UserNotificationReaderOptions`

```C#
public sealed class UserNotificationReaderOptions : IUserNotificationReaderOptions
```

이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다. 

## <a name="constructors"></a>생성자

### <a name="usernotificationreaderoptions"></a>UserNotificationReaderOptions
만들고 UserNotificationReaderOptions의 새 인스턴스를 초기화 합니다.

```C#
public UserNotificationReaderOptions()
```

### <a name="usernotificationreaderoptionsusernotificationreaderstartposition-usernotificationstatusfilter-usernotificationreadstatefilter-usernotificationuseractionstatefilter"></a>UserNotificationReaderOptions(UserNotificationReaderStartPosition, UserNotificationStatusFilter, UserNotificationReadStateFilter, UserNotificationUserActionStateFilter)
만들고 필터와 지정 된 시작 위치 UserNotificationReaderOptions의 새 인스턴스를 초기화 합니다. 

```C#
public UserNotificationReaderOptions(UserNotificationReaderStartPosition startPosition, UserNotificationStatusFilter statusFilter, UserNotificationReadStateFilter readStateFilter, UserNotificationUserActionStateFilter userActionStateFilter)
```

## <a name="properties"></a>속성

|이름 | 설명 |
|:-- |:-- |
|StartPosition |가져오거나 UserNotificationReaderOptions의이 인스턴스에 대 한 시작 위치를 설정 합니다.|
|   StatusFilter |가져오거나 만들 하려는이 사용자 알림 판독기에 대 한 상태 필터를 설정 합니다.| 
|   ReadStateFilter |가져오거나 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 읽기 상태 필터를 설정 합니다.| 
|   UserActionStateFilter|Getor는 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 사용자 동작 상태 필터를 설정 합니다.| 




