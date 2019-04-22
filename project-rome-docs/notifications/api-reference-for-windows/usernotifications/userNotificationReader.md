---
title: UserNotificationReader
description: 이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다. 또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.
keywords: microsoft, windows, 사용자 알림 방법 windows
ms.openlocfilehash: 3a929939be7e2dd9ecd9db65322efadaea3013d5
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801425"
---
# <a name="class-usernotificationreader"></a><span data-ttu-id="0eead-105">클래스 `UserNotificationReader`</span><span class="sxs-lookup"><span data-stu-id="0eead-105">class `UserNotificationReader`</span></span>

```C#
public sealed class UserNotificationReader : IUserNotificationReader
```

<span data-ttu-id="0eead-106">이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eead-106">This class provides new incoming user notifications and user notification updates.</span></span> <span data-ttu-id="0eead-107">또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eead-107">It also provides access to the collection of user notifications persisted in the Connected Device Platform.</span></span>  

## <a name="methods"></a><span data-ttu-id="0eead-108">메서드</span><span class="sxs-lookup"><span data-stu-id="0eead-108">Methods</span></span>

### <a name="readbatchasyncint32"></a><span data-ttu-id="0eead-109">ReadBatchAsync(Int32)</span><span class="sxs-lookup"><span data-stu-id="0eead-109">ReadBatchAsync(Int32)</span></span> 
<span data-ttu-id="0eead-110">수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0eead-110">Create a user notification reader to receive and manage user notifications published by app server.</span></span>
```C#
public IAsyncOperation<IList<UserNotification>> ReadBatchAsync(Int32 maxBatchSize)
```

## <a name="events"></a><span data-ttu-id="0eead-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="0eead-111">Events</span></span>


### <a name="datachanged"></a><span data-ttu-id="0eead-112">DataChanged</span><span class="sxs-lookup"><span data-stu-id="0eead-112">DataChanged</span></span>
<span data-ttu-id="0eead-113">판독기가 서버와 동기화를 완료 하 고 새 변경-때 발생 새 들어오는 UserNotifications 또는 UserNotification 업데이트 앱에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0eead-113">Raised when the reader completes sync with the server and has new change - new incoming UserNotifications or UserNotification updates to notify the app.</span></span> 

```C#
public event TypedEventHandler<UserNotificationReader, DataChangedEventArgs> DataChanged
```
