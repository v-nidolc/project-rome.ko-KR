---
title: MCDRemoteLaunchUriStatus
description: URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 1a0302cd570b8cb25476a8188e3bcb1667707461
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907145"
---
# <a name="enum-mcdremotelaunchuristatus"></a>열거형 `MCDRemoteLaunchUriStatus`

`typedef NS_ENUM(NSInteger, MCDRemoteLaunchUriStatus)`

URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.


| 이름    |값   |설명   |                  
|------ |------- |--|
|MCDRemoteLaunchUriStatusUnknown | 0| 상태를 알 수 없습니다.|
|MCDRemoteLaunchUriStatusSuccess | 1| 원격 시작이 했습니다.|
|MCDRemoteLaunchUriStatusAppUnavailable | 2 | 대상 앱을 사용할 수 없는 경우|
|MCDRemoteLaunchUriStatusProtocolUnavailable | 3 | 대상 앱에서이 URI를 지원 하지 않습니다.|
|MCDRemoteLaunchUriStatusRemoteSystemUnavailable | 4 | 메시지를 보낸 장치를 사용할 수 없는 경우|
|MCDRemoteLaunchUriStatusValueSetTooLarge | 5 | 대상 앱으로 보내는 데이터 번들 너무 큽니다.|
|MCDRemoteLaunchUriStatusDeniedByLocalSystem | 6 | 클라이언트 시스템 원격 시스템 플랫폼을 사용 하지 못하게 합니다.|
|MCDRemoteLaunchUriStatusDeniedByRemoteSystem | 7 | 대상 장치를 원격 시스템 플랫폼을 사용 하지 못하게 합니다.|