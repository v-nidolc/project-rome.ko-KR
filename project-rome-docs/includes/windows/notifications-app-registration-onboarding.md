### <a name="msa-and-aad-authentication-registration"></a>MSA 및 AAD 인증 등록

Microsoft 계정 (MSA) 또는 Azure Active Directory (AAD) 인증 등록이 필요 Nearby 공유 제외 하 고 알림을 포함 하 여 SDK의 모든 기능에 대 한 Api입니다. 

MSA가 있지 않으며 하나를 사용 하려는 경우 레지스터 [account.microsoft.com](https://account.microsoft.com/account)합니다.

다음으로, 인증 및 id 프레임 워크 MSA를 사용 하 여 사용자에 게는, 하는 경우 등록 해야 앱 Microsoft를 사용 하 여 다음 지침에 따라 합니다 [응용 프로그램 등록 포털](https://apps.dev.microsoft.com/) (Microsoft 없는 경우 개발자 계정으로 만들어야 첫 번째). 앱에 대 한 클라이언트 ID 문자열을 받아야 합니다. 위치를 기억 하거나 저장 해야 합니다. 나중에 그래프 알림을 등록 하는 동안이 사용 됩니다. MSA 인증을 사용 하 여 앱 아래와 같이 Live SDK 응용 프로그램으로 등록 해야 note 합니다.
![응용 프로그램 등록 포털](../../notifications/media/msa_app_registration/app_registration_portal.png)

회사 계정 또는 학교 계정 인증 및 id 프레임 워크도 AAD를 사용 하는 앱을 작성 하는 경우에을 통해 앱을 등록 해야 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 표시 된 것 처럼 클라이언트 ID를 가져오려면 아래. 
 ![AAD 등록 포털](../../notifications/media/aad_registration_portal/aad_registration_portal.png) 그래프 알림 및 기타 연결 된 장치 플랫폼 기능을 사용 하는 데 필요한 몇 가지 사용 권한을 가지는 새 앱 등록을 만들 때. 아래를 참조 하세요. 
![AAD 등록 포털-설정-필요한 권한](../../notifications/media/aad_registration_portal/aad_registration_portal_permissions.png)
* 사용자 로그인 권한을 다음과 같이 표시를 추가 합니다.
![필요한 권한 – AAD 사용자 프로필](../../notifications/media/aad_registration_portal/permissions_1_user.png)
* 아래와 같이 표시 되는 장치 정보에 대 한 명령 서비스 권한을 추가 합니다.
![필요한 권한 – 장치](../../notifications/media/aad_registration_portal/permissions_2_devices.png)
* 작업 피드 서비스 Api를 아래와 같이 표시 된 아래 그래프 Notifications 권한을 추가 합니다.
![필요한 권한 – 장치](../../notifications/media/aad_registration_portal/permissions_3_graph_notifications.png)
* 끝으로 Windows에서 실행 되는 UWP 앱을 포함 하 여 플랫폼 간 응용 프로그램을 작성 하는 경우 아래와 같이 표시 된 Windows 알림 서비스 권한을 추가할 있는지 확인 합니다. 
![필요한 권한-WNS](../../notifications/media/aad_registration_portal/permissions_4_wns_push.png)
