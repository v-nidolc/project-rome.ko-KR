---
title: MCDStatelessAppServiceResponseStatus
description: (메시지 데이터를 성공적으로 배달) 여부 다른 하나의 app service에서 보낸 메시지의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9d01e892861c8551b7b3e41d1b227f65f07d752a
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907875"
---
# <a name="enum-mcdstatelessappserviceresponsestatus"></a>열거형 `MCDStatelessAppServiceResponseStatus`

`typedef NS_ENUM(NSInteger, MCDStatelessAppServiceResponseStatus)`

 (메시지 데이터를 성공적으로 배달) 여부 다른 하나의 app service에서 보낸 메시지의 상태를 설명 하는 값을 포함 합니다.


| 이름    |값   |설명   |                  
|------ |------- |--|
|MCDStatelessAppServiceResponseStatusSuccess | 0| 메시지가는 성공적으로 배달 되었습니다. |
|MCDStatelessAppServiceResponseStatusAppNotInstalled | 1| 연결을 시도한 app service에 대 한 패키지를 장치에 설치 되지 않았습니다. 패키지 theap p 서비스에 연결을 시도 하기 전에 설치 되어 있는지 확인 합니다. |
|MCDStatelessAppServiceResponseStatusAppUnavailable | 2 | 연결을 시도한 app service에 대 한 패키지에 일시적으로 사용할 수 없는 경우 나중에 다시 연결 하려고 합니다. |
|MCDStatelessAppServiceResponseStatusAppServiceUnavailable | 3 | 지정 된 패키지 ID 사용 하 여 앱 설치 되어 사용할 수 있지만 앱에 지정 된 app service에 대 한 지원을 선언 하지 않습니다. App service의 이름 및 앱의 버전이 올바른지 확인 합니다. |
|MCDStatelessAppServiceResponseStatusRemoteSystemUnavailable | 4 | 원격 장치에 연결을 설정할 수 없어 메시지를 배달 하지 못했습니다.|
|MCDStatelessAppServiceResponseStatusRemoteSystemNotSupportedByApp | 5 | 원격 응용 프로그램 원격 연결을 지원 하도록 구성 되지 않았습니다. |
|MCDStatelessAppServiceResponseStatusNotAuthorized | 6 | App service가 원격 장치와 통신할 수 있는 권한이 없습니다. |
|MCDStatelessAppServiceResponseStatusResourceLimitsExceeded | 7 | 원격 앱 서비스의 프로그램 메모리 한도 초과 했기 때문에 메시지를 배달 하지 못했습니다.|
|MCDStatelessAppServiceResponseStatusMessageSizeTooLarge | 8 | 허용 되는 크기를 초과 했기 때문에 메시지를 배달 하지 못했습니다. |
|MCDStatelessAppServiceResponseStatusFailure | 9 | 네트워크 오류로 인해 메시지를 배달 하지 못했습니다. |
|MCDStatelessAppServiceResponseStatusUnknown | 10 |알 수 없는 이유로 메시지를 배달 하지 못했습니다. |