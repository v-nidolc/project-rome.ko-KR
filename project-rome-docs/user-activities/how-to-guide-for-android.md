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
# <a name="implementing-user-activities-for-android"></a>Android에 대 한 사용자 활동 구현

사용자 작업은 응용 프로그램 내에서 사용자의 작업을 나타내는 데이터 구조입니다. 이러한 사용 하면 나중에 계속 실행 되어야 하는 작업의 스냅숏을 저장할 수 있습니다. 합니다 [Windows 타임 라인](https://blogs.windows.com/windowsexperience/2018/04/27/make-the-most-of-your-time-with-the-new-windows-10-update/) 기능 텍스트와 그래픽 카드 라고의 해당 하는 모든 최근 활동을 스크롤 가능한 목록이 포함 된 Windows 사용자를 표시 합니다. 사용자 활동에 대 한 자세한 내용은 참조 일반적으로 [장치 에서도 사용자 활동을 계속](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities)합니다. 만들기 또는 업데이트 작업을 하는 경우에 권장 사항을 참조 합니다 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 가이드입니다.

프로젝트 로마 SDK를 사용 하 여 Android 앱 뿐 아니라 시간 표시 막대와 같은 Windows 기능 사용에 대 한 사용자 작업 게시 하지만 수 끝점으로 작동 하 고 수도 마찬가지로 타임 라인 Windows 장치에서 작업 다시 사용자에 게 읽기. 따라서 장치 간 앱이 해당 플랫폼을 초월 하 고 장치가 아닌 사용자는 환경을 제공 합니다.  

참조 된 [API 참조](api-reference-for-android.md) 이러한 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.

이 단계 아래에서 코드 참조는 [프로젝트 로마 Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples)합니다.

[!INCLUDE [android/dev-reqs](../includes/android/dev-reqs.md)]

[!INCLUDE [android/preliminary-setup](../includes/android/preliminary-setup.md)]

[!INCLUDE [android/auth-scopes](../includes/auth-scopes.md)]

[!INCLUDE [android/dev-center-onboarding](../includes/android/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a>플랫폼을 사용 하 여

[!INCLUDE [android/create-setup-events-start-platform](../includes/android/create-setup-events-start-platform.md)]

### <a name="initialize-a-user-activity-channel"></a>사용자 작업 채널 초기화

앱에서 사용자 작업 기능을 구현 하는 피드를 UserActivityChannel를 만들어 사용자 동작을 초기화 하려면 먼저 해야 합니다. 위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.

Microsoft 개발자 대시보드 등록을 통해 검색 된 플랫폼 간 앱 ID를 해야 합니다.
다음 메서드는 UserActivityChannel를 초기화합니다.

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

이 시점에서 mActivityChannel UserActivityChannel 참조가 있어야 합니다.


### <a name="create-and-publish-a-user-activity"></a>만들기 및 사용자 활동을 게시 합니다.

다음으로 어떤 것이 새 ID, DisplayText 및 ActivationURI 데이터를 설정 **UserActivity**합니다. ID는 고유 문자열 이어야 합니다. DisplayText 표시할 다른 장치에서 작업 (Windows 타임 라인에서 예를 들어)를 볼 때 활동에 대 한 간단한 설명 수입니다. ActivationUri 수행할 작업을 시기에 따라 결정 됩니다 합니다 **UserActivity** (선택 하면 타임 라인의 예를 들어) 활성화 됩니다. 다음 코드는 이러한 필드에 대 한 샘플 데이터를 채웁니다.


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

다음으로 만드는 새 메서드를 제공 **UserActivity** 인스턴스.

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
했으면 합니다 **UserActivity** 인스턴스, 위에 정의 된 데이터를 채웁니다.

```Java
//set the properties of the UserActivity:
// Display Text will be shown when the UserActivity is viewed on other devices
mActivity.getVisualElements().setDisplayText(mDisplayText);
// ActivationURI will determine what is launched when your UserActivity is activated from other devices
mActivity.setActivationUri(mActivationUri);
```

마지막으로, 클라우드로 작업을 게시 합니다. 

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
> 위의 속성 외에도 구성할 수 있는 기타 많은 기능이 있습니다. UserActivity를 사용자 지정할 수 있습니다 하는 다양 한 방법 살펴보고 완료에 대 한 참조를  **[UserActivity](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity)** 합니다 **[UserActivityVisualElements](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_visual_elements)**, 및 **[UserActivityAttribution](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_attribution)** 클래스입니다. 참조 된 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 사용자 활동을 디자인 하는 방법에 대 한 자세한 권장 사항은 가이드입니다.

### <a name="update-an-existing-user-activity"></a>기존 사용자 활동을 업데이트 합니다.

기존 활동을 한 해당 정보 (발생 시 새 engagement, 변경 된 페이지 및 등)을 업데이트 하려는 경우 있습니다 이렇게 사용 하는 **UserActivitySession**합니다.

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

앱의 속성에 원하는 변경을 수행 하기 세션을 만든 후 합니다 **UserActivity**합니다. 변경을 마쳤으면 세션을 닫습니다. 

```Java
mActivitySession.close();
mActivitySession = null;
Log.d("UserActivityFragment", "Stopping");
```

A **UserActivitySession** 을 만드는 방법으로 생각할 수 있습니다를 **UserActivitySessionHistoryItem** (다음 섹션에서 설명 됨). 새로 만드는 대신 **UserActivity** 될 때마다 사용자가 새 페이지로 이동할 각 페이지에 대 한 새 세션을 간단히 만들 수 있습니다. 이렇게 하면 읽기 환경을 더욱 직관적이 고 구성 된 활동에 대 한 합니다.

### <a name="read-user-activities"></a>사용자 활동 읽기

앱은 사용자 활동 읽기 하 고 Windows 타임 라인 기능이 수행 하는 것 처럼 사용자에 게 제공할 수 있습니다. 사용자 활동 읽기를 설정 하려면 사용 하 여 동일한 **UserActivityChannel** 앞에서 인스턴스. 이 인스턴스를 노출할 수 있습니다 **UserActivitySessionHistoryItem** 특정 기간 동안 특정 작업에는 사용자의 참여를 나타내는 경우.

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

앱에 채워진된 목록이 있어야 합니다. 이제 **UserActivitySessionHistoryItem**s입니다. 기본 제공할 수 있습니다 이러한 사항의 **UserActivity** (참조 **[UserActivitySessionHistoryItem](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.useractivities._user_activity_session_history_item)** 세부 정보에 대 한), 사용자에 게 표시할 수 있습니다.
