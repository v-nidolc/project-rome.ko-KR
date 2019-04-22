---
title: MCDRemoteLauncher
description: URI를 사용 하 여 원격 장치에 앱을 실행 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: aa0211c1edc33e8a277c4954d94fbcbb6565c923
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907385"
---
# <a name="class-mcdremotelauncher"></a>클래스 `MCDRemoteLauncher` 

```
@interface MCDRemoteLauncher : NSObject
```  

URI를 사용 하 여 원격 장치에 앱을 실행 하는 데 사용 되는 클래스입니다.


## <a name="methods"></a>메서드

### <a name="launchuriasync"></a>launchUriAsync
```
- (void)launchUriAsync:(nonnull NSString*)uri
 withConnectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connection
            completion:(nullable void (^)(MCDRemoteLaunchUriStatus result, NSError* _Nullable error))completionBlock;
```

시작에 지정 된 원격 시스템에 대 한 URI를 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md)합니다.

#### <a name="parameters"></a>매개 변수
* `uri` 앱을 실행 하는 발생할 수 있는 URI입니다.  대상 Windows를 대상 앱 구성표에 따라 선택 됩니다. 대상이 아닌 Windows를 대상 응용 프로그램을 MCDRemoteSystemConnectionRequest에 따라 선택 됩니다.

* `connection` 원격 시스템 또는 응용 프로그램에 연결을 지정 합니다.
* `completionBlock` 블록 완료 시 호출입니다.

### <a name="launchuriasync"></a>launchUriAsync
```
- (void)launchUriAsync:(nonnull NSString*)uri
 withConnectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connection
               options:(nullable MCDRemoteLauncherOptions*)options
            completion:(nullable void (^)(MCDRemoteLaunchUriStatus result, NSError* _Nullable error))completionBlock;
```

시작 옵션에 지정 된 원격 시스템에 대 한 URI를 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md)합니다.

#### <a name="parameters"></a>매개 변수
* `uri` 해당 스키마에 따라 앱을 실행 하는 발생할 수 있는 URI입니다.
* `connection` 원격 시스템 또는 응용 프로그램에 연결을 지정 합니다.
* `options` 앱에 대 한 시작 사양입니다.
* `completionBlock` 블록 완료 시 호출입니다.