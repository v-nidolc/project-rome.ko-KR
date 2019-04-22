---
title: MCDRemoteSystemRemovedEventArgs
description: RemoteSystemWatcher RemoteSystemRemoved 이벤트에 대 한 이벤트 인수입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 652107473e7b716493483057b090f558d82425a2
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801735"
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