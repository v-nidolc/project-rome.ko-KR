---
title: MCDUserNotificationReader
description: 이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다. 또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.
keywords: microsoft, windows, 릴레이 장치, iOS 방법 도움말, 방법 iPhone
ms.openlocfilehash: 486e98c30c82a7607569d252c84e4314738df6c9
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909025"
---
# <a name="class-mcdusernotificationreader"></a><span data-ttu-id="07cb9-105">클래스 `MCDUserNotificationReader`</span><span class="sxs-lookup"><span data-stu-id="07cb9-105">class `MCDUserNotificationReader`</span></span>

```
@interface MCDUserNotificationReader : NSObject
```

<span data-ttu-id="07cb9-106">이 클래스는 들어오는 새 사용자 알림 및 사용자 알림을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-106">This class provides new incoming user notifications and user notification updates.</span></span> <span data-ttu-id="07cb9-107">또한 연결 된 장치 플랫폼에 유지 되는 알림을 사용자 컬렉션에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-107">It also provides access to the collection of user notifications persisted in the Connected Device Platform.</span></span>  

## <a name="properties"></a><span data-ttu-id="07cb9-108">속성</span><span class="sxs-lookup"><span data-stu-id="07cb9-108">Properties</span></span>

### <a name="serializedstate"></a><span data-ttu-id="07cb9-109">serializedState</span><span class="sxs-lookup"><span data-stu-id="07cb9-109">serializedState</span></span>
`@property(nonatomic, readonly, nonnull) NSString* serializedState;`

<span data-ttu-id="07cb9-110">변경 판독기의 현재 상태를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-110">Returns the current state of the change reader.</span></span> <span data-ttu-id="07cb9-111">동일한 상태에서 시작 하는 새 판독기를 생성 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-111">Can be used to construct a new reader starting from the same state.</span></span>
<span data-ttu-id="07cb9-112">알림 변경 내용 (또는 초기 상태, none 성공적으로 완료 하는 경우)의 마지막 완료 된 일괄 처리를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-112">Based upon the last completed batch of notification changes (or initial state, if none have completed successfully).</span></span>

### <a name="datachanged"></a><span data-ttu-id="07cb9-113">dataChanged</span><span class="sxs-lookup"><span data-stu-id="07cb9-113">dataChanged</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDUserNotificationReader*, MCDUserNotificationReaderDataChangedEventArgs*>* dataChanged;`

<span data-ttu-id="07cb9-114">MCDUserNotificationReader에 대 한 이벤트 구독을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-114">Event subscription for MCDUserNotificationReader changed.</span></span>

## <a name="methods"></a><span data-ttu-id="07cb9-115">메서드</span><span class="sxs-lookup"><span data-stu-id="07cb9-115">Methods</span></span>

### <a name="readbatchasyncwithmaxsize"></a><span data-ttu-id="07cb9-116">readBatchAsyncWithMaxSize</span><span class="sxs-lookup"><span data-stu-id="07cb9-116">readBatchAsyncWithMaxSize</span></span>
`- (void)readBatchAsyncWithMaxSize:(NSUInteger)maxBatchSize
                       completion:(nonnull void (^)(NSArray<MCDUserNotification*>* _Nullable, NSError* _Nullable))completion;`

<span data-ttu-id="07cb9-117">일괄 처리에서 들어오는 새 알림 및 기존 알림 업데이트를 포함 하는 알림 변경 내용을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="07cb9-117">Read notification changes including new incoming notifications and updates on existing notifications in batch.</span></span>