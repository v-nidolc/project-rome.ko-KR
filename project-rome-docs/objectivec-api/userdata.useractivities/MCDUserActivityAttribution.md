---
title: MCDUserActivityAttribution
description: 이 클래스는 사용자 활동의 그래픽 요소를 관리합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 94ae2f5afef24a1f4e320014ac930d67b657b0d7
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909255"
---
# <a name="class-mcduseractivityattribution"></a>클래스 `MCDUserActivityAttribution`

```
@interface MCDUserActivityAttribution : NSObject
```

이 클래스는 사용자 활동의 그래픽 요소를 관리합니다.

## <a name="properties"></a>속성

### <a name="iconuri"></a>iconUri
`+ (nullable instancetype)attributionWithIconUri:(nonnull NSString*)iconUri;`

아이콘 이미지에 대 한 URI입니다.

### <a name="alternatetext"></a>alternateText
`@property(nonatomic, copy, nonnull) NSString* alternateText;`

아이콘 이미지 (를 사용 하 여 화면 판독기를 사용 하 여) 설명 하는 텍스트입니다.

### <a name="addimagequery"></a>addImageQuery
`@property(nonatomic, assign) BOOL addImageQuery;`

Windows 이미지에서 제공 된 URI에 쿼리 문자열을 추가 하도록 허용 여부를 결정 **IconUri** 이미지를 검색 하는 경우. 쿼리 문자열에는 사용자의 표시, 고대비 설정 및 사용자의 언어의 DPI를 기준으로 이상적인 이미지를 선택 하는 데 도움이 되는 정보가 포함 됩니다. 이 쿼리 문자열 확장, 대비 설정 및 언어를 지정합니다. 예를 들어를 **IconUri** "www.website.com/images/hello.png"의 값이 됩니다 "www.website.com/images/hello.png?ms-scale=100 및 ms 대비 표준 ms lang = = en-우리"입니다.

## <a name="constructors"></a>생성자

### <a name="useractivityattributionwithiconuri"></a>userActivityAttributionWithIconUri
`+ (nullable instancetype)userActivityAttributionWithIconUri:(nonnull NSString*)iconUri;`

아이콘 URI를 사용 하 여이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `iconUri` 

만든 인스턴스에 속한 아이콘 URI의 문자열 값입니다.

#### <a name="returns"></a>반환 값
아이콘 uri를 사용 하 여 초기화 MCDUserActivityAttribution 개체를 반환 합니다.

### <a name="attributionwithiconuri"></a>attributionWithIconUri
`+ (nullable instancetype)attributionWithIconUri:(nonnull NSString*)iconUri;`

아이콘 uri 특성을 사용 하 여이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `iconUri` 

만든 인스턴스에 속한 아이콘 URI의 문자열 값입니다.

#### <a name="returns"></a>반환 값
아이콘 uri를 사용 하 여 MCDUserActivityAttribution 개체 특성을 반환 합니다.