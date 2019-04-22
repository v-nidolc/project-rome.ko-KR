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
# <a name="class-mcdusernotificationreaderoptions"></a><span data-ttu-id="953cb-104">클래스 `MCDUserNotificationReaderOptions`</span><span class="sxs-lookup"><span data-stu-id="953cb-104">class `MCDUserNotificationReaderOptions`</span></span>

```
@interface MCDUserNotificationReaderOptions : NSObject
```

<span data-ttu-id="953cb-105">이 클래스를 사용 하면 앱 알림 판독기만 새 사용자 알림 및 존재 하지 않는 알림 업데이트를 받는 작업과 같은 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="953cb-105">This class allows the app to provide options on the notification reader, such as only receiving new user notifications and not existing notification updates.</span></span> 

## <a name="properties"></a><span data-ttu-id="953cb-106">속성</span><span class="sxs-lookup"><span data-stu-id="953cb-106">Properties</span></span>

### <a name="startposition"></a><span data-ttu-id="953cb-107">startPosition</span><span class="sxs-lookup"><span data-stu-id="953cb-107">startPosition</span></span>
<span data-ttu-id="953cb-108">`@property(nonatomic, assign) MCDUserNotificationReaderStartPosition startPosition;` 가져오거나 UserNotificationReaderOptions의이 인스턴스에 대 한 시작 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="953cb-108">`@property(nonatomic, assign) MCDUserNotificationReaderStartPosition startPosition;` Get or set the start position for this instance of UserNotificationReaderOptions.</span></span>

### <a name="statusfilter"></a><span data-ttu-id="953cb-109">statusFilter</span><span class="sxs-lookup"><span data-stu-id="953cb-109">statusFilter</span></span>
<span data-ttu-id="953cb-110">`@property(nonatomic, assign) MCDUserNotificationStatusFilter statusFilter;` 가져오거나 만들 하려는이 사용자 알림 판독기에 대 한 상태 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="953cb-110">`@property(nonatomic, assign) MCDUserNotificationStatusFilter statusFilter;` Get or set the status filter for this user notification reader you desire to create.</span></span>

### <a name="readstatefilter"></a><span data-ttu-id="953cb-111">readStateFilter</span><span class="sxs-lookup"><span data-stu-id="953cb-111">readStateFilter</span></span>
<span data-ttu-id="953cb-112">`@property(nonatomic, assign) MCDUserNotificationReadStateFilter readStateFilter;` Get 또는 set UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 읽기 상태 필터</span><span class="sxs-lookup"><span data-stu-id="953cb-112">`@property(nonatomic, assign) MCDUserNotificationReadStateFilter readStateFilter;` Get or set the read state filter that’s set for this instance of UserNotificationReaderOptions</span></span>

### <a name="useractionstatefilter"></a><span data-ttu-id="953cb-113">userActionStateFilter</span><span class="sxs-lookup"><span data-stu-id="953cb-113">userActionStateFilter</span></span>
<span data-ttu-id="953cb-114">`@property(nonatomic, assign) MCDUserNotificationUserActionStateFilter userActionStateFilter;` Getor는 UserNotificationReaderOptions의이 인스턴스에 대해 설정 된 사용자 동작 상태 필터를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="953cb-114">`@property(nonatomic, assign) MCDUserNotificationUserActionStateFilter userActionStateFilter;` Getor set  the user action state filter that’s set for this instance of UserNotificationReaderOptions.</span></span>

## <a name="constructors"></a><span data-ttu-id="953cb-115">생성자</span><span class="sxs-lookup"><span data-stu-id="953cb-115">Constructors</span></span>

### <a name="options"></a><span data-ttu-id="953cb-116">옵션</span><span class="sxs-lookup"><span data-stu-id="953cb-116">options</span></span>
<span data-ttu-id="953cb-117">`+ (nullable instancetype)options;` 만들고 사용자 알림에 대 한 옵션의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="953cb-117">`+ (nullable instancetype)options;` Creates and initializes a new instance of options for User Notifications.</span></span>