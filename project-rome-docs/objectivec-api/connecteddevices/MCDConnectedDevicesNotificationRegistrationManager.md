---
title: MCDConnectedDevicesNotificationRegistrationManager
description: 모든 계정에 대 한 로마 클라우드 알림 등록을 관리합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d4f5f7963514795e3e296d9bdb42b1811af4f7cc
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909905"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationmanager"></a>클래스 `MCDConnectedDevicesNotificationRegistrationManager` 

```
@interface MCDConnectedDevicesNotificationRegistrationManager : NSObject
```  
모든 계정에 대 한 연결 된 장치 플랫폼 클라우드 알림에 대 한 등록을 관리합니다.

MCDConnectedDevicesNotificationRegistrationManager 각 계정에 대 한 등록 알림 정보를 관리 합니다. 언제 든 지 앱의 알림 정보 (예를 들어 변경 될 때 APNS 토큰), 바꾸거나, 앱 정보를 다시 등록 해야 알림 정보를이 만료 되는 경우. 응용 프로그램은만 나가는 통신에 대 한 응답에 대 한 내용, 폴링 등록을 사용할 수 있습니다.

> [!NOTE] 
> 알림 정보 ConnectedDevices 많지 성공적으로 작동 하기 전에 등록 되어야 합니다. 

## <a name="properties"></a>속성

### <a name="registrationstatechanged"></a>registrationStateChanged
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesNotificationRegistrationManager*, MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs*>* registrationStateChanged;`

앱에는 계정에 대 한 알림 등록 상태가 변경 될 때 알립니다 수 있도록 이벤트입니다. 

## <a name="methods"></a>메서드

### <a name="registerforaccountasync"></a>registerForAccountAsync
`- (void) registerForAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account registration:(MCDConnectedDevicesNotificationRegistration* _Nonnull)notificationRegistration callback:(nonnull void (^)(BOOL, NSError* _Nullable))callback __attribute__((deprecated("Use registerAsync instead")));`

주어진된 알림에 등록 정보를 사용 하 여 지정 된 계정을 등록 합니다. 이이 응용 프로그램은이 계정에 대 한 새 연결 된 장치 정보에 대 한 알림을 받을 수 있도록 알림 채널을 만듭니다. 다른 응용 프로그램 MCDRemoteSystemAppRegistration 정보가 게시 될 때까지이 알림 채널을 사용 하 여이 앱과 통신 하지 수 하는 참고 합니다.

> [!WARNING]
> 이 함수는 사용 되지 않습니다. RegisterAsync를 대신 사용 하십시오.

#### <a name="parameters"></a>매개 변수 
* `account` 

알림 정보를 등록 하는 계정입니다.

* `notificationRegistration` 

알림 정보를 등록 합니다.

* `callback` 

성공적으로 등록에 대 한 콜백이 발생 합니다.

### <a name="registerasync"></a>registerAsync
`- (void) registerAsync:(MCDConnectedDevicesAccount* _Nonnull)account registration:(MCDConnectedDevicesNotificationRegistration* _Nonnull)notificationRegistration completion:(nonnull void (^)(MCDConnectedDevicesNotificationRegistrationResult* _Nonnull, NSError* _Nullable))callback;`

주어진된 알림에 등록 정보를 사용 하 여 지정 된 계정을 등록 합니다. 이이 응용 프로그램은이 계정에 대 한 새 연결 된 장치 정보에 대 한 알림을 받을 수 있도록 알림 채널을 만듭니다. 다른 응용 프로그램 MCDRemoteSystemAppRegistration 정보가 게시 될 때까지이 알림 채널을 사용 하 여이 앱과 통신 하지 수 하는 참고 합니다.

#### <a name="parameters"></a>매개 변수 
* `account` 

알림 정보를 등록 하는 계정입니다.

* `notificationRegistration` 

알림 정보를 등록 합니다.

* `callback` 

성공적으로 등록에 대 한 콜백이 발생 합니다.

### <a name="getnotificationregistrationstateforaccount"></a>getNotificationRegistrationStateForAccount
`- (MCDConnectedDevicesNotificationRegistrationState) getNotificationRegistrationStateForAccount:(MCDConnectedDevicesAccount* _Nonnull)account;`

지정된 된 계정에 대 한 현재 알림 등록 상태를 검색 합니다. 등록 된 알림 정보를 (앱 제거 되었거나 매우 오랫동안에서 실행 되지 하는 경우에 유용) 결국 만료 됩니다. 다시 앱 등록이 만료 됨 / 만료 된 경우 해당 알림 정보를 등록 해야 합니다. 

#### <a name="parameters"></a>매개 변수 
* `account`

등록 상태를 가져올 수 있는 계정입니다.

#### <a name="returns"></a>반환 값

알림 등록의 상태입니다.
