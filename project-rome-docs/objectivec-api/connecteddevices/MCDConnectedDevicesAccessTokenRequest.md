---
title: MCDConnectedDevicesAccessTokenRequest
description: 포함 된 범위를 충족 하는 포함 된 MCDConnectedDevicesAccount에 대 한 액세스 토큰에 대 한 요청입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b1cd9b747e98d5e9ccf4885b33897e8c240d7673
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800835"
---
# <a name="class-mcdconnecteddevicesaccesstokenrequest"></a>클래스 `MCDConnectedDevicesAccessTokenRequest` 

```
@interface MCDConnectedDevicesAccessTokenRequest : NSObject
```  
포함 된 범위를 충족 하는 포함 된 MCDConnectedDevicesAccount에 대 한 액세스 토큰에 대 한 요청입니다.

## <a name="properties"></a>속성

### <a name="account"></a>계정으로 이동하면
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

이 MCDConnectedDevicesAccessTokenInvalidatedEventArgs와 연결 된 계정입니다.

### <a name="scopes"></a>범위
`@property (nonatomic, readonly, nonnull) NSArray<NSString*>* scopes;`

목록 범위를 생성 하는 경우 토큰 포함 해야 합니다.

## <a name="methods"></a>메서드

### <a name="completewithaccesstoken"></a>completeWithAccessToken
`- (void) completeWithAccessToken:(NSString* _Nonnull) token;`

요청 된 범위를 사용 하 여 토큰을 생성 하는 경우 요청을 완료 하려면 토큰을 사용 하 여이 메서드를 호출 합니다.

#### <a name="parameters"></a>매개 변수 
* `token` 

성공적으로 생성 된 토큰

### <a name="completewitherrormessage"></a>completeWithErrorMessage
`- (void) completeWithErrorMessage:(NSString* _Nullable) errorMessage;`

어떤 이유로 든 요청 된 범위를 사용 하 여 토큰을 성공적으로 생성 되지 않은 경우 로깅에 사용 되는 메시지를 사용 하 여이 메서드를 호출 합니다.

#### <a name="parameters"></a>매개 변수 
* `errorMessage`

토큰에 성공 하지 못한 이유에 설명 하는 메시지입니다.