---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 60a4e282fc5446e38a80e72979e12daad51b2026
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907215"
---
### <a name="create-an-instance-of-the-platform"></a>플랫폼의 인스턴스를 만듭니다

시작 하려면 플랫폼을 인스턴스화하면 됩니다.

`MCDConnectedDevicesPlatform* platform = [MCDConnectedDevicesPlatform new];`

### <a name="subscribe-to-mcdconnecteddevicesaccountmanager"></a>MCDConnectedDevicesAccountManager 구독

플랫폼에는 플랫폼에 액세스 하려면 인증된 된 사용자에 필요 합니다.  구독할 필요 **MCDConnectedDevicesAccountManager** 유효한 계정 보장 하기 위해 이벤트를 사용 하 되 고 있습니다.

```ObjectiveC
[MCDConnectedDevicesPlatform* platform.accountManager.accessTokenRequested
     subscribe:^(MCDConnectedDevicesAccountManager* _Nonnull manager __unused,
                 MCDConnectedDevicesAccessTokenRequestedEventArgs* _Nonnull request __unused) {

                    // Get access token

                 }
```

```ObjectiveC
[MCDConnectedDevicesPlatform* platform.platform.accountManager.accessTokenInvalidated
     subscribe:^(MCDConnectedDevicesAccountManager* _Nonnull manager __unused,
                 MCDConnectedDevicesAccessTokenInvalidatedEventArgs* _Nonnull request) {

                      // Refresh and renew existing access token

                 }
```

### <a name="subscribe-to-mcdconnecteddevicesnotificationregistrationmanager"></a>MCDConnectedDevicesNotificationRegistrationManager 구독

마찬가지로, 플랫폼 간 장치 명령에 전달할 알림을 사용 합니다.  따라서을 구독 해야 합니다는 **MCDConnectedDevicesNotificationRegistrationManager** 클라우드 등록 상태를 보장 하기 위해 이벤트 사용 되는 계정에 대 한 유효 합니다.  확인을 사용 하 여 상태 **MCDConnectedDevicesNotificationRegistrationState**

```ObjectiveC
[MCDConnectedDevicesPlatform* platform.notificationRegistrationManager.notificationRegistrationStateChanged
     subscribe:^(MCDConnectedDevicesNotificationRegistrationManager* manager __unused,
                 MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs* args __unused) {

                     // Check state using MCDConnectedDevicesNotificationRegistrationState enum

                 }

```

### <a name="start-the-platform"></a>플랫폼 시작
플랫폼 초기화가 진행에서에 이벤트 처리기를 원격 시스템 장치 검색을 시작할 준비가 되었습니다.  

`[MCDConnectedDevicesPlatform* platform start];`

### <a name="retrieve-user-accounts-known-to-the-app"></a>앱에 알려진 사용자 계정 검색

앱에 알려진 사용자 계정 목록을 사용 하 여 제대로 동기화 되었는지 확인 해야 합니다 **MCDConnectedDevicesAccountManager**합니다.

사용 하 여 **MCDConnectedDevicesAccountManager.addAccountAsync** 새 사용자 계정을 추가 합니다.

```ObjectiveC
[MCDConnectedDevicesPlatform* platform.accountManager
     addAccountAsync:self.mcdAccount
     callback:^(MCDConnectedDevicesAddAccountResult* _Nonnull result, NSError* _Nullable error) {

     // Check state using **MCDConnectedDevicesAccountAddedStatus** enum

     }
```

사용할 수 잘못 된 계정을 제거 하려면 **MCDConnectedDevicesAccountManager.removeAccountAsync**

```ObjectiveC
 [MCDConnectedDevicesPlatform* platform.accountManager
     removeAccountAsync:existingAccount
     callback:^(MCDConnectedDevicesRemoveAccountResult* _Nonnull result __unused, NSError* _Nullable error) {

                    // Remove invalid user account

     }
```