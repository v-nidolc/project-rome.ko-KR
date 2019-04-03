---
title: MCDAppServiceRequest
description: 이 앱 서비스 연결에는 원격 응용 프로그램/장치에서 들어오는 메시지를 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 553403ab57b594294072dc082f5646eb1646e55b
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907575"
---
# <a name="class-mcdappservicerequest"></a>클래스 `MCDAppServiceRequest`

```
@interface MCDAppServiceRequest : NSObject
```
이 앱 서비스 연결에는 원격 응용 프로그램/장치에서 들어오는 메시지를 나타냅니다.

## <a name="properties"></a>속성

### <a name="message"></a>message 
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

원격 앱 서비스에 대 한 메시지입니다.

## <a name="methods"></a>메서드

### <a name="sendresponseasync"></a>sendResponseAsync 
```
- (void)sendResponseAsync:(nonnull NSDictionary*)message
               completion:(nonnull void (^)(MCDAppServiceResponseStatus, NSError* _Nullable))completion;
```

요청을 전송한 원격 app service에 대 한 응답 메시지를 보냅니다.

#### <a name="parameters"></a>매개 변수
* `message` 

원격 앱 서비스에 대 한 메시지입니다.

* `completion`     

보내기 작업의 상태를 나타내는 MCDAppServiceResponseStatus 값을 사용 하 여 비동기 작업을 완료 합니다.