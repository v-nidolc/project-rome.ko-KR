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
# <a name="class-mcdremotesystemremovedeventargs"></a>클래스 `MCDRemoteSystemRemovedEventArgs` 

```
@interface MCDRemoteSystemRemovedEventArgs : NSObject
```  

MCDRemoteSystemWatcher.remoteSystemRemoved 이벤트에 대 한 이벤트 인수입니다.

## <a name="properties"></a>속성

### <a name="remotesystem"></a>remoteSystem
`@property(nonatomic, readonly, nonnull) MCDRemoteSystem* remoteSystem;`

제거 된 MCDRemoteSystem 원격 시스템입니다. 이 원격 시스템은이 이벤트 후 사용할 수 없습니다.