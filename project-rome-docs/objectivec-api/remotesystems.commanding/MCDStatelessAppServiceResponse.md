---
title: MCDStatelessAppServiceResponse
description: MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4e650b1b114a3cb05b2d9b03b833b9e1cdd6607c
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801625"
---
# <a name="class-mcdstatelessappserviceresponse"></a><span data-ttu-id="ad3d1-104">클래스 `MCDStatelessAppServiceResponse`</span><span class="sxs-lookup"><span data-stu-id="ad3d1-104">class `MCDStatelessAppServiceResponse`</span></span> 

```
@interface MCDStatelessAppServiceResponse : NSObject
```  

<span data-ttu-id="ad3d1-105">MCDAppServiceConnection.sendStatelessMessageAsync에 대 한 이전 호출에 대 한 응답에서 클라이언트 앱에 원격 app service에서 전달 된 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-105">Represents a message passed from a remote app service to the client app in response to a previous call to MCDAppServiceConnection.sendStatelessMessageAsync.</span></span>


## <a name="properties"></a><span data-ttu-id="ad3d1-106">속성</span><span class="sxs-lookup"><span data-stu-id="ad3d1-106">Properties</span></span>

### <a name="message"></a><span data-ttu-id="ad3d1-107">message</span><span class="sxs-lookup"><span data-stu-id="ad3d1-107">message</span></span>
`@property(nonatomic, readonly, nonnull) NSDictionary* message;`

<span data-ttu-id="ad3d1-108">키/값 쌍으로 구성 된 원격 앱 서비스에서 보낸 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-108">The message sent by the remote app service, consisting of key/value pairs.</span></span>

### <a name="status"></a><span data-ttu-id="ad3d1-109">상태</span><span class="sxs-lookup"><span data-stu-id="ad3d1-109">status</span></span>
`@property(nonatomic, readonly) MCDStatelessAppServiceResponseStatus status;`

<span data-ttu-id="ad3d1-110">원격 앱 서비스에서 응답의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3d1-110">The status of the response from the remote app service.</span></span>

