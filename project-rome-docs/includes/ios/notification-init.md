---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 195e419e-ac8d-4e96-8faa-c3659570fa27
ms.localizationpriority: medium
ms.openlocfilehash: 1780fa768475015946b5e33add55ac0f9f247f86
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909665"
---
## <a name="preliminary-setup-for-push-notifications"></a>푸시 알림에 대 한 예비 설치

### <a name="register-your-app-for-push-notifications"></a>푸시 알림을 위해 앱 등록

에 대 한 응용 프로그램을 등록 [Apple Push Notification](https://developer.apple.com/notifications/) 지원 합니다. 보낸 사람에 게 받은; ID 및 서버 키 기록해 해야 합니다. 나중에 필요 합니다. 

### <a name="register-your-app-form-cross-device-connected-devices-platform-access"></a>응용 프로그램 폼 장치 간 장치 플랫폼 연결 액세스를 등록 합니다.

그런 다음에 대 한 앱을 등록 합니다 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다. 이것이 위의 예비 단계에서 설명 된 Windows 개발자 센터에 등록 절차와는 다릅니다. 이 연결 된 장치 플랫폼, 네이티브 푸시 알림 서비스를 사용 하 여 알림을 보낼 권한을 부여 합니다. 개발자 센터 온 보 딩 프로세스를 필요 합니다.
* 앱의 클라이언트 id입니다.
* Apple Push Notification Service 키입니다. 데이터 및 명령 (잠겨 있거나 절전 수 있는 장치)에서 앱을 제공 하기 위해 필요한이 알림의 형식입니다. 

### <a name="configure-your-app-to-be-notification-compatible"></a>알림 호환 가능 하도록 앱 구성

개발자 대시보드에서 워크플로 완료 한 후 푸시 알림을 수신할 수 있도록 앱의 실제 코드를 수정 해야 합니다. 첫째, "원격 알림"을 추가 해야 **UIBackgroundMode** 앱의 _Info.plist_ 백그라운드에서 실행 하는 동안 알림을 받도록 앱을 허용 하려면. 

TBD

둘째, 앱 시작 되 면 경고 알림을 표시 하도록 권한 부여를 요청 해야 합니다. 호출 하 여 이렇게 `-[UIApplication registerUsernotificationSettings:categories:]` 또는 `-[UNUserNotificationCenter requestAuthorizationWithOptions:completionHandler:]`대상 ios 버전에 따라 합니다. 앱에 대 한 권한 부여를 가져온 후 등록할 수 있습니다 다음 호출 하 여 원격 알림의 받을 `-[UIApplication registerForRemoteNotifications]`합니다. 

연결 된 장치 플랫폼에서 일부 알림 경고를 표시 하 고 이러한 경고의 텍스트를 지역화할 수 있는 응용 프로그램의 문자열 리소스에 삽입 되어야 합니다. 앱의 다음 리소스 태그를 정의 해야 합니다 _en.lproj\Localizable.strings_ 파일입니다. 이 파일을 만드는 해야 합니다. Xcode에서 선택 **새로 만들기**"문자열" 파일 형식에 대 한 검색, 및 라는 파일을 만듭니다 _Localizable.strings_합니다.

```ObjectiveC
/* The text of the toast notification to display when a remote command is received */ 
"ROME_REMOTE_LAUNCH" = "%1$@ wants to launch this app"; 
"ROME_REMOTE_LAUNCH_FROM_APP" = "%1$@ on %2$@ wants to launch this app"; 
 
/* The text of the toast notification to display when multiple remote commands are received simultaneously */ 
"ROME_CONNECT_TEXT_MANY" = "Another device wants to launch this app"; 
```

### <a name="associate-the-notification-service-with-the-local-platform"></a>로컬 플랫폼 알림 서비스에 연결

마지막으로, 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다. 위의 단계를 정의 하지 않고 플랫폼 초기화 된 *notificationProvider* 매개 변수입니다. 여기에서 생성 하 고 구현 하는 개체에 전달할 필요  **[MCDNotificationProvider](../../objectivec-api/core/MCDNotificationProvider.md)** 합니다. 하는 것이 중요 합니다 `getNotificationRegistrationAsync:` 반환 해야 하는 메서드를 **[MCDNotificationRegistration](../../objectivec-api/core/MCDNotificationRegistration.md)** 인스턴스. 합니다 **MCDNotificationRegistration** 는 알림 서비스에 대 한 액세스 토큰 (및 관련된 정보)를 사용 하 여 연결 된 장치 플랫폼을 제공 하는 일을 담당 합니다.

이 등록의 구현에서 제공 **MCDNotificationProvider**합니다. 플랫폼 초기화 호출 시작 요청 및 앱 서비스 메시지를 릴레이 하는 앱이 서버 쪽 연결 된 장치 플랫폼에서 데이터를 받을 수 있도록 푸시 알림 서비스에 대 한 액세스를 사용 하 여 로컬 플랫폼을 제공 해야 그런 다음 다른 장치 합니다. 

다음은 구현의 **MCDNotificationProvider** 샘플 앱에서.

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

다음 샘플 코드 업데이트 **MCDNotificationProvider** 에서 입력 인 **MCDNotificationRegistration**합니다.

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
