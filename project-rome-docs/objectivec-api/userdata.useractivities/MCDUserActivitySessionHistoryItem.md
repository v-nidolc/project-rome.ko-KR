---
title: MCDUserActivitySessionHistoryItem
description: 이 클래스는 사용자가 특정 작업에 참여 하는 시작 및 종료 시간을 제공 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 3a480d9d0d028973554c13ee162b359502c8a772
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907405"
---
# <a name="class-mcduseractivitysessionhistoryitem"></a><span data-ttu-id="4636a-104">클래스 `MCDUserActivitySessionHistoryItem`</span><span class="sxs-lookup"><span data-stu-id="4636a-104">class `MCDUserActivitySessionHistoryItem`</span></span>

```
@interface MCDUserActivitySessionHistoryItem : NSObject
```

<span data-ttu-id="4636a-105">이 클래스는 사용자가 특정 작업에 참여 하는 시작 및 종료 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4636a-105">This class provides the start and end time that a user was engaged in a particular activity.</span></span>


## <a name="properties"></a><span data-ttu-id="4636a-106">속성</span><span class="sxs-lookup"><span data-stu-id="4636a-106">Properties</span></span>

### <a name="useractivity"></a><span data-ttu-id="4636a-107">userActivity</span><span class="sxs-lookup"><span data-stu-id="4636a-107">userActivity</span></span>
`@property(nonatomic, readonly, nonnull) MCDUserActivity* userActivity;`

<span data-ttu-id="4636a-108">사용자 작업 기록을이 클래스 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4636a-108">The user activity whose history this class instance represents.</span></span>

### <a name="starttime"></a><span data-ttu-id="4636a-109">startTime</span><span class="sxs-lookup"><span data-stu-id="4636a-109">startTime</span></span>
`@property(nonatomic, readonly, nonnull) NSDate* startTime;`

<span data-ttu-id="4636a-110">사용자 연결된 작업의 유용한 시작 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4636a-110">The time when the user started engaging in the associated activity.</span></span>

### <a name="endtime"></a><span data-ttu-id="4636a-111">endTime</span><span class="sxs-lookup"><span data-stu-id="4636a-111">endTime</span></span>
`@property(nonatomic, readonly, nullable) NSDate* endTime;`

<span data-ttu-id="4636a-112">연결된 된 활동에 참여 사용자를 중지 하는 경우 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4636a-112">The time when the user stopped engaging in the associated activity.</span></span>

### <a name="remotesystemid"></a><span data-ttu-id="4636a-113">remoteSystemId</span><span class="sxs-lookup"><span data-stu-id="4636a-113">remoteSystemId</span></span>
`@property(nonatomic, readonly, nullable) NSString* remoteSystemId;`

<span data-ttu-id="4636a-114">이 작업에 참여 하는 사용자 장치의 원격 시스템 id를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4636a-114">The string indicating the remote system id of the device the user engaged this activity on.</span></span>