---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: d498d192b6ac909e8b3978b54e6996eef98d2814
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907505"
---
### <a name="create-the-platform"></a><span data-ttu-id="017ff-103">플랫폼 만들기</span><span class="sxs-lookup"><span data-stu-id="017ff-103">Create the platform</span></span>


<span data-ttu-id="017ff-104">시작 하려면 플랫폼을 인스턴스화하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-104">To get started simply instantiate the platform.</span></span>

`ConnectedDevicesPlatform sPlatform = new ConnectedDevicesPlatform(context);`

### <a name="subscribe-to-connecteddevicesaccountmanager-events-to-handle-the-user-account"></a><span data-ttu-id="017ff-105">ConnectedDevicesAccountManager 사용자 계정을 처리 하는 이벤트를 구독합니다</span><span class="sxs-lookup"><span data-stu-id="017ff-105">Subscribe to ConnectedDevicesAccountManager events to handle the user account</span></span> 

<span data-ttu-id="017ff-106">플랫폼에는 플랫폼에 액세스 하려면 인증된 된 사용자에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-106">The platform requires an authenticated user to access the platform.</span></span>  <span data-ttu-id="017ff-107">구독할 필요 **ConnectedDevicesAccountManager** 유효한 계정 보장 하기 위해 이벤트를 사용 하 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-107">You'll need to subscribe to **ConnectedDevicesAccountManager** events to ensure a valid account is being used.</span></span> 

```Java
 ConnectedDevicesPlatform sPlatform.getAccountManager().accessTokenRequested().subscribe((accountManager, args) -> {

    // Get access token
                 
}
```

```Java
 ConnectedDevicesPlatform sPlatform.getAccountManager().accessTokenInvalidated().subscribe((accountManager, args) -> {

    // Refresh and renew existing access token
}
```


### <a name="subscribe-to-connecteddevicesnotificationregistrationmanager-events"></a><span data-ttu-id="017ff-108">ConnectedDevicesNotificationRegistrationManager 이벤트 구독</span><span class="sxs-lookup"><span data-stu-id="017ff-108">Subscribe to ConnectedDevicesNotificationRegistrationManager events</span></span>

<span data-ttu-id="017ff-109">마찬가지로, 플랫폼 간 장치 명령에 전달할 알림을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-109">Similarly, the platform uses notifications to deliver commands between devices.</span></span>  <span data-ttu-id="017ff-110">따라서을 구독 해야 합니다는 **ConnectedDevicesNotificationRegistrationManager** 클라우드 등록 상태를 보장 하기 위해 이벤트 사용 되는 계정에 대 한 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-110">Therefore, you must subscribe to the **ConnectedDevicesNotificationRegistrationManager** events to ensure the cloud registration states are valid for the account being used.</span></span>  <span data-ttu-id="017ff-111">확인을 사용 하 여 상태 **ConnectedDevicesNotificationRegistrationState**</span><span class="sxs-lookup"><span data-stu-id="017ff-111">Verify the the state using **ConnectedDevicesNotificationRegistrationState**</span></span>

```Java
ConnectedDevicesPlatform sPlatform.getNotificationRegistrationManager().notificationRegistrationStateChanged().subscribe((notificationRegistrationManager, args) -> {
    
     // Check state using ConnectedDevicesNotificationRegistrationState enum

}
```
### <a name="start-the-platform"></a><span data-ttu-id="017ff-112">플랫폼 시작</span><span class="sxs-lookup"><span data-stu-id="017ff-112">Start the platform</span></span>
<span data-ttu-id="017ff-113">플랫폼 초기화가 진행에서에 이벤트 처리기를 원격 시스템 장치 검색을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-113">Now that the platform is initialized and event handlers are in place, you are ready to start discovering remote system devices.</span></span>  

`ConnectedDevicesPlatform sPlatform.start();`

### <a name="retrieve-user-accounts-known-to-the-app"></a><span data-ttu-id="017ff-114">앱에 알려진 사용자 계정 검색</span><span class="sxs-lookup"><span data-stu-id="017ff-114">Retrieve user accounts known to the app</span></span>

<span data-ttu-id="017ff-115">앱에 알려진 사용자 계정 목록을 사용 하 여 제대로 동기화 되었는지 확인 해야 합니다 **ConnectedDevicesAccountManager**합니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-115">It is important to ensure that the list of user accounts known to the app are properly synchronized with the **ConnectedDevicesAccountManager**.</span></span>

<span data-ttu-id="017ff-116">사용 하 여 **ConnectedDevicesAccountManager.addAccountAsync** 새 사용자 계정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="017ff-116">Use **ConnectedDevicesAccountManager.addAccountAsync** to add a new user account.</span></span>

```Java
 public synchronized AsyncOperation<ConnectedDevicesAddAccountResult> addAccountToAccountManagerAsync(ConnectedDevicesAccount account) {
        return ConnectedDevicesPlatform sPlatform.getAccountManager().addAccountAsync(account);
    }
```

<span data-ttu-id="017ff-117">사용할 수 잘못 된 계정을 제거 하려면 **ConnectedDevicesAccountManager.removeAccountAsync**</span><span class="sxs-lookup"><span data-stu-id="017ff-117">To remove an invalid account you can use **ConnectedDevicesAccountManager.removeAccountAsync**</span></span>

```Java
 public synchronized AsyncOperation<ConnectedDevicesAddAccountResult> removeAccountToAccountManagerAsync(ConnectedDevicesAccount account) {
        return ConnectedDevicesPlatform sPlatform.getAccountManager().removeAccountAsync(account);
    }
```