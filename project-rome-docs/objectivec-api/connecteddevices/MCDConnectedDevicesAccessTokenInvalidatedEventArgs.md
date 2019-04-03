---
title: MCDConnectedDevicesAccessTokenInvalidatedEventArgs
description: ConnectedDevicesAccount와 연결 된 해당 토큰을 토큰 오류를 보고 알립니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 46a21b534e2b3a5fb588e40af2dbc4eb47143873
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907495"
---
# <a name="class-mcdconnecteddevicesaccesstokeninvalidatedeventargs"></a><span data-ttu-id="38df9-104">클래스 `MCDConnectedDevicesAccessTokenInvalidatedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="38df9-104">class `MCDConnectedDevicesAccessTokenInvalidatedEventArgs`</span></span> 

```
@interface MCDConnectedDevicesAccessTokenInvalidatedEventArgs : NSObject 
```  
<span data-ttu-id="38df9-105">MCDConnectedDevicesAccount MCDConnectedDevicesAccount 연관 된 토큰에 포함 된 범위에 대 한 토큰 오류 보고는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df9-105">Returned by MCDConnectedDevicesAccount to inform that the token associated with MCDConnectedDevicesAccount reported token error for the contained scopes.</span></span> <span data-ttu-id="38df9-106">토큰 공급자가 토큰 캐시를 새로 고치거 나 잠재적으로 사용자에 게 자신의 계정 설정을 수정 하려면 로그인을 요청 하는 UI를 팝업에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df9-106">Token provider needs to either refresh their token cache or potentially pop up UI to ask user to sign in in order to fix their account setup.</span></span>

## <a name="properties"></a><span data-ttu-id="38df9-107">속성</span><span class="sxs-lookup"><span data-stu-id="38df9-107">Properties</span></span>

### <a name="account"></a><span data-ttu-id="38df9-108">계정으로 이동하면</span><span class="sxs-lookup"><span data-stu-id="38df9-108">account</span></span>
`@property (nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

<span data-ttu-id="38df9-109">이 MCDConnectedDevicesAccessTokenInvalidatedEventArgs와 연결 된 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="38df9-109">The Account associated with this MCDConnectedDevicesAccessTokenInvalidatedEventArgs.</span></span>

### <a name="scopes"></a><span data-ttu-id="38df9-110">범위</span><span class="sxs-lookup"><span data-stu-id="38df9-110">scopes</span></span>
`@property (nonatomic, readonly, nonnull) NSArray<NSString*>* scopes;`

<span data-ttu-id="38df9-111">목록 범위를 생성 하는 경우 토큰 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df9-111">The list of scopes for which the token must cover when generated.</span></span>