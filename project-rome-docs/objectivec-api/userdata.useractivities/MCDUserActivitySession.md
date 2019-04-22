---
title: MCDUserActivitySession
description: 이 클래스는 사용자 활동 추적 ([MCDUserActivity](MCDUserActivity.md) 인스턴스)는 사용자 활동에 참여 하는 동안.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2ae85e637bb059e811a60e5bde5f33ea767c8314
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800665"
---
# <a name="class-mcduseractivitysession"></a><span data-ttu-id="871ed-104">클래스 `MCDUserActivitySession`</span><span class="sxs-lookup"><span data-stu-id="871ed-104">class `MCDUserActivitySession`</span></span>

```
@interface MCDUserActivitySession : NSObject
```

<span data-ttu-id="871ed-105">이 클래스는 지정 된 사용자 활동에 대 한 참여를 추적 ([MCDUserActivity](MCDUserActivity.md) 인스턴스).</span><span class="sxs-lookup"><span data-stu-id="871ed-105">This class tracks engagement for a specified user activity ([MCDUserActivity](MCDUserActivity.md) instance).</span></span>

<span data-ttu-id="871ed-106">A [MCDUserActivity](MCDUserActivity.md) 사용자 활동에 참여 하는 기간을 추적 하는 MCDUserActivitySession와 사용 하 여 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-106">A [MCDUserActivity](MCDUserActivity.md) is associated with an MCDUserActivitySession which tracks how long the user is engaged in that activity.</span></span> <span data-ttu-id="871ed-107">예를 들어, 동영상을 시청 같은 활동이 여러 날에 걸쳐 켜기 끄기 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-107">For example, an activity such as watching a movie can occur on-and-off over the course of multiple days.</span></span> <span data-ttu-id="871ed-108">사용자는 동영상을 시청의 새 활동을 처음 시작 하는 경우에 MCDUserActivitySession 생성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-108">When the user first starts the new activity of watching a movie, a MCDUserActivitySession must be created.</span></span> <span data-ttu-id="871ed-109">사용자가 다른 활동을 전환할 때 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-109">It should be disposed when the user switches to a different activity.</span></span> <span data-ttu-id="871ed-110">앱 간에 만들어야 사용자를 다시 시작할 때 **MCDUserActivitySession** 원래에서 [MCDUserActivity](MCDUserActivity.md) 영화를 감시 하는 사용자와 작업을 추적 하려면.</span><span class="sxs-lookup"><span data-stu-id="871ed-110">When the user resumes, the app should create another **MCDUserActivitySession** from the original [MCDUserActivity](MCDUserActivity.md) to track the activity as long as the user is watching the movie.</span></span>


## <a name="properties"></a><span data-ttu-id="871ed-111">속성</span><span class="sxs-lookup"><span data-stu-id="871ed-111">Properties</span></span>

### <a name="activityid"></a><span data-ttu-id="871ed-112">activityId</span><span class="sxs-lookup"><span data-stu-id="871ed-112">activityId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* activityId;`

<span data-ttu-id="871ed-113">이 MCDUserActivitySession 연관 MCDUserActivity에 대 한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-113">A unique ID for the MCDUserActivity associated with this MCDUserActivitySession.</span></span>

## <a name="methods"></a><span data-ttu-id="871ed-114">메서드</span><span class="sxs-lookup"><span data-stu-id="871ed-114">Methods</span></span>

### <a name="stop"></a><span data-ttu-id="871ed-115">stop</span><span class="sxs-lookup"><span data-stu-id="871ed-115">stop</span></span>
`- (void)stop;`

<span data-ttu-id="871ed-116">이 작업 세션을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-116">Stops this activity session.</span></span> <span data-ttu-id="871ed-117">이 사용자는 더 이상이 세션과 연결 된 활동에 참여 하는 경우 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ed-117">This should be called when the user is no longer engaged in the activity associated with this session.</span></span>