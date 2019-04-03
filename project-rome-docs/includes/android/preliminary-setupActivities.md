---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 45aa2364c2b1f7a30e94e2b720a0e4b14d4bff27
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907795"
---
## <a name="preliminary-setup-for-the-connected-devices-platform"></a><span data-ttu-id="efc9d-103">연결 된 장치 플랫폼에 대 한 예비 설치</span><span class="sxs-lookup"><span data-stu-id="efc9d-103">Preliminary setup for the Connected Devices Platform</span></span>

<span data-ttu-id="efc9d-104">원격 연결을 구현 하기 전에 Android 앱을 원격 장치에 연결 하는 기능을 제공 하는 데 해야 하는 몇 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-104">Before implementing remote connectivity, there are a few steps you'll need to take to give your Android app the capability to connect to remote devices.</span></span>

### <a name="sign-in"></a><span data-ttu-id="efc9d-105">로그인</span><span class="sxs-lookup"><span data-stu-id="efc9d-105">Sign-in</span></span>

<span data-ttu-id="efc9d-106">Microsoft 계정 (MSA) 또는 Azure Active Directory (AAD) 인증은 Nearby 공유 제외 하 고 SDK의 모든 기능에 대 한 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-106">Microsoft Account (MSA) or Azure Active Directory (AAD) authentication is required for all features of the SDK, except for the Nearby sharing APIs.</span></span> 

<span data-ttu-id="efc9d-107">MSA가 있지 않으며 하나를 사용 하려는 경우 레지스터 [account.microsoft.com](https://account.microsoft.com/account)합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-107">If you do not already have an MSA and wish to use one, register on [account.microsoft.com](https://account.microsoft.com/account).</span></span>

<span data-ttu-id="efc9d-108">다음 지침에 따라 Microsoft와 앱을 등록 해야 합니다는 다음에 [응용 프로그램 등록 포털](https://apps.dev.microsoft.com/) (Microsoft 개발자 계정이 없는 경우 만들어야 첫 번째).</span><span class="sxs-lookup"><span data-stu-id="efc9d-108">Next, you must register your app with Microsoft by following the instructions on the [Application Registration Portal](https://apps.dev.microsoft.com/) (if you do not have a Microsoft developer account, you must create one first).</span></span> <span data-ttu-id="efc9d-109">앱에 대 한 클라이언트 ID 문자열을 받아야 합니다. 나중에이 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-109">You should receive a client ID string for your app; save this for later.</span></span> <span data-ttu-id="efc9d-110">앱을 Microsoft의 연결 된 장치 플랫폼 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-110">This will allow your app to access Microsoft's Connected Devices Platform resources.</span></span> <span data-ttu-id="efc9d-111">AAD를 사용 하는 경우 참조 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 방법은 클라이언트 ID 문자열에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-111">If you're using AAD, see [Azure Active Directory Authentication Libraries](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) for instructions on getting the client ID string.</span></span>

### <a name="add-the-sdk"></a><span data-ttu-id="efc9d-112">SDK를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-112">Add the SDK</span></span>

<span data-ttu-id="efc9d-113">에 다음 리포지토리 참조를 삽입 합니다 *build.gradle* 프로젝트의 루트에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-113">Insert the following repository references into the *build.gradle* file at the root of your project.</span></span>

```Java
allprojects {
    repositories {
        jcenter()
        maven { url 'https://maven.google.com' }
        maven { url 'https://projectrome.bintray.com/maven/' }
    }
}
```
<span data-ttu-id="efc9d-114">그런 다음에 다음 종속성을 삽입 합니다 _build.gradle_ 프로젝트 폴더에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-114">Then, insert the following dependency into the _build.gradle_ file that is in your project folder.</span></span>

```Java
dependencies { 
    ...
    implementation 'com.microsoft.connecteddevices:connecteddevices-sdk:0.11.0'
}
```

<span data-ttu-id="efc9d-115">앱에 ProGuard를 사용 하려는 경우 이러한 새 Api에 대 한 ProGuard 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-115">If you wish to use ProGuard in your app, add the ProGuard Rules for these new APIs.</span></span> <span data-ttu-id="efc9d-116">라는 파일을 만듭니다 *proguard 추정한* 에 *앱* 붙여넣기의 내용을 확인 하 고 프로젝트의 폴더 [ProGuard_Rules_for_Android_Rome_SDK.txt](https://github.com/Microsoft/project-rome/blob/master/Android/ProGuard_Rules_for_Android_Rome_SDK.txt)합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-116">Create a file called *proguard-rules.txt* in the *App* folder of your project, and paste in the contents of [ProGuard_Rules_for_Android_Rome_SDK.txt](https://github.com/Microsoft/project-rome/blob/master/Android/ProGuard_Rules_for_Android_Rome_SDK.txt).</span></span>

<span data-ttu-id="efc9d-117">프로젝트의 *AndroidManifest.xml* 파일에서 내에서 다음 사용 권한을 추가 `<manifest>` 요소 (없습니다 이미 존재할 경우).</span><span class="sxs-lookup"><span data-stu-id="efc9d-117">In your project's *AndroidManifest.xml* file, add the following permissions inside the `<manifest>` element (if they are not already present).</span></span> <span data-ttu-id="efc9d-118">인터넷에 연결 하 고 장치에서 Bluetooth 검색을 사용 하도록 앱 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-118">This gives your app permission to connect to the Internet and to enable Bluetooth discovery on your device.</span></span>

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

> [!NOTE]
> <span data-ttu-id="efc9d-119">Bluetooth 검색;을 사용 하는 데 필요한 파일만 Bluetooth 관련 권한 연결 된 장치 플랫폼의 다른 기능이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-119">The Bluetooth-related permissions are only necessary for using Bluetooth discovery; they are not needed for the other features in the Connected Devices Platform.</span></span> <span data-ttu-id="efc9d-120">또한 `ACCESS_COARSE_LOCATION` Android Sdk 21에 필요 하 고 이상만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-120">Additionally, `ACCESS_COARSE_LOCATION` is only required on Android SDKs 21 and later.</span></span> <span data-ttu-id="efc9d-121">Android Sdk 23 이상, 개발자는 런타임 시 위치 액세스 권한을 부여할 사용자를 요청도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-121">On Android SDKs 23 and later, the developer must also prompt the user to grant location access at runtime.</span></span>

<span data-ttu-id="efc9d-122">다음으로 이동 활동 클래스 live에 연결 된 장치 기능 하려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-122">Next, go to the activity class(es) where you would like the Connected Devices functionality to live.</span></span> <span data-ttu-id="efc9d-123">가져오기는 다음 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="efc9d-123">Import the the following namespaces.</span></span>

```java
import com.microsoft.connecteddevices;
import com.microsoft.connecteddevices.useractivities;
import com.microsoft.connecteddevices.userdata;
```
