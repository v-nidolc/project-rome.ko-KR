---
title: MCDConnectedDevicesAccount
description: 이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: e9b43bb76e46f3a027247b1d4d564c6e1571bae4
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800935"
---
# <a name="class-mcdconnecteddevicesaccount"></a><span data-ttu-id="ad779-104">클래스 `MCDConnectedDevicesAccount`</span><span class="sxs-lookup"><span data-stu-id="ad779-104">class `MCDConnectedDevicesAccount`</span></span>

```
@interface MCDConnectedDevicesAccount : NSObject
```  

<span data-ttu-id="ad779-105">이 클래스에는 앱에서 알려진 단일 사용자 계정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-105">This class represents a single user account known by an app.</span></span>

## <a name="properties"></a><span data-ttu-id="ad779-106">속성</span><span class="sxs-lookup"><span data-stu-id="ad779-106">Properties</span></span>

### <a name="anonymousaccount"></a><span data-ttu-id="ad779-107">anonymousAccount</span><span class="sxs-lookup"><span data-stu-id="ad779-107">anonymousAccount</span></span>
`+ (nullable instancetype)anonymousAccount;`

<span data-ttu-id="ad779-108">익명 계정의 singleton 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-108">The singleton instance of the Anonymous account.</span></span>

### <a name="accountid"></a><span data-ttu-id="ad779-109">accountId</span><span class="sxs-lookup"><span data-stu-id="ad779-109">accountId</span></span>
`@property(nonatomic, readonly, copy, nonnull) NSString* accountId;`

<span data-ttu-id="ad779-110">이 사용자 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-110">The unique identifier for this user account.</span></span>

### <a name="type"></a><span data-ttu-id="ad779-111">유형</span><span class="sxs-lookup"><span data-stu-id="ad779-111">type</span></span>
`@property(nonatomic, readonly) MCDConnectedDevicesAccountType type;`

<span data-ttu-id="ad779-112">계정 유형을 설명 하는 MCDConnectedDevicesAccountType 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-112">A MCDConnectedDevicesAccountType value describing the type of account.</span></span>

## <a name="constructors"></a><span data-ttu-id="ad779-113">생성자</span><span class="sxs-lookup"><span data-stu-id="ad779-113">Constructors</span></span>

### <a name="accountwithaccountid"></a><span data-ttu-id="ad779-114">accountWithAccountId</span><span class="sxs-lookup"><span data-stu-id="ad779-114">accountWithAccountId</span></span>
`+ (nullable instancetype)accountWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

<span data-ttu-id="ad779-115">이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ad779-115">A new instance of this class with the unique identifier for this user account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ad779-116">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad779-116">Parameters</span></span> 

* `accountId` 

<span data-ttu-id="ad779-117">이 사용자 계정에 대 한 고유 식별자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-117">A unique identifier string for this user account.</span></span>

`type` 

<span data-ttu-id="ad779-118">계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).</span><span class="sxs-lookup"><span data-stu-id="ad779-118">The MCDConnectedDevicesAccountType of the account (depends on which ID provider the account is from).</span></span>

#### <a name="returns"></a><span data-ttu-id="ad779-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad779-119">Returns</span></span>
<span data-ttu-id="ad779-120">계정 id 사용 하 여 MCDConnectedDevicesAccount 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-120">Returns an MCDConnectedDevicesAccount object with the account identifier.</span></span>

### <a name="initwithaccountid"></a><span data-ttu-id="ad779-121">initWithAccountId</span><span class="sxs-lookup"><span data-stu-id="ad779-121">initWithAccountId</span></span>
`- (nullable instancetype)initWithAccountId:(nullable NSString*)accountId type:(MCDConnectedDevicesAccountType)type;`

<span data-ttu-id="ad779-122">이 사용자 계정에 대 한 고유 식별자를 사용 하 여이 클래스의 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ad779-122">A new instance of this class with the unique identifier for this user account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ad779-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad779-123">Parameters</span></span> 
* `type`

<span data-ttu-id="ad779-124">계정의 MCDConnectedDevicesAccountType (종속는 ID 공급자에서 계정이에서).</span><span class="sxs-lookup"><span data-stu-id="ad779-124">The MCDConnectedDevicesAccountType of the account (depends on which ID provider the account is from).</span></span>

#### <a name="returns"></a><span data-ttu-id="ad779-125">반환 값</span><span class="sxs-lookup"><span data-stu-id="ad779-125">Returns</span></span>
<span data-ttu-id="ad779-126">계정 id를 사용 하 여 초기화 MCDConnectedDevicesAccount 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad779-126">Returns an MCDConnectedDevicesAccount object initialized with the account identifier.</span></span>