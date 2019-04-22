---
title: MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs
description: MCDConnectedDevicesNotificationRegistration 상태 변경 이벤트에 대 한 이벤트 인수 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 83b59cc884cc0e8d59387b95388b4b7b2b5fa273
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800695"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstatechangedeventargs"></a>클래스 `MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs` 

```
@interface MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs : NSObject
```  
MCDConnectedDevicesNotificationRegistration 상태 변경 이벤트에 대 한 이벤트 인수 클래스입니다. 이 응용 프로그램에 올바른 알림 메커니즘을 통해 새 연결 된 장치 플랫폼 메시지 정보를 가져옵니다는 되도록 사용 됩니다.

## <a name="properties"></a>속성

### <a name="account"></a>계정으로 이동하면
`@property(nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

알림 등록 상태 변경에는 계정입니다.

### <a name="registration"></a>등록
`@property(nonatomic, readonly, nonnull) MCDConnectedDevicesNotificationRegistration* registration;`

상태가 변경 된 등록 인스턴스에 대 한 정보입니다.

### <a name="state"></a>state
`@property(nonatomic, readonly) MCDConnectedDevicesNotificationRegistrationState state;`

새 등록 상태입니다.