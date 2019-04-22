---
title: 그래프 알림에 UWP 앱 통합
description: 알림에 대 한 수신 끝점에 필요한 등록 단계를 수행 하는 방법에 앱 서버에서 게시 합니다.
ms.assetid: c973d534-08e9-4f6e-8b54-bcae97067961
ms.localizationpriority: medium
ms.custom: seodec18
ms.openlocfilehash: 09f32a9869343778712449db04f74e9341fbc5a6
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801305"
---
# <a name="how-to-guide-integrating-with-ms-graph-notifications-windows-uwp"></a><span data-ttu-id="29b19-103">방법 가이드: MS Graph 알림 (Windows UWP)와 통합</span><span class="sxs-lookup"><span data-stu-id="29b19-103">How-To Guide: Integrating with MS Graph Notifications (Windows UWP)</span></span>

<span data-ttu-id="29b19-104">Windows에서 그래프 알림을 클라이언트 쪽 SDK를 사용 하 여 Windows UWP 앱에는 수신 하는 끝점에 사용자를 대상으로 앱 서버에서 게시 하는 알림을 수신 하는 데 필요한 등록 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-104">With the Graph Notifications client-side SDK on Windows, your Windows UWP app can perform the necessary registration steps to become a receiving endpoint that receives notifications published from your app server targeted at a user.</span></span> <span data-ttu-id="29b19-105">페이로드가이 클라이언트에 도착 하는 새 알림 수신, 알림 상태를 관리 및 알림 기록 검색을 포함 하 여 클라이언트 쪽에서 알림을 관리 하는 SDK 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-105">The SDK is then used to manage the notifications on the client side including receiving new notification payloads arrived on this client, managing the state of notifications, and retrieving notification history.</span></span> <span data-ttu-id="29b19-106">MS Graph 알림 및이 통해 사람이 중심 알림을 배달 하는 방법에 대 한 자세한 내용은 참조 하세요. [Microsoft Graph 알림 개요](index.md)</span><span class="sxs-lookup"><span data-stu-id="29b19-106">For more information about MS Graph Notifications and how it enables human-centric notification delivery, see [Microsoft Graph Notifications Overview](index.md)</span></span>

<span data-ttu-id="29b19-107">참조 된 [API 참조](api-reference-for-windows/index.md) 알림 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-107">See the [API reference](api-reference-for-windows/index.md) page for links to the reference docs relevant to notification scenarios.</span></span>

## <a name="preliminary-setup-for-accessing-the-connected-devices-platform-in-order-to-use-graph-notifications"></a><span data-ttu-id="29b19-108">그래프 알림을 사용 하려면 연결 된 장치 플랫폼에 액세스 하기 위한 예비 설치</span><span class="sxs-lookup"><span data-stu-id="29b19-108">Preliminary setup for accessing the Connected Devices Platform in order to use Graph Notifications</span></span> 
<span data-ttu-id="29b19-109">몇 단계만 그래프 알림과 함께 통합 하기 위해 취해야 할</span><span class="sxs-lookup"><span data-stu-id="29b19-109">There are a few steps you must take to integrate with Graph Notifications</span></span>
* <span data-ttu-id="29b19-110">MSA 또는 AAD 앱 등록</span><span class="sxs-lookup"><span data-stu-id="29b19-110">MSA or AAD App Registration</span></span>
* <span data-ttu-id="29b19-111">플랫폼 간 앱 Id를 제공 하는 개발자 센터 등록 하 고 푸시 알림 자격 증명</span><span class="sxs-lookup"><span data-stu-id="29b19-111">Dev Center Onboarding to Provide Cross-Platform App Identity and Push Notification Credentials</span></span>
* <span data-ttu-id="29b19-112">SDK를 추가 하 고 연결 된 장치 플랫폼 초기화</span><span class="sxs-lookup"><span data-stu-id="29b19-112">Adding the SDK and Initializing the Connected Devices Platform</span></span>
* <span data-ttu-id="29b19-113">연결 된 장치 플랫폼 알림 서비스 연결</span><span class="sxs-lookup"><span data-stu-id="29b19-113">Associate the Notification Service with Connected Devices Platform</span></span>

<span data-ttu-id="29b19-114">첫째, MSA 및/또는 AAD 앱 등록이 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-114">First, you must complete the MSA and/or AAD App Registration.</span></span> <span data-ttu-id="29b19-115">이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-115">If you've done this already, skip to the next section.</span></span>
[!INCLUDE [windows/platform-init](../includes/windows/notifications-app-registration-onboarding.md)]
<span data-ttu-id="29b19-116">다음으로 해야 온 보 딩 그래프 알림 사용을 포함 하는 장치 간 환경을 통합 하기 위해 연결 된 장치 플랫폼에 대 한 액세스를 가져오려면 Microsoft Windows 개발자 센터를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-116">Next, you must onboard with Microsoft Windows Dev Center to get access to the Connected Device Platform in order to integrate with cross-device experiences including use of Graph Notifications.</span></span> <span data-ttu-id="29b19-117">이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-117">If you've done this already, skip to the next section.</span></span>
[!INCLUDE [windows/notification-init](../includes/windows/notifications-dev-center-onboarding.md)]
<span data-ttu-id="29b19-118">다음으로 프로젝트 로마 SDK 프로젝트를 추가 하 고 연결 된 장치 플랫폼을 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-118">Next, you must add the Project Rome SDK to your project and initialize the Connected Devices Platform.</span></span> <span data-ttu-id="29b19-119">이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-119">If you've done this already, skip to the next section.</span></span>
[!INCLUDE [android/notification-init](../includes/android/notifications-platfrom-init.md)]
<span data-ttu-id="29b19-120">마지막으로 푸시 알림을 받도록 앱을 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-120">Lastly, you must enable your app to receive push notifications.</span></span> <span data-ttu-id="29b19-121">이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-121">If you've done this already, skip to the next section.</span></span>
[!INCLUDE [android/notification-init](../includes/android/notifications-notification-init.md)]

## <a name="initialize-a-graph-notification-channel"></a><span data-ttu-id="29b19-122">그래프 알림 채널을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-122">Initialize a Graph Notification channel</span></span>
<span data-ttu-id="29b19-123">높은 수준에서는 SDK에는 앱을을 수신 하 고 다양 한 유형의 사용자 활동 그래프 알림 등을 포함 하 여 사용자 데이터를 관리 하기 위해 다른 채널을 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-123">At a high level, the SDK allows your app to subscribe to different channels in order to receive and manage different types of User Data – including Graph Notifications, User Activities, and more.</span></span> <span data-ttu-id="29b19-124">모두 저장 하 고 동기화에서 이들은 **UserDataFeed**합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-124">These are all stored and synced in **UserDataFeed**.</span></span> <span data-ttu-id="29b19-125">**UserNotification** 사용자 대상 알림 전송 그래프 알림을 통해 해당 클래스 및 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-125">**UserNotification** is the class and data type corresponding to a user-targeted notification sent via Graph Notifications.</span></span> <span data-ttu-id="29b19-126">그래프 알림 및 앱 서버에서 게시 UserNotification 받기 시작와를 통합 하려면 먼저 피드를 만들어서 사용자 데이터를 초기화 하는 **UserNotificationChannel**합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-126">To integrate with Graph Notification and start receiving UserNotification published by your app server, you will first need to initialize the user data feed by creating a **UserNotificationChannel**.</span></span> <span data-ttu-id="29b19-127">위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-127">You should treat this like the platform initialization step above: it should be checked and possibly redone whenever the app comes to the foreground (but not before platform initialization).</span></span> 

## <a name="create-a-usernotificationreader-to-receive-incoming-usernotifications-and-access-usernotification-history"></a><span data-ttu-id="29b19-128">들어오는 UserNotifications 받고 UserNotification 기록에 액세스 하려면 UserNotificationReader 만들기</span><span class="sxs-lookup"><span data-stu-id="29b19-128">Create a UserNotificationReader to receive incoming UserNotifications and access UserNotification history</span></span>
<span data-ttu-id="29b19-129">만든 후는 **UserNotificationChannel** 참조 해야를 **UserNotificationReader** SDK 서버에서 실제 알림 콘텐츠를 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-129">Once you have a **UserNotificationChannel** reference, you need a **UserNotificationReader** in order to allow the SDK to fetch the actual notification content from the server.</span></span> <span data-ttu-id="29b19-130">UserNotificationReader에는 경우이 데이터 피드에 – 앱 클라이언트의 액세스할 수 있도록 이벤트 수신기를 통해 최신 알림 페이로드 또는 사용자의 알림 기록은의 뷰 모델로 사용할 수 있는 전체 UserNotification 컬렉션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-130">A UserNotificationReader in this case enables the app client’s access to this data feed – to receive latest notification payload via event listener, or to access the full UserNotification collection which can be used as view model of the user’s notification history.</span></span>  

<span data-ttu-id="29b19-131">아래 코드 사용자 알림 채널을 인스턴스화하고 사용자 알림 판독기를 만들려면 연결 된 장치 플랫폼 각 동기화를 완료 하 고 새 변경 내용이 될 때 트리거되는 사용자 알림 판독기에서 이벤트 처리기를 추가 하는 단계를 보여 줍니다. 에 대 한 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-131">The code below shows the steps to instantiate a user notification channel, create a user notification reader, and add an event handler on the user notification reader which gets triggered when the COnnected Device Platform completes each sync and has new changes to notify you about.</span></span> 

```C#

public async Task SetupChannel()
{
    var account = m_accoutProvider.SignedInAccount;

    if (m_feed == null)
    {
        await Task.Run(() =>
        {
            lock (this)
            {
                if (m_feed == null)
                {
                    m_platform = new ConnectedDevicesPlatform(m_accoutProvider, this);

                    Logger.Instance.LogMessage($"Create feed for {account.Id} {account.Type}");
                    m_feed = new UserDataFeed(account, m_platform, "graphnotifications.sample.windows.com");
                    m_feed.SyncStatusChanged += Feed_SyncStatusChanged;
                    m_feed.AddSyncScopes(new List<IUserDataFeedSyncScope>
                    {
                        UserNotificationChannel.SyncScope
                    });

                    m_channel = new UserNotificationChannel(m_feed);
                    m_reader = m_channel.CreateReader();
                    m_reader.DataChanged += Reader_DataChanged;
                }
            }
        });
    }
}

```

### <a name="receiving-usernotifications"></a><span data-ttu-id="29b19-132">UserNotifications 받기</span><span class="sxs-lookup"><span data-stu-id="29b19-132">Receiving UserNotifications</span></span>

<span data-ttu-id="29b19-133">위의 섹션에서 사용자 알림 판독기는 이벤트 수신기 추가 되어 있는지을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-133">In the above section we see that an event listner is added to the user notification reader.</span></span> <span data-ttu-id="29b19-134">새 알림 및 알림 업데이트를 모든 판독기에서 읽을이 이벤트 수신기를 구현 하 고 이러한 새로운 변화를 처리 하 여 고유한 비즈니스 논리를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-134">You should implement this event listener to read all the new notifications and notification updates from the reader, and implement your own business logic to handle each of these new changes.</span></span> 

> [!TIP] 
> <span data-ttu-id="29b19-135">이 이벤트 수신기에는 기본 비즈니스 논리를 처리 하 고 "사용" 시나리오에 따라 알림 페이로드 콘텐츠 위치는입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-135">This event listener is where you handle the main business logic and “consume” the content of your notification payload based on your scenarios.</span></span> <span data-ttu-id="29b19-136">현재 WNS의 원시 알림 OS 수준 알림 센터의 로컬 알림 생성을 사용 하는 경우, 일부 앱에서 UI를 업데이트 하려면 알림 영역에서 콘텐츠를 사용 하는 경우 작업을 수행 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-136">If you currently use WNS’s raw notification to construct a local toast notification in the OS-level Action Center, or if you use the content in the notification to update some in-app UI, this is the place to do that.</span></span> 

<span data-ttu-id="29b19-137">아래 코드 활성 되어 알림이 삭제 되 면 앱에서 보기에 해당 알림 UI를 제거 하는 모든 들어오는 UserNotification에 대 한 로컬 알림 메시지를 발생 시키려면 샘플 앱을 선택 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-137">The code below shows you how the sample app chooses to raise a local toast notification for all the incoming UserNotification that are Active, and remove the corresponding notification UI in the in-app view if a notification is deleted.</span></span> 

```C#

private void Reader_DataChanged(UserNotificationReader sender, object args)
{
    ReadNotifications(sender, true);
}

private async void ReadNotifications(UserNotificationReader reader, bool showToast)
{
    var notifications = await reader.ReadBatchAsync(UInt32.MaxValue);

    foreach (var notification in notifications)
    {

        if (notification.Status == UserNotificationStatus.Active)
        {
            m_newNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            if (notification.UserActionState == UserNotificationUserActionState.NoInteraction)
            {
                // new notification, show this to user using the Windows local toast notification APIs
                m_newNotifications.Add(notification);
                if (!string.IsNullOrEmpty(notification.Content) && showToast)
                {
                    ShowToastNotification(BuildToastNotification(notification.Id, notification.Content));
                }
            }

            m_historicalNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            m_historicalNotifications.Insert(0, notification);
        }
        else
        {
            // Existing notification is marked as deleted, remove from display
            m_newNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            m_historicalNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            RemoveToastNotification(notification.Id);
        }
    }
}

```
## <a name="update-the-state-of-an-existing-usernotification"></a><span data-ttu-id="29b19-138">기존 UserNotification의 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-138">Update the state of an existing UserNotification</span></span>
<span data-ttu-id="29b19-139">이전 섹션에서 설명한 대로 따라 판독기를 통해 받은 UserNotification 변경 수는 기존 UserNotification –에서 상태 업데이트를으로 표시 되거나 해제 된 읽음으로 표시 되 고 되는지 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-139">In the previous section, we mentioned that sometimes a UserNotification change received through the reader could be a state update on an existing UserNotification – whether that’s being marked as dismissed or marked as read.</span></span> <span data-ttu-id="29b19-140">이 경우 응용 프로그램 클라이언트를 선택할 수를 유니버설 예를 들어이 특정 장치에서 해당 visual 알림을 제거 하 여 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-140">In this case, the app client can choose what to do, such as enabling universal dismiss by removing the corresponding visual notification on this particular device.</span></span> <span data-ttu-id="29b19-141">다시 단계에서 확인 하 고 앱 클라이언트 경우가이 UserNotification 변경 업데이트를 시작 하려면 – 다른 장치에서 시작 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-141">Taking a step back, your app client is often the one that initiated this UserNotification change update to begin with – from a different device.</span></span> <span data-ttu-id="29b19-142">프로그램 UserNotifications의 상태를 업데이트 하는 시간을 선택할 수 있지만 일반적으로 이러한 업데이트 해당 visual 알림을 해당 장치에서 사용자에 의해 처리 됩니다. 때나 알림을 사용 하도록 설정 하면 일부 앱 내 환경에서 사용자가 추가로 처리 됩니다. .</span><span class="sxs-lookup"><span data-stu-id="29b19-142">You can choose the time to update the state of your UserNotifications, but usually they get updated when the corresponding visual notification is handled by the user on that device, or the notification is further handled by the user in some in-app experience you enable.</span></span> <span data-ttu-id="29b19-143">흐름은 모양을의 예는 다음과 같습니다. 앱 서버 1. 사용자는 자신의 PC 및 앱 클라이언트를 설치할 자신의 휴대폰에서이 알림을 받으면 사용자를 대상으로 알림을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-143">Here is an example of what the flow would look like: Your app server publishes a notification targeted at User A. User A receives this notification on both his PC and his phone where the app clients are installed.</span></span> <span data-ttu-id="29b19-144">PC에서 알림을 클릭 하 고 해당 작업 핸들을 앱에가 하는 사용자.</span><span class="sxs-lookup"><span data-stu-id="29b19-144">The user clicks on the notification on PC, and chases into the app to handles the corresponding task.</span></span> <span data-ttu-id="29b19-145">그런 다음이 PC에 앱 클라이언트에 연결 된 장치 플랫폼 SDK이 모든이 사용자의이 장치 간에 동기화이 업데이트를 위해서는 해당 UserNotification의 상태를 업데이트 하려면 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-145">The app client on this PC will then call into Connected Devices Platform SDK to update the state of the corresponding UserNotification in order to have this update synced across all this user’s devices.</span></span> <span data-ttu-id="29b19-146">이 받으면 다른 앱 클라이언트를 실시간으로 업데이트 상태는 다음 해당 시각적 경고가 제거 / 메시지 / 장치의 알림 센터 알림 / 알림 트레이 작업 센터 /입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-146">The other app clients, upon receiving this state update in real-time, will then remove the corresponding visual alert / message / toast notification from the device’s notification center / notification tray / Action Center.</span></span> <span data-ttu-id="29b19-147">사용자의 장치에서 알림을 해제 보편적으로 가져오기 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-147">This is how notifications get universally dismissed across a user’s devices.</span></span> 

> [!TIP] 
> <span data-ttu-id="29b19-148">UserNotification 클래스에는 현재 두 가지 유형의 상태 업데이트 제공 –는 UserNotificationReadState 또는 UserNotificationUserActionState 수정 하 고 알림을 업데이트 될 때 수행할 동작에 고유한 논리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-148">UserNotification class currently provides 2 types of state updates – you can modify the UserNotificationReadState or the UserNotificationUserActionState and define your own logic on what should happen when notifications are updated.</span></span> <span data-ttu-id="29b19-149">예를 들어 UserActionState Activated 또는 해제를 표시할 수 있습니다 및 universal를 구현 하는 값에서 피벗 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-149">For example, you can mark UserActionState to be Activated or Dismissed, and pivot on that value to implement universal dismiss.</span></span> <span data-ttu-id="29b19-150">또는 읽기 또는 읽지 않음 ReadState를 표시할 수 있습니다 하 고 그에 따라 동시에 앱 내 알림이 기록 보기에서 알림을 표시할지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-150">Alternatively, or at the same time you can mark ReadState as Read or Unread and based on that determine which notifications should show up in the in-app notification history view.</span></span> <span data-ttu-id="29b19-151">아래 코드 조각에서는 UserNotificationUserActionState 알림 해제로 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29b19-151">Below code snippet shows how to mark the UserNotificationUserActionState of a notification as Dismissed.</span></span>

```C#
public async void Dismiss(string id)
{
    var notification = m_newNotifications.Find((n) => { return (n.Id == id); });
    if (notification != null)
    {
        notification.UserActionState = UserNotificationUserActionState.Dismissed;
        await notification.SaveAsync();
    }
}

```
