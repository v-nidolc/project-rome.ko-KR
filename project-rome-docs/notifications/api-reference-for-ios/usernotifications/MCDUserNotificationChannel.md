---
title: MCDUserNotificationChannel
description: 이 클래스는 사용자 알림 수명 주기를 관리합니다.
keywords: microsoft, windows, 릴레이 장치, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 234e1af807ac816918fe1de37a18dc07f73fca09
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907185"
---
# <a name="class-mcdusernotificationchannel"></a>클래스 `MCDUserNotificationChannel`

```
@interface MCDUserNotificationChannel : NSObject
```

이 클래스는 수신 및 응용 프로그램에 대 한 사용자 알림 관리를 처리 하는 알림 변경 판독기를 제공 합니다. 

## <a name="properties"></a>속성

### <a name="syncscope"></a>syncScope
`@property(class, readonly, nonnull) MCDUserDataFeedSyncScope* syncScope;`

SyncScope는 UserNotifications 피드에 포함 되도록 하는 데 사용 합니다.

## <a name="constructors"></a>생성자

### <a name="channelwithuserdatafeed"></a>channelWithUserDataFeed
`+ (nullable instancetype)channelWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

#### <a name="parameters"></a>매개 변수

### <a name="userdatafeed"></a>userDataFeed
MCDUserDataFeed이이 클래스를 초기화 하는 데 사용 합니다.

### <a name="initwithuserdatafeed"></a>initWithUserDataFeed
`- (nullable instancetype)initWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

### <a name="userdatafeed"></a>userDataFeed
MCDUserDataFeed이이 클래스를 초기화 하는 데 사용 합니다.

## <a name="methods"></a>메서드

### <a name="createreader"></a>createReader
`- (MCDUserNotificationReader* _Nullable)createReader`

수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.

### <a name="createreaderwithoptions"></a>createReaderWithOptions
`- (MCDUserNotificationReader* _Nullable)createReaderWithOptions:(MCDUserNotificationReaderOptions* _Nonnull)options`

옵션을 사용 하 여 사용자 알림 판독기를 만듭니다.

### <a name="createreaderwithstate"></a>createReaderWithState
`- (MCDUserNotificationReader* _Nullable)createReaderWithState:(NSString* _Nonnull)readerState`

수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다. 판독기는 제공 된 추적 상태에 시작 됩니다.  

### <a name="getusernotificationasync"></a>getUserNotificationAsync
`- (void)getUserNotificationAsync:(NSString* _Nonnull)notificationId
                      completion:(nonnull void (^)(MCDUserNotification* _Nullable, NSError* _Nullable))completion`

해당 id를 기준으로 사용자 알림을 받습니다.

### <a name="deleteusernotificationasync"></a>deleteUserNotificationAsync
```
- (void)deleteUserNotificationAsync:(NSString* _Nonnull)notificationId
                         completion:(nonnull void (^)(MCDUserNotificationUpdateResult* _Nullable, NSError* _Nullable))completion
```

해당 id를 기준으로 사용자 알림을 삭제 합니다. 