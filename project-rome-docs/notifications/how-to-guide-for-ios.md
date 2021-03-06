---
title: 그래프 알림과 통합 하는 IOs 앱
description: 알림에 대 한 수신 끝점에 필요한 등록 단계를 수행 하는 방법에 앱 서버에서 게시 합니다.
ms.assetid: c973d534-08e9-4f6e-8b54-bcae97067961
ms.localizationpriority: medium
ms.custom: seodec18
ms.openlocfilehash: 889d2a72752a01b60ab1585dd3d4f78624b2b214
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801315"
---
# <a name="how-to-guide-integrating-with-graph-notifications-ios"></a>방법 가이드: 그래프 알림 (iOS)와 통합

그래프 알림을 보내고 여러 장치에서 사용자를 대상으로 알림을 관리 앱을 사용 합니다. 

Ios 프로젝트 로마 클라이언트 쪽 SDK를 사용 하 여 iOS 앱에 로그인된 한 사용자를 대상으로 앱 서버에서 게시 알림을 받도록 등록할 수 있습니다. SDK을 사용 하면 앱 클라이언트가 들어오는 새 알림 페이로드를 수신 하려면 기존 알림 및 검색 알림 기록의 상태를 관리 합니다. 알림 및이 통해 사람이 중심 알림을 배달 하는 방법에 대 한 자세한 내용은 참조 하세요. [Microsoft Graph 알림 개요](index.md)

프로젝트 로마 SDK includng 그래프 알림 등의 모든 기능이 연결 된 장치 플랫폼을 호출 하는 기본 플랫폼 위에 구축 됩니다. 이 가이드에 연결 된 장치 플랫폼을 사용 하 여 시작 하려면 그래프 알림을 구현 하는 SDK의 Api를 사용 하는 방법에 설명 하는 데 필요한 단계를 안내 합니다-특정 기능입니다.

이 단계 아래에서 코드 참조는 [프로젝트 로마 iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples) GitHub에서 사용할 수 있는 합니다.  

참조 된 [API 참조](api-reference-for-ios/index.md) 알림 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.

## <a name="setting-up-the-connected-devices-platform-and-notifications"></a>연결 된 장치 플랫폼 및 알림 설정

[!INCLUDE [ios/preliminary-setup](../includes/ios/preliminary-setup.md)]

[!INCLUDE [auth-scopesiOS](../includes/auth-scopesiOS.md)]

[!INCLUDE [ios/dev-center-onboarding](../includes/ios/notifications-dev-center-onboarding.md)]

## <a name="using-the-platform"></a>플랫폼을 사용 하 여

[!INCLUDE [ios/create-setup-events-start-platform](../includes/ios/create-setup-events-start-platform.md)]

## <a name="initialize-a-graph-notification-channel"></a>그래프 알림 채널을 초기화 합니다.
프로젝트 로마 SDK에는 앱을을 수신 하 고 다양 한 유형의 사용자 활동 그래프 알림 등을 포함 하 여 사용자 데이터를 관리 하기 위해 다른 채널을 구독할 수 있습니다. 모두 저장 하 고 동기화에서 이들은 **MCDUserDataFeed**합니다. **MCDUserNotification** 사용자 대상 알림 전송 그래프 알림을 통해 해당 클래스 및 데이터 형식입니다.
그래프 알림 및 앱 서버에서 게시 MCDUserNotification 받기 시작와를 통합 하려면 먼저 피드를 만들어서 사용자 데이터를 초기화 하는 **MCDUserNotificationChannel**합니다. 위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다.

다음 메서드 초기화를 **MCDUserNotificationChannel**합니다.
```ObjectiveC
// You must be logged in to use UserNotifications
NSArray<MCDUserAccount*>* accounts = [[AppDataSource sharedInstance].accountProvider getUserAccounts];
if (accounts.count > 0)
{
    // Get a UserNotification channel, getting the default channel
    NSLog(@"Creating UserNotificationChannel");
    NSArray<MCDUserAccount*>* accounts = [[AppDataSource sharedInstance].accountProvider getUserAccounts];
    MCDUserDataFeed* userDataFeed = [MCDUserDataFeed userDataFeedForAccount:accounts[0]
        platform:[AppDataSource sharedInstance].platform
        activitySourceHost:CROSS_PLATFORM_APP_ID];
    NSArray<MCDSyncScope*>* syncScopes = @[ [MCDUserNotificationChannel syncScope] ];
    [userDataFeed addSyncScopes:syncScopes];
    self.channel = [MCDUserNotificationChannel userNotificationChannelWithUserDataFeed:userDataFeed];
}
else
{
    NSLog(@"Must log in to receive notifications for the logged in user!");
    self.createNotificationStatusField.text = @"Need to be logged in!";
}
```
이 시점에서 해야는 **MCDUserNotificationChannel** 에서 참조할 `channel`합니다.

## <a name="create-a-mcdusernotificationreader-to-receive-incoming-mcdusernotifications-and-access-mcdusernotification-history"></a>들어오는 MCDUserNotifications 받고 MCDUserNotification 기록에 액세스 하려면 MCDUserNotificationReader 만들기
살펴보았습니다 이전에 초기 APNS 자동으로 앱 클라이언트 에서만 도착 메시지 자격 증명 입력 탭을 포함 및 연결 된 장치 플랫폼에 연결 된 장치를 사용 하 여 전체 동기화를 수행 하려면 SDK를 트리거하기 위해 해당 자격 증명 입력 탭 페이로드를 전달 해야 합니다. 앱 서버에서 게시 된 모든 MCDUserNotifications를 포함 하는 서버 이 자격 증명 입력 탭에 해당 앱 서버에서 게시 된 모든 알림 페이로드를 가져오게 됩니다. (및 경우에서 이전의 모든 알림이 게시 되었지만 장치 연결 또는 기타 문제로 인해이 응용 프로그램 클라이언트에서 수신 하지 됩니다. 가져온도). SDK에서 지속적으로 수행 되어 이러한 실시간 동기화를 사용 하 여 응용 프로그램 클라이언트는이 로그인 한 사용자의 MCDUserNotification 데이터 피드의 로컬 캐시에 액세스할 수 있습니다. MCDUserNotificationReader에는 경우이 데이터 피드에 – 앱 클라이언트의 액세스할 수 있도록 이벤트 수신기를 통해 최신 알림 페이로드 또는 사용자의 알림 뷰 모델로 사용할 수 있는 전체 MCDUserNotification 컬렉션에 액세스 하려면 기록 합니다.  
### <a name="receiving-mcdusernotifications"></a>수신 MCDUserNotifications
먼저 MCDUserNotificationReader, 인스턴스화 및 사용 하도록 설정 하려는 환경에 대 한 정보를 사용 하려는 경우 판독기에는 모든 기존 MCDUserNotifications 이미 가져오기 해야 합니다. 항상 앱 서버에 이미 게시 한다는 알림을이 경우에이 특정 장치 끝점 설정 되지 않을 수 있습니다는 사용자를 로그인 또는 사용자가 앱을 설치 하는 첫 번째 끝점을 가정 하에 안전 합니다. 연결 된 장치 플랫폼 동기화를 완료 하 고 알리는 새 변경 될 때 트리거되는 이벤트 수신기를 추가 합니다. 그래프 알림의 경우 새 변경 내용을 새 수 앱 서버나 MCDUserNotifcation 업데이트, 삭제에서 들어오는 MCDUserNotifications 게시 및 만료 또는 다른 서버에서 발생 하는 끝점을 등록 하는 동일한 사용자 에 기록 됩니다.

> [!TIP] 
> 이 이벤트 수신기에는 기본 비즈니스 논리를 처리 하 고 "사용" 시나리오에 따라 알림 페이로드 콘텐츠 위치는입니다. 현재 OS 수준 알림 센터에서 visual 알림을 생성 하려면 APNS 자동 알림을 사용 하는 경우, 자동 알림 영역에서 콘텐츠를 사용 하 여 일부 앱에서 UI를 업데이트 하는 경우 작업을 수행 하는 위치입니다. 

```ObjectiveC
// Instantiate the reader from a MCDUserNotificationChannel
// Add a data change listener to subscribe to new changes when new notifications or notification updates are received
- (void)setupWithAccount:(MCDUserAccount*)account {
    dispatch_async(dispatch_get_global_queue(QOS_CLASS_DEFAULT, 0), ^{
        @synchronized (self) {
            MCDUserDataFeed* dataFeed = [MCDUserDataFeed userDataFeedForAccount:account platform:_platform activitySourceHost:@"graphnotifications.sample.windows.com"];
            [dataFeed addSyncScopes:@[[MCDUserNotificationChannel syncScope]]];
            self.channel = [MCDUserNotificationChannel userNotificationChannelWithUserDataFeed:dataFeed];
            self.reader = [self.channel createReader];
            
            __weak typeof(self) weakSelf = self;
            _readerRegistrationToken = [self.reader addDataChangedListener:^(__unused MCDUserNotificationReader* source) {
                NSLog(@"ME123 Got a change!");
                if (weakSelf) {
                    [weakSelf forceRead];
                } else {
                    NSLog(@"ME123 WEAKSELF FOR CHANGES IS NULL!!!");
                }
            }];
            
            [self forceRead];
        }
    });
}

// this is your own business logic when the event listener is fired
// In this case, the app reads the existing batch of notifications in the store and handle any new incoming notifications or notification updates after that
- (void)forceRead {
    NSLog(@"ME123 Forced to read!");
    [self.reader readBatchAsyncWithMaxSize:NSUIntegerMax completion:^(NSArray<MCDUserNotification *> * _Nullable notifications, NSError * _Nullable error) {
        if (error) {
            NSLog(@"ME123 Failed to read batch with error %@", error);
        } else {
            [self _handleNotifications:notifications];
            NSLog(@"ME123 Have %ld listeners", self.listenerMap.count);
            for (void (^listener)(void) in self.listenerMap.allValues) {
                NSLog(@"ME123 Calling a listener about an update!");
                listener();
            }
        }
    }];
}

```

## <a name="update-the-state-of-an-existing-mcdusernotification"></a>기존 MCDUserNotification의 상태를 업데이트 합니다.
이전 섹션에서 설명한 대로 따라 판독기를 통해 받은 MCDUserNotification 변경 수는 기존 MCDUserNotification –에서 상태 업데이트를으로 표시 되거나 해제 된 읽음으로 표시 되 고 되는지 여부를 합니다. 이 경우 응용 프로그램 클라이언트를 선택할 수를 유니버설 예를 들어이 특정 장치에서 해당 visual 알림을 제거 하 여 해제 합니다. 다시 단계에서 확인 하 고 앱 클라이언트 경우가이 MCDUserNotification 변경 업데이트를 시작 하려면 – 다른 장치에서 시작 하는 합니다. 프로그램 MCDUserNotifications의 상태를 업데이트 하는 시간을 선택할 수 있지만 일반적으로 이러한 업데이트 해당 visual 알림을 해당 장치에서 사용자에 의해 처리 됩니다 때나 알림을 추가로 처리 됩니다 일부 앱 내 환경에서 사용자가 있습니다. 사용 하도록 설정 합니다. 흐름은 모양을의 예는 다음과 같습니다. 앱 서버 1. 사용자는 자신의 PC 및 앱 클라이언트를 설치할 자신의 휴대폰에서이 알림을 받으면 사용자를 대상으로 알림을 게시 합니다. PC에서 알림을 클릭 하 고 해당 작업 핸들을 앱에가 하는 사용자. 그런 다음이 PC에 앱 클라이언트 연결 된 장치 플랫폼 SDK이 모든이 사용자의이 장치 간에 동기화이 업데이트를 위해서는 해당 사용자 알림 상태를 업데이트할 수를 호출 합니다. 이 받으면 다른 앱 클라이언트를 실시간으로 업데이트 상태는 다음 해당 시각적 경고가 제거 / 메시지 / 장치의 알림 센터 알림 / 알림 트레이 작업 센터 /입니다. 사용자의 장치에서 알림을 해제 보편적으로 가져오기 방법입니다. 

> [!TIP]
> MCDUserNotification 클래스에는 현재 두 가지 유형의 상태 업데이트 제공 –는 MCDUserNotificationReadState 또는 MCDUserNotificationUserActionState 수정 하 고 알림을 업데이트 될 때 수행할 동작에 고유한 논리를 정의할 수 있습니다. 예를 들어, Activated 또는 해제 됨, 작업 상태를 표시할 수 있습니다 및 universal를 구현 하는 값에서 피벗 해제 합니다. 또는 동시에 표시할 수 있습니다를 읽기 또는 읽지 않은 상태를 읽고 기반 앱 내 알림이 기록 보기에서 알림을 표시할지를 결정 하는 합니다. 

```ObjectiveC
- (void)dismissNotification:(MCDUserNotification*)notification {
    @synchronized (self) {
        notification.userActionState = MCDUserNotificationUserActionStateDismissed;
        [notification saveAsync:^(__unused MCDUserNotificationUpdateResult * _Nullable result, __unused NSError * _Nullable err) {
            NSLog(@"ME123 Dismiss notification with result %d error %@", result.succeeded, err);
        }];
    }
}

```
