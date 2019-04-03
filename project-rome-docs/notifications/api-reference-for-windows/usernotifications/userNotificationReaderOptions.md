---
title: UserNotificationReaderOptions
description: 이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다.
keywords: microsoft, windows, 그래프 알림 및 방법 Windows
ms.openlocfilehash: dda9187dccd013f719d564f62b51fd9ac7be8444
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909685"
---
# <a name="class-usernotificationreaderoptions"></a><span data-ttu-id="36741-104">클래스 `UserNotificationReaderOptions`</span><span class="sxs-lookup"><span data-stu-id="36741-104">class `UserNotificationReaderOptions`</span></span>

```C#
public sealed class UserNotificationReaderOptions : IUserNotificationReaderOptions
```

<span data-ttu-id="36741-105">이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-105">This class allows the app to provide options on the notification reader, such as only receiving new user notifications and not existing notification updates.</span></span> 

## <a name="constructors"></a><span data-ttu-id="36741-106">생성자</span><span class="sxs-lookup"><span data-stu-id="36741-106">Constructors</span></span>

### <a name="usernotificationreaderoptions"></a><span data-ttu-id="36741-107">UserNotificationReaderOptions</span><span class="sxs-lookup"><span data-stu-id="36741-107">UserNotificationReaderOptions</span></span>
<span data-ttu-id="36741-108">만들고 UserNotificationReaderOptions의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-108">Creates and initializes a new instance of UserNotificationReaderOptions.</span></span>

```C#
public UserNotificationReaderOptions()
```

### <a name="usernotificationreaderoptionsusernotificationreaderstartposition-usernotificationstatusfilter-usernotificationreadstatefilter-usernotificationuseractionstatefilter"></a><span data-ttu-id="36741-109">UserNotificationReaderOptions(UserNotificationReaderStartPosition, UserNotificationStatusFilter, UserNotificationReadStateFilter, UserNotificationUserActionStateFilter)</span><span class="sxs-lookup"><span data-stu-id="36741-109">UserNotificationReaderOptions(UserNotificationReaderStartPosition, UserNotificationStatusFilter, UserNotificationReadStateFilter, UserNotificationUserActionStateFilter)</span></span>
<span data-ttu-id="36741-110">만들고 필터와 지정 된 시작 위치 UserNotificationReaderOptions의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-110">Creates and initializes a new instance of UserNotificationReaderOptions with filters and start position specified.</span></span> 

```C#
public UserNotificationReaderOptions(UserNotificationReaderStartPosition startPosition, UserNotificationStatusFilter statusFilter, UserNotificationReadStateFilter readStateFilter, UserNotificationUserActionStateFilter userActionStateFilter)
```

## <a name="properties"></a><span data-ttu-id="36741-111">속성</span><span class="sxs-lookup"><span data-stu-id="36741-111">Properties</span></span>

|<span data-ttu-id="36741-112">이름</span><span class="sxs-lookup"><span data-stu-id="36741-112">Name</span></span> | <span data-ttu-id="36741-113">설명</span><span class="sxs-lookup"><span data-stu-id="36741-113">Description</span></span> |
|:-- |:-- |
|<span data-ttu-id="36741-114">StartPosition</span><span class="sxs-lookup"><span data-stu-id="36741-114">StartPosition</span></span> |<span data-ttu-id="36741-115">가져오거나 UserNotificationReaderOptions의이 인스턴스에 대 한 시작 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-115">Get or set the start position for this instance of UserNotificationReaderOptions.</span></span>|
|   <span data-ttu-id="36741-116">StatusFilter</span><span class="sxs-lookup"><span data-stu-id="36741-116">StatusFilter</span></span> |<span data-ttu-id="36741-117">가져오거나 만들 하려는이 사용자 알림 판독기에 대 한 상태 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-117">Get or set the status filter for this user notification reader you desire to create.</span></span>| 
|   <span data-ttu-id="36741-118">ReadStateFilter</span><span class="sxs-lookup"><span data-stu-id="36741-118">ReadStateFilter</span></span> |<span data-ttu-id="36741-119">가져오거나 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 읽기 상태 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-119">Get or set the read state filter that’s set for this instance of UserNotificationReaderOptions.</span></span>| 
|   <span data-ttu-id="36741-120">UserActionStateFilter</span><span class="sxs-lookup"><span data-stu-id="36741-120">UserActionStateFilter</span></span>|<span data-ttu-id="36741-121">Getor는 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 사용자 동작 상태 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36741-121">Getor set  the user action state filter that’s set for this instance of UserNotificationReaderOptions.</span></span>| 




