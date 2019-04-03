---
title: MCDConnectedDevicesAccount
description: 이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: e9b43bb76e46f3a027247b1d4d564c6e1571bae4
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909155"
---
# <a name="class-mcdconnecteddevicesaccount"></a><span data-ttu-id="dc81d-104">클래스 `MCDConnectedDevicesAccount`</span><span class="sxs-lookup"><span data-stu-id="dc81d-104">class `MCDConnectedDevicesAccount`</span></span>

```
@interface MCDConnectedDevicesAccount : NSObject
```  

<span data-ttu-id="dc81d-105">이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-105">This class represents a single user account known by an app.</span></span>

## <a name="properties"></a><span data-ttu-id="dc81d-106">속성</span><span class="sxs-lookup"><span data-stu-id="dc81d-106">Properties</span></span>

### <a name="anonymousaccount"></a><span data-ttu-id="dc81d-107">anonymousAccount</span><span class="sxs-lookup"><span data-stu-id="dc81d-107">anonymousAccount</span></span>
`+ (nullable instancetype)anonymousAccount;`

<span data-ttu-id="dc81d-108">익명 계정의 singleton 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-108">The singleton instance of the Anonymous account.</span></span>

### <a name="accountid"></a><span data-ttu-id="dc81d-109">accountId</span><span class="sxs-lookup"><span data-stu-id="dc81d-109">accountId</span></span>
`@property(nonatomic, readonly, copy, nonnull) NSString* accountId;`

<span data-ttu-id="dc81d-110">이 사용자 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-110">The unique identifier for this user account.</span></span>

### <a name="type"></a><span data-ttu-id="dc81d-111">유형</span><span class="sxs-lookup"><span data-stu-id="dc81d-111">type</span></span>
`@property(nonatomic, readonly) MCDConnectedDevicesAccountType type;`

<span data-ttu-id="dc81d-112">계정 유형을 설명 하는 MCDConnectedDevicesAccountType 값입니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-112">A MCDConnectedDevicesAccountType value describing the type of account.</span></span>

## <a name="constructors"></a><span data-ttu-id="dc81d-113">생성자</span><span class="sxs-lookup"><span data-stu-id="dc81d-113">Constructors</span></span>

### <a name="accountwithaccountid"></a><span data-ttu-id="dc81d-114">accountWithAccountId</span><span class="sxs-lookup"><span data-stu-id="dc81d-114">accountWithAccountId</span></span>
`+ (nullable instancetype)accountWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

<span data-ttu-id="dc81d-115">이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="dc81d-115">A new instance of this class with the unique identifier for this user account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="dc81d-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc81d-116">Parameters</span></span> 

* `accountId` 

<span data-ttu-id="dc81d-117">이 사용자 계정에 대 한 고유 식별자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-117">A unique identifier string for this user account.</span></span>

`type` 

<span data-ttu-id="dc81d-118">계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).</span><span class="sxs-lookup"><span data-stu-id="dc81d-118">The MCDConnectedDevicesAccountType of the account (depends on which ID provider the account is from).</span></span>

#### <a name="returns"></a><span data-ttu-id="dc81d-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc81d-119">Returns</span></span>
<span data-ttu-id="dc81d-120">계정 id 사용 하 여 MCDConnectedDevicesAccount 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-120">Returns an MCDConnectedDevicesAccount object with the account identifier.</span></span>

### <a name="initwithaccountid"></a><span data-ttu-id="dc81d-121">initWithAccountId</span><span class="sxs-lookup"><span data-stu-id="dc81d-121">initWithAccountId</span></span>
`- (nullable instancetype)initWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

<span data-ttu-id="dc81d-122">이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="dc81d-122">A new instance of this class with the unique identifier for this user account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="dc81d-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc81d-123">Parameters</span></span> 
* `type`

<span data-ttu-id="dc81d-124">계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).</span><span class="sxs-lookup"><span data-stu-id="dc81d-124">The MCDConnectedDevicesAccountType of the account (depends on which ID provider the account is from).</span></span>

#### <a name="returns"></a><span data-ttu-id="dc81d-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="dc81d-125">Returns</span></span>
<span data-ttu-id="dc81d-126">계정 id를 사용 하 여 초기화 MCDConnectedDevicesAccount 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc81d-126">Returns an MCDConnectedDevicesAccount object initialized with the account identifier.</span></span>