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
# <a name="class-usernotificationchannel"></a><span data-ttu-id="f31c1-104">클래스 `UserNotificationChannel`</span><span class="sxs-lookup"><span data-stu-id="f31c1-104">class `UserNotificationChannel`</span></span>

```C#
public sealed class UserNotificationChannel : IUserNotificationChannel
```

<span data-ttu-id="f31c1-105">이 클래스는 수신 및 응용 프로그램에 대 한 사용자 알림 관리를 처리 하는 알림 변경 판독기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-105">This class provides the notification change reader which handles the receiving and management of user notifications for the application.</span></span> 

## <a name="methods"></a><span data-ttu-id="f31c1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f31c1-106">Methods</span></span>

### <a name="createreader"></a><span data-ttu-id="f31c1-107">CreateReader()</span><span class="sxs-lookup"><span data-stu-id="f31c1-107">CreateReader()</span></span> 
<span data-ttu-id="f31c1-108">수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-108">Create a user notification reader to receive and manage user notifications published by app server.</span></span>
```C#
public UserNotificationReader CreateReader()
```

### <a name="createreaderusernotificationreaderoptions"></a><span data-ttu-id="f31c1-109">CreateReader(UserNotificationReaderOptions)</span><span class="sxs-lookup"><span data-stu-id="f31c1-109">CreateReader(UserNotificationReaderOptions)</span></span> 
<span data-ttu-id="f31c1-110">옵션을 사용 하 여 사용자 알림 판독기 만들기</span><span class="sxs-lookup"><span data-stu-id="f31c1-110">Create a user notification reader with options</span></span> 
```C#
public UserNotificationReader CreateReader(UserNotificationReaderOptions options)
```

### <a name="createreaderwithstatestring"></a><span data-ttu-id="f31c1-111">CreateReaderWithState(String)</span><span class="sxs-lookup"><span data-stu-id="f31c1-111">CreateReaderWithState(String)</span></span> 
<span data-ttu-id="f31c1-112">수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-112">Create a user notification reader to receive and manage user notifications published by app server.</span></span> <span data-ttu-id="f31c1-113">판독기는 제공 된 추적 상태에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-113">The reader will start at the provided tracking state.</span></span> 
```C#
public UserNotificationReader CreateReaderWithState(String readerState)
```

### <a name="getusernotificationasyncstring"></a><span data-ttu-id="f31c1-114">GetUserNotificationAsync(String)</span><span class="sxs-lookup"><span data-stu-id="f31c1-114">GetUserNotificationAsync(String)</span></span>
<span data-ttu-id="f31c1-115">해당 id를 기준으로 사용자 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-115">Get a user notification based on its id.</span></span> 
```C#
public IAsyncOperation<UserNotification> GetUserNotificationAsync(String notificationId)
```

### <a name="deleteusernotificationasyncstring"></a><span data-ttu-id="f31c1-116">DeleteUserNotificationAsync(String)</span><span class="sxs-lookup"><span data-stu-id="f31c1-116">DeleteUserNotificationAsync(String)</span></span>
<span data-ttu-id="f31c1-117">해당 id를 기준으로 사용자 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-117">Get a user notification based on its id.</span></span> 
```C#
public IAsyncOperation<UserNotificationUpdateResult> DeleteUserNotificationAsync(String notificationId)
```

### <a name="syncscope"></a><span data-ttu-id="f31c1-118">SyncScope()</span><span class="sxs-lookup"><span data-stu-id="f31c1-118">SyncScope()</span></span>
<span data-ttu-id="f31c1-119">이 사용자 알림 채널의 동기화 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f31c1-119">Get the sync scope of this user notification channel.</span></span>
```C#
public static IUserDataFeedSyncScope SyncScope()
```