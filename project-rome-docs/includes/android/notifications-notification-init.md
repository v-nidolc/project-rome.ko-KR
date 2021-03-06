---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 9fb27596-e9a3-443a-9c12-9e02a893e32c
ms.localizationpriority: medium
ms.openlocfilehash: 27ff12ef8b0773f1bd0e1960c285012f7e62fdc9
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801807"
---
### <a name="associate-the-connected-devices-platform-with-the-native-push-notification-for-each-mobile-platform"></a>각 모바일 플랫폼에 대 한 네이티브 푸시 알림을 사용 하 여 연결 된 장치 플랫폼을 연결 합니다. 

와 같은 이전에 언급 했 듯이, 앱 클라이언트가 필요로 하는 동안 사용 되 고 클라이언트 쪽 SDK 각 모바일 플랫폼 및 연결 된 장치 플랫폼에 대 한 등록 프로세스를 그래프 수 있도록 네이티브 푸시 알림 파이프라인에 대 한 지식을 제공 하기 위해 알림 서비스에 앱 서버에서 Microsoft Graph Api를 통해 사용자를 대상으로 알림을 게시할 때 각 앱 클라이언트 끝점에 팬아웃 알림입니다.

위의 단계에서 플랫폼을 초기화 하는 `null` *notificationProvider* 매개 변수입니다. 여기에서 생성 하 고 구현 하는 개체에 전달할 필요  **[NotificationProvider](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.core._notification_provider)** 합니다. 하는 것이 중요 합니다 `getNotificationRegistrationAsync` 반환 해야 하는 메서드를 **[NotificationRegistration](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.core._notification_registration)** 인스턴스. 합니다 **NotificationRegistration** 는 알림 서비스에 대 한 액세스 토큰 (및 관련된 정보)를 사용 하 여 연결 된 장치 플랫폼을 제공 하는 일을 담당 합니다.

```java
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

이 등록의 구현에서 제공 **NotificationProvider**합니다. 그런 다음, **플랫폼** 초기화 호출 로컬 제공 해야 **플랫폼** 푸시 알림 서비스에 대 한 액세스를 사용 하 여 데이터를 Microsoft Graph 알림을 받도록 앱 허용 서버 쪽입니다. 

### <a name="pass-incoming-push-notifications-to-the-client-sdk"></a>클라이언트 SDK에 들어오는 푸시 알림을 전달합니다
이제 수신기가 기본 확장 서비스 클래스 ([FirebaseMessagingService](https://firebase.google.com/docs/reference/android/com/google/firebase/messaging/FirebaseMessagingService) 이 경우이 자습서에서 사용 하므로 Firebase Cloud Messaging)의 특별 한 오버 로드를 사용 하 여는 `onMessageReceived` 메서드 (알림-처리 메서드)입니다.

규정 준수, 보안 및 잠재적인 최적화, 인해 그래프 알림을 서버 쪽에서 들어오는 들어오는 Google Cloud Messaging 알림을 앱 서버에서 처음 게시 된 모든 데이터가 포함 되지 않은 자격 증명 입력 탭을 수 있습니다. 앱 서버에서 게시 실제 알림 콘텐츠 검색 클라이언트 쪽 SDK Api 뒤에 숨겨져 있습니다. 이 때문에 SDK는 앱 클라이언트 항상 들어오는 Google 클라우드 메시징 페이로드를 전달 SDK는 일관 된 프로그래밍 패턴을 제공할 수 있습니다. 이렇게 하면 (에 없는 경우 Android의 네이티브 Google Cloud Messaging 채널은 다른 용도에 클라이언트 앱에서 사용) 또는 연결 된 장치 플랫폼 시나리오에 대 한 알림 인지 여부를 결정할 SDK 및 어떤 시나리오/기능이 들어오는 알림 (그래프 알림, 사용자 활동, 등)에 해당 합니다. 다른 유형의 시나리오 처리에 특정 논리 그 후 앱 클라이언트에서 실행할 수 있습니다. 

```java
/**
* Check whether it's a Connected Devices Platform notification or not.
* If it is a Connected Devices Platform notification, it will notify the apps with the information in the notification.
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

앱에 연결 된 장치 플랫폼에서 알림을 처리할 이제 수 있습니다.

