---
title: MCDRemoteLauncherOptions
description: 원격 실행 기능에 대 한 옵션을 나타내는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 628bf1659dfb4ce50e20631622d8a78a322bb2f5
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801265"
---
# <a name="class-mcdremotelauncheroptions"></a>클래스 `MCDRemoteLauncherOptions` 

```
@interface MCDRemoteLauncherOptions : NSObject
```  

원격 실행 기능에 대 한 옵션을 나타내는 데 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="fallbackuri"></a>fallbackUri
`@property(nonatomic, copy, nullable) NSString* fallbackUri;`

대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.

### <a name="preferredpackageids"></a>preferredPackageIds
`@property(nonatomic, copy, nullable) NSArray<NSString*>* preferredPackageIds;`

목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다. Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.

## <a name="constructors"></a>생성자

### <a name="optionswithfallbackuri"></a>optionsWithFallbackUri
`+ (nullable instancetype)optionsWithFallbackUri: (nullable NSString*)fallbackUri  preferredPackageIds: (nullable NSArray<NSString*>*)preferredPackageIds;`

페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `fallbackUri` 

대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.

* `preferredPackageIds` 

목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다. Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="initwithfallbackuri"></a>initWithFallbackUri
`- (nullable instancetype)initWithFallbackUri:(nullable NSString*)fallbackUri preferredPackageIds:(nullable NSArray<NSString*>*)preferredPackageIds;`

페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `fallbackUri` 

대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.

* `preferredPackageIds` 

목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다. Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) 성공 하면이 고 그렇지 nil 합니다.