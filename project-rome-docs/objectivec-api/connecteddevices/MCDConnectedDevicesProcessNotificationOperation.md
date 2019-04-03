---
title: MCDConnectedDevicesProcessNotificationOperation
description: 처리를 위해 로마 플랫폼에 대 한 알림을 제공 하는 결과입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: cb482e7b00cd5fe090de1708388d140cfd45777b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909895"
---
# <a name="class-mcdconnecteddevicesprocessnotificationoperation"></a>클래스 `MCDConnectedDevicesProcessNotificationOperation` 

```
@interface MCDConnectedDevicesProcessNotificationOperation : NSObject
```  
처리를 위해 연결 된 장치 플랫폼에 APNS 알림을 제공 하는 결과입니다.

> [!NOTE] 
> 이 클래스는 사용 되지 않습니다. MCDConnectedDevicesNotification를 대신 사용 하십시오. 

## <a name="properties"></a>속성

### <a name="connecteddevicesnotification"></a>connectedDevicesNotification
`@property(nonatomic, readonly, getter=isConnectedDevicesNotification) BOOL connectedDevicesNotification;`

연결 된 장치 플랫폼에 대 한 알림을 할지 나타내는 플래그입니다.

## <a name="methods"></a>메서드

### <a name="waitforcompletionasync"></a>waitForCompletionAsync
`- (void)waitForCompletionAsync:(nonnull void (^)(NSError* _Nullable error))callback;`

 알림을 처리 하 고 완료 될 때까지 기다립니다.

#### <a name="parameters"></a>매개 변수 
* `callback` 

알림 완료에 대 한 콜백 결과입니다.
