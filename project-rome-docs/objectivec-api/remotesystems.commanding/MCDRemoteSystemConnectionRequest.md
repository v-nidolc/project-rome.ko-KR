---
title: MCDRemoteSystemConnectionRequest
description: 특정 원격 장치 또는 응용 프로그램을 사용 하 여 통신 시도 나타내는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 54ed7deb1fa2b1c87a3195e61c2ce031d6e0cea9
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907135"
---
# <a name="class-mcdremotesystemconnectionrequest"></a>클래스 `MCDRemoteSystemConnectionRequest` 

```
@interface MCDRemoteSystemConnectionRequest : NSObject
```  

특정 원격 장치 또는 응용 프로그램을 사용 하 여 통신 시도 나타내는 클래스입니다.

## <a name="constructors"></a>생성자

### <a name="requestwithremotesystem"></a>requestWithRemoteSystem
`+ (instancetype)requestWithRemoteSystem:(nonnull MCDRemoteSystem*)remoteSystem;`

초기화 된 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 사용 하 여를 [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) 인스턴스. 이 생성자는 앱을 대상으로 지정 하지 않습니다 하 고 시스템으로 전송 하는 서비스 요청에 선택 된 예기치 않은 앱에서 발생할 수 있으므로 권장 되지 않습니다.

#### <a name="parameters"></a>매개 변수
* `remoteSystem` 

원격 시스템에이 연결 요청에서 대상으로 지정 되어야 합니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="requestwithremotesystemapp"></a>requestWithRemoteSystemApp
`+ (instancetype)requestWithRemoteSystemApp:(nonnull MCDRemoteSystemApp*)remoteSystemApp;`

페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `remoteSystemApp` 

이 연결 요청에서 대상으로 할 원격 앱입니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="initwithremotesystem"></a>initWithRemoteSystem
`- (nullable instancetype)initWithRemoteSystem:(nonnull MCDRemoteSystem*)remoteSystem;`

초기화 된 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 사용 하 여를 [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) 인스턴스. 이 생성자는 앱을 대상으로 지정 하지 않습니다 하 고 시스템으로 전송 하는 서비스 요청에 선택 된 예기치 않은 앱에서 발생할 수 있으므로 권장 되지 않습니다.

#### <a name="parameters"></a>매개 변수
* `remoteSystem` 원격 시스템에이 연결 요청에서 대상으로 지정 되어야 합니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="initwithremotesystemapp"></a>initWithRemoteSystemApp
`- (nullable instancetype)initWithRemoteSystemApp:(nonnull MCDRemoteSystemApp*)remoteSystemApp;`

페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `remoteSystemApp` 

이 연결 요청에서 대상으로 할 원격 앱입니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.