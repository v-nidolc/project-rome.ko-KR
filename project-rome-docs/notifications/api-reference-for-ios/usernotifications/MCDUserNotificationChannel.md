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
# <a name="class-mcdusernotificationchannel"></a><span data-ttu-id="672e8-104">클래스 `MCDUserNotificationChannel`</span><span class="sxs-lookup"><span data-stu-id="672e8-104">class `MCDUserNotificationChannel`</span></span>

```
@interface MCDUserNotificationChannel : NSObject
```

<span data-ttu-id="672e8-105">이 클래스는 수신 및 응용 프로그램에 대 한 사용자 알림 관리를 처리 하는 알림 변경 판독기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-105">This class provides the notification change reader which handles the receiving and management of user notifications for the application.</span></span> 

## <a name="properties"></a><span data-ttu-id="672e8-106">속성</span><span class="sxs-lookup"><span data-stu-id="672e8-106">Properties</span></span>

### <a name="syncscope"></a><span data-ttu-id="672e8-107">syncScope</span><span class="sxs-lookup"><span data-stu-id="672e8-107">syncScope</span></span>
`@property(class, readonly, nonnull) MCDUserDataFeedSyncScope* syncScope;`

<span data-ttu-id="672e8-108">SyncScope는 UserNotifications 피드에 포함 되도록 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-108">SyncScope used to ensure UserNotifications are included in the feed.</span></span>

## <a name="constructors"></a><span data-ttu-id="672e8-109">생성자</span><span class="sxs-lookup"><span data-stu-id="672e8-109">Constructors</span></span>

### <a name="channelwithuserdatafeed"></a><span data-ttu-id="672e8-110">channelWithUserDataFeed</span><span class="sxs-lookup"><span data-stu-id="672e8-110">channelWithUserDataFeed</span></span>
`+ (nullable instancetype)channelWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

#### <a name="parameters"></a><span data-ttu-id="672e8-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="672e8-111">Parameters</span></span>

### <a name="userdatafeed"></a><span data-ttu-id="672e8-112">userDataFeed</span><span class="sxs-lookup"><span data-stu-id="672e8-112">userDataFeed</span></span>
<span data-ttu-id="672e8-113">MCDUserDataFeed이이 클래스를 초기화 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-113">The MCDUserDataFeed used to initialize this class.</span></span>

### <a name="initwithuserdatafeed"></a><span data-ttu-id="672e8-114">initWithUserDataFeed</span><span class="sxs-lookup"><span data-stu-id="672e8-114">initWithUserDataFeed</span></span>
`- (nullable instancetype)initWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

### <a name="userdatafeed"></a><span data-ttu-id="672e8-115">userDataFeed</span><span class="sxs-lookup"><span data-stu-id="672e8-115">userDataFeed</span></span>
<span data-ttu-id="672e8-116">MCDUserDataFeed이이 클래스를 초기화 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-116">The MCDUserDataFeed used to initialize this class.</span></span>

## <a name="methods"></a><span data-ttu-id="672e8-117">메서드</span><span class="sxs-lookup"><span data-stu-id="672e8-117">Methods</span></span>

### <a name="createreader"></a><span data-ttu-id="672e8-118">createReader</span><span class="sxs-lookup"><span data-stu-id="672e8-118">createReader</span></span>
`- (MCDUserNotificationReader* _Nullable)createReader`

<span data-ttu-id="672e8-119">수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-119">Create a user notification reader to receive and manage user notifications published by app server.</span></span>

### <a name="createreaderwithoptions"></a><span data-ttu-id="672e8-120">createReaderWithOptions</span><span class="sxs-lookup"><span data-stu-id="672e8-120">createReaderWithOptions</span></span>
`- (MCDUserNotificationReader* _Nullable)createReaderWithOptions:(MCDUserNotificationReaderOptions* _Nonnull)options`

<span data-ttu-id="672e8-121">옵션을 사용 하 여 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-121">Create a user notification reader with options.</span></span>

### <a name="createreaderwithstate"></a><span data-ttu-id="672e8-122">createReaderWithState</span><span class="sxs-lookup"><span data-stu-id="672e8-122">createReaderWithState</span></span>
`- (MCDUserNotificationReader* _Nullable)createReaderWithState:(NSString* _Nonnull)readerState`

<span data-ttu-id="672e8-123">수신 응용 프로그램 서버에서 게시 하는 사용자 알림을 관리 하는 사용자 알림 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-123">Create a user notification reader to receive and manage user notifications published by app server.</span></span> <span data-ttu-id="672e8-124">판독기는 제공 된 추적 상태에 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-124">The reader will start at the provided tracking state.</span></span>  

### <a name="getusernotificationasync"></a><span data-ttu-id="672e8-125">getUserNotificationAsync</span><span class="sxs-lookup"><span data-stu-id="672e8-125">getUserNotificationAsync</span></span>
`- (void)getUserNotificationAsync:(NSString* _Nonnull)notificationId
                      completion:(nonnull void (^)(MCDUserNotification* _Nullable, NSError* _Nullable))completion`

<span data-ttu-id="672e8-126">해당 id를 기준으로 사용자 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-126">Get a user notification based on its id.</span></span>

### <a name="deleteusernotificationasync"></a><span data-ttu-id="672e8-127">deleteUserNotificationAsync</span><span class="sxs-lookup"><span data-stu-id="672e8-127">deleteUserNotificationAsync</span></span>
```
- (void)deleteUserNotificationAsync:(NSString* _Nonnull)notificationId
                         completion:(nonnull void (^)(MCDUserNotificationUpdateResult* _Nullable, NSError* _Nullable))completion
```

<span data-ttu-id="672e8-128">해당 id를 기준으로 사용자 알림을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="672e8-128">Delete a user notification based on its id.</span></span> 