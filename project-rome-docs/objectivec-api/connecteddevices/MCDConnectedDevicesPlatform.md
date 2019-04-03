---
title: MCDConnectedDevicesPlatform
description: 연결 된 장치 플랫폼을 나타내고 앱의 연결을 관리 하는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 33fdb6f7dfd7d11831da1f7710215e35306d79d1
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909745"
---
# <a name="class-mcdconnecteddevicesplatform"></a>클래스 `MCDConnectedDevicesPlatform` 

```
@interface MCDConnectedDevicesPlatform : NSObject
```  
이 클래스는 연결 된 장치 플랫폼을 나타내고 앱의 연결을 관리입니다.

## <a name="properties"></a>속성

### <a name="accountmanager"></a>accountManager
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccountManager* accountManager;`

플랫폼에서 보유 하 고 있는 MCDConnectedDevicesAccountManager 인스턴스.

### <a name="notificationregistrationmanager"></a>notificationRegistrationManager
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesNotificationRegistrationManager* notificationRegistrationManager;`

플랫폼에서 보유 MCDConnectedDevicesNotificationRegistrationManager 인스턴스입니다.

## <a name="constructors"></a>생성자

### <a name="platformwithsettings"></a>platformWithSettings
`+ (nullable instancetype)platformWithSettings:(MCDConnectedDevicesPlatformSettings* _Nonnull)settings;`

지정 된 플랫폼 설정 사용 하 여이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `settings` 

플랫폼의 응용 프로그램의 설정을 저장 하는 MCDConnectedDevicesPlatformSettings 개체입니다.

#### <a name="returns"></a>반환 값

앱의 플랫폼 설정을 포함 하는 MCDConnectedDevicesPlatform 개체를 반환 합니다.

### <a name="initwithsettings"></a>initWithSettings
`- (nullable instancetype)initWithSettings:(MCDConnectedDevicesPlatformSettings* _Nonnull)settings;`

플랫폼 설정 사용 하 여이 클래스의 새 인스턴스.

#### <a name="parameters"></a>매개 변수 
* `settings` 

플랫폼의 응용 프로그램의 설정을 저장 하는 MCDConnectedDevicesPlatformSettings 개체입니다.

#### <a name="returns"></a>반환 값

앱의 플랫폼 설정으로 초기화 하는 MCDConnectedDevicesPlatform 개체를 반환 합니다.

## <a name="methods"></a>메서드

### <a name="processnotification"></a>processNotification
`- (MCDConnectedDevicesProcessNotificationOperation* _Nonnull)processNotification:(NSDictionary* _Nonnull)notification;`

들어오는 APNs 알림을 처리 합니다.

#### <a name="parameters"></a>매개 변수 
* `notification` 

APNs 알림 처리를 포함 합니다.

#### <a name="returns"></a>반환 값

MCDConnectedDevicesProcessNotificationOperation 클래스의 인스턴스입니다.

### <a name="start"></a>start
`- (void) start;`

플랫폼을 시작 합니다.

### <a name="shutdownasync"></a>shutdownAsync
`- (void)shutdownAsync:(void (^_Nonnull)(NSError* _Nullable))completionBlock;`

연결 된 장치 플랫폼을 종료합니다.

#### <a name="parameters"></a>매개 변수 
* `completionBlock` 

블록 완료 시 호출입니다.