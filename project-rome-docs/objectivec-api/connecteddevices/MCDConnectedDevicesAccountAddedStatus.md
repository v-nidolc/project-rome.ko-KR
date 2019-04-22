---
title: MCDConnectedDevicesAccountAddedStatus
description: 추가 계정 작업 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d7fadec0c3e69eedab23df18d803ee85fd37644b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801565"
---
# <a name="enum-mcdconnecteddevicesaccountaddedstatus"></a>열거형 `MCDConnectedDevicesAccountAddedStatus`

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesAccountAddedStatus)
```  
추가 계정 작업 상태를 설명 하는 값을 포함 합니다.

## <a name="fields"></a>필드

| 이름                              |   값     | 설명 |
|:----------------------------------|:------|:-------------------------------|
| MCDConnectedDevicesAccountAddedStatusSuccess | 0 | 플랫폼에 계정을 추가 했습니다. |
| MCDConnectedDevicesAccountAddedStatusErrorNoNetwork | 1 | 로마 검색 네트워크 액세스 권한이 없는 계정 작업에 실패 합니다. |
| MCDConnectedDevicesAccountAddedStatusErrorServiceFailed | 2 | 로마 웹 서비스에 연결할 수 없습니다. 계정 작업에 실패 합니다. |
| MCDConnectedDevicesAccountAddedStatusErrorNoTokenRequestSubscriber | 3 | 앱 AccessTokenRequested 이벤트를 구독 하지 않은 계정 작업에 실패 합니다. |
| MCDConnectedDevicesAccountAddedStatusErrorTokenRequestFailed | 4 | 앱 토큰을 요청할 때 반환 하지 못했습니다 계정 작업에 실패 합니다. |
| MCDConnectedDevicesAccountAddedStatusErrorUnknown | 5 | 알 수 없는 이유로 계정 작업이 실패 했습니다. |
