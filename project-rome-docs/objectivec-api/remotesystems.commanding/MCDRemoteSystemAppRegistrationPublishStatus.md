---
title: MCDRemoteSystemAppRegistrationPublishStatus
description: URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 32c3e473938925f12838bf6dc5ccc3e98a3394a6
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907545"
---
# <a name="enum-mcdremotesystemappregistrationpublishstatus"></a>열거형 `MCDRemoteSystemAppRegistrationPublishStatus`

`typedef NS_ENUM(NSInteger, MCDRemoteSystemAppRegistrationPublishStatus)`

게시 작업의 상태를 나타내는 열거형입니다.
오류 상태에는 게시를 다시 시도 하려면 앱 개발자 저장할 수 있습니다 하는 일시적인 조건을 나타냅니다.

| 이름    |값   |설명   |                  
|------ |------- |--|
|MCDRemoteSystemAppRegistrationPublishStatusSuccess | 0 | 작업이 완료 되었습니다.|
|MCDRemoteSystemAppRegistrationPublishStatusErrorNoNetwork | 1 | 네트워크를 사용할 수 없습니다. |
|MCDRemoteSystemAppRegistrationPublishStatusErrorWebFailure | 2 | 웹 서비스에는 다음이 실패 했습니다.|
|MCDRemoteSystemAppRegistrationPublishStatusErrorNoTokenRequestSubscriber | 3 | 구독자가 없는 토큰 요청에 응답 했습니다.|
|MCDRemoteSystemAppRegistrationPublishStatusErrorTokenRequestFailed | 4 | 토큰 요청이 실패 했습니다.|
|MCDRemoteSystemAppRegistrationPublishStatusErrorAccountNotFound | 5 | 에 대 한 정보를 게시 하는 계정을 찾을 수 없습니다.|
|MCDRemoteSystemAppRegistrationPublishStatusErrorUnknown | 6 | 작업에 알 수 없는 오류가 발생 했습니다.|