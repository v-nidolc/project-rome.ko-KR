---
title: MCDRemoteSystem
description: 원격 시스템을 나타내기 위해 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5f0ab2108d4efa486b992bf7bc8c8847692623da
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909265"
---
# <a name="class-mcdremotesystem"></a>클래스 `MCDRemoteSystem` 

```
@interface MCDRemoteSystem : NSObject
```  

원격 시스템을 나타내기 위해 사용 되는 클래스입니다.

## <a name="properties"></a>속성

### <a name="kind"></a>kind
`@property(nonatomic, readonly, nonnull) NSString* kind;`

장치 유형 원격이 시스템입니다.

### <a name="systemid"></a>systemId
`@property(nonatomic, readonly, nonnull) NSString* systemId;`

이 원격 시스템에 대 한 식별자입니다.

### <a name="displayname"></a>displayName
`@property(nonatomic, readonly, nonnull) NSString* displayName;`

지정된 된 원격 시스템의 이름입니다.

### <a name="status"></a>상태
`@property(nonatomic, readonly) MCDRemoteSystemStatus status;`

이 원격 시스템의 가용성 상태입니다.

> [!NOTE]
WNS 존재 WNS 알림 유형으로 사용 하는 앱 및 Windows 장치에 대 한 가용성을 보고에 사용 됩니다.  RemoteSystem 때나 해당 현재 상태를 보고 기본 앱 중 장치 (Windows)를 사용할 수 있는 것으로 간주 됩니다 때 "사용 가능"으로 표시 됩니다으로 사용할 수 있습니다 (iOS 및 Android). 

### <a name="manufacturerdisplayname"></a>manufacturerDisplayName
`@property(nonatomic, readonly, nonnull) NSString* manufacturerDisplayName;`

지정된 된 원격 시스템의 제조업체 이름입니다.

### <a name="modeldisplayname"></a>modelDisplayName
`@property(nonatomic, readonly, nonnull) NSString* modelDisplayName;`

지정된 된 원격 시스템의 모델 이름입니다.

### <a name="apps"></a>앱 검색
`@property(nonatomic, readonly, nonnull) NSArray<MCDRemoteSystemApp*>* apps;`

연결에 사용할 수 있는이 원격 시스템에서 응용 프로그램의 배열입니다.

### <a name="platform"></a>플랫폼
`@property(nonatomic, readonly) MCDRemoteSystemPlatform platform;`

MCDRemoteSystemPlatform 원격 시스템 작업을 관리 합니다.