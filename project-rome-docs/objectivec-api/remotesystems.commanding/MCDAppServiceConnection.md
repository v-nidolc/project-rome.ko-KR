---
title: MCDAppServiceConnection
description: 이 클래스는 특정 원격 앱 서비스에 대 한 연결을 관리합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 22e253f137642ad609a22af33aa62e2ef9543503
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908545"
---
# <a name="class-mcdappserviceconnection"></a>클래스 `MCDAppServiceConnection`

```
@interface MCDAppServiceConnection : NSObject
```
이 클래스는 특정 원격 앱 서비스에 대 한 연결을 관리합니다.

## <a name="properties"></a>속성

### <a name="appserviceinfo"></a>appServiceInfo
`@property(nonatomic, retain, nonnull) MCDAppServiceInfo* appServiceInfo;`

연결할 대상 app service에 대 한 정보를 제공 합니다.

### <a name="requestreceived"></a>requestReceived 
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDAppServiceConnection*, MCDAppServiceRequestReceivedEventArgs*>* requestReceived;`

원격 앱에서 서비스 요청을 수신 되는 경우에 대 한 이벤트입니다.

### <a name="serviceclosed"></a>serviceClosed 
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDAppServiceConnection*, MCDAppServiceClosedEventArgs*>* serviceClosed;`

App service에 대 한 연결을 닫을 때에 대 한 이벤트입니다.

## <a name="constructors"></a>생성자

### <a name="init"></a>Init
`- (nullable instancetype)init;`

페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="returns"></a>반환 값
초기화 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="initwithappserviceinfo"></a>initWithAppServiceInfo
- (nullable instancetype) initWithAppServiceInfo:(nonnull MCDAppServiceInfo*) appServiceInfo;

#### <a name="parameters"></a>매개 변수
* `appServiceInfo` 앱 서비스 설명입니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.

### <a name="appserviceconnectionwithappserviceinfo"></a>appServiceConnectionWithAppServiceInfo
`+ (nullable instancetype)appServiceConnectionWithAppServiceInfo:(nonnull MCDAppServiceInfo*) appServiceInfo;`

만들고 앱 서비스 정보를 사용 하 여이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `appServiceInfo` 

앱 서비스 설명입니다.

#### <a name="returns"></a>반환 값
초기화 반환 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.

## <a name="methods"></a>메서드

### <a name="openremoteasync"></a>openRemoteAsync
`- (void)openRemoteAsync:(nonnull MCDRemoteSystemConnectionRequest*)connectionRequest completion:(nonnull void (^)(MCDAppServiceConnectionStatus, NSError* _Nullable))completion;`

지정 된 원격 장치 또는 응용 프로그램에서 앱 서비스 연결을 엽니다. 연결을 열 수 없으며, 예외가 throw 됩니다.

>**참고:** 이 메서드는 다음 중 하나에 해당할 경우 예외를 throw 합니다.
> * 연결이 이미 열려 있거나를 여는 동안.
> * 앱 서비스 설명을 설정 되지 않은 또는 지웠습니다.
> * 플랫폼 초기화 되지 않았습니다.
> * 앱 메서드는 연결의 "수신한 요청" 이벤트를 구독에 있지만 제공 하지는 **MCDNotificationProvider** 플랫폼을 초기화 하는 경우. 모든 호스팅 시나리오에 필요는 **MCDNotificationProvider**합니다.

#### <a name="parameters"></a>매개 변수
* `connectionRequest` 

원격 시스템 또는 원격 대상 앱을 나타내는 연결 요청입니다.

### <a name="sendmessageasync"></a>sendMessageAsync
`- (void)sendMessageAsync:(nonnull NSDictionary*)message completion:(nonnull void (^)(MCDAppServiceResponse* _Nonnull, NSError* _Nullable))completion;`

원격 앱 서비스에 메시지를 보내고 응답을 수신 대기를 시작 합니다.  이 메서드는 단일 메시지/응답을 수행 하 고 영구 연결을 설정 하지 않습니다.  연결이 성공적으로 열린 후에 호출 합니다.

#### <a name="parameters"></a>매개 변수
* `message` 

App service에 보낼 데이터를 키-값 집합이 있습니다.

### <a name="close"></a>닫기
`- (void)close;`

원격 앱 서비스에 대 한 연결을 닫습니다. 클라이언트 앱이 종료 되거나 사용자 또는 시스템에 의해 중지 될 때마다이 메서드를 호출 해야 합니다.

### <a name="sendstatelessmessageasync"></a>sendStatelessMessageAsync
```
+ (void)sendStatelessMessageAsync:(nonnull NSDictionary*)message
                     toAppService:(nonnull MCDAppServiceInfo*)appServiceInfo
                connectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connectionRequest
                       completion:(nonnull void (^)(MCDStatelessAppServiceResponse* _Nonnull, NSError* _Nullable))completion;
```

지정 된 원격 앱 서비스에 메시지를 보내고 응답을 수신 대기를 시작 합니다.

#### <a name="parameters"></a>매개 변수
* `message` App service에 보낼 데이터를 키-값 집합이 있습니다.
* `appServiceInfo` 대상 app service에 대 한 설명이 포함 된 정보입니다.
* `connectionRequest` 연결 요청 지정 app service에 연결할입니다.
* `completion` 비동기 완료 콜백입니다.