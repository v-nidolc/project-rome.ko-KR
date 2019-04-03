---
title: MCDConnectedDevicesAccount
description: 이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: e9b43bb76e46f3a027247b1d4d564c6e1571bae4
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909155"
---
# <a name="class-mcdconnecteddevicesaccount"></a>클래스 `MCDConnectedDevicesAccount`

```
@interface MCDConnectedDevicesAccount : NSObject
```  

이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.

## <a name="properties"></a>속성

### <a name="anonymousaccount"></a>anonymousAccount
`+ (nullable instancetype)anonymousAccount;`

익명 계정의 singleton 인스턴스입니다.

### <a name="accountid"></a>accountId
`@property(nonatomic, readonly, copy, nonnull) NSString* accountId;`

이 사용자 계정에 대 한 고유 식별자입니다.

### <a name="type"></a>유형
`@property(nonatomic, readonly) MCDConnectedDevicesAccountType type;`

계정 유형을 설명 하는 MCDConnectedDevicesAccountType 값입니다.

## <a name="constructors"></a>생성자

### <a name="accountwithaccountid"></a>accountWithAccountId
`+ (nullable instancetype)accountWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 

* `accountId` 

이 사용자 계정에 대 한 고유 식별자 문자열입니다.

`type` 

계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).

#### <a name="returns"></a>반환 값
계정 id 사용 하 여 MCDConnectedDevicesAccount 개체를 반환합니다.

### <a name="initwithaccountid"></a>initWithAccountId
`- (nullable instancetype)initWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `type`

계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).

#### <a name="returns"></a>반환 값
계정 id를 사용 하 여 초기화 MCDConnectedDevicesAccount 개체를 반환 합니다.