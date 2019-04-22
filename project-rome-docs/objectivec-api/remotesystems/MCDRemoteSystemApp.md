---
title: MCDRemoteSystemApp
description: 연결에 사용할 수 있는 원격 시스템에서 응용 프로그램을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 28ec3fbe03150cb45c0a554a0499f1a6b657e50d
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801585"
---
# <a name="class-mcdremotesystemapp"></a>클래스 `MCDRemoteSystemApp` 

```
@interface MCDRemoteSystemApp : NSObject
```  

연결에 사용할 수 있는 원격 시스템에서 응용 프로그램을 나타냅니다.

## <a name="properties"></a>속성

### <a name="appid"></a>appId
`@property(nonatomic, readonly, nonnull) NSString* appId;`

이 응용 프로그램에 대 한 고유 식별자입니다.

### <a name="displayname"></a>displayName
`@property(nonatomic, readonly, nonnull) NSString* displayName;`

이 응용 프로그램에 대 한 친숙 한 표시 이름입니다. Bluetooth id에 대 한 장치에서 사용 하는 이름입니다. 이 설정 되지 않은 장치에서 Bluetooth를 지원 하지 않습니다, 경우이 필드는 비어 있게 됩니다.

### <a name="availablebyproximity"></a>availableByProximity
`@property(nonatomic, readonly, getter=isAvailableByProximity) BOOL availableByProximity;`

이 응용 프로그램은 현재 proximal 연결에 사용할 수 있는지 여부를 나타냅니다.

### <a name="availablebyspatialproximity"></a>availableBySpatialProximity
`@property(nonatomic, readonly, getter=isAvailableBySpatialProximity) BOOL availableBySpatialProximity;`

이 응용 프로그램은 공간 공유 연결에 대 한 현재 사용할 수 있는지 여부를 나타냅니다.

### <a name="attributes"></a>특성
`@property(nonatomic, readonly, nonnull) NSDictionary<NSString*, NSString*>* attributes;`

이 응용 프로그램의 특성을 정의 하는 키/값 쌍의 사전입니다.

### <a name="appservices"></a>appServices
`@property(nonatomic, readonly, nullable) NSArray<MCDAppServiceDescription*>* appServices;`

이 응용 프로그램 원격 연결을 위해 제공 되는 앱 서비스를 설명 하는 MCDAppServiceDescription 인스턴스의 배열입니다.

### <a name="accounts"></a>계정
`@property(nonatomic, readonly, nullable) NSArray<MCDConnectedDevicesAccount*>* accounts;`

에 대해 알아야 할 권한이 있는 MCDRemoteSystemApp와 연결 된 계정입니다. MCDRemoteSystemWatcher 시작 될 때를 MCDConnectedDevicesAccount는 MCDConnectedDevicesAccountManager에 있는지는 사용 권한을 결정 합니다.