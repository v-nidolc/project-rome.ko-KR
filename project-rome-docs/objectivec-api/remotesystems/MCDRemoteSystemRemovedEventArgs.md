---
title: MCDRemoteSystemRemovedEventArgs
description: RemoteSystemWatcher RemoteSystemRemoved 이벤트에 대 한 이벤트 인수입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 652107473e7b716493483057b090f558d82425a2
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907045"
---
# <a name="class-mcdremotesystemremovedeventargs"></a><span data-ttu-id="6e019-104">클래스 `MCDRemoteSystemRemovedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="6e019-104">class `MCDRemoteSystemRemovedEventArgs`</span></span> 

```
@interface MCDRemoteSystemRemovedEventArgs : NSObject
```  

<span data-ttu-id="6e019-105">MCDRemoteSystemWatcher.remoteSystemRemoved 이벤트에 대 한 이벤트 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="6e019-105">Event arguments for the MCDRemoteSystemWatcher.remoteSystemRemoved event.</span></span>

## <a name="properties"></a><span data-ttu-id="6e019-106">속성</span><span class="sxs-lookup"><span data-stu-id="6e019-106">Properties</span></span>

### <a name="remotesystem"></a><span data-ttu-id="6e019-107">remoteSystem</span><span class="sxs-lookup"><span data-stu-id="6e019-107">remoteSystem</span></span>
`@property(nonatomic, readonly, nonnull) MCDRemoteSystem* remoteSystem;`

<span data-ttu-id="6e019-108">제거 된 MCDRemoteSystem 원격 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="6e019-108">The MCDRemoteSystem remote system that was removed.</span></span> <span data-ttu-id="6e019-109">이 원격 시스템은이 이벤트 후 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e019-109">This remote system should not be used after this event.</span></span>