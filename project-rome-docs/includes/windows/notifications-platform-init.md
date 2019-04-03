### <a name="add-the-sdk"></a><span data-ttu-id="58d3c-101">SDK를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-101">Add the SDK</span></span>

<span data-ttu-id="58d3c-102">Windows에 대 한 그래프 Notification SDK 사용할 수 있습니다 기본 제공 OS Windows SDK 대신 NuGet 패키지를 통해 개발자가 더 하위 수준 지원 및 유연한 릴리스 일정 하려면.</span><span class="sxs-lookup"><span data-stu-id="58d3c-102">For Windows, Graph Notification SDK is made available to developers through a NuGet package instead of built-in OS Windows SDK in order to have better down-level support and more flexible release schedule.</span></span> <span data-ttu-id="58d3c-103">NuGet 패키지를 nuget.org에서 msgraphsdkteam에서 게시 되 고 확인할 수 있습니다 [여기](https://www.nuget.org/profiles/msgraphsdkteam)합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-103">The NuGet package is published by msgraphsdkteam on nuget.org and can be found [here](https://www.nuget.org/profiles/msgraphsdkteam).</span></span> 

<span data-ttu-id="58d3c-104">포함 하 여 UWP 앱에서 NuGet 패키지 사용에 대 한 자세한 내용은 다음이 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58d3c-104">For more details on including and consuming NuGet packages from your UWP app, please see these links.</span></span> 
* [<span data-ttu-id="58d3c-105">Nuget.org에서 패키지를 직접 사용</span><span class="sxs-lookup"><span data-stu-id="58d3c-105">Use packages from nuget.org</span></span>](https://docs.microsoft.com/en-us/azure/devops/artifacts/nuget/upstream-sources?view=vsts&tabs=new-nav)
* [<span data-ttu-id="58d3c-106">빠른 시작: 설치 하 고 Visual Studio에서 패키지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-106">Quickstart: Install and use a package in Visual Studio</span></span>](https://docs.microsoft.com/en-us/nuget/quickstart/install-and-use-a-package-in-visual-studio)




<span data-ttu-id="58d3c-107">구현 하는 경우에 따라 대부분 필요 하지 있습니다 모든 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-107">Depending on which scenarios you implement, you many not need all of the namespaces.</span></span> <span data-ttu-id="58d3c-108">그래프 알림에 특히 해야는 아래와 같이 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-108">For Graph Notifications specifically, you will need the below namespaces as shown.</span></span>


```C#
using Microsoft.ConnectedDevices.Core;
using Microsoft.ConnectedDevices.UserData;
using Microsoft.ConnectedDevices.UserNotifications;

```


### <a name="initialize-the-connected-devices-platform"></a><span data-ttu-id="58d3c-109">연결 된 장치 플랫폼 초기화</span><span class="sxs-lookup"><span data-stu-id="58d3c-109">Initialize the Connected Devices Platform</span></span>

<span data-ttu-id="58d3c-110">모든 연결 된 장치 기능을 사용할 수 있습니다, 전에 플랫폼 앱 내에서 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-110">Before any Connected Devices features can be used, the platform must be initialized within your app.</span></span> <span data-ttu-id="58d3c-111">기본 클래스의 초기화 단계를 수행할지 **OnLaunched** 하거나 **onActivated** 메서드는 다른 연결 된 장치 시나리오 수행 되기 전 필요 하므로.</span><span class="sxs-lookup"><span data-stu-id="58d3c-111">The initialization steps should occur in your main class' **OnLaunched** or **onActivated** method, because they are required before other Connected Devices scenarios can take place.</span></span> 

<span data-ttu-id="58d3c-112">인스턴스화해야 합니다 **ConnectedDevicesPlatform** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-112">You must instantiate the **ConnectedDevicesPlatform** class.</span></span> <span data-ttu-id="58d3c-113">**ConnectedDevicesPlatform** 세 개의 매개 변수를 사용 하는 생성자: 합니다 **상황에 맞는** 앱에 대 한를 **NotificationProvider**, 및  **UserAccountProvider**합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-113">The **ConnectedDevicesPlatform** constructor takes three parameters: the **Context** for the app, a **NotificationProvider**, and a **UserAccountProvider**.</span></span>

<span data-ttu-id="58d3c-114">합니다 **NotificationProvider** 매개 변수는 특정 시나리오에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-114">The **NotificationProvider** parameter is only needed for certain scenarios.</span></span> <span data-ttu-id="58d3c-115">Microsoft Graph 알림을 사용 하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-115">In the case of using Microsoft Graph Notifications, it is required.</span></span> <span data-ttu-id="58d3c-116">지금은 비워 둡니다 하 고 클라이언트 네이티브 푸시 채널을 통해 사용자 중심 들어오는 알림을 처리 하는 SDK를 사용 하도록 설정 하는 방법은 다음 섹션에서 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-116">Leave it empty for now and find out in next section on how to enable the client SDK to handle incoming user-centric notifications via native push channels.</span></span>

<span data-ttu-id="58d3c-117">합니다 **UserAccountProvider** 연결 된 장치 플랫폼에 현재 사용자의 액세스를 위한 OAuth 2.0 액세스 토큰을 제공 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-117">The **UserAccountProvider** is needed to deliver an OAuth 2.0 access token for the current user's access to the Connected Devices Platform.</span></span> <span data-ttu-id="58d3c-118">처음으로 앱 실행 되 고 새로 고침 토큰을 플랫폼에서 관리 하는 만료 되 면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-118">It will be called the first time the app is run and upon the expiration of a platform-managed refresh token.</span></span> 

<span data-ttu-id="58d3c-119">위해 온 보 딩 개발자 플랫폼을 사용 하 여 보다 쉽게 하기 위해 제공 된 계정 공급자 구현을 샘플 코드에서는 Windows 했는지 확인 하려면에 대 한 **MicrosoftAccountProvider.cs** 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-119">In order to help developers onboard with the platform more easily, we have provided account provider implementations for Windows in sample code, please make sure to check **MicrosoftAccountProvider.cs** for more details.</span></span> 

<span data-ttu-id="58d3c-120">생성할 수 있습니다 다음을 **플랫폼** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="58d3c-120">Then you can construct a **Platform** instance.</span></span> 

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

<span data-ttu-id="58d3c-121">앱 전경 종료 될 때 플랫폼을 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58d3c-121">You should shut down the platform when your app exits the foreground.</span></span>

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
