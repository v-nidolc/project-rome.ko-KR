---
title: MCDUserDataFeedNotificationTypes
description: 이 클래스는 알림 유형을 제공 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 49f13fd2dbb13c439993f79a2b7275d4a705826a
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908915"
---
# <a name="class-mcduserdatafeednotificationtypes"></a><span data-ttu-id="878a5-104">클래스 `MCDUserDataFeedNotificationTypes`</span><span class="sxs-lookup"><span data-stu-id="878a5-104">class `MCDUserDataFeedNotificationTypes`</span></span>

```
@interface MCDUserDataFeedNotificationTypes : NSObject
```

<span data-ttu-id="878a5-105">이 클래스는 MCDUserDataFeedSyncScope.notificationType 유효한 알림 유형을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="878a5-105">This class provides the valid notification types for MCDUserDataFeedSyncScope.notificationType.</span></span>


## <a name="properties"></a><span data-ttu-id="878a5-106">속성</span><span class="sxs-lookup"><span data-stu-id="878a5-106">Properties</span></span>

### <a name="notificationwithpayload"></a><span data-ttu-id="878a5-107">notificationWithPayload</span><span class="sxs-lookup"><span data-stu-id="878a5-107">notificationWithPayload</span></span>
`@property(class, nonatomic, readonly, nonnull) NSString* notificationWithPayload;`

<span data-ttu-id="878a5-108">들어오는 푸시 알림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="878a5-108">Represents the incoming push notifications.</span></span>  <span data-ttu-id="878a5-109">도메인/서버 제한 이외의 푸시 알림을 없습니다 rescrictions 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="878a5-109">There are no rescrictions to push notifications other than domain/server restrictions.</span></span>

### <a name="notificationonly"></a><span data-ttu-id="878a5-110">notificationOnly</span><span class="sxs-lookup"><span data-stu-id="878a5-110">notificationOnly</span></span>
`@property(class, nonatomic, readonly, nonnull) NSString* notificationOnly;`

<span data-ttu-id="878a5-111">데이터 푸시 알림을 포함 될 수 있습니다 하는 경우에 데이터를 받는 동기화만 시스템을 알리는 알림 푸시 알림을 모든 수준을 내립니다.</span><span class="sxs-lookup"><span data-stu-id="878a5-111">Demote all push notifications to a notification only telling the system to sync to receive the data, even if the data could be contained in the push notification.</span></span>


### <a name="nonotification"></a><span data-ttu-id="878a5-112">noNotification</span><span class="sxs-lookup"><span data-stu-id="878a5-112">noNotification</span></span>
`@property(class, nonatomic, readonly, nonnull) NSString* noNotification;`

<span data-ttu-id="878a5-113">새 사용자 데이터에 대 한 모든 알림을 방지, UserDataFeed.startSync 호출 될 때 또는 다른 방법으로 서버와 상호 작용 하는 경우 새 데이터 수신</span><span class="sxs-lookup"><span data-stu-id="878a5-113">Prevent any notifications for new user data, only receive new data when UserDataFeed.startSync is called, or when interacting with the server in other ways</span></span>
