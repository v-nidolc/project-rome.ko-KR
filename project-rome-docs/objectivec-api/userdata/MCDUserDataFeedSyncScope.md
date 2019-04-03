---
title: MCDUserDataFeedSyncScope
description: 이 클래스에는 앱에서 특정 사용자별 연결 된 장치 기능을 사용 하는 경우 연결 된 장치 플랫폼 백 엔드와 동기화 되는 사용자 데이터를 나타냅니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 941381a61c9b17c837c25b089f7c7073d581c4a8
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907175"
---
# <a name="class-mcduserdatafeedsyncscope"></a>클래스 `MCDUserDataFeedSyncScope`

```
@interface MCDUserDataFeedSyncScope : NSObject
```
 이 인터페이스에는 앱은 사용자 활동 등의 특정 사용자 고유의 연결 된 장치 기능을 사용 하는 경우 연결 된 장치 플랫폼 백 엔드와 동기화 되는 사용자 데이터를 나타냅니다. 인스턴스는 이러한 기능을 관리 하는 클래스에서 정적으로 검색 됩니다 (예: **MCDUserActivityChannel**)를 생성에 사용 됩니다 **MCDUserDataFeed**합니다.

## <a name="properties"></a>속성

### <a name="platform"></a>플랫폼
`@property (nonatomic, readwrite, nullable, copy) NSString* platform;`

합니다 **ConnectedDevicesPlatform** 이 앱의 연결 된 장치 기능에 대 한 초기화 된 인스턴스.

### <a name="syncscopeflags"></a>syncScopeFlags
`@property (nonatomic, readwrite, nullable, copy) NSArray<NSString*>* syncScopeFlags;`

들어오는 활동을 필터링 하는 것에 대 한 선택적 플래그를 설정 합니다.

### <a name="notificationtype"></a>notificationType
`@property (nonatomic, readwrite, nullable, copy) NSString* notificationType;`

변경 알림 유형의 받을 사용자 피드는 데이터 동기화 범위에 대 한 형식 설정

```