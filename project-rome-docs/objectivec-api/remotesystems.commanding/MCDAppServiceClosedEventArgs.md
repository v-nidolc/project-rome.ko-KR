---
title: MCDAppServiceClosedEventArgs
description: MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: a115ea4cc753efac445a466dbdfbfb14bf184370
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801295"
---
# <a name="class-mcdappserviceclosedeventargs"></a><span data-ttu-id="e5b2a-104">클래스 `MCDAppServiceClosedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="e5b2a-104">class `MCDAppServiceClosedEventArgs`</span></span> 

```
@interface MCDAppServiceClosedEventArgs : NSObject
```  

<span data-ttu-id="e5b2a-105">MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b2a-105">Returned by MCDAppServiceConnection.serviceClosed to inform that the MCDAppServiceConnection has been closed and provide a reason behind the close event.</span></span>

## <a name="properties"></a><span data-ttu-id="e5b2a-106">속성</span><span class="sxs-lookup"><span data-stu-id="e5b2a-106">Properties</span></span>

### <a name="status"></a><span data-ttu-id="e5b2a-107">상태</span><span class="sxs-lookup"><span data-stu-id="e5b2a-107">status</span></span>
`@property(nonatomic, readonly) MCDAppServiceClosedStatus status;`

<span data-ttu-id="e5b2a-108">App service를 닫은 방법의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b2a-108">The status of how the app service closed.</span></span>