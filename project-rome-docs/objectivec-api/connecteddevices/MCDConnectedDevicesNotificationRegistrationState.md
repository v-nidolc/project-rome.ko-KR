---
title: MCDConnectedDevicesNotificationRegistrationState
description: 클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: be390f4f8e5d3c026d35bb8998e2818b9db05e86
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800715"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstate"></a>클래스 `MCDConnectedDevicesNotificationRegistrationState` 

```
typedef NS_ENUM(NSUInteger, MCDConnectedDevicesNotificationRegistrationState)
```  
클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.

## <a name="fields"></a>필드

| 이름                              |   값     | 설명 |
|:----------------------------------|:------|:-------------------------------|
| MCDConnectedDevicesNotificationRegistrationStateUnregistered | 0 | 등록 시작 되지 않았습니다.
| MCDConnectedDevicesNotificationRegistrationStateRegistered | 1 | 등록을 완료 했습니다. |
| MCDConnectedDevicesNotificationRegistrationStateExpiring | 2 | 등록 만료 되려고 이며 따라서 앱은 등록 다시 수행 합니다. |
| MCDConnectedDevicesNotificationRegistrationStateExpired | 3 | 등록 만료 되어 있으므로 앱 등록을 다시 수행 해야 합니다. |