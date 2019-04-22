---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: fcbcfd8f-6eea-421a-97bb-31ea3c987728
ms.localizationpriority: medium
ms.openlocfilehash: 57115d59657d91200d969e2bb05154c3d2499dc7
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801576"
---
## <a name="preliminary-setup-for-push-notifications"></a>푸시 알림에 대 한 예비 설치

### <a name="register-your-app-for-push-notifications"></a>푸시 알림을 위해 앱 등록

알림 지원에 대 한 Google을 사용 하 여 응용 프로그램을 등록 합니다. 보낸 사람에 게 받은; ID 및 서버 키 기록해 해야 합니다. 나중에 필요 합니다. 

### <a name="register-your-app-for-cross-device-connected-devices-platform-access"></a>장치 간 장치 플랫폼 연결 액세스를 위해 앱 등록

그런 다음에 대 한 앱을 등록 합니다 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다. 이것이 위의 예비 단계에서 설명 된 Windows 개발자 센터에 등록 절차와는 다릅니다. 이 연결 된 장치 플랫폼, 네이티브 푸시 알림 서비스를 사용 하 여 알림을 보낼 권한을 부여 합니다. 개발자 센터 온 보 딩 프로세스를 필요 합니다.
* 앱의 클라이언트 id입니다.
* Google Cloud Messaging 키입니다. 데이터 및 명령 (잠겨 있거나 절전 수 있는 장치)에서 앱을 제공 하기 위해 필요한이 푸시 알림의 형식입니다. 

### <a name="configure-your-app-to-be-notification-compatible"></a>알림 호환 가능 하도록 앱 구성

개발자 대시보드에서 워크플로 완료 한 후 푸시 알림을 수신할 수 있도록 앱의 실제 코드를 수정 해야 합니다. 참조 [설정 하는 Firebase 클라우드 메시징 클라이언트 Android에서 앱](https://firebase.google.com/docs/cloud-messaging/android/client) 이 작업을 수행 하는 방법을 잘 모르는 경우.

### <a name="associate-the-notification-service-with-the-local-platform"></a>로컬 플랫폼 알림 서비스에 연결

마지막으로, 앱에서 연결 된 장치 플랫폼을 사용 하 여 푸시 알림 기능을 연결 해야 합니다. 위의 단계에서 플랫폼을 초기화 하는 `null` *notificationProvider* 매개 변수입니다. 여기에서 생성 하 고 구현 하는 개체에 전달할 필요  **[NotificationProvider](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.core._notification_provider)** 합니다. 하는 것이 중요 합니다 `getNotificationRegistrationAsync` 반환 해야 하는 메서드를 **[NotificationRegistration](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.core._notification_registration)** 인스턴스. 합니다 **NotificationRegistration** 는 알림 서비스에 대 한 액세스 토큰 (및 관련된 정보)를 사용 하 여 연결 된 장치 플랫폼을 제공 하는 일을 담당 합니다.


```Java
private NotificationRegistration mNotificationRegistration;

// ...

/**
* NotificationRegistration is constructed with four parameters:
* Type: This is the notification platform type.
* Token: This is the string that GCM or FCM sends to your registration intent service.
* SenderId: This is the numeric Sender ID that you received when you registered your app for push notifications.
* DisplayName: This should be the name of the app that you used when you registered it on the Microsoft dev portal. 
*/
mNotificationRegistration = new NotificationRegistration(NotificationType.FCM, token, FCM_SENDER_ID, "MyAppName");
```

이 등록의 구현에서 제공 **NotificationProvider**합니다. 그런 다음, **플랫폼** 초기화 호출 로컬 제공 해야 **플랫폼** 푸시 알림 서비스에 대 한 액세스를 사용 하 여 서버 쪽 연결 된 장치에서 데이터를 받도록 앱 허용 플랫폼 시작 요청 및 기타 장치에서 앱 서비스 메시지를 릴레이 합니다. 

기본 수신기에 확장 하기만 하면 이제는 서비스 클래스 ([FirebaseMessagingService](https://firebase.google.com/docs/reference/android/com/google/firebase/messaging/FirebaseMessagingService) 이 경우이 가이드를 사용 하므로 Firebase Cloud Messaging)의 특별 한 오버 로드를 사용 하 여는 `onMessageReceived` (메서드 알림 처리 방법)입니다.

```Java
/**
* Check whether it's a rome notification or not.
* If it is a rome notification, it will notify the apps with the information in the notification.
* @param from describes message sender.
* @param data message data as String key/value pairs.
*/
@Override
public void onMessageReceived(String from, Bundle data) {
    Log.d(TAG, "From: " + from);

    // Ensure that the Platform is initialized here before going on
    // ...

    // This method passes the data to the Connected Devices Platform if is compatible.
    if (!NotificationReceiver.Receive(data)) {
        // a value of false indicates a non-Rome notification
        Log.d(TAG, "GCM client received a message that was not a Rome notification");
    }
}
```

앱을 연결 된 장치 플랫폼에서 알림을 처리할 수 되었습니다.
