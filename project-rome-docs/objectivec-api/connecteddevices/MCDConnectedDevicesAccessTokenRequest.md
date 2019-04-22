---
title: MCDConnectedDevicesAccessTokenRequest
description: 포함 된 범위를 충족 하는 포함 된 MCDConnectedDevicesAccount에 대 한 액세스 토큰에 대 한 요청입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b1cd9b747e98d5e9ccf4885b33897e8c240d7673
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800835"
---
# <a name="class-mcdconnecteddevicesaccesstokenrequest"></a><span data-ttu-id="47652-104">클래스 `MCDConnectedDevicesAccessTokenRequest`</span><span class="sxs-lookup"><span data-stu-id="47652-104">class `MCDConnectedDevicesAccessTokenRequest`</span></span> 

```
@interface MCDConnectedDevicesAccessTokenRequest : NSObject
```  
<span data-ttu-id="47652-105">포함 된 범위를 충족 하는 포함 된 MCDConnectedDevicesAccount에 대 한 액세스 토큰에 대 한 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="47652-105">Request for an access token for the contained MCDConnectedDevicesAccount which satisfies the contained scopes.</span></span>

## <a name="properties"></a><span data-ttu-id="47652-106">속성</span><span class="sxs-lookup"><span data-stu-id="47652-106">Properties</span></span>

### <a name="account"></a><span data-ttu-id="47652-107">계정으로 이동하면</span><span class="sxs-lookup"><span data-stu-id="47652-107">account</span></span>
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

<span data-ttu-id="47652-108">이 MCDConnectedDevicesAccessTokenInvalidatedEventArgs와 연결 된 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="47652-108">The Account associated with this MCDConnectedDevicesAccessTokenInvalidatedEventArgs.</span></span>

### <a name="scopes"></a><span data-ttu-id="47652-109">범위</span><span class="sxs-lookup"><span data-stu-id="47652-109">scopes</span></span>
`@property (nonatomic, readonly, nonnull) NSArray<NSString*>* scopes;`

<span data-ttu-id="47652-110">목록 범위를 생성 하는 경우 토큰 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47652-110">The list of scopes for which the token must cover when generated.</span></span>

## <a name="methods"></a><span data-ttu-id="47652-111">메서드</span><span class="sxs-lookup"><span data-stu-id="47652-111">Methods</span></span>

### <a name="completewithaccesstoken"></a><span data-ttu-id="47652-112">completeWithAccessToken</span><span class="sxs-lookup"><span data-stu-id="47652-112">completeWithAccessToken</span></span>
`- (void) completeWithAccessToken:(NSString* _Nonnull) token;`

<span data-ttu-id="47652-113">요청 된 범위를 사용 하 여 토큰을 생성 하는 경우 요청을 완료 하려면 토큰을 사용 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="47652-113">If a token with the requested scopes was successfully generated, call this method with the token to complete the request.</span></span>

#### <a name="parameters"></a><span data-ttu-id="47652-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47652-114">Parameters</span></span> 
* `token` 

<span data-ttu-id="47652-115">성공적으로 생성 된 토큰</span><span class="sxs-lookup"><span data-stu-id="47652-115">Successfully generated token</span></span>

### <a name="completewitherrormessage"></a><span data-ttu-id="47652-116">completeWithErrorMessage</span><span class="sxs-lookup"><span data-stu-id="47652-116">completeWithErrorMessage</span></span>
`- (void) completeWithErrorMessage:(NSString* _Nullable) errorMessage;`

<span data-ttu-id="47652-117">어떤 이유로 든 요청 된 범위를 사용 하 여 토큰을 성공적으로 생성 되지 않은 경우 로깅에 사용 되는 메시지를 사용 하 여이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="47652-117">If a token with the requested scopes was not successfully generated for any reason, call this method with a message to be used for logging.</span></span>

#### <a name="parameters"></a><span data-ttu-id="47652-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47652-118">Parameters</span></span> 
* `errorMessage`

<span data-ttu-id="47652-119">토큰에 성공 하지 못한 이유에 설명 하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="47652-119">A message describing why the token was unsuccessful.</span></span>