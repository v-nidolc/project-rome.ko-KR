---
title: MCDUserActivityVisualElements
description: 이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c969b8a52bc6d2a22fd0a00808f9bb374c63cd8a
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801065"
---
# <a name="class-mcduseractivityvisualelements"></a>클래스 `MCDUserActivityVisualElements`

```
@interface MCDUserActivityVisualElements : NSObject 
```

이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.

## <a name="properties"></a>속성

### <a name="displaytext"></a>displayText
`@property(nonatomic, copy, nonnull) NSString* displayText;`

작업의 "세부 정보" 타일에 대 한 표시 텍스트입니다.

### <a name="descriptiontext"></a>descriptionText
`@property(nonatomic, copy, nullable) NSString* descriptionText;`

작업의 "세부 정보" 타일에 대 한 설명 텍스트입니다.

### <a name="backgroundcolor"></a>backgroundColor
`@property(nonatomic, copy, nullable) SKColor* backgroundColor;`

활동의 타일에 대 한 배경색입니다.

### <a name="attribution"></a>Attribution
`@property(nonatomic, retain, nullable) MCDUserActivityAttribution* attribution;`

작업에 대 한 그래픽 정보입니다.

### <a name="adaptivecardjson"></a>adaptiveCardJson
`@property(nonatomic, copy, nullable) NSString* adaptiveCardJson;`

작업의 "세부 정보" 타일에 대 한 텍스트 콘텐츠입니다.

### <a name="attributiondisplaytext"></a>attributionDisplayText
`@property(nonatomic, copy, nullable) NSString* attributionDisplayText;`

활동 카드의 맨 위 배너에 표시 되는 텍스트입니다.