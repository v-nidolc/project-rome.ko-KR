---
title: MCDUserDataFeed
description: 이 클래스는 연결 된 장치 플랫폼 백 엔드를 사용 하 여 사용자 고유의 데이터를 동기화 하는 일을 담당 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 66898563bdad8adb2f1ebfe75f010cd5ef1d9ca2
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58908995"
---
# <a name="class-mcduserdatafeed"></a>클래스 `MCDUserDataFeed`

```
@interface MCDUserDataFeed : NSObject
```

이 클래스는 연결 된 장치 플랫폼 백 엔드를 사용 하 여 사용자 고유의 데이터를 동기화 하는 일을 담당 합니다. 동기화 되는 데이터는 종속 **[MCDUserDataFeedSyncScope](MCDUserDataFeedSyncScope.md)** 인스턴스 포함 되어 있습니다.

## <a name="properties"></a>속성

### <a name="syncstatus"></a>syncStatus
`@property(nonatomic, readonly) MCDUserDataSyncStatus syncStatus;`

사용자 데이터 동기화의 현재 상태를 설명합니다.

### <a name="syncstatuschanged"></a>syncStatusChanged
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDUserDataFeed*, MCDUserDataFeedSyncStatusChangedEventArgs*>* syncStatusChanged;`

UserDataFeed의 동기화 상태를 변경 하는 경우에 대 한 이벤트입니다.

### <a name="daystosync"></a>daysToSync
`@property(nonatomic, readwrite) NSInteger daysToSync;`

30 개 미만인 해야 하는 데이터 동기화의 일 수입니다.  서버에 의해 결정 됩니다는 기본값을 나타냅니다.

## <a name="constructors"></a>생성자

### <a name="getforaccount"></a>getForAccount
`+ (nullable instancetype)getForAccount:(nonnull MCDConnectedDevicesAccount*)userAccount
                                   platform:(nonnull MCDConnectedDevicesPlatform*)platform
                         activitySourceHost:(nonnull NSString*)activitySourceHost;`

만들고 사용자 계정, 플랫폼 인스턴스 및 플랫폼 간 앱 ID를 사용 하 여이 클래스의 새 인스턴스를 초기화 합니다.

#### <a name="parameters"></a>매개 변수
* `userAccount` 

이 데이터와 연결 된 사용자 계정입니다.

* `platform` 

합니다 **MCDPlatform** 이 앱의 연결 된 장치 기능에 대 한 초기화 된 인스턴스.

* `activitySourceHost` 

플랫폼 간 앱 id입니다. 이 Microsoft 개발자 대시보드 등록을 통해 검색 됩니다.

#### <a name="returns"></a>반환 값
이 클래스의 인스턴스를 반환 합니다.

## <a name="methods"></a>메서드

### <a name="subscribetosyncscopesasync"></a>subscribeToSyncScopesAsync
`- (void)subscribeToSyncScopesAsync:(NSArray<MCDUserDataFeedSyncScope*>* _Nonnull) syncScopes callback:(nonnull void (^)(BOOL, NSError* _Nullable)) callback;`

추가 **MCDUserDataFeedSyncScope** 이 MCDUserDataFeed 인스턴스.  이 MCDUserDataFeed에 따라 동기화 되는 **MCDUserDataFeedSyncScope** 지정 된 인스턴스.

#### <a name="parameters"></a>매개 변수

* `syncScopes` 배열을 **MCDSyncScope** 인스턴스.

* `callback`

콜백 결과 구독 인지 성공 여부를 나타냅니다. 

### <a name="startsync"></a>startSync
`- (void)startSync;`

연결 된 장치 플랫폼을 사용 하 여 동기화 프로세스를 시작합니다. 이 작업을이 수행 하는 동안 합니다 **syncStatus** 속성은 업데이트 되 고 변경 이벤트가 발생 합니다.