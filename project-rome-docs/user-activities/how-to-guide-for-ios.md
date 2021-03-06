---
title: 사용자 활동 (iOS)를 읽고 게시
description: 이 가이드에는 만들기, 게시 및 iOS 앱에서 Windows 기반 사용자 활동을 읽는 방법을 보여 줍니다.
ms.topic: article
keywords: microsoft, windows, 로마, 사용자 활동, ios 프로젝트
ms.assetid: 445f1dd4-f3c7-46e4-a7cd-42a1fb411172
ms.localizationpriority: medium
ms.openlocfilehash: 3cc19463a5e036ab76288760aa70d86f1861675b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801675"
---
# <a name="implementing-user-activities-for-ios"></a>IOS에 대 한 사용자 활동 구현

사용자 작업은 응용 프로그램 내에서 사용자의 작업을 나타내는 데이터 구조입니다. 이러한 사용 하면 나중에 계속 실행 되어야 하는 현재 작업의 스냅숏을 저장할 수 있습니다. 합니다 [Windows 타임 라인](https://blogs.windows.com/windowsexperience/2018/04/27/make-the-most-of-your-time-with-the-new-windows-10-update/) 기능 텍스트와 그래픽 카드 라고의 해당 하는 모든 최근 활동을 스크롤 가능한 목록이 포함 된 Windows 사용자를 표시 합니다. 사용자 활동에 대 한 자세한 내용은 참조 일반적으로 [장치 에서도 사용자 활동을 계속](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities)합니다. 만들기 또는 업데이트 작업을 하는 경우에 권장 사항을 참조 합니다 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 가이드입니다.

프로젝트 로마 SDK를 사용 하 여 iOS 앱 사용자 활동 타임 라인 같은 Windows 기능에서 사용 하기 위해만 게시할 없습니다 수 있지만 또한 끝점으로 작동 하 고 타임 라인 마찬가지로 다시 사용자에 게 작업을 읽을 수 있습니다. 이 완전히 해당 플랫폼과 장치가 아닌 사용자가 따르는 있는 환경을 초월 하 여 장치 간 앱을 허용 합니다.

프로젝트 로마 기능의 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼에서 지원 됩니다. 이 가이드는 연결 된 장치 플랫폼을 사용 하 여 시작 하는 데 필요한 단계를 제공 하 고 사용자 활동 관련된 기능을 구현 하는 플랫폼을 사용 하는 방법에 설명 합니다.

이 단계 아래에서 코드 참조는 [프로젝트 로마 iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) GitHub에서 사용할 수 있는 합니다.  

참조 된 [API 참조](api-reference-for-ios.md) 이러한 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.

## <a name="setting-up-the-connected-devices-platform-and-notifications"></a>연결 된 장치 플랫폼 및 알림 설정

[!INCLUDE [ios/preliminary-setup](../includes/ios/preliminary-setup.md)]

[!INCLUDE [auth-scopesiOS](../includes/auth-scopesiOS.md)]

[!INCLUDE [ios/dev-center-onboarding](../includes/ios/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a>플랫폼을 사용 하 여

[!INCLUDE [ios/create-setup-events-start-platform](../includes/ios/create-setup-events-start-platform.md)]

### <a name="initialize-a-user-activity-channel"></a>사용자 작업 채널 초기화

앱에서 사용자 작업 기능을 구현 하는 피드를 MCDUserActivityChannel를 만들어 사용자 동작을 초기화 하려면 먼저 해야 합니다. 위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.

이 단계에서 로그인 한 사용자 계정을 해야 합니다. 으로 위의 클래스는 인증 공급자 샘플에서을 쉽게는 MCDUserAccount(s)를 획득 하 사용할 수 있습니다. Microsoft 개발자 대시보드 등록을 통해 검색 된 플랫폼 간 앱 ID를 해야 합니다.
샘플 앱에서 다음 메서드는 MCDUserActivityChannel를 초기화합니다.

샘플 앱에서 다음 메서드는 MCDUserActivityChannel를 초기화합니다.

```ObjectiveC

    // Get a UserActivity channel, getting the default channel        
    NSLog(@"Creating UserActivityChannel");
    NSArray<MCDUserAccount*>* accounts = [[AppDataSource sharedInstance].accountProvider getUserAccounts];
    MCDUserDataFeed* userDataFeed = [MCDUserDataFeed userDataFeedForAccount:accounts[0]
        platform:[AppDataSource sharedInstance].platform
        activitySourceHost:CROSS_PLATFORM_APP_ID];
    NSArray<MCDSyncScope*>* syncScopes = @[ [MCDUserActivityChannel syncScope] ];
    [userDataFeed addSyncScopes:syncScopes];
    self.channel = [MCDUserActivityChannel userActivityChannelWithUserDataFeed:userDataFeed];
}
else
{
    NSLog(@"Must have an active account to publish activities!");
    self.createActivityStatusField.text = @"Need to be logged in!";
}
```
이 시점에서 채널에는 MCDUserActivityChannel 참조가 있어야 합니다.

### <a name="create-and-publish-a-user-activity"></a>만들기 및 사용자 활동을 게시 합니다.

다음 샘플 코드에서 보여 주는 새 어떻게 **MCDUserActivity** 인스턴스가 만들어집니다.

```ObjectiveC
- (IBAction)createActivityButton:(id)sender
{
    // Step #2: Create a UserActivity
    [self.channel getOrCreateUserActivityAsync:[[NSUUID UUID] UUIDString]
        completion:^(MCDUserActivity* activity, NSError* error) {
            if (error)
            {
                NSLog(@"%@", error);
                self.createActivityStatusField.text = @"Error creating activity!";
            }
            else if (!activity)
            {
                NSLog(@"No activity created!");
            }
            else
            {
                dispatch_async(dispatch_get_main_queue(), ^{
                    self.activity = activity;

                    // Create an activityId so the app knows so you know how to get back
                    self.activityId.text = activity.activityId;
                    self.createActivityStatusField.text = @"Created by iOSSample";
                    // Create a deep link so the app can get right back to where it was
                    self.activationUri.text = @"roman-app:";
                    self.createActivityStatusField.text = @"Activity created";
                });
            }
        }];
}
```

다음 메서드에서 시각적 데이터를 **MCDUserActivity** 활동을 게시 하기 전에 설정 됩니다. 활성화 URI (선택 하면 타임 라인의 예를 들어) 활동이 활성화 될 때 수행할 작업을 결정 합니다. 표시 텍스트를 표시할 다른 장치에서 볼 때 활동 (예를 들어 Windows 타임 라인,). iconUri는 아이콘 이미지에 대 한 웹 링크입니다.


```ObjectiveC
- (IBAction)publishActivityButton:(id)sender
{
    self.createActivityStatusField.text = @"Saving";
    self.activity.activationUri = self.activationUri.text;
    // Set the display text for your activity.
    self.activity.visualElements.displayText = @"Visual Element, like an Adaptive Card";
    self.activity.visualElements.attribution.iconUri = @"https://www.microsoft.com/favicon.ico";

    // ...
```

한 번 합니다 **MCDUserActivity** 채워집니다이 데이터를 사용 하 여 게시 작업을 수행 합니다.

```ObjectiveC
    // ...

    // Publish the Activity
    [self.activity saveAsync:^(NSError* error) {
        dispatch_async(dispatch_get_main_queue(), ^{
            if (error)
            {
                NSLog(@"%@", error);
                self.createActivityStatusField.text = @"Error saving activity";
            }
            else
            {
                self.createActivityStatusField.text = @"Saved successfully!";
                [self.sessionButton setTitle:@"Start Session" forState:normal];
            }
        });
    }];
}

mActivityId = UUID.randomUUID().toString();
mDisplayText = "Created by OneSDK Sample App";
mActivationUri = "http://contoso.com");
```
> [!TIP] 
> 위의 속성 외에도 구성할 수 있는 기타 많은 기능이 있습니다. UserActivity를 사용자 지정할 수 있습니다 하는 다양 한 방법 살펴보고 완료에 대 한 참조를  **[MCDUserActivity](../objectivec-api/userdata.useractivities/MCDUserActivity.md)** 합니다 **[MCDUserActivityVisualElements](../objectivec-api/userdata.useractivities/MCDUserActivityVisualElements.md)**, 및 **[MCDUserActivityAttribution](../objectivec-api/userdata.useractivities/MCDUserActivityAttribution.md)** 클래스입니다. 참조 된 [사용자 작업 모범 사례](https://docs.microsoft.com/windows/uwp/launch-resume/useractivities-best-practices) 사용자 활동을 디자인 하는 방법에 대 한 자세한 권장 사항은 가이드입니다.

## <a name="update-an-existing-user-activity"></a>기존 사용자 활동을 업데이트 합니다.

기존 활동을 한 해당 정보 (발생 시 새 engagement, 변경 된 페이지 및 등)을 업데이트 하려는 경우 있습니다 이렇게 사용 하는 **MCDUserActivitySession**합니다. 

앱의 속성에 원하는 변경을 수행 하기 세션을 만든 후 합니다 **UserActivity**합니다. 변경을 마쳤으면 세션을 닫습니다. 

샘플 앱에서 다음 메서드는 세션을 설정 및 해제 합니다.

```ObjectiveC
- (IBAction)manageSessionButton:(id)sender
{

    // Start a new a session for the UserActivity
    if (self.session == nil)
    {
       self.session = [self.activity createSession];
        dispatch_async(dispatch_get_main_queue(), ^{
            NSLog(@"UserActivitySession has started %@", self.session);
            self.session = [self.activity createSession];
            dispatch_async(dispatch_get_main_queue(), ^{ [self.sessionButton setTitle:@"Stop Session" forState:normal]; });
        });
    }
    else
    {
        // Stop the UserActivitySession
        [self.session close];
        self.session = nil;
        dispatch_async(dispatch_get_main_queue(), ^{
            NSLog(@"UserActivitySession has stopped %@", self.session);
            [self.sessionButton setTitle:@"Start Session" forState:normal];
        });
    }
}
```


**MCDUserActivitySession** 을 만드는 방법으로 생각할 수 있습니다를 **MCDUserActivitySessionHistoryItem** (다음 섹션에서 설명 됨). 새로 만드는 대신 **MCDUserActivity** 될 때마다 사용자가 새 페이지로 이동할 각 페이지에 대 한 새 세션을 간단히 만들 수 있습니다. 이렇게 하면 읽기 환경을 더욱 직관적이 고 구성 된 활동에 대 한 합니다.

## <a name="read-user-activities"></a>사용자 활동 읽기

앱은 사용자 활동 읽기 하 고 Windows 타임 라인 기능이 수행 하는 것 처럼 사용자에 게 제공할 수 있습니다. 사용자 활동 읽기를 설정 하려면 사용할 동일 **MCDUserActivityChannel** 앞에서 인스턴스. 이 인스턴스를 노출할 수 있습니다 **MCDUserActivitySessionHistoryItem** 특정 기간 동안 특정 작업에는 사용자의 참여를 나타내는 경우.

```ObjectiveC
- (IBAction)readActivityButton:(id)sender
{

    // Read/sync your UserActivities
    [self.channel getRecentUserActivitiesAsync:(NSInteger)5
        completion:^(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull result, NSError* _Nullable error) {
            dispatch_async(dispatch_get_main_queue(), ^{
                if (error)
                {
                    self.readActivityStatusField.text = @"Error reading activity!";
                }
                else if (result.count == 0)
                {
                    self.readActivityStatusField.text = @"Read completed, no activities returned";
                }
                else
                {
                    self.readActivityStatusField.text = @"Read completed!";
                    MCDUserActivitySessionHistoryItem* item = result.firstObject;
                    self.activityList.text = item.userActivity.activityId;
                    self.activityDisplay.text = item.userActivity.visualElements.displayText;
                }
            });
        }];
}
```

앱에 채워진된 목록이 있어야 합니다. 이제 **MCDUserActivitySessionHistoryItem**s입니다. 기본 제공할 수 있습니다 이러한 사항의 **MCDUserActivity** (참조 **[MCDUserActivitySessionHistoryItem](../objectivec-api/userdata.useractivities/MCDUserActivitySessionHistoryItem.md)** 세부 정보에 대 한), 사용자에 게 표시할 수 있습니다.
