---
title: MCDAppServiceClosedStatus
description: 원격 앱 서비스에 닫힌된 연결을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9a56ee489175cb065fde281acb4ae8a345fb851b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800775"
---
# <a name="enum-mcdappserviceclosedstatus"></a>열거형 `MCDAppServiceClosedStatus`

```
typedef NS_ENUM(NSInteger, MCDAppServiceClosedStatus)
```

원격 앱 서비스에 닫힌된 연결을 설명 하는 값을 포함 합니다.

|멤버   |값   |설명   |
|--------|-------|-------------|
|MCDAppServiceClosedStatusCompleted |0| App service에 대 한 끝점을 정상적으로 닫힙니다.|
|MCDAppServiceClosedStatusCanceled |1| App service에 대 한 끝점은 클라이언트 또는 시스템에서 닫혔습니다.|
|MCDAppServiceClosedStatusResourceLimitsExceeded |2| App service에 대 한 끝점은 끝점 리소스가 부족 하기 때문에 종료 되었습니다.|
|MCDAppServiceClosedStatusUnknown |3| 알 수 없는 오류가 발생했습니다.|