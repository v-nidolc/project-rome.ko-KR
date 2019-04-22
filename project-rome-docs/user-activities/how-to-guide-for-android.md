---
title: 사용자 활동 (Android)를 읽고 게시
description: 이 가이드에는 만들기, 게시 및 Android 앱에서 Windows 기반 사용자 활동을 읽는 방법을 보여 줍니다.
ms.topic: article
keywords: microsoft, windows, 로마, 사용자 활동, android 프로젝트
ms.assetid: 8cfb7544-913c-48c0-8528-52b93ba8b0c6
ms.localizationpriority: medium
ms.openlocfilehash: 67f793341a108853d5b36e062fd04f441efff473
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801535"
---
# <a name="implementing-user-activities-for-android"></a><span data-ttu-id="29151-104">Android에 대 한 사용자 활동 구현</span><span class="sxs-lookup"><span data-stu-id="29151-104">Implementing User Activities for Android</span></span>

<span data-ttu-id="29151-105">사용자 작업은 응용 프로그램 내에서 사용자의 작업을 나타내는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-105">User Activities are data constructs that represent a user's tasks within an application.</span></span> <span data-ttu-id="29151-106">이러한 사용 하면 나중에 계속 실행 되어야 하는 작업의 스냅숏을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-106">They make it possible to save a snapshot of a task to be continued at a later time.</span></span> <span data-ttu-id="29151-107">합니다 [Windows 타임 라인](https://blogs.windows.com/windowsexperience/2018/04/27/make-the-most-of-your-time-with-the-new-windows-10-update/) 기능 텍스트와 그래픽 카드 라고의 해당 하는 모든 최근 활동을 스크롤 가능한 목록이 포함 된 Windows 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-107">The [Windows Timeline](https://blogs.windows.com/windowsexperience/2018/04/27/make-the-most-of-your-time-with-the-new-windows-10-update/) feature presents Windows users with a scrollable list of all their recent activities, represented as cards with text and graphics.</span></span> <span data-ttu-id="29151-108">사용자 활동에 대 한 자세한 내용은 참조 일반적으로 [장치 에서도 사용자 활동을 계속](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities)합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-108">For more information about User Activities in general, see [Continue user activity, even across devices](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities).</span></span> <span data-ttu-id="29151-109">만들기 또는 업데이트 작업을 하는 경우에 권장 사항을 참조 합니다 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-109">For recommendations on when to create or update Activities, see the [User Activities best practices](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) guide.</span></span>

<span data-ttu-id="29151-110">프로젝트 로마 SDK를 사용 하 여 Android 앱 뿐 아니라 시간 표시 막대와 같은 Windows 기능 사용에 대 한 사용자 작업 게시 하지만 수 끝점으로 작동 하 고 수도 마찬가지로 타임 라인 Windows 장치에서 작업 다시 사용자에 게 읽기.</span><span class="sxs-lookup"><span data-stu-id="29151-110">With the Project Rome SDK, your Android app can not only publish User Activities for use in Windows features such as Timeline, but can also act as an endpoint and read Activities back to the user just as Timeline does on Windows devices.</span></span> <span data-ttu-id="29151-111">따라서 장치 간 앱이 해당 플랫폼을 초월 하 고 장치가 아닌 사용자는 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-111">This allows cross-device apps to transcend their platforms and provide experiences that follow users rather than devices.</span></span>  

<span data-ttu-id="29151-112">참조 된 [API 참조](api-reference-for-android.md) 이러한 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-112">See the [API reference](api-reference-for-android.md) page for links to the reference docs relevant to these scenarios.</span></span>

<span data-ttu-id="29151-113">이 단계 아래에서 코드 참조는 [프로젝트 로마 Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples)합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-113">This steps below will reference code from the [Project Rome Android sample app](https://github.com/Microsoft/project-rome/tree/master/Android/samples).</span></span>

[!INCLUDE [android/dev-reqs](../includes/android/dev-reqs.md)]

[!INCLUDE [android/preliminary-setup](../includes/android/preliminary-setup.md)]

[!INCLUDE [android/auth-scopes](../includes/auth-scopes.md)]

[!INCLUDE [android/dev-center-onboarding](../includes/android/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a><span data-ttu-id="29151-114">플랫폼을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="29151-114">Using the platform</span></span>

[!INCLUDE [android/create-setup-events-start-platform](../includes/android/create-setup-events-start-platform.md)]

### <a name="initialize-a-user-activity-channel"></a><span data-ttu-id="29151-115">사용자 작업 채널 초기화</span><span class="sxs-lookup"><span data-stu-id="29151-115">Initialize a User Activity channel</span></span>

<span data-ttu-id="29151-116">앱에서 사용자 작업 기능을 구현 하는 피드를 UserActivityChannel를 만들어 사용자 동작을 초기화 하려면 먼저 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-116">To implement User Activity features in your app, you will first need to initialize the user activity feed by creating a UserActivityChannel.</span></span> <span data-ttu-id="29151-117">위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-117">You should treat this like the Platform initialization step above: it should be checked and possibly redone whenever the app comes to the foreground (but not before Platform initialization).</span></span>

<span data-ttu-id="29151-118">Microsoft 개발자 대시보드 등록을 통해 검색 된 플랫폼 간 앱 ID를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-118">You will also need your cross-platform app ID, which was retrieved through the Microsoft Developer Dashboard registration.</span></span>
<span data-ttu-id="29151-119">다음 메서드는 UserActivityChannel를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-119">The following methods initialize a UserActivityChannel.</span></span>

```Java
private UserActivityChannel mActivityChannel;
private UserDataFeed mUserDataFeed;

// ...

/**
 * Initializes the UserActivityFeed.
 */
public void initializeUserActivityFeed() {

    // define what scope of data this app needs
    SyncScope[] scopes = { UserActivityChannel.getSyncScope(), UserNotificationChannel.getSyncScope() };

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
    mActivityChannel = getUserActivityChannel();
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
private UserActivityChannel getUserActivityChannel() {
    UserActivityChannel channel = null;
    try {
        // create a UserActivityChannel for the signed in account
        channel = new UserActivityChannel(mUserDataFeed);
    } catch (Exception e) {
        e.printStackTrace();
        // handle exception
    }
    return channel;
}
```

<span data-ttu-id="29151-120">이 시점에서 mActivityChannel UserActivityChannel 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-120">At this point, you should have a UserActivityChannel reference in mActivityChannel.</span></span>


### <a name="create-and-publish-a-user-activity"></a><span data-ttu-id="29151-121">만들기 및 사용자 활동을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-121">Create and publish a User Activity</span></span>

<span data-ttu-id="29151-122">다음으로 어떤 것이 새 ID, DisplayText 및 ActivationURI 데이터를 설정 **UserActivity**합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-122">Next, set the ID, DisplayText and ActivationURI data of what will be a new **UserActivity**.</span></span> <span data-ttu-id="29151-123">ID는 고유 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-123">The ID should be a unique String.</span></span> <span data-ttu-id="29151-124">DisplayText 표시할 다른 장치에서 작업 (Windows 타임 라인에서 예를 들어)를 볼 때 활동에 대 한 간단한 설명 수입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-124">The DisplayText will be shown on other devices when they view the Activity (in Windows Timeline, for example), so it should be a concise description of the activity.</span></span> <span data-ttu-id="29151-125">ActivationUri 수행할 작업을 시기에 따라 결정 됩니다 합니다 **UserActivity** (선택 하면 타임 라인의 예를 들어) 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29151-125">The ActivationUri will determine what action is taken when the **UserActivity** is activated (when it is selected in Timeline, for example).</span></span> <span data-ttu-id="29151-126">다음 코드는 이러한 필드에 대 한 샘플 데이터를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="29151-126">The following code fills in sample data for these fields.</span></span>


```Java
private UserActivity mActivity;
private String mActivityId;
private String mDisplayText;
private String mActivationUri;

// ...

mActivityId = UUID.randomUUID().toString();
mDisplayText = "Created by OneSDK Sample App";
mActivationUri = "http://contoso.com");
```

<span data-ttu-id="29151-127">다음으로 만드는 새 메서드를 제공 **UserActivity** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="29151-127">Next, provide a method that creates a new **UserActivity** instance.</span></span>

```Java
// Create the UserActivity (with unique ID) using a custom method. 
mActivity = createUserActivity(mActivityChannel, mActivityId);

// ...

// Custom method for creating a new UserActivity
@Nullable
private UserActivity createUserActivity(UserActivityChannel channel, String activityId)
{
    UserActivity activity = null;
    AsyncOperation<UserActivity> activityOperation = channel.getOrCreateUserActivityAsync(activityId);
    try {
        activity = activityOperation.get();
        Log.d("UserActivityFragment","Created user activity successfully");
    } catch (Exception e) {
        e.printStackTrace();
        Log.d("UserActivityFragment","Created user activity successfully");
    }
    return activity;
}
```
<span data-ttu-id="29151-128">했으면 합니다 **UserActivity** 인스턴스, 위에 정의 된 데이터를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="29151-128">Once you have the **UserActivity** instance, populate it with the data defined above.</span></span>

```Java
//set the properties of the UserActivity:
// Display Text will be shown when the UserActivity is viewed on other devices
mActivity.getVisualElements().setDisplayText(mDisplayText);
// ActivationURI will determine what is launched when your UserActivity is activated from other devices
mActivity.setActivationUri(mActivationUri);
```

<span data-ttu-id="29151-129">마지막으로, 클라우드로 작업을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-129">Finally, publish the Activity to the cloud.</span></span> 

```Java
// This code saves and publishes the activity
AsyncOperation<Void> operation = mActivity.saveAsync();
operation.whenCompleteAsync(new AsyncOperation.ResultBiConsumer<Void, Throwable>() {
    @Override
    public void accept(Void aVoid, Throwable throwable) throws Throwable {
        if (throwable != null)
        {
            Log.d("UserActivityFragment", "Failed to save");
        } else {
            Log.d("UserActivityFragment", "User activity saved");
        }
    }
});
```

> [!TIP] 
> <span data-ttu-id="29151-130">위의 속성 외에도 구성할 수 있는 기타 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-130">In addition to the properties above, there are many other features that can be configured.</span></span> <span data-ttu-id="29151-131">UserActivity를 사용자 지정할 수 있습니다 하는 다양 한 방법 살펴보고 완료에 대 한 참조를  **[UserActivity](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity)** 합니다 **[UserActivityVisualElements](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_visual_elements)**, 및 **[UserActivityAttribution](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_attribution)** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-131">For a complete look at the different ways that a UserActivity can be customized, see the **[UserActivity](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity)**, **[UserActivityVisualElements](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_visual_elements)**, and **[UserActivityAttribution](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_attribution)** classes.</span></span> <span data-ttu-id="29151-132">참조 된 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 사용자 활동을 디자인 하는 방법에 대 한 자세한 권장 사항은 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-132">See the [User Activities best practices](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) guide for detailed recommendations on how to design User Activities.</span></span>

### <a name="update-an-existing-user-activity"></a><span data-ttu-id="29151-133">기존 사용자 활동을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-133">Update an existing User Activity</span></span>

<span data-ttu-id="29151-134">기존 활동을 한 해당 정보 (발생 시 새 engagement, 변경 된 페이지 및 등)을 업데이트 하려는 경우 있습니다 이렇게 사용 하는 **UserActivitySession**합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-134">If you have an existing Activity and wish to update its information (in the event of a new engagement, changed page, and so on), you can do so by using a **UserActivitySession**.</span></span>

```Java
private UserActivitySession mActivitySession;

// ...

if (mActivity != null)
{
    // create a session from a previous UserActivity instance.
    mActivitySession = mActivity.createSession();
    Log.d("UserActivityFragment", "Starting");
}
```

<span data-ttu-id="29151-135">앱의 속성에 원하는 변경을 수행 하기 세션을 만든 후 합니다 **UserActivity**합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-135">Once you've created a session, your app can make any desired changes to the properties of the **UserActivity**.</span></span> <span data-ttu-id="29151-136">변경을 마쳤으면 세션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-136">When you're done making changes, close the session.</span></span> 

```Java
mActivitySession.close();
mActivitySession = null;
Log.d("UserActivityFragment", "Stopping");
```

<span data-ttu-id="29151-137">A **UserActivitySession** 을 만드는 방법으로 생각할 수 있습니다를 **UserActivitySessionHistoryItem** (다음 섹션에서 설명 됨).</span><span class="sxs-lookup"><span data-stu-id="29151-137">A **UserActivitySession** can be thought of as a way to create a **UserActivitySessionHistoryItem** (covered in the next section).</span></span> <span data-ttu-id="29151-138">새로 만드는 대신 **UserActivity** 될 때마다 사용자가 새 페이지로 이동할 각 페이지에 대 한 새 세션을 간단히 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-138">Rather than create a new **UserActivity** every time a user moves to a new page, you can simply create a new session for each page.</span></span> <span data-ttu-id="29151-139">이렇게 하면 읽기 환경을 더욱 직관적이 고 구성 된 활동에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="29151-139">This will make for a more intuitive and organized activity reading experience.</span></span>

### <a name="read-user-activities"></a><span data-ttu-id="29151-140">사용자 활동 읽기</span><span class="sxs-lookup"><span data-stu-id="29151-140">Read User Activities</span></span>

<span data-ttu-id="29151-141">앱은 사용자 활동 읽기 하 고 Windows 타임 라인 기능이 수행 하는 것 처럼 사용자에 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-141">Your app can read User Activities and present them to the user just as the Windows Timeline feature does.</span></span> <span data-ttu-id="29151-142">사용자 활동 읽기를 설정 하려면 사용 하 여 동일한 **UserActivityChannel** 앞에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="29151-142">To set up User Activity reading, use the same **UserActivityChannel** instance from earlier.</span></span> <span data-ttu-id="29151-143">이 인스턴스를 노출할 수 있습니다 **UserActivitySessionHistoryItem** 특정 기간 동안 특정 작업에는 사용자의 참여를 나타내는 경우.</span><span class="sxs-lookup"><span data-stu-id="29151-143">This instance can expose **UserActivitySessionHistoryItem** instances, which represent a user's engagement in a particular Activity during a specific period of time.</span></span>

```Java
private ArrayList<UserActivitySessionHistoryItem> mHistoryItems; 

// ...

mHistoryItems.clear();

Log.d("UserActivityFragment", "Read");
//Async method to read activities. Last (most recent) 5 activities will be returned
AsyncOperation<UserActivitySessionHistoryItem[]> operation = mActivityChannel.getRecentUserActivitiesAsync(5);

operation.whenCompleteAsync(new AsyncOperation.ResultBiConsumer<UserActivitySessionHistoryItem[], Throwable>() {
    @Override
    public void accept(UserActivitySessionHistoryItem[] result, Throwable throwable) throws Throwable {
        if (throwable != null)
        {
            Log.d("UserActivityFragment", "Failed to read user activity!" + throwable.getMessage() + " " + throwable.getStackTrace());
        } else {
            // get the returned UserActivitySessionHistoryItems
            for (UserActivitySessionHistoryItem item : result)
            {
                mHistoryItems.add(item);
            }
        }
    }
});
```

<span data-ttu-id="29151-144">앱에 채워진된 목록이 있어야 합니다. 이제 **UserActivitySessionHistoryItem**s입니다.</span><span class="sxs-lookup"><span data-stu-id="29151-144">Now your app should have a populated list of **UserActivitySessionHistoryItem**s.</span></span> <span data-ttu-id="29151-145">기본 제공할 수 있습니다 이러한 사항의 **UserActivity** (참조 **[UserActivitySessionHistoryItem](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_session_history_item)** 세부 정보에 대 한), 사용자에 게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29151-145">Each of these can deliver the underlying **UserActivity** (see **[UserActivitySessionHistoryItem](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_session_history_item)** for details), which you can then display to the user.</span></span>
