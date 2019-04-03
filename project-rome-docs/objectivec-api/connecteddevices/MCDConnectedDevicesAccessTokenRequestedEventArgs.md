---
title: MCDConnectedDevicesAccessTokenRequestedEventArgs
description: MCDConnectedDevicesAccessTokenRequested, 토큰을 요청 해야 할 때 발생 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d50b7dc75944e3c3df553c95247b0ec578a477a4
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908325"
---
# <a name="class-mcdconnecteddevicesaccesstokenrequestedeventargs"></a><span data-ttu-id="05cd5-104">클래스 `MCDConnectedDevicesAccessTokenRequestedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="05cd5-104">class `MCDConnectedDevicesAccessTokenRequestedEventArgs`</span></span> 

```
@interface MCDConnectedDevicesAccessTokenRequestedEventArgs : NSObject
```  

<span data-ttu-id="05cd5-105">MCDConnectedDevicesAccessTokenRequested, 토큰을 요청 해야 할 때 발생 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05cd5-105">Returned by MCDConnectedDevicesAccessTokenRequested, fired when there is a need to request a token.</span></span> 

## <a name="properties"></a><span data-ttu-id="05cd5-106">속성</span><span class="sxs-lookup"><span data-stu-id="05cd5-106">Properties</span></span>

### <a name="request"></a><span data-ttu-id="05cd5-107">요청</span><span class="sxs-lookup"><span data-stu-id="05cd5-107">request</span></span>
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccessTokenRequest* request;`

<span data-ttu-id="05cd5-108">이 MCDConnectedDevicesAccessTokenRequest와 연결 된 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="05cd5-108">The request associated with this MCDConnectedDevicesAccessTokenRequest.</span></span>