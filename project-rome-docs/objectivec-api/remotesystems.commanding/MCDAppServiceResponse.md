---
title: MCDAppServiceResponse
description: 연결 된 원격 앱 서비스에서 받은 응답을 나타내는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 74cff4a84bdc4bf073dd57319c987e274ea8ceaf
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800795"
---
# <a name="class-mcdappserviceresponse"></a>클래스 `MCDAppServiceResponse`

```
@interface MCDAppServiceResponse : NSObject
```

연결 된 원격 앱 서비스에서 받은 응답을 나타내는 클래스입니다.

## <a name="properties"></a>속성

### <a name="message"></a>message 
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

원격 앱 서비스에서 받은 메시지입니다.

### <a name="status"></a>상태
`@property(nonatomic, readonly) MCDAppServiceResponseStatus status;`

받은 응답의 상태입니다.