---
title: MCDConnectedDevicesAccessTokenInvalidatedEventArgs
description: ConnectedDevicesAccount와 연결 된 해당 토큰을 토큰 오류를 보고 알립니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 46a21b534e2b3a5fb588e40af2dbc4eb47143873
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801775"
---
# <a name="class-mcdconnecteddevicesaccesstokeninvalidatedeventargs"></a>클래스 `MCDConnectedDevicesAccessTokenInvalidatedEventArgs` 

```
@interface MCDConnectedDevicesAccessTokenInvalidatedEventArgs : NSObject 
```  
MCDConnectedDevicesAccount MCDConnectedDevicesAccount 연관 된 토큰에 포함 된 범위에 대 한 토큰 오류 보고는를 반환 합니다. 토큰 공급자가 토큰 캐시를 새로 고치거 나 잠재적으로 사용자에 게 자신의 계정 설정을 수정 하려면 로그인을 요청 하는 UI를 팝업에 필요 합니다.

## <a name="properties"></a>속성

### <a name="account"></a>계정으로 이동하면
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

이 MCDConnectedDevicesAccessTokenInvalidatedEventArgs와 연결 된 계정입니다.

### <a name="scopes"></a>범위
`@property (nonatomic, readonly, nonnull) NSArray<NSString*>* scopes;`

목록 범위를 생성 하는 경우 토큰 포함 해야 합니다.