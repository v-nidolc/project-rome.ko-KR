---
title: MCDAppServiceProvider
description: 이 프로토콜에는 로컬 앱 서비스를 원격 장치에 액세스할 수 있도록 하는 것에 대 한 메서드가 포함 됩니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: f5af56a2c87e3b4335a2a59a0130ef3622af6c26
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908665"
---
# <a name="protocol-mcdappserviceprovider"></a>protocol `MCDAppServiceProvider`

```
@protocol MCDAppServiceProvider<NSObject>
```

이 프로토콜에는 로컬 앱 서비스를 원격 장치에 액세스할 수 있도록 하는 것에 대 한 메서드가 포함 됩니다. 개발자는 앱 서비스를 원격 연결에 사용할 수 있도록 하기 위해이 프로토콜을 구현 해야 합니다.

## <a name="properties"></a>속성
 
### <a name="appserviceinfo"></a>appServiceInfo
`@property(nonatomic, readonly, strong, nonnull) MCDAppServiceInfo* appServiceInfo;`

이 app service에 대 한 설명 정보입니다.

## <a name="methods"></a>메서드

### <a name="connectiondidopen"></a>connectionDidOpen
`- (void)connectionDidOpen:(nonnull MCDAppServiceConnectionOpenedInfo*)openedInfo;`

이 메서드는이 app service에는 원격 앱 서비스 연결이 열릴 때 호출 됩니다.

#### <a name="parameters"></a>매개 변수 
* `openedInfo`

App service를 사용 하 여 원격 메시징에 대 한 정보를 포함 하는 MDCAppServiceConnectionOpenedInfo 인스턴스.