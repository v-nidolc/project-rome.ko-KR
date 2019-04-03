---
title: MCDAppServiceConnectionOpenedInfo
description: 이 클래스는 원격 장치 로컬 앱 서비스에 대 한 연결을 열 때 발생 하는 MCDAppServiceProvider.connectionDidOpen 이벤트에 대 한 데이터를 제공 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b700c95d7ab093b47a94c856c25b946fc5df12d7
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907555"
---
# <a name="class-mcdappserviceconnectionopenedinfo"></a>클래스 `MCDAppServiceConnectionOpenedInfo` 

```
@interface MCDAppServiceConnectionOpenedInfo : NSObject
```  

이 클래스는 원격 장치 로컬 앱 서비스에 대 한 연결을 열 때 발생 하는 MCDAppServiceProvider.connectionDidOpen 이벤트에 대 한 데이터를 제공 합니다.

## <a name="properties"></a>속성

### <a name="appserviceconnection"></a>appServiceConnection
`@property(nonatomic, readonly, nonnull) MCDAppServiceConnection* appServiceConnection;`

로컬 app service와 원격 장치 간의 연결을 나타내는 MCDAppServiceConnection 인스턴스.

### <a name="remotesystemapp"></a>remoteSystemApp
`@property(nonatomic, readonly, nullable) MCDRemoteSystemApp* remoteSystemApp;`

MCDRemoteSystemApp 원격 응용 프로그램 로컬 app service에 대 한 연결을 시작 합니다.