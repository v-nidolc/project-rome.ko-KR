---
title: MCDConnectedDevicesNotificationType
description: 알림의 유형 (서비스)를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: eb537450a9e8a970bd07652fe201e94071211d92
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801695"
---
# <a name="enum-mcdconnecteddevicesnotificationtype"></a>열거형 `MCDConnectedDevicesNotificationType`

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesNotificationType)
```  
알림의 유형 (서비스)를 설명 하는 값을 포함 합니다.

## <a name="fields"></a>필드

| 이름                              |   값     | 설명 |
|:----------------------------------|:------|:-------------------------------|
| MCDNotificationTypeUnknown | 0 | ConnectedDevicesNotificationType 알려진 아닙니다. |
| MCDNotificationTypeWNS | 1 | Windows 푸시 알림 서비스입니다. |
| MCDNotificationTypeGCM | 2 | Google Cloud Messaging 합니다. |
| MCDNotificationTypeFCM | 3 | Firebase Cloud Messaging 합니다.|
| MCDNotificationTypeAPN | 4 | Apple Push Notification Service입니다. |
| MCDNotificationTypePolling | 5 | 클라우드 알림 서비스가 없습니다. 대신 들어오는 응답에 대해 폴링하십시오. |
