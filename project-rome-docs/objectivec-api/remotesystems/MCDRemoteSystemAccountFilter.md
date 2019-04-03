---
title: MCDRemoteSystemAccountFilter
description: 사용 하 여 원격 시스템 검색 계정에 대 한 필터입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 34721c2dee89adc380b721a027382f81c2ecb751
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907325"
---
# <a name="class-mcdremotesystemaccountfilter"></a>클래스 `MCDRemoteSystemAccountFilter` 

```
@interface MCDRemoteSystemAccountFilter : NSObject<MCDRemoteSystemFilter>
```  

사용 하 여 원격 시스템 검색 계정에 대 한 필터입니다.

## <a name="properties"></a>속성

### <a name="account"></a>계정으로 이동하면
`@property(nonatomic, readonly, strong, nonnull) MCDConnectedDevicesAccount* account;`

이 MCDRemoteSystemAccountFilter와 연결 된 계정입니다.

## <a name="constructors"></a>생성자

### <a name="filterwithaccount"></a>filterWithAccount
`+ (nullable instancetype)filterWithAccount:(nonnull MCDConnectedDevicesAccount*)account;`

MCDConnectedDevicesAccount 계정 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `account` 

사용 중인 MCDConnectedDevicesAccount 계정입니다.

#### <a name="returns"></a>반환 값
계정을 사용 하 여 필터링 MCDRemoteSystemAccountFilter 개체를 반환 합니다.

### <a name="initwithaccount"></a>initWithAccount
`- (nullable instancetype)initWithAccount:(nonnull MCDConnectedDevicesAccount*)account;`

MCDConnectedDevicesAccount 계정 사용 하 여 클래스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수 
* `account` 

사용 중인 MCDConnectedDevicesAccount 계정입니다.

#### <a name="returns"></a>반환 값
반환 MCDRemoteSystemAccountFilter 개체 초기화 계정을 사용 하 여 필터링 합니다.