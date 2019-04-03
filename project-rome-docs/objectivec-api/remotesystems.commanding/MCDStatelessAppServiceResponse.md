---
title: MCDStatelessAppServiceResponse
description: MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4e650b1b114a3cb05b2d9b03b833b9e1cdd6607c
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907235"
---
# <a name="class-mcdstatelessappserviceresponse"></a>클래스 `MCDStatelessAppServiceResponse` 

```
@interface MCDStatelessAppServiceResponse : NSObject
```  

MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.


## <a name="properties"></a>속성

### <a name="message"></a>message
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

키/값 쌍으로 구성 된 원격 앱 서비스에서 보낸 메시지입니다.

### <a name="status"></a>상태
`@property(nonatomic, readonly) MCDStatelessAppServiceResponseStatus status;`

원격 앱 서비스에서 응답의 상태입니다.

