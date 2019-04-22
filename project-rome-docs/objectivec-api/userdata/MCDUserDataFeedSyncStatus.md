---
title: MCDUserDataSyncStatus
description: 상태를 설명 하는 값을 포함 한  **[MCDUserDataFeed](MCDUserDataFeed.md)** 의 연결 된 장치 플랫폼 백 엔드와 동기화 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 805192b0d9169c799f30b7daa0371767145ae86f
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801415"
---
# <a name="enum-mcduserdatasyncstatus"></a><span data-ttu-id="671ff-104">열거형 `MCDUserDataSyncStatus`</span><span class="sxs-lookup"><span data-stu-id="671ff-104">enum `MCDUserDataSyncStatus`</span></span>

```
typedef NS_ENUM(NSInteger, MCDUserDataSyncStatus)
```

<span data-ttu-id="671ff-105">상태를 설명 하는 값을 포함 한  **[MCDUserDataFeed](MCDUserDataFeed.md)** 의 연결 된 장치 플랫폼 백 엔드와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="671ff-105">Contains values that describe the state of a **[MCDUserDataFeed](MCDUserDataFeed.md)**'s synchronization with the Connected Devices Platform backend.</span></span>

|<span data-ttu-id="671ff-106">이름</span><span class="sxs-lookup"><span data-stu-id="671ff-106">Name</span></span> | <span data-ttu-id="671ff-107">값</span><span class="sxs-lookup"><span data-stu-id="671ff-107">Value</span></span> | <span data-ttu-id="671ff-108">설명</span><span class="sxs-lookup"><span data-stu-id="671ff-108">Description</span></span> |
|:-- |:-- |:-- |
|  <span data-ttu-id="671ff-109">MCDUserDataFeedSyncStatusQueued</span><span class="sxs-lookup"><span data-stu-id="671ff-109">MCDUserDataFeedSyncStatusQueued</span></span> |<span data-ttu-id="671ff-110">0</span><span class="sxs-lookup"><span data-stu-id="671ff-110">0</span></span>| <span data-ttu-id="671ff-111">데이터를 아직 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="671ff-111">The data is not yet synchronized.</span></span> |
| <span data-ttu-id="671ff-112">MCDUserDataFeedSyncStatusSynchronized</span><span class="sxs-lookup"><span data-stu-id="671ff-112">MCDUserDataFeedSyncStatusSynchronized</span></span> |<span data-ttu-id="671ff-113">1</span><span class="sxs-lookup"><span data-stu-id="671ff-113">1</span></span>| <span data-ttu-id="671ff-114">데이터 동기화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="671ff-114">The data has been synchronized.</span></span>|