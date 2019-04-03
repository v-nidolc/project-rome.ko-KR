---
title: MCDRemoteSystemConnectionRequest
description: 특정 원격 장치 또는 응용 프로그램을 사용 하 여 통신 시도 나타내는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 54ed7deb1fa2b1c87a3195e61c2ce031d6e0cea9
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907135"
---
# <a name="class-mcdremotesystemconnectionrequest"></a><span data-ttu-id="d587d-104">클래스 `MCDRemoteSystemConnectionRequest`</span><span class="sxs-lookup"><span data-stu-id="d587d-104">class `MCDRemoteSystemConnectionRequest`</span></span> 

```
@interface MCDRemoteSystemConnectionRequest : NSObject
```  

<span data-ttu-id="d587d-105">특정 원격 장치 또는 응용 프로그램을 사용 하 여 통신 시도 나타내는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-105">A class that represents an attempt to communicate with a specific remote device or application.</span></span>

## <a name="constructors"></a><span data-ttu-id="d587d-106">생성자</span><span class="sxs-lookup"><span data-stu-id="d587d-106">Constructors</span></span>

### <a name="requestwithremotesystem"></a><span data-ttu-id="d587d-107">requestWithRemoteSystem</span><span class="sxs-lookup"><span data-stu-id="d587d-107">requestWithRemoteSystem</span></span>
`+ (instancetype)requestWithRemoteSystem:(nonnull MCDRemoteSystem*)remoteSystem;`

<span data-ttu-id="d587d-108">초기화 된 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 사용 하 여를 [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d587d-108">Initializes the [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) with a [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) instance.</span></span> <span data-ttu-id="d587d-109">이 생성자는 앱을 대상으로 지정 하지 않습니다 하 고 시스템으로 전송 하는 서비스 요청에 선택 된 예기치 않은 앱에서 발생할 수 있으므로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-109">This constructor is not recommended, as it does not specify an app to target and therefore may result in an unexpected app being selected to service requests sent to the system.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d587d-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d587d-110">Parameters</span></span>
* `remoteSystem` 

<span data-ttu-id="d587d-111">원격 시스템에이 연결 요청에서 대상으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-111">The remote system to be targeted in this connection request.</span></span>

#### <a name="returns"></a><span data-ttu-id="d587d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="d587d-112">Returns</span></span>
<span data-ttu-id="d587d-113">초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-113">Returns the initialized [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) if successful, otherwise nil.</span></span>

### <a name="requestwithremotesystemapp"></a><span data-ttu-id="d587d-114">requestWithRemoteSystemApp</span><span class="sxs-lookup"><span data-stu-id="d587d-114">requestWithRemoteSystemApp</span></span>
`+ (instancetype)requestWithRemoteSystemApp:(nonnull MCDRemoteSystemApp*)remoteSystemApp;`

<span data-ttu-id="d587d-115">페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-115">Creates and initializes a new instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d587d-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d587d-116">Parameters</span></span>
* `remoteSystemApp` 

<span data-ttu-id="d587d-117">이 연결 요청에서 대상으로 할 원격 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-117">The remote app to be targeted in this connection request.</span></span>

#### <a name="returns"></a><span data-ttu-id="d587d-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="d587d-118">Returns</span></span>
<span data-ttu-id="d587d-119">초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-119">Returns the initialized [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) if successful, otherwise nil.</span></span>

### <a name="initwithremotesystem"></a><span data-ttu-id="d587d-120">initWithRemoteSystem</span><span class="sxs-lookup"><span data-stu-id="d587d-120">initWithRemoteSystem</span></span>
`- (nullable instancetype)initWithRemoteSystem:(nonnull MCDRemoteSystem*)remoteSystem;`

<span data-ttu-id="d587d-121">초기화 된 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 사용 하 여를 [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d587d-121">Initializes the [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) with a [MCDRemoteSystem](../remotesystems/MCDRemoteSystem.md) instance.</span></span> <span data-ttu-id="d587d-122">이 생성자는 앱을 대상으로 지정 하지 않습니다 하 고 시스템으로 전송 하는 서비스 요청에 선택 된 예기치 않은 앱에서 발생할 수 있으므로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-122">This constructor is not recommended, as it does not specify an app to target and therefore may result in an unexpected app being selected to service requests sent to the system.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d587d-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d587d-123">Parameters</span></span>
* <span data-ttu-id="d587d-124">`remoteSystem` 원격 시스템에이 연결 요청에서 대상으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-124">`remoteSystem` The remote system to be targeted in this connection request.</span></span>

#### <a name="returns"></a><span data-ttu-id="d587d-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="d587d-125">Returns</span></span>
<span data-ttu-id="d587d-126">초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-126">Returns the initialized [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) if successful, otherwise nil.</span></span>

### <a name="initwithremotesystemapp"></a><span data-ttu-id="d587d-127">initWithRemoteSystemApp</span><span class="sxs-lookup"><span data-stu-id="d587d-127">initWithRemoteSystemApp</span></span>
`- (nullable instancetype)initWithRemoteSystemApp:(nonnull MCDRemoteSystemApp*)remoteSystemApp;`

<span data-ttu-id="d587d-128">페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-128">Creates and initializes a new instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d587d-129">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d587d-129">Parameters</span></span>
* `remoteSystemApp` 

<span data-ttu-id="d587d-130">이 연결 요청에서 대상으로 할 원격 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-130">The remote app to be targeted in this connection request.</span></span>

#### <a name="returns"></a><span data-ttu-id="d587d-131">반환 값</span><span class="sxs-lookup"><span data-stu-id="d587d-131">Returns</span></span>
<span data-ttu-id="d587d-132">초기화 반환 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="d587d-132">Returns the initialized [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md) if successful, otherwise nil.</span></span>