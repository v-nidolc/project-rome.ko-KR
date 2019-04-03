---
title: MCDRemoteSystemKindFilter
description: 원격 시스템 장치 종류에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 162e8f881b532fae50f6d301149b50c5ddf344b5
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907265"
---
# <a name="class-mcdremotesystemkindfilter"></a>클래스 `MCDRemoteSystemKindFilter` 

```
@interface MCDRemoteSystemKindFilter : NSObject <MCDRemoteSystemFilter>
```  

원격 시스템 장치 종류에 따라 필터링 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="kinds"></a>종류
`@property(nonatomic, readonly, copy, nonnull) NSArray<NSString*>* kinds;`

배열에 대해 필터링 할 장치의 종류를 나타내는 문자열입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithkinds"></a>filterWithKinds
`+ (nullable instancetype)filterWithKinds:(nonnull NSArray<NSString*>*)kinds;`

종류의 필터링이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `kinds`

 배열에 대해 필터링 할 장치 종류를 나타내는 문자열입니다.

#### <a name="returns"></a>반환 값
종류를 사용 하 여 필터링 MCDRemoteSystemKindFilter 개체를 반환 합니다.

### <a name="initwithkinds"></a>initWithKinds
`- (nullable instancetype)initWithKinds:(nonnull NSArray<NSString*>*)kinds;`

종류의 필터링이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `kinds` 

배열에 대해 필터링 할 장치 종류를 나타내는 문자열입니다.

#### <a name="returns"></a>반환 값
종류를 사용 하 여 초기화 MCDRemoteSystemKindFilter 개체를 반환 합니다.