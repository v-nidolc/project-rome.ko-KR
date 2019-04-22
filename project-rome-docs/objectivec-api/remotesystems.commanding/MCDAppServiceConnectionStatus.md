---
title: MCDAppServiceConnectionStatus
description: 원격 앱 서비스에 대 한 연결의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5beba7ae30d8ffd9149c5e8a599eacc38213b6d2
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801455"
---
# <a name="enum-mcdappserviceconnectionstatus"></a>열거형 `MCDAppServiceConnectionStatus`

```
typedef NS_ENUM(NSInteger, MCDAppServiceConnectionStatus)
```

원격 앱 서비스에 대 한 연결의 상태를 설명 하는 값을 포함 합니다. 참조 [Create app service를 사용 하 고](https://docs.microsoft.com/windows/uwp/launch-resume/how-to-create-and-consume-an-app-service) Windows 장치에서 앱 서비스에 대 한 정보에 대 한 합니다.

|이름   |값   |설명   |
|--------|-------|-------------|
|MCDAppServiceConnectionStatusSuccess | 0| App service에 대 한 연결에 대 한 연결이 성공적으로 열었습니다.|
|MCDAppServiceConnectionStatusAppNotInstalled | 1| 연결을 시도한 app service에 대 한 패키지를 장치에 설치 되지 않았습니다. App service에 연결을 시도 하기 전에 패키지가 설치 되어 있는지 확인 합니다.|
|MCDAppServiceConnectionStatusAppUnavailable | 2| 연결을 시도한 app service에 대 한 패키지에 일시적으로 사용할 수 없는 경우 나중에 다시 연결 하려고 합니다.|
|MCDAppServiceConnectionStatusAppServiceUnavailable | 3| 지정 된 패키지 ID 사용 하 여 앱 설치 되어 사용할 수 있지만 앱에 지정 된 app service에 대 한 지원을 선언 하지 않습니다. App service의 이름 및 앱의 버전이 올바른지 확인 합니다.|
|MCDAppServiceConnectionStatusUnknown | 4| 알 수 없는 이유로 연결을 설정할 수 없습니다.|
|MCDAppServiceConnectionStatusRemoteSystemUnavailable | 5| 대상 원격 장치 또는 응용 프로그램 제품은 더 이상 연결에 대 한입니다.|
|MCDAppServiceConnectionStatusRemoteSystemNotSupportedByApp | 6|클라이언트 앱을 원격 연결을 지원 하도록 구성 되지 않았습니다.|
|MCDAppServiceConnectionStatusNotAuthorized | 7| 클라이언트 장치에서 원격 연결을 지원 하도록 권한이 없습니다. 이 MCDAppServiceConnection 잘못 된 토큰이 전달 되어 서 발생할 수 있습니다.|