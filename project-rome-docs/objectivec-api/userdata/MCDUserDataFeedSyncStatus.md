---
title: MCDUserDataSyncStatus
description: 상태를 설명 하는 값을 포함 한  **[MCDUserDataFeed](MCDUserDataFeed.md)** 의 연결 된 장치 플랫폼 백 엔드와 동기화 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 805192b0d9169c799f30b7daa0371767145ae86f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801415"
---
# <a name="enum-mcduserdatasyncstatus"></a>열거형 `MCDUserDataSyncStatus`

```
typedef NS_ENUM(NSInteger, MCDUserDataSyncStatus)
```

상태를 설명 하는 값을 포함 한  **[MCDUserDataFeed](MCDUserDataFeed.md)** 의 연결 된 장치 플랫폼 백 엔드와 동기화 합니다.

|이름 | 값 | 설명 |
|:-- |:-- |:-- |
|  MCDUserDataFeedSyncStatusQueued |0| 데이터를 아직 동기화 되지 않습니다. |
| MCDUserDataFeedSyncStatusSynchronized |1| 데이터 동기화 되었습니다.|