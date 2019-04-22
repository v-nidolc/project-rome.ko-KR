---
title: MCDRemoteSystemUpdatedEventArgs
description: MCDRemoteSystemWatcher remoteSystemUpdated 이벤트에 대 한 이벤트 인수입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 3bd52c73fcc8bc28f766b7f6261d726c65f938f9
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801235"
---
# <a name="class-mcdremotesystemupdatedeventargs"></a>클래스 `MCDRemoteSystemUpdatedEventArgs` 

```
@interface MCDRemoteSystemUpdatedEventArgs : NSObject
```  

MCDRemoteSystemWatcher remoteSystemUpdated 이벤트에 대 한 이벤트 인수입니다.

## <a name="properties"></a>속성

### <a name="remotesystem"></a>remoteSystem
`@property(nonatomic, readonly, nonnull) MCDRemoteSystem* remoteSystem;`

업데이트 된 MCDRemoteSystem 원격 시스템입니다.