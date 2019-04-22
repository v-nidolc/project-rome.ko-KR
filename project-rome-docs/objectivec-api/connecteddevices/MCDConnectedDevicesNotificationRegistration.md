---
title: MCDConnectedDevicesNotificationRegistration
description: 이 클래스는 푸시 알림 서비스 (일부 프로젝트 로마 시나리오에 필요)를 사용 하 여 앱의 등록을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 38cd140538d6e6dabddda39ba98f736fc708ade7
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801435"
---
# <a name="class-mcdconnecteddevicesnotificationregistration"></a>클래스 `MCDConnectedDevicesNotificationRegistration` 

```
@interface MCDConnectedDevicesNotificationRegistration : NSObject
```  
 이 클래스는 푸시 알림 서비스 (일부 프로젝트 로마 시나리오에 필요)를 사용 하 여 앱의 등록을 나타냅니다. 연결 된 장치 플랫폼에이 정보를 전달 하는 것입니다.

## <a name="properties"></a>속성

### <a name="type"></a>유형
`@property(nonatomic, readwrite) MCDConnectedDevicesNotificationType type;`

이 알림의 형식입니다.

### <a name="token"></a>token
`@property(nonatomic, readwrite, nonnull) NSString* token;`

등록 토큰입니다.

### <a name="appid"></a>appId
`@property(nonatomic, readwrite, nonnull) NSString* appId;`

푸시 알림 등록에 대 한 앱 ID입니다.

### <a name="appdisplayname"></a>appDisplayName
`@property(nonatomic, readwrite, nonnull) NSString* appDisplayName;`

앱 표시 이름입니다. 이 Microsoft 개발자 포털에서 등록에 사용 된 앱의 이름과 같아야 합니다.