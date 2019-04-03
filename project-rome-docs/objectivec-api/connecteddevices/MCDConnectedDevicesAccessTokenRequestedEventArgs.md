---
title: MCDConnectedDevicesAccessTokenRequestedEventArgs
description: MCDConnectedDevicesAccessTokenRequested, 토큰을 요청 해야 할 때 발생 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d50b7dc75944e3c3df553c95247b0ec578a477a4
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908325"
---
# <a name="class-mcdconnecteddevicesaccesstokenrequestedeventargs"></a>클래스 `MCDConnectedDevicesAccessTokenRequestedEventArgs` 

```
@interface MCDConnectedDevicesAccessTokenRequestedEventArgs : NSObject
```  

MCDConnectedDevicesAccessTokenRequested, 토큰을 요청 해야 할 때 발생 하 여 반환 합니다. 

## <a name="properties"></a>속성

### <a name="request"></a>요청
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccessTokenRequest* request;`

이 MCDConnectedDevicesAccessTokenRequest와 연결 된 요청입니다.