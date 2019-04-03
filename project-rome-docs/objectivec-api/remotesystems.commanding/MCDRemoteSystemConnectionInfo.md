---
title: MCDRemoteSystemConnectionInfo
description: 추가 지정된 MCDAppServiceConnection 인스턴스에 대 한 정보를 제공 하는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: cdfe9dec49e90013f8c967223803144ad655378e
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907055"
---
# <a name="class-mcdremotesystemconnectioninfo"></a>클래스 `MCDRemoteSystemConnectionInfo` 

```
@interface MCDRemoteSystemConnectionInfo : NSObject
```  

에 대 한 추가 정보를 제공 하는 클래스는 주어진 **[MCDAppServiceConnection](MCDAppServiceConnection.md)** 인스턴스.

## <a name="properties"></a>속성

### <a name="proximal"></a>proximal
`@property(nonatomic, readonly, getter=isProximal) BOOL proximal;`

연결 된 연결이 proximal 연결 되었는지 여부가 표시 됩니다 (**예**) 여부 (**NO**).

## <a name="constructors"></a>생성자

### <a name="trycreatefromappserviceconnection"></a>tryCreateFromAppServiceConnection
`+ (nullable instancetype)tryCreateFromAppServiceConnection:(nonnull MCDAppServiceConnection*)appServiceConnection;`

지정 된 앱 서비스 연결에서이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `appServiceConnection` 

**MCDAppServiceConnection** 인스턴스.

#### <a name="returns"></a>반환 값
앱 서비스 연결에 해당 하는이 클래스의 인스턴스를 반환 합니다.