---
title: MCDEvent
description: 이 인터페이스는 단순 이벤트 모델을 제공합니다. 이벤트는 EventListeners에서 사용 하는 항목을 생성 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: eabe9464a104593b06460153ed30f42f7cc103eb
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801395"
---
# <a name="class-mcdevent"></a>클래스 `MCDEvent` 

```
@interface MCDEvent<__covariant SourceType, __covariant ArgsType> : NSObject
```  
 
 이 인터페이스는 단순 이벤트 모델을 제공합니다. 이벤트는 EventListeners에서 사용 하는 항목을 생성 합니다.
이벤트 항목의 흐름을 MCDEventSubscription에 의해 제어 됩니다.

## <a name="methods"></a>메서드

### <a name="subscribe"></a>subscribe
`- (nonnull MCDEventSubscription*)subscribe:(nonnull void (^)(SourceType _Nonnull, ArgsType _Nonnull))listener;`

지정한 연결 된 장치 플랫폼의 이벤트를 구독 합니다.

#### <a name="parameters"></a>매개 변수 
* `listener` 

MCDEventSubscriptions 수신 대기 합니다.

#### <a name="returns"></a>반환 값
MCDEventSubscription의 인스턴스입니다.