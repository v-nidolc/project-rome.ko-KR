---
title: MCDAppServiceRequestReceivedEventArgs
description: "\"요청 받은\" 이벤트와 연결 된 데이터를 포함 합니다."
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5fa7a3b2742d5ecacd7c6a90e39e86f4c46f2218
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800645"
---
# <a name="class-mcdappservicerequestreceivedeventargs"></a><span data-ttu-id="3ebe3-104">클래스 `MCDAppServiceRequestReceivedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="3ebe3-104">class `MCDAppServiceRequestReceivedEventArgs`</span></span> 

```
@interface MCDAppServiceRequestReceivedEventArgs : NSObject
```  
<span data-ttu-id="3ebe3-105">"요청 받은" 이벤트와 연결 된 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ebe3-105">Contains data associated with a "request received" event.</span></span>

## <a name="properties"></a><span data-ttu-id="3ebe3-106">속성</span><span class="sxs-lookup"><span data-stu-id="3ebe3-106">Properties</span></span>

### <a name="request"></a><span data-ttu-id="3ebe3-107">요청</span><span class="sxs-lookup"><span data-stu-id="3ebe3-107">request</span></span>
`@property(nonatomic, readonly, nonnull) MCDAppServiceRequest* request;`

<span data-ttu-id="3ebe3-108">원격 장치에서 보낸 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="3ebe3-108">The request sent by the remote device.</span></span>