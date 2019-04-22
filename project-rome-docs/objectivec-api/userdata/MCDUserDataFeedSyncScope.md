---
title: MCDUserDataFeedSyncScope
description: 이 클래스에는 앱에서 특정 사용자별 연결 된 장치 기능을 사용 하는 경우 연결 된 장치 플랫폼 백 엔드와 동기화 되는 사용자 데이터를 나타냅니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 941381a61c9b17c837c25b089f7c7073d581c4a8
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801005"
---
# <a name="class-mcduserdatafeedsyncscope"></a><span data-ttu-id="c982c-104">클래스 `MCDUserDataFeedSyncScope`</span><span class="sxs-lookup"><span data-stu-id="c982c-104">class `MCDUserDataFeedSyncScope`</span></span>

```
@interface MCDUserDataFeedSyncScope : NSObject
```
 <span data-ttu-id="c982c-105">이 인터페이스에는 앱은 사용자 활동 등의 특정 사용자 고유의 연결 된 장치 기능을 사용 하는 경우 연결 된 장치 플랫폼 백 엔드와 동기화 되는 사용자 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c982c-105">This interface represents the user data that is synchronized with the Connected Devices Platform backend when the app uses certain user-specific Connected Devices functionality, such as user activities.</span></span> <span data-ttu-id="c982c-106">인스턴스는 이러한 기능을 관리 하는 클래스에서 정적으로 검색 됩니다 (예: **MCDUserActivityChannel**)를 생성에 사용 됩니다 **MCDUserDataFeed**합니다.</span><span class="sxs-lookup"><span data-stu-id="c982c-106">An instance is retrieved statically from the class that manages such functionality (e.g. **MCDUserActivityChannel**), and it is used in the construction of **MCDUserDataFeed**.</span></span>

## <a name="properties"></a><span data-ttu-id="c982c-107">속성</span><span class="sxs-lookup"><span data-stu-id="c982c-107">Properties</span></span>

### <a name="platform"></a><span data-ttu-id="c982c-108">플랫폼</span><span class="sxs-lookup"><span data-stu-id="c982c-108">platform</span></span>
`@property (nonatomic, readwrite, nullable, copy) NSString* platform;`

<span data-ttu-id="c982c-109">합니다 **ConnectedDevicesPlatform** 이 앱의 연결 된 장치 기능에 대 한 초기화 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="c982c-109">The **ConnectedDevicesPlatform** instance that has been initialized for this app's Connected Devices functionality.</span></span>

### <a name="syncscopeflags"></a><span data-ttu-id="c982c-110">syncScopeFlags</span><span class="sxs-lookup"><span data-stu-id="c982c-110">syncScopeFlags</span></span>
`@property (nonatomic, readwrite, nullable, copy) NSArray<NSString*>* syncScopeFlags;`

<span data-ttu-id="c982c-111">들어오는 활동을 필터링 하는 것에 대 한 선택적 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c982c-111">Set any optional flags for filtering incoming activities.</span></span>

### <a name="notificationtype"></a><span data-ttu-id="c982c-112">notificationType</span><span class="sxs-lookup"><span data-stu-id="c982c-112">notificationType</span></span>
`@property (nonatomic, readwrite, nullable, copy) NSString* notificationType;`

<span data-ttu-id="c982c-113">변경 알림 유형의 받을 사용자 피드는 데이터 동기화 범위에 대 한 형식 설정</span><span class="sxs-lookup"><span data-stu-id="c982c-113">Set type of change notification type to receive for user data feed sync scope</span></span>

```