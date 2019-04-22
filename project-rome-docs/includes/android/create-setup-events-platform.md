---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 559752038bb8d73c95d853dcc39be061e64b322f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800295"
---
### <a name="create-the-platform"></a><span data-ttu-id="93084-103">플랫폼 만들기</span><span class="sxs-lookup"><span data-stu-id="93084-103">Create the platform</span></span>

<span data-ttu-id="93084-104">시작 하려면 플랫폼을 인스턴스화하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93084-104">To get started simply instantiate the platform.</span></span>

`ConnectedDevicesPlatform sPlatform = new ConnectedDevicesPlatform(context);`

## <a name="subscribe-to-connecteddevicesaccountmanager-events-to-handle-the-user-account"></a><span data-ttu-id="93084-105">ConnectedDevicesAccountManager 사용자 계정을 처리 하는 이벤트를 구독합니다</span><span class="sxs-lookup"><span data-stu-id="93084-105">Subscribe to ConnectedDevicesAccountManager events to handle the user account</span></span> 

<span data-ttu-id="93084-106">플랫폼에는 플랫폼에 액세스 하려면 인증된 된 사용자에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="93084-106">The platform requires an authenticated user to access the platform.</span></span>  <span data-ttu-id="93084-107">구독할 필요 **ConnectedDevicesAccountManager** 유효한 계정 보장 하기 위해 이벤트를 사용 하 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93084-107">You'll need to subscribe to **ConnectedDevicesAccountManager** events to ensure a valid account is being used.</span></span> 

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


### <a name="subscribe-to-connecteddevicesnotificationregistrationmanager-events"></a><span data-ttu-id="93084-108">ConnectedDevicesNotificationRegistrationManager 이벤트 구독</span><span class="sxs-lookup"><span data-stu-id="93084-108">Subscribe to ConnectedDevicesNotificationRegistrationManager events</span></span>

<span data-ttu-id="93084-109">마찬가지로, 플랫폼 간 장치 명령에 전달할 알림을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93084-109">Similarly, the platform uses notifications to deliver commands between devices.</span></span>  <span data-ttu-id="93084-110">따라서을 구독 해야 합니다는 **ConnectedDevicesNotificationRegistrationManager** 클라우드 등록 상태를 보장 하기 위해 이벤트 사용 되는 계정에 대 한 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="93084-110">Therefore, you must subscribe to the **ConnectedDevicesNotificationRegistrationManager** events to ensure the cloud registration states are valid for the account being used.</span></span>  <span data-ttu-id="93084-111">확인을 사용 하 여 상태 **ConnectedDevicesNotificationRegistrationState**</span><span class="sxs-lookup"><span data-stu-id="93084-111">Verify the the state using **ConnectedDevicesNotificationRegistrationState**</span></span>

```Java
ConnectedDevicesPlatform sPlatform.getNotificationRegistrationManager().notificationRegistrationStateChanged().subscribe((notificationRegistrationManager, args) -> {
    
    // Check state using ConnectedDevicesNotificationRegistrationState enum

}
```