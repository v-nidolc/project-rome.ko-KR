---
title: MCDRemoteSystemWatcher
description: 원격 시스템을 검색 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 88bb52465de165224c62270e0630dfb72f47b31f
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908835"
---
# <a name="class-mcdremotesystemwatcher"></a>클래스 `MCDRemoteSystemWatcher`

```
@interface MCDRemoteSystemWatcher : NSObject
```

원격 시스템을 검색 하는 데 사용 되는 클래스입니다. 

## <a name="properties"></a>속성

### <a name="remotesystemadded"></a>remoteSystemAdded
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemAddedEventArgs*>* remoteSystemAdded;`

새 원격 시스템은 검색 하는 경우에 대 한 이벤트입니다.

### <a name="remotesystemupdated"></a>remoteSystemUpdated
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemUpdatedEventArgs*>* remoteSystemUpdated;`

이 검색 세션에서 이전에 검색 된 원격 시스템 proximally 연결에 연결 하는 클라우드 또는 그 반대로 변경 하는 경우에 대 한 이벤트입니다. 

### <a name="remotesystemremoved"></a>remoteSystemRemoved
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemRemovedEventArgs*>* remoteSystemRemoved;`

원격 시스템을 제거한 경우에 대 한 이벤트입니다. 

### <a name="enumerationcompleted"></a>enumerationCompleted
' '@property(비 원자성을 읽기 전용, null이 아닌) MCDEvent < MCDRemoteSystemWatcher *, MCDRemoteSystemEnumerationCompletedEventArgs*> * enumerationCompleted;
```

Event for when the initial discovery of currently-discoverable devices has finished.  The discovery process will continue to run and will raise additional events if the set of existing remote systems changes.

### errorOccurred
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemWatcherErrorOccurredEventArgs*>* errorOccurred;`

Event for when an error occurs during discovery. The discovery process will continue if possible. For example, if the error
occurs with a value of **MCDRemoteSystemWatcherError.MCDRemoteSystemWatcherErrorInternetNotAvailable**, proximal discovery
may continue because the error applies only to cloud discovery (see **MCDRemoteSystemDiscoveryType**).

## Constructors

### watcher
`+ (nullable instancetype)watcher;`

Creates and initializes a new instance of this class.

#### Returns 
Returns a new instance of this class.

### watcherWithFilters
`+ (nullable instancetype)watcherWithFilters:(nonnull NSArray<NSObject<MCDRemoteSystemFilter>*>*)filters;`

Creates and initializes a new instance of this class with filters.

#### Parameters 
* `filters` 

An array of filters to use in the device discovery process.

#### Returns 
Returns an MCDRemoteSystemWatcher object with filters.

### initWithFilters
`- (nullable instancetype)initWithFilters:(nonnull NSArray<NSObject<MCDRemoteSystemFilter>*>*)filters;`

Creates and initializes a new instance of this class with filters.

#### Parameters 
* `filters` 

An array of filters to use in the device discovery process.

#### Returns 
Returns an MCDRemoteSystemWatcher object initialized with filters.

## Methods

### start
`- (void)start;`

Begins discovering remote systems.

### stop
`- (void)stop;` 

Stops the active discovery.