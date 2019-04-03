---
title: MCDAppServiceClosedEventArgs
description: MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: a115ea4cc753efac445a466dbdfbfb14bf184370
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909185"
---
# <a name="class-mcdappserviceclosedeventargs"></a>클래스 `MCDAppServiceClosedEventArgs` 

```
@interface MCDAppServiceClosedEventArgs : NSObject
```  

MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.

## <a name="properties"></a>속성

### <a name="status"></a>상태
`@property(nonatomic, readonly) MCDAppServiceClosedStatus status;`

App service를 닫은 방법의 상태입니다.