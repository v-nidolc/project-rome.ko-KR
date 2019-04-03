### <a name="register-your-app-in-microsoft-windows-dev-center-for-cross-device-experiences"></a>장치 간 환경을 위한 Microsoft Windows 개발자 센터에서 앱 등록
에 대 한 앱을 등록 해야 하는 다음에 [Microsoft 개발자 대시보드에서 장치 간 환경 기능의](https://developer.microsoft.com/dashboard/crossplatform/web)합니다. 위의 단계에서 설명 된 MSA 및 AAD 앱 등록에서 다른 프로시저입니다. 이 프로세스에 대 한 주요 목표는 연결 된 장치 플랫폼에서 인식 되 고 동시에 Microsoft Graph 알림 네이티브를 사용 하 여 알림을 보낼 권한을 부여 하는 플랫폼 간 앱 id 사용 하 여 플랫폼 특정 앱 id를 매핑할 푸시 알림 서비스를 각 OS 플랫폼에 해당 합니다. 이 경우 그래프 알림을 WNS – Windows 알림 서비스를 통해 Windows UWP 앱 끝점에 알림을 보낼 수 있습니다. Dev Center 대시보드로 이동, 왼쪽 탐색 창에서 장치 간 환경을로 이동 하 고 아래와 같이 표시 된 새 장치 간 앱을 구성를 선택 합니다.
![개발자 센터 대시보드 – 장치 간 환경](../../notifications/media/dev_center_portal/dev_center_portal_1_overview.png)

개발자 센터 온 보 딩 프로세스에는 다음 단계를 필요 합니다.
* 앱의 존재가 됩니다 및 장치 간 환경을 사용할 수 있는 플랫폼 선택 – 지원 되는 플랫폼을 선택 합니다. 그래프 알림을 통합의 경우 Windows, Android 및/또는 iOS에서 선택할 수 있습니다. 아래와 같이 표시 됩니다.
![장치 간 환경을 – 지원 되는 플랫폼](../../notifications/media/dev_center_portal/dev_center_portal_2_supported_platforms.png)

* 앱 Id를 제공 합니다.-각 앱을 현재 상태에 플랫폼에 대 한 앱 Id를 제공 합니다. 아래와 같이 표시 됩니다.
![장치 간 환경을-앱 Id](../../notifications/media/dev_center_portal/dev_center_portal_3_app_ids.png)
> [!NOTE]
> 플랫폼 당 10) (최대 서로 다른 Id를 추가할 수 있습니다 –이 여러 버전의 동일한 앱 또는 다른 앱과 동일한 사용자를 대상으로 하 여 응용 프로그램 서버에서 보낸 동일한 알림을 받을 수 있게 되기를 원하는 경우에 합니다. 

* 하거나 MSA 및/또는 AAD 앱 등록에서 앱 Id를 선택 합니다. MSA 또는 AAD 앱 등록에 해당 하는 이러한 클라이언트 Id는 위에서 이전 MSA/AAD 앱 등록 단계에서 가져왔습니다. 아래와 같이 표시 됩니다. 
![장치 간 환경을 – MSA 및 AAD 앱 등록](../../notifications/media/dev_center_portal/dev_center_portal_4_msa_aad_connections.png)
* 주요 플랫폼에서 클라이언트 끝점, 즉, 앱으로 알림을 보낼 WNS (Windows UWP) 용,의 GCM (Android) 및 (iOS 용 APNS 기본 알림 플랫폼의 각 그래프 알림 및 기타 연결 된 장치 플랫폼 기능 활용 ). 알림을 배달 하기 위해 앱 서버에 대해 사용자를 대상으로 알림을 게시할 때 그래프 알림을 사용 하도록이 알림 플랫폼을 위한 자격 증명을 제공 합니다. 아래와 같이 표시 됩니다. 
![장치 간 환경을 – 푸시 자격 증명](../../notifications/media/dev_center_portal/dev_center_portal_5_push_credentials.png)
> [!NOTE] 
> Windows UWP 앱에 대 한 Microsoft Graph 알림을 사용 하려면 필수 구성 요소는 WNS 푸시 알림을 사용 하도록 설정 합니다. 참조 [WNS 개요](https://docs.microsoft.com/en-us/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview) 대 한 자세한 내용은 합니다. 온 보 딩을 완료 하면 연결 된 장치 플랫폼에 Windows 개발자 센터를 통해 푸시 자격 증명을 제공할 수 있습니다. 
* 마지막 단계는 확인 프로세스는 앱에이 도메인의 소유권을 컴퓨터에 등록 된 장치 간 앱 id 앱 처럼 작동 하는 증명으로 사용 되는 장치 간 앱 도메인을 확인 하는 것입니다. 아래와 같이 표시 됩니다.  
![장치 간 환경을 – 도메인 확인](../../notifications/media/dev_center_portal/dev_center_portal_6_domain_verification.png) 온 보 딩을 사용 하 여 모든 설정이 이제! 다음 섹션을 진행 하세요. 


