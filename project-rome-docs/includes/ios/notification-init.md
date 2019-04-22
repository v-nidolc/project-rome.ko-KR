---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 195e419e-ac8d-4e96-8faa-c3659570fa27
ms.localizationpriority: medium
ms.openlocfilehash: 1780fa768475015946b5e33add55ac0f9f247f86
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801155"
---
## <a name="preliminary-setup-for-push-notifications"></a><span data-ttu-id="5b71b-103">푸시 알림에 대 한 예비 설치</span><span class="sxs-lookup"><span data-stu-id="5b71b-103">Preliminary setup for push notifications</span></span>

### <a name="register-your-app-for-push-notifications"></a><span data-ttu-id="5b71b-104">푸시 알림을 위해 앱 등록</span><span class="sxs-lookup"><span data-stu-id="5b71b-104">Register your app for push notifications</span></span>

<span data-ttu-id="5b71b-105">에 대 한 응용 프로그램을 등록 [Apple Push Notification](https://developer.apple.com/notifications/) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-105">Register your application for [Apple Push Notification](https://developer.apple.com/notifications/) support.</span></span> <span data-ttu-id="5b71b-106">보낸 사람에 게 받은; ID 및 서버 키 기록해 해야 합니다. 나중에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-106">Be sure to make note of the sender ID and server key that you receive; you'll need them later.</span></span> 

### <a name="register-your-app-form-cross-device-connected-devices-platform-access"></a><span data-ttu-id="5b71b-107">응용 프로그램 폼 장치 간 장치 플랫폼 연결 액세스를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-107">Register your app form cross-device Connected Devices Platform access</span></span>

<span data-ttu-id="5b71b-108">그런 다음에 대 한 앱을 등록 합니다 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-108">Next, register your app for the [cross-device experiences feature of the Microsoft Developer Dashboard](https://developer.microsoft.com/dashboard/crossplatform/web).</span></span> <span data-ttu-id="5b71b-109">이것이 위의 예비 단계에서 설명 된 Windows 개발자 센터에 등록 절차와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-109">This is a different procedure from registering on the Windows Dev Center, which was covered in the preliminary steps above.</span></span> <span data-ttu-id="5b71b-110">이 연결 된 장치 플랫폼, 네이티브 푸시 알림 서비스를 사용 하 여 알림을 보낼 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-110">It authorizes the Connected Devices Platform to send notifications using the native push notification service.</span></span> <span data-ttu-id="5b71b-111">개발자 센터 온 보 딩 프로세스를 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-111">The Dev Center on-boarding process will require:</span></span>
* <span data-ttu-id="5b71b-112">앱의 클라이언트 id입니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-112">Your app's client ID.</span></span>
* <span data-ttu-id="5b71b-113">Apple Push Notification Service 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-113">The Apple Push Notification Service key.</span></span> <span data-ttu-id="5b71b-114">데이터 및 명령 (잠겨 있거나 절전 수 있는 장치)에서 앱을 제공 하기 위해 필요한이 알림의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-114">This is needed in order to deliver data and commands to the app (on a device which may be locked or asleep) in the form of notifications.</span></span> 

### <a name="configure-your-app-to-be-notification-compatible"></a><span data-ttu-id="5b71b-115">알림 호환 가능 하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="5b71b-115">Configure your app to be notification-compatible</span></span>

<span data-ttu-id="5b71b-116">개발자 대시보드에서 워크플로 완료 한 후 푸시 알림을 수신할 수 있도록 앱의 실제 코드를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-116">After you complete the workflow on the Developer dashboard, you must modify the actual code of your app to make capable of receiving push notifications.</span></span> <span data-ttu-id="5b71b-117">첫째, "원격 알림"을 추가 해야 **UIBackgroundMode** 앱의 _Info.plist_ 백그라운드에서 실행 하는 동안 알림을 받도록 앱을 허용 하려면.</span><span class="sxs-lookup"><span data-stu-id="5b71b-117">First, make sure to add the "remote-notifications" **UIBackgroundMode** to your app's _Info.plist_ to allow the app to receive notifications while running in the background.</span></span> 

<span data-ttu-id="5b71b-118">TBD</span><span class="sxs-lookup"><span data-stu-id="5b71b-118">TBD</span></span>

<span data-ttu-id="5b71b-119">둘째, 앱 시작 되 면 경고 알림을 표시 하도록 권한 부여를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-119">Second, when your app starts up, you must request authorization to display alert notifications.</span></span> <span data-ttu-id="5b71b-120">호출 하 여 이렇게 `-[UIApplication registerUsernotificationSettings:categories:]` 또는 `-[UNUserNotificationCenter requestAuthorizationWithOptions:completionHandler:]`대상 ios 버전에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-120">This is done by calling either `-[UIApplication registerUsernotificationSettings:categories:]` or `-[UNUserNotificationCenter requestAuthorizationWithOptions:completionHandler:]`, depending on what version of iOS you're targeting.</span></span> <span data-ttu-id="5b71b-121">앱에 대 한 권한 부여를 가져온 후 등록할 수 있습니다 다음 호출 하 여 원격 알림의 받을 `-[UIApplication registerForRemoteNotifications]`합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-121">Once your app has acquired the authorization, you can then register to receive remote notifications by calling `-[UIApplication registerForRemoteNotifications]`.</span></span> 

<span data-ttu-id="5b71b-122">연결 된 장치 플랫폼에서 일부 알림 경고를 표시 하 고 이러한 경고의 텍스트를 지역화할 수 있는 응용 프로그램의 문자열 리소스에 삽입 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-122">Some notifications from the Connected Devices Platform will present alerts, and the text of these alerts is localizable and must be inserted into your application's string resources.</span></span> <span data-ttu-id="5b71b-123">앱의 다음 리소스 태그를 정의 해야 합니다 _en.lproj\Localizable.strings_ 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-123">You must define the following resource tags in your app's _en.lproj\Localizable.strings_ file.</span></span> <span data-ttu-id="5b71b-124">이 파일을 만드는 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-124">You may need to create this file.</span></span> <span data-ttu-id="5b71b-125">Xcode에서 선택 **새로 만들기**"문자열" 파일 형식에 대 한 검색, 및 라는 파일을 만듭니다 _Localizable.strings_합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-125">In Xcode, select **New**, search for the file type "Strings", and create a file called _Localizable.strings_.</span></span>

```ObjectiveC
/* The text of the toast notification to display when a remote command is received */ 
"ROME_REMOTE_LAUNCH" = "%1$@ wants to launch this app"; 
"ROME_REMOTE_LAUNCH_FROM_APP" = "%1$@ on %2$@ wants to launch this app"; 
 
/* The text of the toast notification to display when multiple remote commands are received simultaneously */ 
"ROME_CONNECT_TEXT_MANY" = "Another device wants to launch this app"; 
```

### <a name="associate-the-notification-service-with-the-local-platform"></a><span data-ttu-id="5b71b-126">로컬 플랫폼 알림 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="5b71b-126">Associate the notification service with the local Platform</span></span>

<span data-ttu-id="5b71b-127">마지막으로, 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-127">Finally, you must associate push notification functionality with the Connected Devices Platform in your app.</span></span> <span data-ttu-id="5b71b-128">위의 단계를 정의 하지 않고 플랫폼 초기화 된 *notificationProvider* 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-128">In the steps above, you initialized the Platform without defining the *notificationProvider* parameter.</span></span> <span data-ttu-id="5b71b-129">여기에서 생성 하 고 구현 하는 개체에 전달할 필요  **[MCDNotificationProvider](../../objectivec-api/core/MCDNotificationProvider.md)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-129">Here, you need to construct and pass in an object that implements **[MCDNotificationProvider](../../objectivec-api/core/MCDNotificationProvider.md)**.</span></span> <span data-ttu-id="5b71b-130">하는 것이 중요 합니다 `getNotificationRegistrationAsync:` 반환 해야 하는 메서드를 **[MCDNotificationRegistration](../../objectivec-api/core/MCDNotificationRegistration.md)** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5b71b-130">The main thing to note is the `getNotificationRegistrationAsync:` method, which must return a **[MCDNotificationRegistration](../../objectivec-api/core/MCDNotificationRegistration.md)** instance.</span></span> <span data-ttu-id="5b71b-131">합니다 **MCDNotificationRegistration** 는 알림 서비스에 대 한 액세스 토큰 (및 관련된 정보)를 사용 하 여 연결 된 장치 플랫폼을 제공 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-131">The **MCDNotificationRegistration** is responsible for supplying the Connected Devices Platform with an access token (and related information) for the notification service.</span></span>

<span data-ttu-id="5b71b-132">이 등록의 구현에서 제공 **MCDNotificationProvider**합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-132">Deliver this registration in your implementation of **MCDNotificationProvider**.</span></span> <span data-ttu-id="5b71b-133">플랫폼 초기화 호출 시작 요청 및 앱 서비스 메시지를 릴레이 하는 앱이 서버 쪽 연결 된 장치 플랫폼에서 데이터를 받을 수 있도록 푸시 알림 서비스에 대 한 액세스를 사용 하 여 로컬 플랫폼을 제공 해야 그런 다음 다른 장치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-133">Then, the Platform initialization call should provide the local Platform with access to the push notification service, allowing your app to receive data from the server-side Connected Devices Platform, which relays launch requests and app service messages from other devices.</span></span> 

<span data-ttu-id="5b71b-134">다음은 구현의 **MCDNotificationProvider** 샘플 앱에서.</span><span class="sxs-lookup"><span data-stu-id="5b71b-134">The following is an implementation of **MCDNotificationProvider** from the sample app.</span></span>

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

<span data-ttu-id="5b71b-135">다음 샘플 코드 업데이트 **MCDNotificationProvider** 에서 입력 인 **MCDNotificationRegistration**합니다.</span><span class="sxs-lookup"><span data-stu-id="5b71b-135">The following sample code updates this **MCDNotificationProvider** with a filled-in **MCDNotificationRegistration**.</span></span>

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
