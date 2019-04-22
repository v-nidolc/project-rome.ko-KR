---
title: MCDRemoteSystem
description: 원격 시스템을 나타내기 위해 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5f0ab2108d4efa486b992bf7bc8c8847692623da
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801765"
---
# <a name="class-mcdremotesystem"></a><span data-ttu-id="75102-104">클래스 `MCDRemoteSystem`</span><span class="sxs-lookup"><span data-stu-id="75102-104">class `MCDRemoteSystem`</span></span> 

```
@interface MCDRemoteSystem : NSObject
```  

<span data-ttu-id="75102-105">원격 시스템을 나타내기 위해 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-105">A class to represent a remote system.</span></span>

## <a name="properties"></a><span data-ttu-id="75102-106">속성</span><span class="sxs-lookup"><span data-stu-id="75102-106">Properties</span></span>

### <a name="kind"></a><span data-ttu-id="75102-107">kind</span><span class="sxs-lookup"><span data-stu-id="75102-107">kind</span></span>
`@property(nonatomic, readonly, nonnull) NSString* kind;`

<span data-ttu-id="75102-108">장치 유형 원격이 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-108">The device type of this remote system.</span></span>

### <a name="systemid"></a><span data-ttu-id="75102-109">systemId</span><span class="sxs-lookup"><span data-stu-id="75102-109">systemId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* systemId;`

<span data-ttu-id="75102-110">이 원격 시스템에 대 한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-110">The identifier for this remote system.</span></span>

### <a name="displayname"></a><span data-ttu-id="75102-111">displayName</span><span class="sxs-lookup"><span data-stu-id="75102-111">displayName</span></span>
`@property(nonatomic, readonly, nonnull) NSString* displayName;`

<span data-ttu-id="75102-112">지정된 된 원격 시스템의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-112">The name of the given remote system.</span></span>

### <a name="status"></a><span data-ttu-id="75102-113">상태</span><span class="sxs-lookup"><span data-stu-id="75102-113">status</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemStatus status;`

<span data-ttu-id="75102-114">이 원격 시스템의 가용성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-114">The status of this remote system's availability.</span></span>

> [!NOTE]
<span data-ttu-id="75102-115">WNS 존재 WNS 알림 유형으로 사용 하는 앱 및 Windows 장치에 대 한 가용성을 보고에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75102-115">WNS presence is used for reporting availability for Windows devices and apps which use WNS as notification type.</span></span>  <span data-ttu-id="75102-116">RemoteSystem 때나 해당 현재 상태를 보고 기본 앱 중 장치 (Windows)를 사용할 수 있는 것으로 간주 됩니다 때 "사용 가능"으로 표시 됩니다으로 사용할 수 있습니다 (iOS 및 Android).</span><span class="sxs-lookup"><span data-stu-id="75102-116">RemoteSystem will be marked as "available" when the device is considered available (Windows) or when one of the underlying apps reports their presence as available (iOS and Android).</span></span> 

### <a name="manufacturerdisplayname"></a><span data-ttu-id="75102-117">manufacturerDisplayName</span><span class="sxs-lookup"><span data-stu-id="75102-117">manufacturerDisplayName</span></span>
`@property(nonatomic, readonly, nonnull) NSString* manufacturerDisplayName;`

<span data-ttu-id="75102-118">지정된 된 원격 시스템의 제조업체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-118">The manufacturer name of the given remote system.</span></span>

### <a name="modeldisplayname"></a><span data-ttu-id="75102-119">modelDisplayName</span><span class="sxs-lookup"><span data-stu-id="75102-119">modelDisplayName</span></span>
`@property(nonatomic, readonly, nonnull) NSString* modelDisplayName;`

<span data-ttu-id="75102-120">지정된 된 원격 시스템의 모델 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-120">The model name of the given remote system.</span></span>

### <a name="apps"></a><span data-ttu-id="75102-121">앱 검색</span><span class="sxs-lookup"><span data-stu-id="75102-121">apps</span></span>
`@property(nonatomic, readonly, nonnull) NSArray<MCDRemoteSystemApp*>* apps;`

<span data-ttu-id="75102-122">연결에 사용할 수 있는이 원격 시스템에서 응용 프로그램의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="75102-122">An array of the applications on this remote system that are available for connectivity.</span></span>

### <a name="platform"></a><span data-ttu-id="75102-123">플랫폼</span><span class="sxs-lookup"><span data-stu-id="75102-123">platform</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemPlatform platform;`

<span data-ttu-id="75102-124">MCDRemoteSystemPlatform 원격 시스템 작업을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="75102-124">The MCDRemoteSystemPlatform managing remote system activity.</span></span>