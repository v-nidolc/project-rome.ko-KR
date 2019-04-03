---
title: MCDStatelessAppServiceResponse
description: MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4e650b1b114a3cb05b2d9b03b833b9e1cdd6607c
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907235"
---
# <a name="class-mcdstatelessappserviceresponse"></a><span data-ttu-id="e287e-104">클래스 `MCDStatelessAppServiceResponse`</span><span class="sxs-lookup"><span data-stu-id="e287e-104">class `MCDStatelessAppServiceResponse`</span></span> 

```
@interface MCDStatelessAppServiceResponse : NSObject
```  

<span data-ttu-id="e287e-105">MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e287e-105">Represents a message passed from a remote app service to the client app in response to a previous call to MCDAppServiceConnection.sendStatelessMessageAsync.</span></span>


## <a name="properties"></a><span data-ttu-id="e287e-106">속성</span><span class="sxs-lookup"><span data-stu-id="e287e-106">Properties</span></span>

### <a name="message"></a><span data-ttu-id="e287e-107">message</span><span class="sxs-lookup"><span data-stu-id="e287e-107">message</span></span>
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

<span data-ttu-id="e287e-108">키/값 쌍으로 구성 된 원격 앱 서비스에서 보낸 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="e287e-108">The message sent by the remote app service, consisting of key/value pairs.</span></span>

### <a name="status"></a><span data-ttu-id="e287e-109">상태</span><span class="sxs-lookup"><span data-stu-id="e287e-109">status</span></span>
`@property(nonatomic, readonly) MCDStatelessAppServiceResponseStatus status;`

<span data-ttu-id="e287e-110">원격 앱 서비스에서 응답의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e287e-110">The status of the response from the remote app service.</span></span>

