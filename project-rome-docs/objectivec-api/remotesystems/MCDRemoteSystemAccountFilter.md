---
title: MCDRemoteSystemAccountFilter
description: 사용 하 여 원격 시스템 검색 계정에 대 한 필터입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 34721c2dee89adc380b721a027382f81c2ecb751
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907325"
---
# <a name="class-mcdremotesystemaccountfilter"></a><span data-ttu-id="32ff4-104">클래스 `MCDRemoteSystemAccountFilter`</span><span class="sxs-lookup"><span data-stu-id="32ff4-104">class `MCDRemoteSystemAccountFilter`</span></span> 

```
@interface MCDRemoteSystemAccountFilter : NSObject<MCDRemoteSystemFilter>
```  

<span data-ttu-id="32ff4-105">사용 하 여 원격 시스템 검색 계정에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-105">Filter for the accounts to discover remote systems with.</span></span>

## <a name="properties"></a><span data-ttu-id="32ff4-106">속성</span><span class="sxs-lookup"><span data-stu-id="32ff4-106">Properties</span></span>

### <a name="account"></a><span data-ttu-id="32ff4-107">계정으로 이동하면</span><span class="sxs-lookup"><span data-stu-id="32ff4-107">account</span></span>
`@property(nonatomic, readonly, strong, nonnull) MCDConnectedDevicesAccount* account;`

<span data-ttu-id="32ff4-108">이 MCDRemoteSystemAccountFilter와 연결 된 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-108">The Account associated with this MCDRemoteSystemAccountFilter.</span></span>

## <a name="constructors"></a><span data-ttu-id="32ff4-109">생성자</span><span class="sxs-lookup"><span data-stu-id="32ff4-109">Constructors</span></span>

### <a name="filterwithaccount"></a><span data-ttu-id="32ff4-110">filterWithAccount</span><span class="sxs-lookup"><span data-stu-id="32ff4-110">filterWithAccount</span></span>
`+ (nullable instancetype)filterWithAccount:(nonnull MCDConnectedDevicesAccount*)account;`

<span data-ttu-id="32ff4-111">MCDConnectedDevicesAccount 계정 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-111">Initialize the class with the MCDConnectedDevicesAccount account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="32ff4-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32ff4-112">Parameters</span></span> 
* `account` 

<span data-ttu-id="32ff4-113">사용 중인 MCDConnectedDevicesAccount 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-113">The MCDConnectedDevicesAccount account being used.</span></span>

#### <a name="returns"></a><span data-ttu-id="32ff4-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="32ff4-114">Returns</span></span>
<span data-ttu-id="32ff4-115">계정을 사용 하 여 필터링 MCDRemoteSystemAccountFilter 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-115">Returns a MCDRemoteSystemAccountFilter object filtered with the Account.</span></span>

### <a name="initwithaccount"></a><span data-ttu-id="32ff4-116">initWithAccount</span><span class="sxs-lookup"><span data-stu-id="32ff4-116">initWithAccount</span></span>
`- (nullable instancetype)initWithAccount:(nonnull MCDConnectedDevicesAccount*)account;`

<span data-ttu-id="32ff4-117">MCDConnectedDevicesAccount 계정 사용 하 여 클래스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-117">Initialize the class with the MCDConnectedDevicesAccount account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="32ff4-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32ff4-118">Parameters</span></span> 
* `account` 

<span data-ttu-id="32ff4-119">사용 중인 MCDConnectedDevicesAccount 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-119">The MCDConnectedDevicesAccount account being used.</span></span>

#### <a name="returns"></a><span data-ttu-id="32ff4-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="32ff4-120">Returns</span></span>
<span data-ttu-id="32ff4-121">반환 MCDRemoteSystemAccountFilter 개체 초기화 계정을 사용 하 여 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ff4-121">Returns an MCDRemoteSystemAccountFilter object initialized filtered with the Account.</span></span>