---
title: MCDRemoteSystemLocalVisibilityKindFilter
description: 원격 시스템을 검색 하는 경우 로컬 (호출) 응용 프로그램 표시 기본 설정을 설정 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b54614c1ee0a820e605df05768c164d07a5a9464
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909575"
---
# <a name="class-mcdremotesystemlocalvisibilitykindfilter"></a>클래스 `MCDRemoteSystemLocalVisibilityKindFilter` 

```
@interface MCDRemoteSystemLocalVisibilityKindFilter : NSObject <MCDRemoteSystemFilter>
```  

원격 시스템을 검색 하는 경우 로컬 (호출) 응용 프로그램 표시 기본 설정을 설정 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="kind"></a>kind
`@property(nonatomic, readonly) MCDRemoteSystemLocalVisibilityKind kind;`

사용 하 여 필터링에 표시 유형 설정입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithkind"></a>filterWithKind
`+ (nullable instancetype)filterWithKind:(MCDRemoteSystemLocalVisibilityKind)localVisibilityKind;`

페이지를 만들고이 클래스의 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `localVisibilityKind` 

사용 하 여 필터링 하는 로컬 앱 표시 설정을 나타내는 MCDRemoteSystemLocalVisibilityKind 값입니다.

#### <a name="returns"></a>반환 값
종류별로 필터링 MCDRemoteSystemLocalVisibilityKind 개체를 반환 합니다.

### <a name="initwithkind"></a>initWithKind
`- (nullable instancetype)initWithKind:(MCDRemoteSystemLocalVisibilityKind)localVisibilityKind;`

페이지를 만들고이 클래스의 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `localVisibilityKind` 

사용 하 여 필터링 하는 로컬 앱 표시 설정을 나타내는 MCDRemoteSystemLocalVisibilityKind 값입니다.

#### <a name="returns"></a>반환 값
종류를 사용 하 여 초기화 MCDRemoteSystemLocalVisibilityKind 개체를 반환 합니다.