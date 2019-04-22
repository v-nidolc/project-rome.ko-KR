---
title: 그래프 알림을 사용 하 여 Android 앱을 통합합니다.
description: 알림에 대 한 수신 끝점에 필요한 등록 단계를 수행 하는 방법에 앱 서버에서 게시 합니다.
ms.assetid: c973d534-08e9-4f6e-8b54-bcae97067961
ms.localizationpriority: medium
ms.custom: seodec18
ms.openlocfilehash: 69084d2a3ac99445c8c1919b7dc4748de865153e
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801205"
---
# <a name="how-to-guide-integrating-with-graph-notifications-android"></a><span data-ttu-id="a3ed3-103">방법 가이드: 그래프 알림 (Android)를 사용 하 여 통합</span><span class="sxs-lookup"><span data-stu-id="a3ed3-103">How-To Guide: Integrating with Graph Notifications (Android)</span></span>

<span data-ttu-id="a3ed3-104">그래프 알림을 보내고 여러 장치에서 사용자를 대상으로 알림을 관리 앱을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-104">Graph Notifications enable your app to send and manage user-targeting notifications across multiple devices.</span></span> 

<span data-ttu-id="a3ed3-105">Android에서 프로젝트 로마 클라이언트 쪽 SDK를 사용 하 여 Android 앱에 로그인된 한 사용자를 대상으로 앱 서버에서 게시 알림을 받도록 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-105">With the Project Rome client-side SDK on Android, your Android app can register to receive notifications published from your app server targeted at a logged in user.</span></span> <span data-ttu-id="a3ed3-106">SDK을 사용 하면 앱 클라이언트가 들어오는 새 알림 페이로드를 수신 하려면 기존 알림 및 검색 알림 기록의 상태를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-106">The SDK enables the app client to receive new incoming notification payloads, manage the state of the existing notifications, and retreive notification history.</span></span> <span data-ttu-id="a3ed3-107">알림 및이 통해 사람이 중심 알림을 배달 하는 방법에 대 한 자세한 내용은 참조 하세요. [Microsoft Graph 알림 개요](index.md)</span><span class="sxs-lookup"><span data-stu-id="a3ed3-107">For more information about Notifications and how it enables human-centric notification delivery, see [Microsoft Graph Notifications Overview](index.md)</span></span>

<span data-ttu-id="a3ed3-108">프로젝트 로마 SDK includng 그래프 알림 등의 모든 기능이 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼 위에 구축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-108">All features in the Project Rome SDK, includng Graph Notifications and more, are built on top of an underlying platform called the Connected Devices Platform.</span></span> <span data-ttu-id="a3ed3-109">이 가이드에 연결 된 장치 플랫폼을 사용 하 여 시작 하려면 그래프 알림을 구현 하는 SDK의 Api를 사용 하는 방법에 설명 하는 데 필요한 단계를 안내 합니다-특정 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-109">This guide is designed to guide you through the necessary steps to get started using the Connected Devices Platform, and to explain how to consume APIs in the SDK to implement Graph Notifications -specific features.</span></span>

<span data-ttu-id="a3ed3-110">참조 된 [API 참조](api-reference-for-android.md) 알림 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-110">See the [API reference](api-reference-for-android.md) page for links to the reference docs relevant to notification scenarios.</span></span>

<span data-ttu-id="a3ed3-111">이 단계 아래에서 코드 참조는 [프로젝트 로마 Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-111">This steps below will reference code from the [Project Rome Android sample app](https://github.com/Microsoft/project-rome/tree/master/Android/samples).</span></span>

[!INCLUDE [android/dev-reqs](../includes/android/dev-reqs.md)]

[!INCLUDE [android/preliminary-setup](../includes/android/preliminary-setup.md)]

[!INCLUDE [android/auth-scopes](../includes/auth-scopes.md)]

[!INCLUDE [android/dev-center-onboarding](../includes/android/notifications-dev-center-onboarding.md)]


## <a name="initialize-a-graph-notification-channel"></a><span data-ttu-id="a3ed3-112">그래프 알림 채널을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-112">Initialize a Graph Notification channel</span></span>
<span data-ttu-id="a3ed3-113">프로젝트 로마 SDK에는 앱을을 수신 하 고 다양 한 유형의 사용자 활동 그래프 알림 등을 포함 하 여 사용자 데이터를 관리 하기 위해 다른 채널을 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-113">The Project Rome SDK allows your app to subscribe to different channels in order to receive and manage various types of user data – including Graph Notifications, User Activities, and more.</span></span> <span data-ttu-id="a3ed3-114">모두 저장 하 고 동기화에서 이들은 **UserDataFeed**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-114">These are all stored and synced in **UserDataFeed**.</span></span> <span data-ttu-id="a3ed3-115">**UserNotification** 사용자 대상 알림 전송 그래프 알림을 통해 해당 클래스 및 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-115">**UserNotification** is the class and data type corresponding to a user-targeted notification sent via Graph Notifications.</span></span> <span data-ttu-id="a3ed3-116">그래프 알림 및 앱 서버에서 게시 UserNotification 받기 시작와를 통합 하려면 먼저 피드를 만들어서 사용자 데이터를 초기화 하는 **UserNotificationChannel**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-116">To integrate with Graph Notification and start receiving UserNotification published by your app server, you will first need to initialize the user data feed by creating a **UserNotificationChannel**.</span></span> <span data-ttu-id="a3ed3-117">위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-117">You should treat this like the platform initialization step above: it should be checked and possibly redone whenever the app comes to the foreground (but not before platform initialization).</span></span> 

<span data-ttu-id="a3ed3-118">다음 메서드 초기화를 **UserNotificationChannel**합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-118">The following methods initialize a **UserNotificationChannel**.</span></span>

```Java
private UserNotificationChannel mNotificationChannel;
private UserDataFeed mUserDataFeed;

// ...

/**
 * Initializes the UserNotificationFeed.
 */
public void initializeUserNotificationFeed() {

    // define what scope of data this app needs
    SyncScope[] scopes = { UserNotificationChannel.getSyncScope() };

    // Get a reference to the UserDataFeed. This method is defined below
    mUserDataFeed = getUserDataFeed(scopes, new EventListener<UserDataFeed, Void>() {
        @Override
        public void onEvent(UserDataFeed userDataFeed, Void aVoid) {
            if (userDataFeed.getSyncStatus() == UserDataSyncStatus.SYNCHRONIZED) {
                // log synchronized.
            } else {
                // log synchronization not completed.
            }
        }
    });

    // this method is defined below
    mNotificationChannel = getUserNotificationChannel();
}

// instantiate the UserDataFeed
private UserDataFeed getUserDataFeed(SyncScope[] scopes, EventListener<UserDataFeed, Void> listener) {
    UserAccount[] accounts = AccountProviderBroker.getSignInHelper().getUserAccounts();
    if (accounts.length <= 0) {
        // notify the user that sign-in is required
        return null;
    }

    // use the initialized Platform instance, along with the cross-device app ID.
    UserDataFeed feed = UserDataFeed.getForAccount(accounts[0], PlatformBroker.getPlatform(), Secrets.APP_HOST_NAME);
    feed.addSyncStatusChangedListener(listener);
    feed.addSyncScopes(scopes);
    // sync data with the server
    feed.startSync();
    return feed;
}

// use the UserDataFeed reference to create a UserActivityChannel
@Nullable
private UserNotificationChannel getUserNotificationChannel() {
    UserNotificationChannel channel = null;
    try {
        // create a UserNotificationChannel for the signed in account
        channel = new UserNotificationChannel(mUserDataFeed);
    } catch (Exception e) {
        e.printStackTrace();
        // handle exception
    }
    return channel;
}
```
<span data-ttu-id="a3ed3-119">이 시점에서 해야는 **UserNotificationChannel** 에서 참조할 `mNotificationChannel`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-119">At this point, you should have a **UserNotificationChannel** reference in `mNotificationChannel`.</span></span>

## <a name="create-a-usernotificationreader-to-receive-incoming-usernotifications-and-access-usernotification-history"></a><span data-ttu-id="a3ed3-120">들어오는 UserNotifications 받고 UserNotification 기록에 액세스 하려면 UserNotificationReader 만들기</span><span class="sxs-lookup"><span data-stu-id="a3ed3-120">Create a UserNotificationReader to receive incoming UserNotifications and access UserNotification history</span></span>
<span data-ttu-id="a3ed3-121">도착 초기 Google Cloud Messaging 알림이 이전에 살펴보았습니다 앱 클라이언트만 포함 하면 자격 증명 입력을 탭 한 번 및 사용 하 여 전체 동기화를 수행 하려면 SDK를 트리거하기 위해 연결 된 장치 플랫폼에 해당 자격 증명 입력 탭 페이로드를 전달 해야 합니다 앱 서버에서 게시 된 모든 UserNotifications를 포함 하는 장치 서버를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-121">As we showed previously, the initial Google Cloud Messaging notification arriving on the app client only contains a shoulder tap, and you need to pass that shoulder tap payload to the Connected Devices Platform in order to trigger the SDK to perform a full sync with the Connected Device server, which contains all the UserNotifications published by your app server.</span></span> <span data-ttu-id="a3ed3-122">이 자격 증명 입력 탭에 해당 앱 서버에서 게시 된 모든 알림 페이로드를 가져오게 됩니다. (및 경우에서 이전의 모든 알림이 게시 되었지만 장치 연결 또는 기타 문제로 인해이 응용 프로그램 클라이언트에서 수신 하지 됩니다. 가져온도).</span><span class="sxs-lookup"><span data-stu-id="a3ed3-122">This will pull down the full notification payload published by your app server corresponding to this shoulder tap (and in case if any previous notifications were published but not received on this app client due to device connectivity or other issues, they will be pulled down as well).</span></span> <span data-ttu-id="a3ed3-123">SDK에서 지속적으로 수행 되어 이러한 실시간 동기화를 사용 하 여 응용 프로그램 클라이언트는이 로그인 한 사용자의 UserNotification 데이터 피드의 로컬 캐시에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-123">With these real-time syncs constantly performed by the SDK, the app client is able to have access to a local cache of this logged-in user’s UserNotification data feed.</span></span> <span data-ttu-id="a3ed3-124">UserNotificationReader에는 경우이 데이터 피드에 – 앱 클라이언트의 액세스할 수 있도록 이벤트 수신기를 통해 최신 알림 페이로드 또는 사용자의 알림 기록은의 뷰 모델로 사용할 수 있는 전체 UserNotification 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-124">A UserNotificationReader in this case enables the app client’s access to this data feed – to receive latest notification payload via event listener, or to access the full UserNotification collection which can be used as view model of the user’s notification history.</span></span>  
### <a name="receiving-usernotifications"></a><span data-ttu-id="a3ed3-125">UserNotifications 받기</span><span class="sxs-lookup"><span data-stu-id="a3ed3-125">Receiving UserNotifications</span></span>
<span data-ttu-id="a3ed3-126">먼저 UserNotificationReader, 인스턴스화 및 사용 하도록 설정 하려는 환경에 대 한 정보를 사용 하려는 경우 판독기에는 모든 기존 UserNotifications 이미 가져오기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-126">First you need to instantiate a UserNotificationReader, and get all the existing UserNotifications already in the reader if you are interested in consuming that information for the experience you are trying to enable.</span></span> <span data-ttu-id="a3ed3-127">항상 앱 서버에 이미 게시 한다는 알림을이 경우에이 특정 장치 끝점 설정 되지 않을 수 있습니다는 사용자를 로그인 또는 사용자가 앱을 설치 하는 첫 번째 끝점을 가정 하에 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-127">It’s safe to always assume that the app server has already published notifications to this logged in user, given that this particular device endpoint might not be the only or the first endpoint that the user has installed your app.</span></span> 
```Java
private static UserNotificationReader mReader;
private static final ArrayList<UserNotification> mHistoricalNotifications = new ArrayList<>();
// Instantiate UserNotificationReader
UserNotificationReaderOptions options = new UserNotificationReaderOptions();
mReader = mNotificationChannel.createReaderWithOptions(options);
// Read any previously published UserNotifications that have not expired yet
mReader.readBatchAsync(Long.MAX_VALUE).thenAccept(new AsyncOperation.ResultConsumer<UserNotification[]>() {
    @Override
    public void accept(UserNotification[] userNotifications) throws Throwable {
        synchronized (mHistoricalNotifications) {
            for (UserNotification notification : userNotifications) {
                if (notification.getReadState() == UserNotificationReadState.UNREAD) {
                    mHistoricalNotifications.add(notification);
                }
            }
        }
 
        if (RunnableManager.getHistoryUpdated() != null) {
            activity.runOnUiThread(RunnableManager.getHistoryUpdated());
        }
    }
});

```
<span data-ttu-id="a3ed3-128">이제 연결 된 장치 플랫폼 동기화를 완료 하 고 알리는 새 변경 될 때 트리거되는 이벤트 수신기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-128">Now, add an event listener which gets triggered when the Connected Device Platform completes a sync and has new changes to notify you about.</span></span> <span data-ttu-id="a3ed3-129">그래프 알림의 경우 새 변경 내용을 새 수 만료 또는 다른 서버에서 발생 하는 동일한 사용자가 로그인 하는 끝점을 등록 및 앱 서버나 UserNotifcation 업데이트, 삭제에서 들어오는 UserNotifications 게시 .</span><span class="sxs-lookup"><span data-stu-id="a3ed3-129">In the case of Graph Notifications, new changes could be new incoming UserNotifications published by your app server, or UserNotifcation updates, deletions, and expirations that happened from the server or from other registered endpoints that the same user logged in.</span></span> 
> [!TIP] 
> <span data-ttu-id="a3ed3-130">이 이벤트 수신기에는 기본 비즈니스 논리를 처리 하 고 "사용" 시나리오에 따라 알림 페이로드 콘텐츠 위치는입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-130">This event listener is where you handle the main business logic and “consume” the content of your notification payload based on your scenarios.</span></span> <span data-ttu-id="a3ed3-131">현재 OS 수준 알림 트레이에 visual 알림을 생성 하려면 Google Cloud Messaging의 데이터 메시지를 사용 하는 경우, 일부 앱에서 UI를 업데이트 하려면 알림 영역에서 콘텐츠를 사용 하는 경우 작업을 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-131">If you currently use Google Cloud Messaging’s data message to construct a visual notification in the OS-level notification tray, or if you use the content in the notification to update some in-app UI, this is the place to do that.</span></span> 
```Java
mReader.addDataChangedListener(new EventListener<UserNotificationReader, Void>() {
    @Override
    public void onEvent(UserNotificationReader userNotificationReader, Void aVoid) {
        userNotificationReader.readBatchAsync(Long.MAX_VALUE).thenAccept(new AsyncOperation.ResultConsumer<UserNotification[]>() {
        @Override
        public void accept(UserNotification[] userNotifications) throws Throwable {
            boolean updatedNew = false;
            boolean updatedHistorical = false;
            synchronized (sHistoricalNotifications) {
                for (final UserNotification notification : userNotifications) {
                    if (notification.getStatus() == UserNotificationStatus.ACTIVE && notification.getReadState() == UserNotificationReadState.UNREAD) {
                        switch (notification.getUserActionState()) {
                            case NO_INTERACTION:
                                // Brand new notification
                                // Insert business logic to construct a new visual notification in Android notification tray for the user to see
                                // ...
                            case DISMISSED:
                                // Existing notification that is marked as dismissed
                                // An app client receive this type of changes because another app client logged in by the same user has marked the notification as dismissed and the change is fanned-out to everywhere
                                // This state sync across app clients on different devices enable universal dismiss of notifications and other scenarios across multiple devices owned by the same user
                                // Insert business logic to dismiss the corresponding visual notification inside Android system notification tray, to make sure users don’t have to deal with redundant information across devices, and potentially insert this notification in your app’s notification history view
                                // ...
                            default:
                                // Unexpected
                        }
                    } else {
                        // ...
                    }
                }
            }
        }
    });
}
});

```
## <a name="update-the-state-of-an-existing-usernotification"></a><span data-ttu-id="a3ed3-132">기존 UserNotification의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-132">Update the state of an existing UserNotification</span></span>
<span data-ttu-id="a3ed3-133">이전 섹션에서 설명한 대로 따라 판독기를 통해 받은 UserNotification 변경 수는 기존 UserNotification –에서 상태 업데이트를으로 표시 되거나 해제 된 읽음으로 표시 되 고 되는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-133">In the previous section, we mentioned that sometimes a UserNotification change received through the reader could be a state update on an existing UserNotification – whether that’s being marked as dismissed or marked as read.</span></span> <span data-ttu-id="a3ed3-134">이 경우 응용 프로그램 클라이언트를 선택할 수를 유니버설 예를 들어이 특정 장치에서 해당 visual 알림을 제거 하 여 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-134">In this case, the app client can choose what to do, such as enabling universal dismiss by removing the corresponding visual notification on this particular device.</span></span> <span data-ttu-id="a3ed3-135">다시 단계에서 확인 하 고 앱 클라이언트 경우가이 UserNotification 변경 업데이트를 시작 하려면 – 다른 장치에서 시작 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-135">Taking a step back, your app client is often the one that initiated this UserNotification change update to begin with – from a different device.</span></span> <span data-ttu-id="a3ed3-136">프로그램 UserNotifications의 상태를 업데이트 하는 시간을 선택할 수 있지만 일반적으로 이러한 업데이트 해당 visual 알림을 해당 장치에서 사용자에 의해 처리 됩니다. 때나 알림을 사용 하도록 설정 하면 일부 앱 내 환경에서 사용자가 추가로 처리 됩니다. .</span><span class="sxs-lookup"><span data-stu-id="a3ed3-136">You can choose the time to update the state of your UserNotifications, but usually they get updated when the corresponding visual notification is handled by the user on that device, or the notification is further handled by the user in some in-app experience you enable.</span></span> <span data-ttu-id="a3ed3-137">흐름은 모양을의 예는 다음과 같습니다. 앱 서버 1. 사용자는 자신의 PC 및 앱 클라이언트를 설치할 자신의 휴대폰에서이 알림을 받으면 사용자를 대상으로 알림을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-137">Here is an example of what the flow would look like: Your app server publishes a notification targeted at User A. User A receives this notification on both his PC and his phone where the app clients are installed.</span></span> <span data-ttu-id="a3ed3-138">PC에서 알림을 클릭 하 고 해당 작업 핸들을 앱에가 하는 사용자.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-138">The user clicks on the notification on PC, and chases into the app to handles the corresponding task.</span></span> <span data-ttu-id="a3ed3-139">그런 다음이 PC에 앱 클라이언트에 연결 된 장치 플랫폼 SDK이 모든이 사용자의이 장치 간에 동기화이 업데이트를 위해서는 해당 UserNotification의 상태를 업데이트 하려면 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-139">The app client on this PC will then call into Connected Devices Platform SDK to update the state of the corresponding UserNotification in order to have this update synced across all this user’s devices.</span></span> <span data-ttu-id="a3ed3-140">이 받으면 다른 앱 클라이언트를 실시간으로 업데이트 상태는 다음 해당 시각적 경고가 제거 / 메시지 / 장치의 알림 센터 알림 / 알림 트레이 작업 센터 /입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-140">The other app clients, upon receiving this state update in real-time, will then remove the corresponding visual alert / message / toast notification from the device’s notification center / notification tray / Action Center.</span></span> <span data-ttu-id="a3ed3-141">사용자의 장치에서 알림을 해제 보편적으로 가져오기 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-141">This is how notifications get universally dismissed across a user’s devices.</span></span> 

> [!TIP] 
> <span data-ttu-id="a3ed3-142">UserNotification 클래스에는 현재 두 가지 유형의 상태 업데이트 제공 –는 UserNotificationReadState 또는 UserNotificationUserActionState 수정 하 고 알림을 업데이트 될 때 수행할 동작에 고유한 논리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-142">UserNotification class currently provides 2 types of state updates – you can modify the UserNotificationReadState or the UserNotificationUserActionState and define your own logic on what should happen when notifications are updated.</span></span> <span data-ttu-id="a3ed3-143">예를 들어 UserActionState Activated 또는 해제를 표시할 수 있습니다 및 universal를 구현 하는 값에서 피벗 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-143">For example, you can mark UserActionState to be Activated or Dismissed, and pivot on that value to implement universal dismiss.</span></span> <span data-ttu-id="a3ed3-144">또는 읽기 또는 읽지 않음 ReadState를 표시할 수 있습니다 하 고 그에 따라 동시에 앱 내 알림이 기록 보기에서 알림을 표시할지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-144">Alternatively, or at the same time you can mark ReadState as Read or Unread and based on that determine which notifications should show up in the in-app notification history view.</span></span> <span data-ttu-id="a3ed3-145">아래 코드 조각에서는 UserNotificationUserActionState 알림 해제로 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3ed3-145">Below code snippet shows how to mark the UserNotificationUserActionState of a notification as Dismissed.</span></span>

```Java
public void dismissNotification(int position) {
    final UserNotification notification = mNewNotifications.get(position);
          
    notification.setUserActionState(UserNotificationUserActionState.DISMISSED);
    notification.saveAsync();
}

```
