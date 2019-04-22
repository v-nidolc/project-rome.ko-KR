---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: d498d192b6ac909e8b3978b54e6996eef98d2814
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804660"
---
### <a name="create-the-platform"></a>플랫폼 만들기


시작 하려면 플랫폼을 인스턴스화하면 됩니다.

`ConnectedDevicesPlatform sPlatform = new ConnectedDevicesPlatform(context);`

### <a name="subscribe-to-connecteddevicesaccountmanager-events-to-handle-the-user-account"></a>ConnectedDevicesAccountManager 사용자 계정을 처리 하는 이벤트를 구독합니다 

플랫폼에는 플랫폼에 액세스 하려면 인증된 된 사용자에 필요 합니다.  구독할 필요 **ConnectedDevicesAccountManager** 유효한 계정 보장 하기 위해 이벤트를 사용 하 되 고 있습니다. 

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


### <a name="subscribe-to-connecteddevicesnotificationregistrationmanager-events"></a>ConnectedDevicesNotificationRegistrationManager 이벤트 구독

마찬가지로, 플랫폼 간 장치 명령에 전달할 알림을 사용 합니다.  따라서을 구독 해야 합니다는 **ConnectedDevicesNotificationRegistrationManager** 클라우드 등록 상태를 보장 하기 위해 이벤트 사용 되는 계정에 대 한 유효 합니다.  확인을 사용 하 여 상태 **ConnectedDevicesNotificationRegistrationState**

```Java
ConnectedDevicesPlatform sPlatform.getNotificationRegistrationManager().notificationRegistrationStateChanged().subscribe((notificationRegistrationManager, args) -> {
    
     // Check state using ConnectedDevicesNotificationRegistrationState enum

}
```
### <a name="start-the-platform"></a>플랫폼 시작
플랫폼 초기화가 진행에서에 이벤트 처리기를 원격 시스템 장치 검색을 시작할 준비가 되었습니다.  

`ConnectedDevicesPlatform sPlatform.start();`

### <a name="retrieve-user-accounts-known-to-the-app"></a>앱에 알려진 사용자 계정 검색

앱에 알려진 사용자 계정 목록을 사용 하 여 제대로 동기화 되었는지 확인 해야 합니다 **ConnectedDevicesAccountManager**합니다.

사용 하 여 **ConnectedDevicesAccountManager.addAccountAsync** 새 사용자 계정을 추가 합니다.

```Java
 public synchronized AsyncOperation<ConnectedDevicesAddAccountResult> addAccountToAccountManagerAsync(ConnectedDevicesAccount account) {
        return ConnectedDevicesPlatform sPlatform.getAccountManager().addAccountAsync(account);
    }
```

사용할 수 잘못 된 계정을 제거 하려면 **ConnectedDevicesAccountManager.removeAccountAsync**

```Java
 public synchronized AsyncOperation<ConnectedDevicesAddAccountResult> removeAccountToAccountManagerAsync(ConnectedDevicesAccount account) {
        return ConnectedDevicesPlatform sPlatform.getAccountManager().removeAccountAsync(account);
    }
```