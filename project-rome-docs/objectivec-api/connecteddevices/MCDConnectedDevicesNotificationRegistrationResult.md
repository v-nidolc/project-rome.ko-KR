---
title: MCDConnectedDevicesNotificationRegistrationResult
description: 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9ee253ff1c07f498b42ccf0cd0edeb9937f31f59
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801355"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationresult"></a>클래스 `MCDConnectedDevicesNotificationRegistrationResult` 

```
@interface MCDConnectedDevicesNotificationRegistrationResult : NSObject
```  
MCDConnectedDevicesNotificationRegistrationResult 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다. 이 결과 통해 통신 하는 오류 상태를 사용할 수 없는 네트워크와 같은 특정 일시적인 장애가 발생할 경우 등록을 다시 시도 하는 앱에서 사용할 해야 합니다.

## <a name="properties"></a>속성

### <a name="status"></a>상태

`@property(nonatomic, readonly) MCDConnectedDevicesNotificationRegistrationStatus status;`

등록 작업의 상태 열거형입니다.