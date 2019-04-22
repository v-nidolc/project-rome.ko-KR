---
title: MCDConnectedDevicesNotification
description: 알림을 처리의 결과입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2a60e2cab26c3d2df39314aa5b61a65de1529356
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800605"
---
# <a name="class-mcdconnecteddevicesnotification"></a>클래스 `MCDConnectedDevicesNotification` 

```
@interface MCDConnectedDevicesNotification : NSObject
```  
알림을 처리의 결과입니다.

## <a name="methods"></a>메서드

### <a name="tryparse"></a>tryParse

`+ (nullable instancetype)tryParse:(NSDictionary* _Nonnull)dictionary;`

APNS에서 MCDConnectedDevicesNotification 구문 분석 하려고 맵 서식이 지정 됩니다.

#### <a name="parameters"></a>매개 변수 
* `dictionary` 

처리를 위해 연결 된 장치 플랫폼에서 APNS 알림을 수신 하는 맵.
