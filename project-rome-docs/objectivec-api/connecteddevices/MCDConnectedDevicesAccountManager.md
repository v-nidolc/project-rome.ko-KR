---
title: MCDConnectedDevicesAccountManager
description: SDK의 모든 계정 관련 기능에 대 한 단일 진입점을 제공합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c265a0c7114704ea6f9ae9818eb9abdb39b5437f
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908395"
---
# <a name="class-mcdconnecteddevicesaccountmanager"></a><span data-ttu-id="d3f26-104">클래스 `MCDConnectedDevicesAccountManager`</span><span class="sxs-lookup"><span data-stu-id="d3f26-104">class `MCDConnectedDevicesAccountManager`</span></span> 

```
@interface MCDConnectedDevicesAccountManager : NSObject
```  
<span data-ttu-id="d3f26-105">SDK의 모든 계정 관련 기능에 대 한 단일 진입점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-105">Provides a single entrypoint for all account-related features in the SDK.</span></span>

## <a name="properties"></a><span data-ttu-id="d3f26-106">속성</span><span class="sxs-lookup"><span data-stu-id="d3f26-106">Properties</span></span>

### <a name="accesstokenrequested"></a><span data-ttu-id="d3f26-107">accessTokenRequested</span><span class="sxs-lookup"><span data-stu-id="d3f26-107">accessTokenRequested</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesAccountManager*, MCDConnectedDevicesAccessTokenRequestedEventArgs*>* accessTokenRequested;`

<span data-ttu-id="d3f26-108">이 이벤트는 토큰을 요청 해야 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-108">This event is fired when there is a need to request a token.</span></span> <span data-ttu-id="d3f26-109">이 이벤트를 구독 하 고 모든 요청을 전송 하기 전에 대응할 수 있도록 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-109">This event should be subscribed and ready to respond before any request is sent out.</span></span>

### <a name="accesstokeninvalidated"></a><span data-ttu-id="d3f26-110">accessTokenInvalidated</span><span class="sxs-lookup"><span data-stu-id="d3f26-110">accessTokenInvalidated</span></span>
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDConnectedDevicesAccountManager*, MCDConnectedDevicesAccessTokenInvalidatedEventArgs*>* accessTokenInvalidated;`

<span data-ttu-id="d3f26-111">이 이벤트는 토큰 소비자 토큰 오류를 보고 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-111">This event is fired when a token consumer reports a token error.</span></span> <span data-ttu-id="d3f26-112">토큰 공급자가 토큰 캐시를 새로 고치거 나 해당 계정 설정을 수정 하려면 새 사용자 로그인을 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-112">The token provider needs to either refresh their token cache or request a new user login to fix their account setup.</span></span>

### <a name="allaccounts"></a><span data-ttu-id="d3f26-113">allAccounts</span><span class="sxs-lookup"><span data-stu-id="d3f26-113">allAccounts</span></span>
`@property (nonatomic, readonly, nonnull) NSArray<MCDConnectedDevicesAccount*>* allAccounts;`

<span data-ttu-id="d3f26-114">현재이 관리자에 의해 추적 되는 모든 MCDConnectedDevicesAccount 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-114">All MCDConnectedDevicesAccount which are currently tracked by this manager.</span></span>

## <a name="methods"></a><span data-ttu-id="d3f26-115">메서드</span><span class="sxs-lookup"><span data-stu-id="d3f26-115">Methods</span></span>

### <a name="addaccountasync"></a><span data-ttu-id="d3f26-116">addAccountAsync</span><span class="sxs-lookup"><span data-stu-id="d3f26-116">addAccountAsync</span></span>
`- (void) addAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account callback:(nonnull void (^)(MCDConnectedDevicesAddAccountResult* _Nonnull, NSError* _Nullable))callback;`

<span data-ttu-id="d3f26-117">계정에 관리자를 추가, 작업이 완료 될 때 콜백이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-117">Add an account to account manager, callback will be invoked when it completes.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d3f26-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3f26-118">Parameters</span></span> 
* `callback`

<span data-ttu-id="d3f26-119">콜백 결과 계정 추가 성공 인지 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-119">The callback result indicates if Account addition is successful or not.</span></span> 

### <a name="removeaccountasync"></a><span data-ttu-id="d3f26-120">removeAccountAsync</span><span class="sxs-lookup"><span data-stu-id="d3f26-120">removeAccountAsync</span></span>
`- (void) removeAccountAsync:(MCDConnectedDevicesAccount* _Nonnull)account callback:(nonnull void (^)(MCDConnectedDevicesRemoveAccountResult* _Nonnull, NSError* _Nullable))callback;`

<span data-ttu-id="d3f26-121">계정 관리자에서 계정 제거, 작업이 완료 될 때 콜백이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-121">Remove an account from account manager, callback will be invoked when it completes.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d3f26-122">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3f26-122">Parameters</span></span> 
* `callback` 

 <span data-ttu-id="d3f26-123">콜백 결과 계정 제거 성공 인지 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3f26-123">The callback result indicates if Account removal is successful or not.</span></span> 