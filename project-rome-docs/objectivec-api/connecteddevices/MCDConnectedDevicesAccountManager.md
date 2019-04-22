---
title: MCDConnectedDevicesAccountManager
description: SDK의 모든 계정 관련 기능에 대 한 단일 진입점을 제공합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c265a0c7114704ea6f9ae9818eb9abdb39b5437f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801645"
---
# <a name="class-mcdconnecteddevicesaccountmanager"></a>클래스 `MCDConnectedDevicesAccountManager` 

```
@interface MCDConnectedDevicesAccountManager : NSObject
```  
SDK의 모든 계정 관련 기능에 대 한 단일 진입점을 제공합니다.

## <a name="properties"></a>속성

### <a name="accesstokenrequested"></a>accessTokenRequested
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesAccountManager*, MCDConnectedDevicesAccessTokenRequestedEventArgs*>* accessTokenRequested;`

이 이벤트는 토큰을 요청 해야 하는 경우에 발생 합니다. 이 이벤트를 구독 하 고 모든 요청을 전송 하기 전에 대응할 수 있도록 준비 해야 합니다.

### <a name="accesstokeninvalidated"></a>accessTokenInvalidated
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesAccountManager*, MCDConnectedDevicesAccessTokenInvalidatedEventArgs*>* accessTokenInvalidated;`

이 이벤트는 토큰 소비자 토큰 오류를 보고 하는 경우에 발생 합니다. 토큰 공급자가 토큰 캐시를 새로 고치거 나 해당 계정 설정을 수정 하려면 새 사용자 로그인을 요청 해야 합니다.

### <a name="allaccounts"></a>allAccounts
`@property (nonatomic, readonly, nonnull) NSArray<MCDConnectedDevicesAccount*>* allAccounts;`

현재이 관리자에 의해 추적 되는 모든 MCDConnectedDevicesAccount 합니다.

## <a name="methods"></a>메서드

### <a name="addaccountasync"></a>addAccountAsync
`- (void) addAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account callback:(nonnull void (^)(MCDConnectedDevicesAddAccountResult* _Nonnull, NSError* _Nullable))callback;`

계정에 관리자를 추가, 작업이 완료 될 때 콜백이 호출 됩니다.

#### <a name="parameters"></a>매개 변수 
* `callback`

콜백 결과 계정 추가 성공 인지 인지를 나타냅니다. 

### <a name="removeaccountasync"></a>removeAccountAsync
`- (void) removeAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account callback:(nonnull void (^)(MCDConnectedDevicesRemoveAccountResult* _Nonnull, NSError* _Nullable))callback;`

계정 관리자에서 계정 제거, 작업이 완료 될 때 콜백이 호출 됩니다.

#### <a name="parameters"></a>매개 변수 
* `callback` 

 콜백 결과 계정 제거 성공 인지 인지를 나타냅니다. 