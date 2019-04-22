---
title: MCDEvent
description: 이 인터페이스는 단순 이벤트 모델을 제공합니다. 이벤트는 EventListeners에서 사용 하는 항목을 생성 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: eabe9464a104593b06460153ed30f42f7cc103eb
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801395"
---
# <a name="class-mcdevent"></a><span data-ttu-id="731f2-105">클래스 `MCDEvent`</span><span class="sxs-lookup"><span data-stu-id="731f2-105">class `MCDEvent`</span></span> 

```
@interface MCDEvent<__covariant SourceType, __covariant ArgsType> : NSObject
```  
 
 <span data-ttu-id="731f2-106">이 인터페이스는 단순 이벤트 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-106">This interface provides a simple event model.</span></span> <span data-ttu-id="731f2-107">이벤트는 EventListeners에서 사용 하는 항목을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-107">Events produce items consumed by EventListeners.</span></span>
<span data-ttu-id="731f2-108">이벤트 항목의 흐름을 MCDEventSubscription에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-108">The flow of event items is controlled by the MCDEventSubscription.</span></span>

## <a name="methods"></a><span data-ttu-id="731f2-109">메서드</span><span class="sxs-lookup"><span data-stu-id="731f2-109">Methods</span></span>

### <a name="subscribe"></a><span data-ttu-id="731f2-110">subscribe</span><span class="sxs-lookup"><span data-stu-id="731f2-110">subscribe</span></span>
`- (nonnull MCDEventSubscription*)subscribe:(nonnull void (^)(SourceType _Nonnull, ArgsType _Nonnull))listener;`

<span data-ttu-id="731f2-111">지정한 연결 된 장치 플랫폼의 이벤트를 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-111">Subscribe to given events in the Connected Devices Platform.</span></span>

#### <a name="parameters"></a><span data-ttu-id="731f2-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="731f2-112">Parameters</span></span> 
* `listener` 

<span data-ttu-id="731f2-113">MCDEventSubscriptions 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-113">Listen to MCDEventSubscriptions.</span></span>

#### <a name="returns"></a><span data-ttu-id="731f2-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="731f2-114">Returns</span></span>
<span data-ttu-id="731f2-115">MCDEventSubscription의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="731f2-115">An instance of the MCDEventSubscription.</span></span>