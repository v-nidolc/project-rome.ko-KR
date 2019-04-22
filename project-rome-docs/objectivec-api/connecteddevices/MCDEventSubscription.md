---
title: MCDEventSubscription
description: 이 인터페이스는 단순 이벤트 구독을 제공 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: ce5a5782f80b54e78a6e3890cd68d9e92c52226c
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801621"
---
# <a name="class-mcdeventsubscription"></a>클래스 `MCDEventSubscription` 

```
@interface MCDEventSubscription : NSObject
```  
이 인터페이스는 단순 이벤트 구독을 제공 합니다.

## <a name="methods"></a>메서드

### <a name="cancel"></a>취소
`- (void)cancel;`

이벤트 구독을 취소합니다. 이 호출 후 연결 된 EventListener는 (이미 비행 이벤트에서 계속 제공 될 수 있습니다) 자세한 이벤트를 받지 못합니다.
네이티브 코드에서 수행 됩니다 ConnectedDevices 기능을 많이, 이므로 하거나 취소 호출 하거나 Weakreference는 정리 된 EventListener 보유 중인 리소스의 적절 한 데 항상 확인 해야 합니다.
