---
title: MCDUserActivitySessionHistoryItem
description: 이 클래스는 사용자가 특정 작업에 참여 하는 시작 및 종료 시간을 제공 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 3a480d9d0d028973554c13ee162b359502c8a772
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801635"
---
# <a name="class-mcduseractivitysessionhistoryitem"></a>클래스 `MCDUserActivitySessionHistoryItem`

```
@interface MCDUserActivitySessionHistoryItem : NSObject
```

이 클래스는 사용자가 특정 작업에 참여 하는 시작 및 종료 시간을 제공 합니다.


## <a name="properties"></a>속성

### <a name="useractivity"></a>userActivity
`@property(nonatomic, readonly, nonnull) MCDUserActivity* userActivity;`

사용자 작업 기록을이 클래스 인스턴스를 나타냅니다.

### <a name="starttime"></a>startTime
`@property(nonatomic, readonly, nonnull) NSDate* startTime;`

사용자 연결된 작업의 유용한 시작 된 시간입니다.

### <a name="endtime"></a>endTime
`@property(nonatomic, readonly, nullable) NSDate* endTime;`

연결된 된 활동에 참여 사용자를 중지 하는 경우 시간입니다.

### <a name="remotesystemid"></a>remoteSystemId
`@property(nonatomic, readonly, nullable) NSString* remoteSystemId;`

이 작업에 참여 하는 사용자 장치의 원격 시스템 id를 나타내는 문자열입니다.