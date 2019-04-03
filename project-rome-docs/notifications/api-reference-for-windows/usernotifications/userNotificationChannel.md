---
title: UserNotificationChannel
description: 이 클래스는 사용자 알림 수명 주기를 관리합니다.
keywords: microsoft, windows, 그래프 알림 및 방법 Windows
ms.openlocfilehash: ee30f0eab2bb212dddf1de401a91f0487c512705
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907485"
---
# <a name="class-usernotificationchannel"></a>클래스 `UserNotificationChannel`

```C#
public sealed class UserNotificationChannel : IUserNotificationChannel
```

이 클래스는 수신 및 응용 프로그램에 대 한 사용자 알림 관리를 처리 하는 알림 변경 판독기를 제공 합니다. 

## <a name="methods"></a>메서드

### <a name="createreader"></a>CreateReader() 
수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.
```C#
public UserNotificationReader CreateReader()
```

### <a name="createreaderusernotificationreaderoptions"></a>CreateReader(UserNotificationReaderOptions) 
옵션을 사용 하 여 사용자 알림 판독기 만들기 
```C#
public UserNotificationReader CreateReader(UserNotificationReaderOptions options)
```

### <a name="createreaderwithstatestring"></a>CreateReaderWithState(String) 
수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다. 판독기는 제공 된 추적 상태에 시작 됩니다. 
```C#
public UserNotificationReader CreateReaderWithState(String readerState)
```

### <a name="getusernotificationasyncstring"></a>GetUserNotificationAsync(String)
해당 id를 기준으로 사용자 알림을 받습니다. 
```C#
public IAsyncOperation<UserNotification> GetUserNotificationAsync(String notificationId)
```

### <a name="deleteusernotificationasyncstring"></a>DeleteUserNotificationAsync(String)
해당 id를 기준으로 사용자 알림을 받습니다. 
```C#
public IAsyncOperation<UserNotificationUpdateResult> DeleteUserNotificationAsync(String notificationId)
```

### <a name="syncscope"></a>SyncScope()
이 사용자 알림 채널의 동기화 범위를 가져옵니다.
```C#
public static IUserDataFeedSyncScope SyncScope()
```