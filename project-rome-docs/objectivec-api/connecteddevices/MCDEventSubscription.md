---
title: MCDEventSubscription
description: 이 인터페이스는 단순 이벤트 구독을 제공 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: ce5a5782f80b54e78a6e3890cd68d9e92c52226c
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801621"
---
# <a name="class-mcdeventsubscription"></a><span data-ttu-id="620f2-104">클래스 `MCDEventSubscription`</span><span class="sxs-lookup"><span data-stu-id="620f2-104">class `MCDEventSubscription`</span></span> 

```
@interface MCDEventSubscription : NSObject
```  
<span data-ttu-id="620f2-105">이 인터페이스는 단순 이벤트 구독을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="620f2-105">This interface provides a simple event subscription.</span></span>

## <a name="methods"></a><span data-ttu-id="620f2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="620f2-106">Methods</span></span>

### <a name="cancel"></a><span data-ttu-id="620f2-107">취소</span><span class="sxs-lookup"><span data-stu-id="620f2-107">cancel</span></span>
`- (void)cancel;`

<span data-ttu-id="620f2-108">이벤트 구독을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="620f2-108">Cancels an event subscription.</span></span> <span data-ttu-id="620f2-109">이 호출 후 연결 된 EventListener는 (이미 비행 이벤트에서 계속 제공 될 수 있습니다) 자세한 이벤트를 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="620f2-109">After making this call, the attached EventListener will not receive any more events (Already in flight events may still be delivered).</span></span>
<span data-ttu-id="620f2-110">네이티브 코드에서 수행 됩니다 ConnectedDevices 기능을 많이, 이므로 하거나 취소 호출 하거나 Weakreference는 정리 된 EventListener 보유 중인 리소스의 적절 한 데 항상 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="620f2-110">Because much of the ConnectedDevices functionality is done in native code, it is important to either always ensure cancel is called or WeakReferences are used to ensure proper clean up of resources held by the EventListener.</span></span>
