---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: 9f679e13-b1b3-40f8-bd44-679e4dffc0d4
ms.localizationpriority: medium
ms.openlocfilehash: eafd435f0cd9eabc5aa121cdb5288bd0b522df60
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801802"
---
### <a name="add-the-sdk"></a><span data-ttu-id="2822a-103">SDK를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-103">Add the SDK</span></span>

<span data-ttu-id="2822a-104">에 다음 리포지토리 참조를 삽입 합니다 *build.gradle* 프로젝트의 루트에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-104">Insert the following repository references into the *build.gradle* file at the root of your project.</span></span>

```java
allprojects {
    repositories {
        jcenter()
        maven { url 'https://maven.google.com' }
        maven { url 'https://projectrome.bintray.com/maven/' }
    }
}
```
<span data-ttu-id="2822a-105">그런 다음에 다음 종속성을 삽입 합니다 _build.gradle_ 프로젝트 폴더에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-105">Then, insert the following dependency into the _build.gradle_ file that is in your project folder.</span></span>

```java
dependencies { 
    ...
    implementation 'com.microsoft.connecteddevices:connecteddevices-sdk:0.11.0'
}
```

<span data-ttu-id="2822a-106">앱에 ProGuard를 사용 하려는 경우 이러한 새 Api에 대 한 ProGuard 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-106">If you wish to use ProGuard in your app, add the ProGuard Rules for these new APIs.</span></span> <span data-ttu-id="2822a-107">라는 파일을 만듭니다 *proguard 추정한* 에 *앱* 붙여넣기의 내용을 확인 하 고 프로젝트의 폴더 [ProGuard_Rules_for_Android_Rome_SDK.txt](https://github.com/Microsoft/project-rome/blob/master/Android/ProGuard_Rules_for_Android_Rome_SDK.txt)합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-107">Create a file called *proguard-rules.txt* in the *App* folder of your project, and paste in the contents of [ProGuard_Rules_for_Android_Rome_SDK.txt](https://github.com/Microsoft/project-rome/blob/master/Android/ProGuard_Rules_for_Android_Rome_SDK.txt).</span></span>

<span data-ttu-id="2822a-108">프로젝트의 *AndroidManifest.xml* 파일에서 내에서 다음 사용 권한을 추가 `<manifest>` 요소 (없습니다 이미 존재할 경우).</span><span class="sxs-lookup"><span data-stu-id="2822a-108">In your project's *AndroidManifest.xml* file, add the following permissions inside the `<manifest>` element (if they are not already present).</span></span> <span data-ttu-id="2822a-109">인터넷에 연결 하 고 장치에서 Bluetooth 검색을 사용 하도록 앱 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-109">This gives your app permission to connect to the Internet and to enable Bluetooth discovery on your device.</span></span>

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

> [!NOTE]
> <span data-ttu-id="2822a-110">Bluetooth 검색;을 사용 하는 데 필요한 파일만 Bluetooth 관련 권한 연결 된 장치 플랫폼의 다른 기능이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-110">The Bluetooth-related permissions are only necessary for using Bluetooth discovery; they are not needed for the other features in the Connected Devices Platform.</span></span> <span data-ttu-id="2822a-111">또한 `ACCESS_COARSE_LOCATION` Android Sdk 21에 필요 하 고 이상만 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-111">Additionally, `ACCESS_COARSE_LOCATION` is only required on Android SDKs 21 and later.</span></span> <span data-ttu-id="2822a-112">Android Sdk 23 이상, 개발자는 런타임 시 위치 액세스 권한을 부여할 사용자를 요청도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-112">On Android SDKs 23 and later, the developer must also prompt the user to grant location access at runtime.</span></span>

<span data-ttu-id="2822a-113">다음으로 이동할 활동 클래스 연결 된 장치 기능을 추가 하려는.</span><span class="sxs-lookup"><span data-stu-id="2822a-113">Next, go to the activity class(es) where you would like to add the Connected Devices functionality.</span></span> <span data-ttu-id="2822a-114">가져오기의 **connecteddevices** 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-114">Import the **connecteddevices** namespaces.</span></span>

```java
import com.microsoft.connecteddevices.*;
```

<span data-ttu-id="2822a-115">구현 하는 경우에 따라 대부분 필요 하지 있습니다 모든 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-115">Depending on which scenarios you implement, you many not need all of the namespaces.</span></span> <span data-ttu-id="2822a-116">또한 있습니다 진행 됨에 따라 다른 Android 네이티브 네임 스페이스를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-116">You may also need to add other Android-native namespaces as you progress.</span></span>

### <a name="initialize-the-connected-devices-platform"></a><span data-ttu-id="2822a-117">연결 된 장치 플랫폼 초기화</span><span class="sxs-lookup"><span data-stu-id="2822a-117">Initialize the Connected Devices Platform</span></span>

<span data-ttu-id="2822a-118">모든 연결 된 장치 기능을 사용할 수 있습니다, 전에 플랫폼 앱 내에서 초기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-118">Before any Connected Devices features can be used, the platform must be initialized within your app.</span></span> <span data-ttu-id="2822a-119">기본 클래스의 초기화 단계를 수행할지 **onCreate** 하거나 **onResume** 메서드는 다른 연결 된 장치 시나리오 수행 되기 전 필요 하므로.</span><span class="sxs-lookup"><span data-stu-id="2822a-119">The initialization steps should occur in your main class' **onCreate** or **onResume** method, because they are required before other Connected Devices scenarios can take place.</span></span> 

<span data-ttu-id="2822a-120">인스턴스화해야 합니다 **플랫폼** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-120">You must instantiate the **Platform** class.</span></span> <span data-ttu-id="2822a-121">**플랫폼** 세 개의 매개 변수를 사용 하는 생성자: 합니다 **상황에 맞는** 앱에 대 한를 **NotificationProvider**, 및 **UserAccountProvider**.</span><span class="sxs-lookup"><span data-stu-id="2822a-121">The **Platform** constructor takes three parameters: the **Context** for the app, a **NotificationProvider**, and a **UserAccountProvider**.</span></span>

<span data-ttu-id="2822a-122">합니다 **NotificationProvider** 매개 변수는 특정 시나리오에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-122">The **NotificationProvider** parameter is only needed for certain scenarios.</span></span> <span data-ttu-id="2822a-123">Microsoft Graph 알림을 사용 하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-123">In the case of using Microsoft Graph Notifications, it is required.</span></span> <span data-ttu-id="2822a-124">그대로 `null` 지금은 하 고 다음 섹션에서 네이티브 푸시 채널을 통해 사용자 중심 들어오는 알림을 처리 하는 SDK 클라이언트를 사용 하도록 설정 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-124">Leave it as `null` for now and find out how to enable the client SDK to handle incoming user-centric notifications via native push channels in next section.</span></span>

<span data-ttu-id="2822a-125">합니다 **UserAccountProvider** 연결 된 장치 플랫폼에 현재 사용자의 액세스를 위한 OAuth 2.0 액세스 토큰을 제공 하는 데 필요한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-125">The **UserAccountProvider** is needed to deliver an OAuth 2.0 access token for the current user's access to the Connected Devices Platform.</span></span> <span data-ttu-id="2822a-126">처음으로 앱 실행 되 고 새로 고침 토큰을 플랫폼에서 관리 하는 만료 되 면 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-126">It will be called the first time the app is run and upon the expiration of a platform-managed refresh token.</span></span> 

<span data-ttu-id="2822a-127">위해 온 보 딩 개발자 플랫폼을 사용 하 여 보다 쉽게 하기 위해 제공 했습니다 계정 공급자 구현에서 Android 및 iOS 용.</span><span class="sxs-lookup"><span data-stu-id="2822a-127">In order to help developers onboard with the platform more easily, we have provided account provider implementations for Android and iOS.</span></span> <span data-ttu-id="2822a-128">이러한 구현에는 [인증 공급자 샘플](https://github.com/Microsoft/project-rome/tree/master/Android/samples/account-provider-sample), OAuth 2.0 액세스 토큰을 가져오고 앱에 대 한 토큰 새로 고침을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-128">These implementations, found in the [authentication provider sample](https://github.com/Microsoft/project-rome/tree/master/Android/samples/account-provider-sample), can be used to obtain the OAuth 2.0 access token and refresh token for your app.</span></span>

[!INCLUDE [auth-scopes](../auth-scopes.md)]

<span data-ttu-id="2822a-129">아래 코드에 `mSignInHelper` 참조를 **MSAAccountProvider**아래도 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-129">In the code below, `mSignInHelper` references an **MSAAccountProvider**, also initialized below.</span></span> <span data-ttu-id="2822a-130">이 구현 클래스를 제공 합니다 **UserAccountProvider** 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-130">This provided class implements the **UserAccountProvider** interface.</span></span>

```java
private MSAAccountProvider mSignInHelper;

// ...

// Create sign-in helper from helper lib, which does user account and access token management for us
// Takes two parameters: a client id for msa, and the Context
mSignInHelper = new MSAAccountProvider(Secrets.MSA_CLIENT_ID, getContext());

// add an event listener, which changes the button text when account state changes
mSignInHelper.addUserAccountChangedListener(new EventListener<UserAccountProvider, Void>() {
    @Override
    public void onEvent(UserAccountProvider provider, Void aVoid){
        if (mSignInHelper.isSignedIn()) {
            // update the UI indicating a user is signed in.
        }
        else
        {
            // update the UI indicating a user is not signed in.
        }
    }
});
```

<span data-ttu-id="2822a-131">이제 생성할 수 있습니다는 **플랫폼** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="2822a-131">Now you can construct a **Platform** instance.</span></span> <span data-ttu-id="2822a-132">별도 도우미 클래스에 다음 코드를 배치 하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-132">You may wish to put the following code in a separate helper class.</span></span> 

```java
// Platform helper class:

private static Platform sPlatform;

//...

// This is the main Platform-generating method
public static synchronized Platform getOrCreatePlatform(Context context, UserAccountProvider accountProvider, NotificationProvider notificationProvider) {
    // check whether the local platform variable is already initialized.
    Platform platform = getPlatform();

    if (platform == null) {
        // if it is not initialized, do so:
        platform = createPlatform(context, accountProvider, notificationProvider);
    }
    return platform;
}

// gets the local platform variable
public static synchronized Platform getPlatform() {
        return sPlatform;
}

// creates and returns a new Platform instance
public static synchronized Platform createPlatform(Context context, UserAccountProvider accountProvider, NotificationProvider notificationProvider) {
    sPlatform = new Platform(context, accountProvider, notificationProvider);
    return sPlatform;
}
```
<span data-ttu-id="2822a-133">기본 클래스에 있는 `mSignInHelper` 는 다음 코드를 추가 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-133">In your main class, where `mSignInHelper` is initialized, add the following code.</span></span>

```java
private Platform mPlatform;

//...

mPlatform = PlatformHelperClass.getOrCreatePlatform(this, mSignInHelper, null);
```

<span data-ttu-id="2822a-134">앱 전경 종료 될 때 플랫폼을 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2822a-134">You should shut down the platform when your app exits the foreground.</span></span>

```Java
mPlatform.shutdownAsync();
```
