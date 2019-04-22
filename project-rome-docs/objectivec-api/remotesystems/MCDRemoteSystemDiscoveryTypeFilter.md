---
title: MCDRemoteSystemDiscoveryTypeFilter
description: 원격 시스템 검색 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 8054d378f203d5cde29af6b4452cc03e15e24828
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907525"
---
# <a name="class-mcdremotesystemdiscoverytypefilter"></a>클래스 `MCDRemoteSystemDiscoveryTypeFilter` 

```
@interface MCDRemoteSystemDiscoveryTypeFilter : NSObject<MCDRemoteSystemFilter>
```  

원격 시스템 검색 형식에 따라 필터링 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="type"></a>유형
`@property(nonatomic, readonly) MCDRemoteSystemDiscoveryType type;`

필터링 할 검색 형식입니다.

> 참고: Android에서 연결 된 장치 플랫폼에만 사용할 수 Bluetooth Android 8.0 oreo (용)를 실행 하는 시스템 이상.

## <a name="constructors"></a>생성자

### <a name="filterwithtype"></a>filterWithType
`+ (nullable instancetype)filterWithType:(MCDRemoteSystemDiscoveryType)discoveryType;`

#### <a name="parameters"></a>매개 변수 
* `discoveryType` 필터링 할 검색 형식입니다.

#### <a name="returns"></a>반환 값
지정 된 형식 값을 사용 하 여이 클래스의 새 인스턴스. 값은 한 번에 여러 필터를 적용 하려면 함께 and 연산 수 있습니다.

### <a name="initwithtype"></a>initWithType
`- (nullable instancetype)initWithType:(MCDRemoteSystemDiscoveryType)discoveryType;`

#### <a name="parameters"></a>매개 변수 
* `discoveryType` 필터링 할 검색 형식입니다.

#### <a name="returns"></a>반환 값
지정 된 형식 값을 사용 하 여이 클래스의 새 인스턴스. 값은 한 번에 여러 필터를 적용 하려면 함께 and 연산 수 있습니다.