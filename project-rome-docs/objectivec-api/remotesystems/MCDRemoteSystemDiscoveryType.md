---
title: MCDRemoteSystemDiscoveryType
description: 포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: dc94b92311cb666fd2ffd3949b3d4d66a49e6e5b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800505"
---
# <a name="enum-mcdremotesystemdiscoverytype"></a>열거형 `MCDRemoteSystemDiscoveryType` 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemDiscoveryType)
```  

포함 하는 방법을 원격 시스템을 설명 하는 값은 검색할 수 있습니다. 

## <a name="fields"></a>필드

| 이름                              | 값 | 설명                    |
|:----------------------------------|:------|:-------------------------------|
| MCDRemoteSystemDiscoveryTypeAny   | 0     | 원격 시스템 모든 연결을 통해 검색할 수 있습니다.  |
| MCDRemoteSystemDiscoveryTypeProximal | 1     | 원격 시스템은 로컬 같은 proximal 연결을 통해 검색할 수만
네트워크 또는 Bluetooth 연결 합니다. |
| MCDRemoteSystemDiscoveryTypeCloud | 2     | 원격 시스템은 클라우드 연결을 통해 검색할 수만 있습니다. |
| MCDRemoteSystemDiscoveryTypeSpatiallyProximal | 3     | 원격 시스템 proximal 연결을 통해 검색할 수 고 할 수 있어야
Bluetooth 범위에서 예를 들어 클라이언트 장치 곧이 공간적으로입니다.  |

