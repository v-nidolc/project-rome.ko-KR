---
title: MCDUserNotification
description: 이 클래스에는 그래프 알림을 통해 앱 서버에서 게시 한 앱 클라이언트에서 받은 사용자 알림을 나타냅니다.
keywords: microsoft, ios, 그래프 알림, ios 방법 도움말, 방법 iphone
ms.openlocfilehash: 5ca1360c34e2bf9aa5d9847b8df2c462e2956b31
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907895"
---
# <a name="class-mcdusernotification"></a>클래스 `MCDUserNotification`

```
@interface MCDUserNotification : NSObject
```


이 클래스는 단일 사용자 알림 인스턴스를 나타냅니다. 사용자 알림 만들어지고 사용자가 로그인 한 사용자의 모든 장치 끝점에 배포를 목표로 앱 서버에서 게시 합니다.
앱 클라이언트에서 받은 후 사용자 알림을 생성 하 고 해당 되는 플랫폼에 대 한 로컬 알림을 Api를 사용 하 여 visual 알림 배너가 표시와 같은 환경에서 발생할 수 있습니다.

## <a name="properties"></a>속성

### <a name="notificationid"></a>notificationId
`@property(nonatomic, readonly, nonnull) NSString* notificationId;` 지정 된 개발자 고유 가져옵니다이 사용자 알림에 대 한 id입니다.

### <a name="groupid"></a>groupId
`@property(nonatomic, readonly, nonnull) NSString* groupId;` 지정 된 개발자 가져옵니다이 사용자 알림에 대 한 그룹 id입니다.

### <a name="expirationtime"></a>expirationTime
`@property(nonatomic, readonly, nonnull) NSDate* expirationTime;` 이 사용자 알림에 대 한 만료 시간을 가져옵니다.

### <a name="status"></a>상태
`@property(nonatomic, readonly) MCDUserNotificationStatus status;` 사용자 알림 메시지의 상태를 가져옵니다.

### <a name="changetime"></a>changeTime
`@property(nonatomic, readonly, nonnull) NSDate* changeTime;` 변경 된 시간을 가져옵니다.

### <a name="priority"></a>priority
`@property(nonatomic, readonly) MCDUserNotificationPriority priority;` 지정 된 개발자 가져옵니다이 사용자 알림에 대 한 우선 순위입니다.

### <a name="content"></a>콘텐츠
`@property(nonatomic, readonly, nonnull) NSString* content;` 임의의 데이터를 정의 하는 개발자는이 알림에 대 한 콘텐츠 페이로드를 가져옵니다.

###  <a name="readstate"></a>readState
`@property(nonatomic, assign, readwrite) MCDUserNotificationReadState readState;` 알림을 읽거나 읽지 않은 메시지 인지 나타내는이 사용자 알림에 대 한 읽기 상태 값을 가져옵니다.

### <a name="useractionstate"></a>userActionState
`@property(nonatomic, assign, readwrite) MCDUserNotificationUserActionState userActionState;` 사용자 알림이 있는지 여부를 확인 알림을 하지 상호 작용, 해제, 활성화, 연기에 대 한 사용자 동작 상태 값을 가져옵니다. 

## <a name="methods"></a>메서드

### <a name="saveasync"></a>saveAsync
`- (void)saveAsync:(nonnull void (^)(MCDUserNotificationUpdateStatus* _Nullable, NSError* _Nullable))completion;`

사용자 알림 변경 내용을 게시 하는 경우이 호출 해야 합니다. 앱을 UserNotification의 속성을 업데이트할 수 있는 수정 될 때마다이 메서드를 호출 해야 합니다.

#### <a name="parameters"></a>매개 변수
* `completion` 완료 될 때 실행할 코드 블록입니다.
