---
title: MCDLaunchUriProvider
description: ''
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4cbfaa9fd1e88345f4ce35987508b061e479854e
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907465"
---
# <a name="protocol-mcdlaunchuriprovider"></a>protocol `MCDLaunchUriProvider`

```
@protocol MCDLaunchUriProvider <NSObject>
```

이 클래스를 통해 응용 프로그램을 실행 하는 URI의 처리를 관리 합니다.

## <a name="properties"></a>속성 
### <a name="supportedurischemes"></a>supportedUriSchemes
`@property(nonatomic, readonly, strong, nullable) NSArray<NSString*>* supportedUriSchemes;`

지원 되는 URI 스키마를 나타내는 문자열 배열입니다.

## <a name="methods"></a>메서드

### <a name="onlaunchuriasync"></a>onLaunchUriAsync
```
- (void)onLaunchUriAsync:(nonnull NSString*)uri
         options:(nullable MCDRemoteLauncherOptions*)options
              completion:(nonnull void (^)(BOOL, NSError* _Nullable))completionBlock;
```

이 메서드는 원격 장치에서이 장치에서 URI를 시작 하려고 할 때 호출 됩니다.

#### <a name="parameters"></a>매개 변수 
* `uri` 시작 URI입니다.
* `options` 집합 URI를 실행 하기 위한 옵션입니다. 대체 URI는 설정할 수 있는 가능한 옵션 중 하나만 있습니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다.