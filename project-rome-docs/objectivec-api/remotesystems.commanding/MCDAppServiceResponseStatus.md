---
title: MCDAppServiceResponseStatus
description: 원격 앱 서비스에서 응답 메시지의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 395c2669af7178ef90ff7fd2dc8bafe9b1044028
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800335"
---
# <a name="enum-mcdappserviceresponsestatus"></a>열거형 `MCDAppServiceResponseStatus`

```
typedef NS_ENUM(NSInteger, MCDAppServiceResponseStatus)
```

원격 앱 서비스에서 응답 메시지의 상태를 설명 하는 값을 포함 합니다.

|이름         | 값  | 설명    |                           
|--------|-------------|-----|
|MCDAppServiceResponseStatusSuccess |0| App service는 성공적으로 수신 하 고 메시지를 처리 합니다.|
|MCDAppServiceResponseStatusFailure |1| App service를 받고 메시지를 처리 하지 못했습니다.|
|MCDAppServiceResponseStatusResourceLimitsExceeded |2| App service에는 사용 가능한 리소스가 부족 했기 때문에 종료 되었습니다.|
|MCDAppServiceResponseStatusUnknown |3| 알 수 없는 오류가 발생했습니다.|
|MCDAppServiceResponseStatusRemoteSystemUnavailable |4| 메시지를 보낸 장치를 사용할 수 없는 경우|
|MCDAppServiceResponseStatusMessageTooLarge |5| App service는 너무 크기 때문에 메시지를 처리 하지 못했습니다.|
|MCDAppServiceResponseStatusAppServiceConnectionClosed|6| 앱 서비스 연결에는 응답이 보내지기 전에 닫혔습니다.|