---
title: MCDUserNotificationReader
description: 이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다. 또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.
keywords: microsoft, windows, 릴레이 장치, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 486e98c30c82a7607569d252c84e4314738df6c9
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909025"
---
# <a name="class-mcdusernotificationreader"></a>클래스 `MCDUserNotificationReader`

```
@interface MCDUserNotificationReader : NSObject
```

이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다. 또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.  

## <a name="properties"></a>속성

### <a name="serializedstate"></a>serializedState
`@property(nonatomic, readonly, nonnull) NSString* serializedState;`

변경 판독기의 현재 상태를 반환합니다. 동일한 상태에서 시작 하는 새 판독기를 생성 하려면 사용할 수 있습니다.
알림 변경 내용 (또는 초기 상태, none 성공적으로 완료 하는 경우)의 마지막 완료 된 일괄 처리를 기반으로 합니다.

### <a name="datachanged"></a>dataChanged
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDUserNotificationReader*, MCDUserNotificationReaderDataChangedEventArgs*>* dataChanged;`

MCDUserNotificationReader에 대 한 이벤트 구독을 변경 합니다.

## <a name="methods"></a>메서드

### <a name="readbatchasyncwithmaxsize"></a>readBatchAsyncWithMaxSize
`- (void)readBatchAsyncWithMaxSize:(NSUInteger)maxBatchSize
                       completion:(nonnull void (^)(NSArray<MCDUserNotification*>* _Nullable, NSError* _Nullable))completion;`

일괄 처리에서 들어오는 새 알림 및 기존 알림 업데이트를 포함 하는 알림 변경 내용을 읽습니다.