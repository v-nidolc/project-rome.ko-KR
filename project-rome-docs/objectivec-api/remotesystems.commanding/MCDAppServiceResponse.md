---
title: MCDAppServiceResponse
description: 연결 된 원격 앱 서비스에서 받은 응답을 나타내는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 74cff4a84bdc4bf073dd57319c987e274ea8ceaf
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800795"
---
# <a name="class-mcdappserviceresponse"></a><span data-ttu-id="03574-104">클래스 `MCDAppServiceResponse`</span><span class="sxs-lookup"><span data-stu-id="03574-104">class `MCDAppServiceResponse`</span></span>

```
@interface MCDAppServiceResponse : NSObject
```

<span data-ttu-id="03574-105">연결 된 원격 앱 서비스에서 받은 응답을 나타내는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="03574-105">A class that represents a response received from a connected remote app service.</span></span>

## <a name="properties"></a><span data-ttu-id="03574-106">속성</span><span class="sxs-lookup"><span data-stu-id="03574-106">Properties</span></span>

### <a name="message"></a><span data-ttu-id="03574-107">message</span><span class="sxs-lookup"><span data-stu-id="03574-107">message</span></span> 
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

<span data-ttu-id="03574-108">원격 앱 서비스에서 받은 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="03574-108">The message received from the remote app service.</span></span>

### <a name="status"></a><span data-ttu-id="03574-109">상태</span><span class="sxs-lookup"><span data-stu-id="03574-109">status</span></span>
`@property(nonatomic, readonly) MCDAppServiceResponseStatus status;`

<span data-ttu-id="03574-110">받은 응답의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="03574-110">The status of the response received.</span></span>