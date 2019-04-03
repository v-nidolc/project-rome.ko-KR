### <a name="associate-the-connected-devices-platform-with-the-native-push-notification-for-each-platform"></a>각 플랫폼에 대 한 네이티브 푸시 알림을 사용 하 여 연결 된 장치 플랫폼을 연결 합니다. 

와 같은 이전에 언급 했 듯이, 앱 클라이언트가 필요로 하는 동안 사용 되 고 클라이언트 쪽 SDK 각 플랫폼과 연결 된 장치 플랫폼에 대 한 등록 프로세스를 그래프를 허용 하기 위해 네이티브 푸시 알림 파이프라인에 대 한 지식을 제공 하기 위해 알림 서비스에 앱 서버에서 MS Graph Api를 통해 사용자를 대상으로 알림을 게시할 때 각 앱 클라이언트 끝점에 팬아웃 알림입니다.
위의 단계에서 없이 플랫폼 초기화 **NotificationProvider** 매개 변수입니다. 여기에서 생성 하 고 구현 하는 개체에 전달할 필요 **NotificationProvider**합니다. 참조 하세요 **GraphNotificationProvider.cs** 세부 정보에 대 한 샘플. 



이 등록의 구현에서 제공 **NotificationProvider**합니다. 그런 다음, **플랫폼** 초기화 호출 로컬 제공 해야 **플랫폼** 푸시 알림 서비스에 대 한 액세스를 사용 하 여 앱이 MS Graph 알림을 서버 쪽에서 데이터를 받을 수 있도록 합니다. 

### <a name="pass-incoming-push-notifications-to-the-client-sdk"></a>클라이언트 SDK에 들어오는 푸시 알림을 전달합니다
이제 네이티브 백그라운드 작업에 수신기의 또는 PushNotificationTrigger를 사용 하 여 등록 된 Windows 내에서 들어오는 UserNotification 페이로드를 처리할 수 있습니다 합니다 [PushNotificationReceived 이벤트](https://docs.microsoft.com/en-us/uwp/api/windows.networking.pushnotifications.pushnotificationchannel.pushnotificationreceived)합니다. 

규정 준수, 보안, 잠재적인 최적화 등의 이유로 Graph 알림을 서버 쪽에서 들어오는 들어오는 WNS 원시 알림 앱 서버에서 처음 게시 된 모든 데이터를 포함 되어 있지 않은 어깨 탭 수 종종 있습니다. 앱 서버에서 게시 실제 알림 콘텐츠 검색 클라이언트 쪽 SDK Api 뒤에 숨겨져 있습니다. 이 경우 SDK는 항상 SDK로 들어오는 WNS 원시 알림 페이로드를 전달할 수 있도록 앱 클라이언트를 요청 합니다. 이 SDK이 없습니다 (하는 경우 WNS 푸시 앱 클라이언트에서 다른 용도로 사용할 수도 있습니다) 또는 그래프 알림 시나리오에 대 한 알림 인지 여부를 결정할 수 있습니다. 
