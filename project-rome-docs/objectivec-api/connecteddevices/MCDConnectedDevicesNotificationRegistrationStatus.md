---
title: MCDConnectedDevicesNotificationRegistrationStatus
description: 클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c7d770c73479afb949a4917b5457b12e23b78698
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801365"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstatus"></a>클래스 `MCDConnectedDevicesNotificationRegistrationStatus` 

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesNotificationRegistrationStatus)
```  
등록 작업의 상태를 나타내는 열거형입니다.
오류 상태 위치 앱 개발자 할 등록을 다시 시도 하는 일시적인 상태를 나타냅니다.

## <a name="fields"></a>필드

| 이름                              |   값     | 설명 |
|:----------------------------------|:------|:-------------------------------|
| MCDConnectedDevicesNotificationRegistrationStatusSuccess | 0 | 작업이 완료 되었습니다.
| MCDConnectedDevicesNotificationRegistrationStatusErrorNoNetwork | 1 | 네트워크를 사용할 수 없습니다. |
| MCDConnectedDevicesNotificationRegistrationStatusErrorWebFailure | 2 | 웹 서비스에는 다음이 실패 했습니다. |
| MCDConnectedDevicesNotificationRegistrationStatusErrorNoTokenRequestSubscriber | 3 | 구독자가 없는 토큰 요청에 응답 했습니다. |
| MCDConnectedDevicesNotificationRegistrationStatusErrorTokenRequestFailed | 4 | 토큰 요청이 실패 했습니다. |
| MCDConnectedDevicesNotificationRegistrationStatusErrorAccountNotFound | 5 | 에 대 한 정보를 등록 하는 계정을 찾을 수 없습니다. |
| MCDConnectedDevicesNotificationRegistrationStatusErrorUnknown | 6 | 작업에 알 수 없는 오류가 발생 했습니다. |