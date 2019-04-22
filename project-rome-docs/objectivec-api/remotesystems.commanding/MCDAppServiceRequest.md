---
title: MCDAppServiceRequest
description: 이 앱 서비스 연결에는 원격 응용 프로그램/장치에서 들어오는 메시지를 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 553403ab57b594294072dc082f5646eb1646e55b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800535"
---
# <a name="class-mcdappservicerequest"></a><span data-ttu-id="81d4d-104">클래스 `MCDAppServiceRequest`</span><span class="sxs-lookup"><span data-stu-id="81d4d-104">class `MCDAppServiceRequest`</span></span>

```
@interface MCDAppServiceRequest : NSObject
```
<span data-ttu-id="81d4d-105">이 앱 서비스 연결에는 원격 응용 프로그램/장치에서 들어오는 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81d4d-105">Represents an incoming message from a remote app/device to this app service connection.</span></span>

## <a name="properties"></a><span data-ttu-id="81d4d-106">속성</span><span class="sxs-lookup"><span data-stu-id="81d4d-106">Properties</span></span>

### <a name="message"></a><span data-ttu-id="81d4d-107">message</span><span class="sxs-lookup"><span data-stu-id="81d4d-107">message</span></span> 
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

<span data-ttu-id="81d4d-108">원격 앱 서비스에 대 한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="81d4d-108">The message for the remote app service.</span></span>

## <a name="methods"></a><span data-ttu-id="81d4d-109">메서드</span><span class="sxs-lookup"><span data-stu-id="81d4d-109">Methods</span></span>

### <a name="sendresponseasync"></a><span data-ttu-id="81d4d-110">sendResponseAsync</span><span class="sxs-lookup"><span data-stu-id="81d4d-110">sendResponseAsync</span></span> 
```
- (void)sendResponseAsync:(nonnull NSDictionary*)message
               completion:(nonnull void (^)(MCDAppServiceResponseStatus, NSError* _Nullable))completion;
```

<span data-ttu-id="81d4d-111">요청을 전송한 원격 app service에 대 한 응답 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="81d4d-111">Sends a response message to the remote app service that sent the request.</span></span>

#### <a name="parameters"></a><span data-ttu-id="81d4d-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81d4d-112">Parameters</span></span>
* `message` 

<span data-ttu-id="81d4d-113">원격 앱 서비스에 대 한 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="81d4d-113">The message for the remote app service.</span></span>

* `completion`     

<span data-ttu-id="81d4d-114">보내기 작업의 상태를 나타내는 MCDAppServiceResponseStatus 값을 사용 하 여 비동기 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="81d4d-114">The completion of the asynchronous operation with an MCDAppServiceResponseStatus value indicating the status of the send operation.</span></span>