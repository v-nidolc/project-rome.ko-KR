---
title: MCDAppServiceClosedEventArgs
description: MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: a115ea4cc753efac445a466dbdfbfb14bf184370
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909185"
---
# <a name="class-mcdappserviceclosedeventargs"></a><span data-ttu-id="db50f-104">클래스 `MCDAppServiceClosedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="db50f-104">class `MCDAppServiceClosedEventArgs`</span></span> 

```
@interface MCDAppServiceClosedEventArgs : NSObject
```  

<span data-ttu-id="db50f-105">MCDAppServiceConnection.serviceClosed는 MCDAppServiceConnection 닫 혔 음을 알리고 닫기 이벤트는 이유를 제공 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="db50f-105">Returned by MCDAppServiceConnection.serviceClosed to inform that the MCDAppServiceConnection has been closed and provide a reason behind the close event.</span></span>

## <a name="properties"></a><span data-ttu-id="db50f-106">속성</span><span class="sxs-lookup"><span data-stu-id="db50f-106">Properties</span></span>

### <a name="status"></a><span data-ttu-id="db50f-107">상태</span><span class="sxs-lookup"><span data-stu-id="db50f-107">status</span></span>
`@property(nonatomic, readonly) MCDAppServiceClosedStatus status;`

<span data-ttu-id="db50f-108">App service를 닫은 방법의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="db50f-108">The status of how the app service closed.</span></span>