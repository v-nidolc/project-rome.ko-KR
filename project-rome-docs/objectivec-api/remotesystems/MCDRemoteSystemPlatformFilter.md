---
title: MCDRemoteSystemPlatformFilter
description: 실행 중인 OS 플랫폼을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 1b82d7b3a1626489a83196bf949567b3ce7b94f0
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908755"
---
# <a name="class-mcdremotesystemplatformfilter"></a>클래스 `MCDRemoteSystemPlatformFilter` 

```
@interface MCDRemoteSystemPlatformFilter : NSObject<MCDRemoteSystemFilter> 
```  

실행 중인 OS 플랫폼을 기반으로 하는 원격 시스템을 필터링 하는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="platform"></a>플랫폼
`@property(nonatomic, readonly) MCDRemoteSystemPlatform platform;`

플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithplatform"></a>filterWithPlatform
`+ (nullable instancetype)filterWithPlatform:(MCDRemoteSystemPlatform)platform;`

#### <a name="parameters"></a>매개 변수 
* `platform` 

플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.

#### <a name="returns"></a>반환 값
플랫폼별으로 필터링 MCDRemoteSystemPlatformFilter 개체를 반환 합니다.

### <a name="initwithplatform"></a>initWithPlatform
`- (nullable instancetype)initWithPlatform:(MCDRemoteSystemPlatform)platform;`

#### <a name="parameters"></a>매개 변수 
* `platform` 

플랫폼에 대 한 필터링을 나타내는 MCDRemoteSystemPlatform 값입니다.

#### <a name="returns"></a>반환 값
필터를 사용 하 여 플랫폼별 초기화 MCDRemoteSystemPlatformFilter 개체를 반환 합니다.