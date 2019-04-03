---
title: MCDAppServiceInfo
description: 이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5cb01d664a07653387b523eeec68ebd50bbc2798
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907115"
---
# <a name="class-mcdappserviceinfo"></a>클래스 `MCDAppServiceInfo` 

```
@interface MCDAppServiceInfo : NSObject<NSCopying>
```  

이 클래스는 원격 장치 또는 응용 프로그램에 속하는 앱 서비스를 설명 합니다.

## <a name="properties"></a>속성

### <a name="name"></a>NAME
`@property(nonatomic, readonly, nullable) NSString* name;`

설명 하 고 app service의 이름입니다.

### <a name="packageid"></a>packageId
`@property(nonatomic, readonly, nullable) NSString* packageId;`

설명 하 고 app service의 패키지 ID입니다.

## <a name="constructors"></a>생성자

### <a name="infowithname"></a>infoWithName
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name;`

App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `name` 

설명 하 고 app service의 이름입니다.

#### <a name="returns"></a>반환 값
제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.

### <a name="initwithname"></a>initWithName
`- (nullable instancetype)initWithName:(nonnull NSString*)name;`

App service의 이름 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `name` 

설명 하 고 app service의 이름입니다.

#### <a name="returns"></a>반환 값
제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.

### <a name="infowithname"></a>infoWithName
`+ (nullable instancetype)infoWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

App service의 이름과 정보를 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `name` 

설명 하 고 app service의 이름입니다.

* `packageId` 

설명 하 고 app service의 패키지 ID입니다.

#### <a name="returns"></a>반환 값
제공 된 이름이 포함 된 MCDAppServiceInfo 개체를 반환 합니다.

### <a name="initwithname"></a>initWithName
`- (nullable instancetype)initWithName:(nonnull NSString*)name packageId:(nonnull NSString*)packageId;`

App service의 이름 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `name` 

설명 하 고 app service의 이름입니다.

* `packageId` 

설명 하 고 app service의 패키지 ID입니다.

#### <a name="returns"></a>반환 값
제공된 된 이름을 사용 하 여 초기화 MCDAppServiceInfo 개체를 반환 합니다.
