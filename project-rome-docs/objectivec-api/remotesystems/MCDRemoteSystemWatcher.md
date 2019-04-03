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
# <a name="class-mcdremotesystemwatcher"></a><span data-ttu-id="e20c9-104">클래스 `MCDRemoteSystemWatcher`</span><span class="sxs-lookup"><span data-stu-id="e20c9-104">class `MCDRemoteSystemWatcher`</span></span>

```
@interface MCDRemoteSystemWatcher : NSObject
```

<span data-ttu-id="e20c9-105">원격 시스템을 검색 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e20c9-105">A class used to discover remote systems.</span></span> 

## <a name="properties"></a><span data-ttu-id="e20c9-106">속성</span><span class="sxs-lookup"><span data-stu-id="e20c9-106">Properties</span></span>

### <a name="remotesystemadded"></a><span data-ttu-id="e20c9-107">remoteSystemAdded</span><span class="sxs-lookup"><span data-stu-id="e20c9-107">remoteSystemAdded</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemAddedEventArgs*>* remoteSystemAdded;`

<span data-ttu-id="e20c9-108">새 원격 시스템은 검색 하는 경우에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e20c9-108">Event for when a new remote system is discovered.</span></span>

### <a name="remotesystemupdated"></a><span data-ttu-id="e20c9-109">remoteSystemUpdated</span><span class="sxs-lookup"><span data-stu-id="e20c9-109">remoteSystemUpdated</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemUpdatedEventArgs*>* remoteSystemUpdated;`

<span data-ttu-id="e20c9-110">이 검색 세션에서 이전에 검색 된 원격 시스템 proximally 연결에 연결 하는 클라우드 또는 그 반대로 변경 하는 경우에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e20c9-110">Event for when a remote system that was previously discovered in this discovery session changes from proximally connected to cloud connected, or the reverse.</span></span> 

### <a name="remotesystemremoved"></a><span data-ttu-id="e20c9-111">remoteSystemRemoved</span><span class="sxs-lookup"><span data-stu-id="e20c9-111">remoteSystemRemoved</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher*, MCDRemoteSystemRemovedEventArgs*>* remoteSystemRemoved;`

<span data-ttu-id="e20c9-112">원격 시스템을 제거한 경우에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e20c9-112">Event for when a remote system is removed.</span></span> 

### <a name="enumerationcompleted"></a><span data-ttu-id="e20c9-113">enumerationCompleted</span><span class="sxs-lookup"><span data-stu-id="e20c9-113">enumerationCompleted</span></span>
<span data-ttu-id="e20c9-114">' '@property(비 원자성을 읽기 전용, null이 아닌) MCDEvent < MCDRemoteSystemWatcher *, MCDRemoteSystemEnumerationCompletedEventArgs*> \* enumerationCompleted;</span><span class="sxs-lookup"><span data-stu-id="e20c9-114">\`\`\`@property(nonatomic, readonly, nonnull) MCDEvent<MCDRemoteSystemWatcher *, MCDRemoteSystemEnumerationCompletedEventArgs*>\* enumerationCompleted;</span></span>
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