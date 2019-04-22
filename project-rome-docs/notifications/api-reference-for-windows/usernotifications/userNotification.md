---
title: UserNotification
description: 이 클래스에는 그래프 알림을 통해 앱 서버에서 게시 한 앱 클라이언트에서 받은 사용자 알림을 나타냅니다.
keywords: microsoft, windows, 그래프 알림 방법 windows
ms.openlocfilehash: 5f0489b9db0e644cd0dedd14b07bf2357615419f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801595"
---
# <a name="class-usernotification"></a><span data-ttu-id="bb7db-104">클래스 `UserNotification`</span><span class="sxs-lookup"><span data-stu-id="bb7db-104">class `UserNotification`</span></span>

```C#
public sealed class UserNotification : IUserNotification
```

<span data-ttu-id="bb7db-105">이 클래스는 단일 사용자 알림 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-105">This class represent a single user notification instance.</span></span> <span data-ttu-id="bb7db-106">사용자 알림 만들어지고 사용자가 로그인 한 사용자의 모든 장치 끝점에 배포를 목표로 앱 서버에서 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-106">A user notification is created and published by your app server targeted at a user, distributed to all device endpoints of the same logged in user.</span></span>
<span data-ttu-id="bb7db-107">앱 클라이언트에서 받은 후 사용자 알림을 생성 하 고 해당 되는 플랫폼에 대 한 로컬 알림을 Api를 사용 하 여 visual 알림 배너가 표시와 같은 환경에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-107">A user notification, once received by the app client, can result in experiences such as generating and showing a visual notification banner using local notification APIs of the corresponding platform.</span></span>

## <a name="properties"></a><span data-ttu-id="bb7db-108">속성</span><span class="sxs-lookup"><span data-stu-id="bb7db-108">Properties</span></span>

|<span data-ttu-id="bb7db-109">이름</span><span class="sxs-lookup"><span data-stu-id="bb7db-109">Name</span></span> | <span data-ttu-id="bb7db-110">설명</span><span class="sxs-lookup"><span data-stu-id="bb7db-110">Description</span></span> |
|:-- |:-- |
|<span data-ttu-id="bb7db-111">Id</span><span class="sxs-lookup"><span data-stu-id="bb7db-111">Id</span></span> |<span data-ttu-id="bb7db-112">지정 된 개발자 고유 가져옵니다이 사용자 알림에 대 한 id입니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-112">Gets the developer specified unique id for this user notification.</span></span>|
|   <span data-ttu-id="bb7db-113">GroupId</span><span class="sxs-lookup"><span data-stu-id="bb7db-113">GroupId</span></span> |<span data-ttu-id="bb7db-114">지정 된 개발자 가져옵니다이 사용자 알림에 대 한 그룹 id입니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-114">Gets the developer specified group id for this user notification.</span></span>| 
|   <span data-ttu-id="bb7db-115">ExpirationTime</span><span class="sxs-lookup"><span data-stu-id="bb7db-115">ExpirationTime</span></span> |<span data-ttu-id="bb7db-116">이 사용자 알림에 대 한 만료 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-116">Gets the expiration time for this user notification.</span></span>| 
|   <span data-ttu-id="bb7db-117">우선 순위</span><span class="sxs-lookup"><span data-stu-id="bb7db-117">Priority</span></span>|<span data-ttu-id="bb7db-118">지정 된 개발자 가져옵니다이 사용자 알림에 대 한 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-118">Gets the developer specified priority for this user notification.</span></span>| 
|   <span data-ttu-id="bb7db-119">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="bb7db-119">Content</span></span>|<span data-ttu-id="bb7db-120">임의의 데이터를 정의 하는 개발자는이 알림에 대 한 콘텐츠 페이로드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-120">Gets the content payload for this notification which is developer defined arbitrary data.</span></span>| 
|   <span data-ttu-id="bb7db-121">ReadState</span><span class="sxs-lookup"><span data-stu-id="bb7db-121">ReadState</span></span>|<span data-ttu-id="bb7db-122">알림을 읽거나 읽지 않은 메시지 인지 나타내는이 사용자 알림에 대 한 읽기 상태 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-122">Gets the value of the read state for this user notification that indicates the notification is read or unread.</span></span>| 
|   <span data-ttu-id="bb7db-123">UserActionState</span><span class="sxs-lookup"><span data-stu-id="bb7db-123">UserActionState</span></span>|<span data-ttu-id="bb7db-124">사용자 알림이 있는지 여부를 확인 알림을 하지 상호 작용, 해제, 활성화, 연기에 대 한 사용자 동작 상태 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-124">Gets the value of the user action state for a user notification to determine whether the notification is not interacted, dismissed, activated, or snoozed.</span></span>| 


## <a name="methods"></a><span data-ttu-id="bb7db-125">메서드</span><span class="sxs-lookup"><span data-stu-id="bb7db-125">Methods</span></span>

### <a name="saveasync"></a><span data-ttu-id="bb7db-126">SaveAsync()</span><span class="sxs-lookup"><span data-stu-id="bb7db-126">SaveAsync()</span></span> 
<span data-ttu-id="bb7db-127">사용자 알림 변경 내용을 게시 하는 경우이 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-127">This should be called when publishing user notification changes.</span></span> <span data-ttu-id="bb7db-128">앱을 UserNotification의 속성을 업데이트할 수 있는 수정 될 때마다이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb7db-128">This method should be called whenever the app modifies an updatable property of the UserNotification.</span></span>
```C#
public IAsyncOperation SaveAsync()
```

