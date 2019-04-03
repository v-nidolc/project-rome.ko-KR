---
title: MCDRemoteSystemAuthorizationKind
description: 원격 시스템 검색에 대 한 잠재적인 권한 부여 종류 (사용자 계정 기반 권한 부여 범위)를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4f54d187282e946dd2912d1d72eacc02c7ee4077
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907635"
---
# <a name="enum-mcdremotesystemauthorizationkind"></a><span data-ttu-id="2ffaf-104">열거형 `MCDRemoteSystemAuthorizationKind`</span><span class="sxs-lookup"><span data-stu-id="2ffaf-104">enum `MCDRemoteSystemAuthorizationKind`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemAuthorizationKind)
```  

<span data-ttu-id="2ffaf-105">원격 시스템 검색에 대 한 잠재적인 권한 부여 종류 (사용자 계정 기반 권한 부여 범위)를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-105">Contains values that describe the potential authorization kinds (user-account-based authorization scopes) for remote system discovery.</span></span> 

## <a name="fields"></a><span data-ttu-id="2ffaf-106">필드</span><span class="sxs-lookup"><span data-stu-id="2ffaf-106">Fields</span></span>

| <span data-ttu-id="2ffaf-107">이름</span><span class="sxs-lookup"><span data-stu-id="2ffaf-107">Name</span></span>                              | <span data-ttu-id="2ffaf-108">값</span><span class="sxs-lookup"><span data-stu-id="2ffaf-108">Value</span></span> | <span data-ttu-id="2ffaf-109">설명</span><span class="sxs-lookup"><span data-stu-id="2ffaf-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="2ffaf-110">MCDRemoteSystemAuthorizationKindSameUser</span><span class="sxs-lookup"><span data-stu-id="2ffaf-110">MCDRemoteSystemAuthorizationKindSameUser</span></span>   | <span data-ttu-id="2ffaf-111">0</span><span class="sxs-lookup"><span data-stu-id="2ffaf-111">0</span></span>     | <span data-ttu-id="2ffaf-112">만 시스템 검색 하 고 동일한 사용자 계정으로 로그온 하는 장치를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-112">The system can only discover and connect with devices signed onto by the same user account.</span></span>   |
| <span data-ttu-id="2ffaf-113">MCDRemoteSystemAuthorizationKindAnonymous</span><span class="sxs-lookup"><span data-stu-id="2ffaf-113">MCDRemoteSystemAuthorizationKindAnonymous</span></span> | <span data-ttu-id="2ffaf-114">1</span><span class="sxs-lookup"><span data-stu-id="2ffaf-114">1</span></span>     | <span data-ttu-id="2ffaf-115">시스템 검색 하 고 근접에서 되며 익명 검색을 허용 하는 제공 다른 사용자의 장치를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ffaf-115">The system can discover and connect with other users' devices, provided they are in proximity and allow anonymous discovery.</span></span>  |

