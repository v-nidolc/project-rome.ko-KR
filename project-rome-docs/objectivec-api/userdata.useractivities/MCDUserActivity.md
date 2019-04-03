---
title: MCDUserActivity
description: 이 클래스는 단일 사용자 활동 인스턴스를 나타냅니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: f01889f5e41c761fe359ed1fa90befee4a8aca46
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907425"
---
# <a name="class-mcduseractivity"></a>클래스 `MCDUserActivity`

```
@interface MCDUserActivity : NSObject
```

이 클래스는 단일 사용자 활동 인스턴스를 나타냅니다. 사용자 작업을 동일한 장치에 다른 시간에 또는 다른 장치에서 계속 될 수 있는 사용자 작업 스트림의 시스템에 알리기 위해 실행 하는 동안 앱에서 생성 됩니다. 사용자에 참여 하는 작업에 대 한 정보를 제공 합니다.

>**참고:** MCDUserActivity 인스턴스는 크기 제한이 100kb, 기준이 되는 게시할 수 없습니다.

## <a name="properties"></a>속성

### <a name="activityid"></a>activityId
`@property(nonatomic, readonly, nonnull) NSString* activityId;`

이 작업에 대 한 고유 ID입니다.

### <a name="state"></a>state
`@property(nonatomic, readonly) MCDUserActivityState state;`

이 작업의 상태입니다.

### <a name="activationuri"></a>activationUri
`@property(nonatomic, copy, nonnull) NSString* activationUri;`

이 사용자 활동이 활성화 될 때 이동할 URI입니다.

### <a name="fallbackuri"></a>fallbackUri
`@property(nonatomic, copy, nullable) NSString* fallbackUri;`

웹용 URI이이 작업을 소유 기본 URI에 실패 하는 경우에 사용 합니다.

### <a name="contenturi"></a>contentUri
`@property(nonatomic, copy, nullable) NSString* contentUri;`

이 작업 (다른 장치에서 작업을 나타내는 데 사용할 이미지의 URI)에 대 한 콘텐츠 URI입니다.

### <a name="contenttype"></a>contentType
`@property(nonatomic, copy, nullable) NSString* contentType;`

MIME (Multipurpose Internet Mail Extensions) 형식에 저장 된 콘텐츠의 **contentUri**합니다. 예를 들어, "텍스트/plain"입니다.

### <a name="contentinfojson"></a>contentInfoJson
`@property(nonatomic, copy, nullable) NSString* contentInfoJson;`

이 작업에 대 한 기본 콘텐츠 정보입니다. 예를 들어, 활동이 RSS 피드를 읽고, 콘텐츠 문자열에 문서 및 해당 작성자의 이름을 포함할 수 있습니다.

### <a name="appdisplayname"></a>appDisplayName
`@property(nonatomic, readonly, nullable) NSString* appDisplayName;`

이 작업에 대 한 앱 표시 이름입니다.

### <a name="visualelements"></a>VisualElements
`@property(nonatomic, retain, nonnull) MCDUserActivityVisualElements* visualElements`

이 활동 (활동의 "세부 정보" 타일에 대해 사용할 수 있는 정보)에 대 한 시각적 요소입니다.

### <a name="roamable"></a>있는 로밍 가능한
`@property(nonatomic, assign, getter = isRoamable) BOOL roamable;`

이 작업은 다른 끝점에 로밍 여부를 나타내는 값을 가져오거나 설정 합니다.

## <a name="constructors"></a>생성자

### <a name="activitywithactivityid"></a>activityWithActivityId
`+ (nullable instancetype)activityWithActivityId:(nonnull NSString*)activityId;`

지정 된 ID를 사용 하 여이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `activityId` 

(고유한 문자열 이어야 함)이이 작업에 대 한 식별자입니다.

#### <a name="returns"></a>반환 값
이 클래스의 인스턴스를 반환 합니다.

### <a name="initwithactivityid"></a>initWithActivityId
`- (nullable instancetype)initWithActivityId:(nonnull NSString*)activityId;`

지정 된 ID를 사용 하 여이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `activityId`

(고유한 문자열 이어야 함)이이 작업에 대 한 식별자입니다.

#### <a name="returns"></a>반환 값
이 클래스의 인스턴스를 반환 합니다.

## <a name="methods"></a>메서드

### <a name="createsession"></a>createSession
`- (nonnull MCDUserActivitySession*)createSession;`

이 MCDUserActivity와 연결 된 사용자 활동 세션을 만듭니다. 연결된 MCDUserActivitySession는 사용자는 현재 활동에 포함 됩니다 것을 나타냅니다.

#### <a name="returns"></a>반환 값
만든된 세션입니다.

### <a name="saveasync"></a>saveAsync
`- (void)saveAsync:(nonnull void (^)(NSError* _Nullable))completionBlock;`

사용자 활동을 게시합니다. MCDUserActivity이이 메서드가 호출 되기 전에 활성화 하는 URI 및 텍스트를 표시 하는 집합을 사용 하 여 VisualElements 멤버인 있어야 합니다. 앱 (하기 위해 업데이트를 게시)를 MCDUserActivity의 속성을 수정 될 때마다이 메서드를 호출 해야 합니다.

#### <a name="parameters"></a>매개 변수
* `completionBlock` 완료 될 때 실행할 코드 블록입니다.