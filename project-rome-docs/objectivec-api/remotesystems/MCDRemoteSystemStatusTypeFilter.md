---
title: MCDRemoteSystemStatusTypeFilter
description: 원격 시스템 가용성 상태 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 201570c16a8eb9cf1a31e450b3408c8ab255fe1a
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907125"
---
# <a name="class-mcdremotesystemstatustypefilter"></a>클래스 `MCDRemoteSystemStatusTypeFilter`

```
@interface MCDRemoteSystemStatusTypeFilter : NSObject <MCDRemoteSystemFilter>
```

원격 시스템 가용성 상태 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="type"></a>유형
`@property(nonatomic, readonly) MCDRemoteSystemStatusType type;` 이 필터 인스턴스의 원격 시스템 상태 형식입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithtype"></a>filterWithType
`+ (nullable instancetype)filterWithType:(MCDRemoteSystemStatusType)statusType;`

#### <a name="parameters"></a>매개 변수 
* `statusType` 가용성 상태 형식에 대 한 필터를 나타내는 값입니다.

#### <a name="returns"></a>반환 값
유형별로 필터링 MCDRemoteSystemStatusTypeFilter 개체를 반환 합니다.

### <a name="initwithtype"></a>initWithType
`- (nullable instancetype)initWithType:(MCDRemoteSystemStatusType)statusType;`

#### <a name="parameters"></a>매개 변수 
* `statusType` 

가용성 상태 형식에 대 한 필터를 나타내는 값입니다.

#### <a name="returns"></a>반환 값
형식을 사용 하 여 초기화 하는 MCDRemoteSystemStatusTypeFilter 개체를 반환 합니다.