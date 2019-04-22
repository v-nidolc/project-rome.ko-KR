---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 30df8538-1c1f-498f-af25-0be0aed687c8
ms.localizationpriority: medium
ms.openlocfilehash: 95b6dd68706a1582a91718a48ba7961cd8d07ddf
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801505"
---
### <a name="todo-configure-your-app-to-be-apns-notification-compatible"></a><span data-ttu-id="f8dba-103">APNs 알림 호환 되도록 앱 TODO 구성</span><span class="sxs-lookup"><span data-stu-id="f8dba-103">TODO Configure your app to be APNs notification-compatible</span></span>

<span data-ttu-id="f8dba-104">개발자 대시보드에서 워크플로 완료 한 후 푸시 알림을 수신할 수 있도록 앱의 실제 코드를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-104">After you complete the workflow on the Developer dashboard, you must modify the actual code of your app to make capable of receiving push notifications.</span></span> <span data-ttu-id="f8dba-105">첫째, "원격 알림"을 추가 해야 **UIBackgroundMode** 앱의 _Info.plist_ 백그라운드에서 실행 하는 동안 알림을 받도록 앱을 허용 하려면.</span><span class="sxs-lookup"><span data-stu-id="f8dba-105">First, make sure to add the "remote-notifications" **UIBackgroundMode** to your app's _Info.plist_ to allow the app to receive notifications while running in the background.</span></span> 

<span data-ttu-id="f8dba-106">둘째, 앱 시작 되 면 경고 알림을 표시 하도록 권한 부여를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-106">Second, when your app starts up, you must request authorization to display alert notifications.</span></span> <span data-ttu-id="f8dba-107">호출 하 여 이렇게 `-[UIApplication registerUsernotificationSettings:categories:]` 또는 `-[UNUserNotificationCenter requestAuthorizationWithOptions:completionHandler:]`대상 ios 버전에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-107">This is done by calling either `-[UIApplication registerUsernotificationSettings:categories:]` or `-[UNUserNotificationCenter requestAuthorizationWithOptions:completionHandler:]`, depending on what version of iOS you're targeting.</span></span> <span data-ttu-id="f8dba-108">앱에 대 한 권한 부여를 가져온 후 등록할 수 있습니다 다음 호출 하 여 원격 알림의 받을 `-[UIApplication registerForRemoteNotifications]`합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-108">Once your app has acquired the authorization, you can then register to receive remote notifications by calling `-[UIApplication registerForRemoteNotifications]`.</span></span> 

### <a name="associate-the-connected-devices-platform-with-apns-native-push-notification-for-ios"></a><span data-ttu-id="f8dba-109">IOS 용 APNs 네이티브 푸시 알림을 사용 하 여 연결 된 장치 플랫폼을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-109">Associate the Connected Devices Platform with APNs native push notification for iOS.</span></span> 
<span data-ttu-id="f8dba-110">와 같은 이전에 언급 했 듯이, 앱 클라이언트가 필요로 하는 동안 사용 되 고 클라이언트 쪽 SDK 각 모바일 플랫폼 및 연결 된 장치 플랫폼에 대 한 등록 프로세스를 그래프 수 있도록 네이티브 푸시 알림 파이프라인에 대 한 지식을 제공 하기 위해 알림 서비스에 앱 서버에서 MS Graph Api를 통해 사용자를 대상으로 알림을 게시할 때 각 앱 클라이언트 끝점에 팬아웃 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-110">Like previously mentioned, the app clients need to provide knowledge about the native push notification pipeline being used for each mobile platform to the client-side SDK and the Connected Devices Platform during the registration process, to allow Graph notification service to fan-out notifications to each app client endpoint when your app server publishes a user-targeting notification via MS Graph APIs.</span></span>

<span data-ttu-id="f8dba-111">위의 단계를 정의 하지 않고 플랫폼 초기화 된 *notificationProvider* 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-111">In the steps above, you initialized the Platform without defining the *notificationProvider* parameter.</span></span> <span data-ttu-id="f8dba-112">여기에서 생성 하 고 구현 하는 개체에 전달할 필요  **[MCDNotificationProvider](../../objectivec-api/core/MCDNotificationProvider.md)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-112">Here, you need to construct and pass in an object that implements **[MCDNotificationProvider](../../objectivec-api/core/MCDNotificationProvider.md)**.</span></span> <span data-ttu-id="f8dba-113">하는 것이 중요 합니다 `getNotificationRegistrationAsync:` 반환 해야 하는 메서드를 **[MCDNotificationRegistration](../../objectivec-api/core/MCDNotificationRegistration.md)** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f8dba-113">The main thing to note is the `getNotificationRegistrationAsync:` method, which must return a **[MCDNotificationRegistration](../../objectivec-api/core/MCDNotificationRegistration.md)** instance.</span></span> <span data-ttu-id="f8dba-114">합니다 **MCDNotificationRegistration** 는 알림 서비스에 대 한 액세스 토큰 (및 관련된 정보)를 사용 하 여 연결 된 장치 플랫폼을 제공 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-114">The **MCDNotificationRegistration** is responsible for supplying the Connected Devices Platform with an access token (and related information) for the notification service.</span></span>

<span data-ttu-id="f8dba-115">이 등록의 구현에서 제공 **MCDNotificationProvider**합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-115">Deliver this registration in your implementation of **MCDNotificationProvider**.</span></span> <span data-ttu-id="f8dba-116">플랫폼 초기화 호출 시작 요청 및 앱 서비스 메시지를 릴레이 하는 앱이 서버 쪽 연결 된 장치 플랫폼에서 데이터를 받을 수 있도록 푸시 알림 서비스에 대 한 액세스를 사용 하 여 로컬 플랫폼을 제공 해야 그런 다음 다른 장치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-116">Then, the Platform initialization call should provide the local Platform with access to the push notification service, allowing your app to receive data from the server-side Connected Devices Platform, which relays launch requests and app service messages from other devices.</span></span> 

<span data-ttu-id="f8dba-117">다음은 구현의 **MCDNotificationProvider** 샘플 앱에서.</span><span class="sxs-lookup"><span data-stu-id="f8dba-117">The following is an implementation of **MCDNotificationProvider** from the sample app.</span></span>

```ObjectiveC
@implementation NotificationProvider
{
    MCDRegistrationUpdatedEvent* _registrationUpdated;
    MCDNotificationRegistration* _notificationRegistration;
}

+ (instancetype)sharedInstance
{
    static NotificationProvider* sharedInstance = nil;

    static dispatch_once_t onceToken;
    dispatch_once(&onceToken, ^{ sharedInstance = [[NotificationProvider alloc] init]; });

    return sharedInstance;
}

+ (void)updateNotificationRegistration:(MCDNotificationRegistration*)notificationRegistration
{
    dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0),
        ^{ [[NotificationProvider sharedInstance] _updateNotificationRegistration:notificationRegistration]; });
}

// MCDNotificationProvider
@synthesize registrationUpdated = _registrationUpdated;

- (void)getNotificationRegistrationAsync:(nonnull void (^)(MCDNotificationRegistration* _Nullable, NSError* _Nullable))completionBlock
{
    dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0), ^{ completionBlock(_notificationRegistration, nil); });
}

- (instancetype)init
{
    if (self = [super init])
    {
        _registrationUpdated = [MCDRegistrationUpdatedEvent new];
    }

    return self;
}

- (void)_updateNotificationRegistration:(MCDNotificationRegistration*)notificationRegistration
{
    _notificationRegistration = notificationRegistration;

    [_registrationUpdated raiseWithNotificationRegistration:notificationRegistration];
}
@end
```

<span data-ttu-id="f8dba-118">다음 샘플 코드 업데이트 **MCDNotificationProvider** 에서 입력 인 **MCDNotificationRegistration**합니다.</span><span class="sxs-lookup"><span data-stu-id="f8dba-118">The following sample code updates this **MCDNotificationProvider** with a filled-in **MCDNotificationRegistration**.</span></span>

```ObjectiveC
/*
* NotificationRegistration is constructed with four parameters:
* Type: This is GCM or FCM or APN (the notification platform type).
* Token: This is the NSData that APNs sends to your app delegate's didRegisterForRemoteNotificationsWithDeviceToken: method. You must convert the NSData into a string by hex-encoding it.
* SenderId: This is your app’s bundle identifier. 
* DisplayName: This should be the name of the app that you used when you registered it on the Microsoft dev portal. 
*/
[NotificationProvider
    updateNotificationRegistration:[[MCDNotificationRegistration alloc]
        initWithNotificationType:MCDNotificationTypeAPN
        token:deviceTokenStr
        appId:[[NSBundle mainBundle] bundleIdentifier]
        appDisplayName:(NSString*)[[NSBundle mainBundle]
            objectForInfoDictionaryKey:@"CFBundleDisplayName"]]];
```
