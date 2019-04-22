---
title: MCDUserActivitySession
description: 이 클래스는 사용자 활동 추적 ([MCDUserActivity](MCDUserActivity.md) 인스턴스)는 사용자 활동에 참여 하는 동안.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2ae85e637bb059e811a60e5bde5f33ea767c8314
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800665"
---
# <a name="class-mcduseractivitysession"></a>클래스 `MCDUserActivitySession`

```
@interface MCDUserActivitySession : NSObject
```

이 클래스는 지정 된 사용자 활동에 대 한 참여를 추적 ([MCDUserActivity](MCDUserActivity.md) 인스턴스).

A [MCDUserActivity](MCDUserActivity.md) 사용자 활동에 참여 하는 기간을 추적 하는 MCDUserActivitySession와 사용 하 여 연결 합니다. 예를 들어, 동영상을 시청 같은 활동이 여러 날에 걸쳐 켜기 끄기 발생할 수 있습니다. 사용자는 동영상을 시청의 새 활동을 처음 시작 하는 경우에 MCDUserActivitySession 생성 되어야 합니다. 사용자가 다른 활동을 전환할 때 삭제 해야 합니다. 앱 간에 만들어야 사용자를 다시 시작할 때 **MCDUserActivitySession** 원래에서 [MCDUserActivity](MCDUserActivity.md) 영화를 감시 하는 사용자와 작업을 추적 하려면.


## <a name="properties"></a>속성

### <a name="activityid"></a>activityId
`@property(nonatomic, readonly, nonnull) NSString* activityId;`

이 MCDUserActivitySession 연관 MCDUserActivity에 대 한 고유 ID입니다.

## <a name="methods"></a>메서드

### <a name="stop"></a>stop
`- (void)stop;`

이 작업 세션을 중지합니다. 이 사용자는 더 이상이 세션과 연결 된 활동에 참여 하는 경우 호출 되어야 합니다.