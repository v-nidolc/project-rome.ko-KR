---
title: MCDAppServiceRequestReceivedEventArgs
description: "\"요청 받은\" 이벤트와 연결 된 데이터를 포함 합니다."
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5fa7a3b2742d5ecacd7c6a90e39e86f4c46f2218
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908565"
---
# <a name="class-mcdappservicerequestreceivedeventargs"></a>클래스 `MCDAppServiceRequestReceivedEventArgs` 

```
@interface MCDAppServiceRequestReceivedEventArgs : NSObject
```  
"요청 받은" 이벤트와 연결 된 데이터를 포함 합니다.

## <a name="properties"></a>속성

### <a name="request"></a>요청
`@property(nonatomic, readonly, nonnull) MCDAppServiceRequest* request;`

원격 장치에서 보낸 요청입니다.