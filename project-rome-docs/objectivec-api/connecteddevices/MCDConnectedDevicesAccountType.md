---
title: MCDConnectedDevicesAccountType
description: Microsoft에서 제공한 사용자 계정의 유형을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5461398e3725b7a1e6937172c40336db60432666
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908905"
---
# <a name="enum-mcdconnecteddevicesaccounttype"></a><span data-ttu-id="034ba-104">열거형 `MCDConnectedDevicesAccountType`</span><span class="sxs-lookup"><span data-stu-id="034ba-104">enum `MCDConnectedDevicesAccountType`</span></span>

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesAccountType)
```  

<span data-ttu-id="034ba-105">Microsoft에서 제공한 사용자 계정의 유형을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="034ba-105">Contains values that describe the type of Microsoft-provided user account.</span></span>

## <a name="fields"></a><span data-ttu-id="034ba-106">필드</span><span class="sxs-lookup"><span data-stu-id="034ba-106">Fields</span></span>

| <span data-ttu-id="034ba-107">이름</span><span class="sxs-lookup"><span data-stu-id="034ba-107">Name</span></span>                              | <span data-ttu-id="034ba-108">값</span><span class="sxs-lookup"><span data-stu-id="034ba-108">Value</span></span> | <span data-ttu-id="034ba-109">설명</span><span class="sxs-lookup"><span data-stu-id="034ba-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="034ba-110">MCDConnectedDevicesAccountTypeAAD</span><span class="sxs-lookup"><span data-stu-id="034ba-110">MCDConnectedDevicesAccountTypeAAD</span></span>       | <span data-ttu-id="034ba-111">0</span><span class="sxs-lookup"><span data-stu-id="034ba-111">0</span></span>     | <span data-ttu-id="034ba-112">Azure Active Directory workplace 계정</span><span class="sxs-lookup"><span data-stu-id="034ba-112">Azure Active Directory workplace Account</span></span>  |
| <span data-ttu-id="034ba-113">MCDConnectedDevicesAccountTypeMSA</span><span class="sxs-lookup"><span data-stu-id="034ba-113">MCDConnectedDevicesAccountTypeMSA</span></span>       | <span data-ttu-id="034ba-114">1</span><span class="sxs-lookup"><span data-stu-id="034ba-114">1</span></span>     | <span data-ttu-id="034ba-115">Microsoft 개인 계정</span><span class="sxs-lookup"><span data-stu-id="034ba-115">Microsoft Personal Account</span></span> |
| <span data-ttu-id="034ba-116">MCDConnectedDevicesAccountTypeAnonymous</span><span class="sxs-lookup"><span data-stu-id="034ba-116">MCDConnectedDevicesAccountTypeAnonymous</span></span> | <span data-ttu-id="034ba-117">2</span><span class="sxs-lookup"><span data-stu-id="034ba-117">2</span></span>     | <span data-ttu-id="034ba-118">익명 (로컬, 인증 되지 않은) 계정</span><span class="sxs-lookup"><span data-stu-id="034ba-118">Anonymous (local, non-authenticated) Account</span></span> |