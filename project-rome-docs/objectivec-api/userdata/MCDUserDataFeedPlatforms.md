---
title: MCDUserDataFeedPlatforms
description: MCDUserDataFeedSyncScope에 대 한 올바른 플랫폼을 제공합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 7474c5896fec97a94799423ba0748bd2814d2c7a
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907195"
---
# <a name="class-mcduserdatafeedplatforms"></a>클래스 `MCDUserDataFeedPlatforms`

```
@interface MCDUserDataFeedPlatforms : NSObject

This class is responsible for providing the valid platform for the MCDUserDataFeedSyncScope.
```

## <a name="properties"></a>속성

### <a name="all"></a>모든
`@property(class, nonatomic, readonly, nonnull) NSString* all;`

플랫폼의 모든 개체

### <a name="android"></a>android
`@property(class, nonatomic, readonly, nonnull) NSString* android;`

Android 플랫폼 개체입니다.

### <a name="ios"></a>iOS
`@property(class, nonatomic, readonly, nonnull) NSString* iOS;`

iOS 플랫폼 개체입니다.

### <a name="windowsuwp"></a>windowsUWP
`@property(class, nonatomic, readonly, nonnull) NSString* windowsUWP;`

UWP 플랫폼 개체입니다.

### <a name="windows32"></a>windows32
`@property(class, nonatomic, readonly, nonnull) NSString* windows32;`

Windows32 플랫폼 개체입니다.

### <a name="linux"></a>linux
`@property(class, nonatomic, readonly, nonnull) NSString* linux;`

Linux 플랫폼 개체입니다.