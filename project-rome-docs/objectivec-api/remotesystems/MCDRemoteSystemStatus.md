---
title: MCDRemoteSystemStatus
description: 원격 시스템의 가용성을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4a69961b12def736733e1b6a78d376d57b2fa33f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801375"
---
# <a name="enum-mcdremotesystemstatus"></a>열거형 `MCDRemoteSystemStatus` 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemStatus)
```  
원격 시스템의 가용성을 설명 하는 값을 포함 합니다. IOS 앱의 값에 **MCDRemoteSystemStatusUnknown** 항상 발생할 수, 다른 값은 Windows 시스템에서 사용할 수 있습니다.

## <a name="fields"></a>필드

| 이름                              | 값 | 설명                    |
|:----------------------------------|:------|:-------------------------------|
| MCDRemoteSystemStatusUnavailable | 0 | 원격 시스템을 사용할 수 없는 상태로 보고 됩니다. |
| MCDRemoteSystemStatusDiscoveringAvailablilty | 1 | 원격 시스템의 상태를 결정 하는 (검색 프로세스 중에 발생). |
| MCDRemoteSystemStatusAvailable | 2 | 원격 시스템은 사용 가능한 것으로 보고 됩니다. |
| MCDRemoteSystemStatusUnknown | 3 | 상태를 알 수 없습니다. |
