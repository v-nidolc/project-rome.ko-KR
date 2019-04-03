### <a name="add-the-sdk"></a>SDK를 추가 합니다.

Windows에 대 한 그래프 Notification SDK 사용할 수 있습니다 기본 제공 OS Windows SDK 대신 NuGet 패키지를 통해 개발자가 더 하위 수준 지원 및 유연한 릴리스 일정 하려면. NuGet 패키지를 nuget.org에서 msgraphsdkteam에서 게시 되 고 확인할 수 있습니다 [여기](https://www.nuget.org/profiles/msgraphsdkteam)합니다. 

포함 하 여 UWP 앱에서 NuGet 패키지 사용에 대 한 자세한 내용은 다음이 링크를 참조 하세요. 
* [Nuget.org에서 패키지를 직접 사용](https://docs.microsoft.com/en-us/azure/devops/artifacts/nuget/upstream-sources?view=vsts&tabs=new-nav)
* [빠른 시작: 설치 하 고 Visual Studio에서 패키지를 사용 합니다.](https://docs.microsoft.com/en-us/nuget/quickstart/install-and-use-a-package-in-visual-studio)




구현 하는 경우에 따라 대부분 필요 하지 있습니다 모든 네임 스페이스입니다. 그래프 알림에 특히 해야는 아래와 같이 네임 스페이스입니다.


```C#
using Microsoft.ConnectedDevices.Core;
using Microsoft.ConnectedDevices.UserData;
using Microsoft.ConnectedDevices.UserNotifications;

```


### <a name="initialize-the-connected-devices-platform"></a>연결 된 장치 플랫폼 초기화

모든 연결 된 장치 기능을 사용할 수 있습니다, 전에 플랫폼 앱 내에서 초기화 되어야 합니다. 기본 클래스의 초기화 단계를 수행할지 **OnLaunched** 하거나 **onActivated** 메서드는 다른 연결 된 장치 시나리오 수행 되기 전 필요 하므로. 

인스턴스화해야 합니다 **ConnectedDevicesPlatform** 클래스입니다. **ConnectedDevicesPlatform** 세 개의 매개 변수를 사용 하는 생성자: 합니다 **상황에 맞는** 앱에 대 한를 **NotificationProvider**, 및  **UserAccountProvider**합니다.

합니다 **NotificationProvider** 매개 변수는 특정 시나리오에만 필요 합니다. Microsoft Graph 알림을 사용 하는 경우 필수입니다. 지금은 비워 둡니다 하 고 클라이언트 네이티브 푸시 채널을 통해 사용자 중심 들어오는 알림을 처리 하는 SDK를 사용 하도록 설정 하는 방법은 다음 섹션에서 알아봅니다.

합니다 **UserAccountProvider** 연결 된 장치 플랫폼에 현재 사용자의 액세스를 위한 OAuth 2.0 액세스 토큰을 제공 하는 데 필요한 합니다. 처음으로 앱 실행 되 고 새로 고침 토큰을 플랫폼에서 관리 하는 만료 되 면 호출 됩니다. 

위해 온 보 딩 개발자 플랫폼을 사용 하 여 보다 쉽게 하기 위해 제공 된 계정 공급자 구현을 샘플 코드에서는 Windows 했는지 확인 하려면에 대 한 **MicrosoftAccountProvider.cs** 대 한 자세한 내용은 합니다. 

생성할 수 있습니다 다음을 **플랫폼** 인스턴스. 

```C#

public async Task InstantiatePlatform()
{
    var account = m_accoutProvider.SignedInAccount;

    if (m_feed == null)
    {
        await Task.Run(() =>
        {
            lock (this)
            {
                if (m_feed == null)
                {
                    m_platform = new ConnectedDevicesPlatform(m_accoutProvider, this);


                }
            }
        });
    }
}

```

앱 전경 종료 될 때 플랫폼을 종료 해야 합니다.

```C#

public async void Reset()
{
    if (m_platform != null)
    {
        await m_platform.ShutdownAsync();
        m_platform = null;
        m_feed = null;
        m_newNotifications.Clear();
        m_historicalNotifications.Clear();
    }
}

```
