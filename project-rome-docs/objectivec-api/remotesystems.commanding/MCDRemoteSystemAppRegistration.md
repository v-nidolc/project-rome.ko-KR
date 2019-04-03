---
title: MCDRemoteSystemAppRegistration
description: 이 클래스는 연결 된 장치 플랫폼에 등록 해야 하는 응용 프로그램을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2c931d3eeacd4aa48e1ef22d573bf0325eb5b98b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909915"
---
# <a name="class-mcdremotesystemappregistration"></a>클래스 `MCDRemoteSystemAppRegistration` 

```
@interface MCDRemoteSystemAppRegistration : NSObject
```  

이 클래스는 모든 다른 검색 하 고 사용할 수 있는이 앱에 대 한 정보를 포함 합니다.

> [!NOTE] 
> 다른 앱으로 보내는 모든 통신은 possble MCDRemoteSystemAppRegistration 정보 게시 해야 합니다. 이 경우 다른 응용 프로그램을 알 수 있도록 해당 통신에 응답 하는 방법

## <a name="properties"></a>속성

### <a name="account"></a>계정으로 이동하면
`@property(nonatomic, readonly, nullable) MCDConnectedDevicesAccount* account;`

이 등록 속해 있는 계정입니다.

### <a name="attributes"></a>특성
`@property(nonatomic, copy, nullable) NSDictionary<NSString*, NSString*>* attributes;`

 이 앱의 특성을 설명 하는 문자열의 사전입니다.

### <a name="appserviceproviders"></a>appServiceProviders
`@property(nonatomic, copy, nullable) NSArray<id<MCDAppServiceProvider>>* appServiceProviders;`

이 앱을 지 원하는 AppServiceProviders의 배열입니다.

> [!NOTE] 
> App service 공급자는 들어오는 연결을 수신 하려면이 배열에 있는 여야 합니다.  MCDRemoteSystemAppRegistration.publishAsync() 요청을 수신 하도록 app service 공급자에 대해 호출할 필요가 없습니다.  

### <a name="launchuriprovider"></a>launchUriProvider
`@property(nonatomic, readwrite, nullable) id<MCDLaunchUriProvider> launchUriProvider;`

이 앱에 대 한 Uri 공급자를 시작 합니다.

> [!NOTE] 
> 시작 uri 공급자는 들어오는 요청을 수신 하기 위해이 속성에 저장 되어야 합니다.  MCDRemoteSystemAppRegistration.publishAsync() 요청을 수신 하도록 app service 공급자에 대해 호출할 필요가 없습니다.  

## <a name="constructors"></a>생성자

### <a name="getforaccount"></a>getForAccount
`+(nullable instancetype) getForAccount:(MCDConnectedDevicesAccount* _Nonnull) account
                              platform:(MCDConnectedDevicesPlatform* _Nonnull) platform;`

계정의 현재 원격 시스템 앱 등록을 가져옵니다.

#### <a name="parameters"></a>매개 변수
* `account` 

에 대 한 등록을 검색 하는 계정입니다.

* `platform` 

등록을 가져올 플랫폼입니다.

#### <a name="returns"></a>반환 값
제공 된 계정에 대 한 MCDRemoteSystemAppRegistration 개체를 반환합니다.

## <a name="methods"></a>메서드

### <a name="saveasync"></a>saveAsync
`- (void)saveAsync:(nonnull void (^)(BOOL, NSError* _Nullable))callback  __attribute__((deprecated("Use publishAsync instead")));`

현재 저장 된 정보는 RemoteSystemAppRegistration 다른 응용 프로그램에서 검색할 수 있도록 저장 합니다.

> [!NOTE] 
> MCDConnectedDevicesNotificationRegistration 되려면이 호출에 대 한 등록 되어야 합니다.

> [!WARNING] 
> 사용되지 않습니다. PublishAsync를 대신 사용 합니다.

#### <a name="parameters"></a>매개 변수

* `callback`

콜백 정보를 저장 하는 결과 나타냅니다.

### <a name="publishasync"></a>publishAsync
`- (void)publishAsync:(nonnull void (^)(MCDRemoteSystemAppRegistrationPublishResult* _Nonnull, NSError* _Nullable))completionBlock;`

현재 저장 된 정보는 MCDRemoteSystemAppRegistration 다른 응용 프로그램에서 검색할 수 있도록 게시 합니다.

> [!NOTE] 
> MCDConnectedDevicesNotificationRegistration 되려면이 호출에 대 한 등록 되어야 합니다.

#### <a name="parameters"></a>매개 변수

* `callback`

콜백 정보를 저장 하는 결과 나타냅니다.
