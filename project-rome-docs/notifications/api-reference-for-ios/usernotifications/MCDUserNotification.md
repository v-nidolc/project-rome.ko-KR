---
title: MCDUserNotification
description: 이 클래스에는 그래프 알림을 통해 앱 서버에서 게시 한 앱 클라이언트에서 받은 사용자 알림을 나타냅니다.
keywords: microsoft, ios, 그래프 알림, ios 방법 도움말, 방법 iphone
ms.openlocfilehash: 5ca1360c34e2bf9aa5d9847b8df2c462e2956b31
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907895"
---
# <a name="class-mcdusernotification"></a><span data-ttu-id="f296b-104">클래스 `MCDUserNotification`</span><span class="sxs-lookup"><span data-stu-id="f296b-104">class `MCDUserNotification`</span></span>

```
@interface MCDUserNotification : NSObject
```


<span data-ttu-id="f296b-105">이 클래스는 단일 사용자 알림 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-105">This class represent a single user notification instance.</span></span> <span data-ttu-id="f296b-106">사용자 알림 만들어지고 사용자가 로그인 한 사용자의 모든 장치 끝점에 배포를 목표로 앱 서버에서 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-106">A user notification is created and published by your app server targeted at a user, distributed to all device endpoints of the same logged in user.</span></span>
<span data-ttu-id="f296b-107">앱 클라이언트에서 받은 후 사용자 알림을 생성 하 고 해당 되는 플랫폼에 대 한 로컬 알림을 Api를 사용 하 여 visual 알림 배너가 표시와 같은 환경에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-107">A user notification, once received by the app client, can result in experiences such as generating and showing a visual notification banner using local notification APIs of the corresponding platform.</span></span>

## <a name="properties"></a><span data-ttu-id="f296b-108">속성</span><span class="sxs-lookup"><span data-stu-id="f296b-108">Properties</span></span>

### <a name="notificationid"></a><span data-ttu-id="f296b-109">notificationId</span><span class="sxs-lookup"><span data-stu-id="f296b-109">notificationId</span></span>
<span data-ttu-id="f296b-110">`@property(nonatomic, readonly, nonnull) NSString* notificationId;` 지정 된 개발자 고유 가져옵니다이 사용자 알림에 대 한 id입니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-110">`@property(nonatomic, readonly, nonnull) NSString* notificationId;` Gets the developer specified unique id for this user notification.</span></span>

### <a name="groupid"></a><span data-ttu-id="f296b-111">groupId</span><span class="sxs-lookup"><span data-stu-id="f296b-111">groupId</span></span>
<span data-ttu-id="f296b-112">`@property(nonatomic, readonly, nonnull) NSString* groupId;` 지정 된 개발자 가져옵니다이 사용자 알림에 대 한 그룹 id입니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-112">`@property(nonatomic, readonly, nonnull) NSString* groupId;` Gets the developer specified group id for this user notification.</span></span>

### <a name="expirationtime"></a><span data-ttu-id="f296b-113">expirationTime</span><span class="sxs-lookup"><span data-stu-id="f296b-113">expirationTime</span></span>
<span data-ttu-id="f296b-114">`@property(nonatomic, readonly, nonnull) NSDate* expirationTime;` 이 사용자 알림에 대 한 만료 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-114">`@property(nonatomic, readonly, nonnull) NSDate* expirationTime;` Gets the expiration time for this user notification.</span></span>

### <a name="status"></a><span data-ttu-id="f296b-115">상태</span><span class="sxs-lookup"><span data-stu-id="f296b-115">status</span></span>
<span data-ttu-id="f296b-116">`@property(nonatomic, readonly) MCDUserNotificationStatus status;` 사용자 알림 메시지의 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-116">`@property(nonatomic, readonly) MCDUserNotificationStatus status;` Gets the status of the user notification.</span></span>

### <a name="changetime"></a><span data-ttu-id="f296b-117">changeTime</span><span class="sxs-lookup"><span data-stu-id="f296b-117">changeTime</span></span>
<span data-ttu-id="f296b-118">`@property(nonatomic, readonly, nonnull) NSDate* changeTime;` 변경 된 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-118">`@property(nonatomic, readonly, nonnull) NSDate* changeTime;` Gets the time the change was made.</span></span>

### <a name="priority"></a><span data-ttu-id="f296b-119">priority</span><span class="sxs-lookup"><span data-stu-id="f296b-119">priority</span></span>
<span data-ttu-id="f296b-120">`@property(nonatomic, readonly) MCDUserNotificationPriority priority;` 지정 된 개발자 가져옵니다이 사용자 알림에 대 한 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-120">`@property(nonatomic, readonly) MCDUserNotificationPriority priority;` Gets the developer specified priority for this user notification.</span></span>

### <a name="content"></a><span data-ttu-id="f296b-121">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f296b-121">content</span></span>
<span data-ttu-id="f296b-122">`@property(nonatomic, readonly, nonnull) NSString* content;` 임의의 데이터를 정의 하는 개발자는이 알림에 대 한 콘텐츠 페이로드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-122">`@property(nonatomic, readonly, nonnull) NSString* content;` Gets the content payload for this notification which is developer defined arbitrary data.</span></span>

###  <a name="readstate"></a><span data-ttu-id="f296b-123">readState</span><span class="sxs-lookup"><span data-stu-id="f296b-123">readState</span></span>
<span data-ttu-id="f296b-124">`@property(nonatomic, assign, readwrite) MCDUserNotificationReadState readState;` 알림을 읽거나 읽지 않은 메시지 인지 나타내는이 사용자 알림에 대 한 읽기 상태 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-124">`@property(nonatomic, assign, readwrite) MCDUserNotificationReadState readState;` Gets the value of the read state for this user notification that indicates the notification is read or unread.</span></span>

### <a name="useractionstate"></a><span data-ttu-id="f296b-125">userActionState</span><span class="sxs-lookup"><span data-stu-id="f296b-125">userActionState</span></span>
<span data-ttu-id="f296b-126">`@property(nonatomic, assign, readwrite) MCDUserNotificationUserActionState userActionState;` 사용자 알림이 있는지 여부를 확인 알림을 하지 상호 작용, 해제, 활성화, 연기에 대 한 사용자 동작 상태 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-126">`@property(nonatomic, assign, readwrite) MCDUserNotificationUserActionState userActionState;` Gets the value of the user action state for a user notification to determine whether the notification is not interacted, dismissed, activated, or snoozed.</span></span> 

## <a name="methods"></a><span data-ttu-id="f296b-127">메서드</span><span class="sxs-lookup"><span data-stu-id="f296b-127">Methods</span></span>

### <a name="saveasync"></a><span data-ttu-id="f296b-128">saveAsync</span><span class="sxs-lookup"><span data-stu-id="f296b-128">saveAsync</span></span>
`- (void)saveAsync:(nonnull void (^)(MCDUserNotificationUpdateStatus* _Nullable, NSError* _Nullable))completion;`

<span data-ttu-id="f296b-129">사용자 알림 변경 내용을 게시 하는 경우이 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-129">This should be called when publishing user notification changes.</span></span> <span data-ttu-id="f296b-130">앱을 UserNotification의 속성을 업데이트할 수 있는 수정 될 때마다이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-130">This method should be called whenever the app modifies an updatable property of the UserNotification.</span></span>

#### <a name="parameters"></a><span data-ttu-id="f296b-131">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f296b-131">Parameters</span></span>
* <span data-ttu-id="f296b-132">`completion` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="f296b-132">`completion` The code block to execute upon completion.</span></span>
