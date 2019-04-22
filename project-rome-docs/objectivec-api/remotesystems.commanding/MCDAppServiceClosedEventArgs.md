---
title: MCDAppServiceClosedEventArgs
description: MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: a115ea4cc753efac445a466dbdfbfb14bf184370
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801295"
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