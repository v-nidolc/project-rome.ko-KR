---
title: MCDAppServiceRequestReceivedEventArgs
description: "\"요청 받은\" 이벤트와 연결 된 데이터를 포함 합니다."
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5fa7a3b2742d5ecacd7c6a90e39e86f4c46f2218
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800645"
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