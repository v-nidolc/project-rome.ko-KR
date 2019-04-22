---
title: MCDRemoteSystemAuthorizationKindFilter
description: 권한 부여 유형을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: da68c7a0eacd2018332d5e2fe5c8e3c906f473f8
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801255"
---
# <a name="class-mcdremotesystemauthorizationkindfilter"></a>클래스 `MCDRemoteSystemAuthorizationKindFilter` 

```
@interface MCDRemoteSystemAuthorizationKindFilter : NSObject<MCDRemoteSystemFilter>
```  

권한 부여 유형을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="kind"></a>kind
`@property(nonatomic, readonly) MCDRemoteSystemAuthorizationKind kind;`

권한 부여 형식에 대 한 필터입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithkind"></a>filterWithKind
`+ (nullable instancetype)filterWithKind:(MCDRemoteSystemAuthorizationKind)authorizationKind;`

MCDRemoteSystemAuthorizationKind 필터링이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `authorizationKind` 

권한 부여 형식에 대 한 필터입니다.

#### <a name="returns"></a>반환 값
제공 된 권한 부여 필터를 사용 하 여 MCDRemoteSystemAuthorizationKindFilter 개체를 반환합니다.

### <a name="initwithkind"></a>initWithKind
`- (nullable instancetype)initWithKind:(MCDRemoteSystemAuthorizationKind)authorizationKind;`

MCDRemoteSystemAuthorizationKind 사용 하 여이 클래스의 새 인스턴스입니다.

#### <a name="parameters"></a>매개 변수 
* `authorizationKind` 

권한 부여 형식에 대 한 필터입니다.

#### <a name="returns"></a>반환 값
authorizationKind를 사용 하 여 초기화 MCDRemoteSystemAuthorizationKindFilter 개체를 반환 합니다.