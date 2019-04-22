---
title: MCDRemoteSystemLocalVisibilityKind
description: 원격 시스템을 검색 하는 경우 로컬 응용 프로그램 표시 기본 설정을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 0596b7fa3381a06e6f0cf63b86f9382214564ee8
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801105"
---
# <a name="enum-mcdremotesystemlocalvisibilitykind"></a><span data-ttu-id="2b50c-104">열거형 `MCDRemoteSystemLocalVisibilityKind`</span><span class="sxs-lookup"><span data-stu-id="2b50c-104">enum `MCDRemoteSystemLocalVisibilityKind`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemLocalVisibilityKind)
```  
<span data-ttu-id="2b50c-105">원격 시스템을 검색 하는 경우 로컬 응용 프로그램 표시 기본 설정을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50c-105">Contains values that describe the local application visibility preference when discovering remote systems.</span></span>

## <a name="fields"></a><span data-ttu-id="2b50c-106">필드</span><span class="sxs-lookup"><span data-stu-id="2b50c-106">Fields</span></span>

| <span data-ttu-id="2b50c-107">이름</span><span class="sxs-lookup"><span data-stu-id="2b50c-107">Name</span></span>                              | <span data-ttu-id="2b50c-108">값</span><span class="sxs-lookup"><span data-stu-id="2b50c-108">Value</span></span> | <span data-ttu-id="2b50c-109">설명</span><span class="sxs-lookup"><span data-stu-id="2b50c-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="2b50c-110">MCDRemoteSystemLocalVisibilityKindShowAll</span><span class="sxs-lookup"><span data-stu-id="2b50c-110">MCDRemoteSystemLocalVisibilityKindShowAll</span></span> | <span data-ttu-id="2b50c-111">0</span><span class="sxs-lookup"><span data-stu-id="2b50c-111">0</span></span> | <span data-ttu-id="2b50c-112">호출 앱 등 모든 검색 가능한 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b50c-112">Show all discoverable applications, including the calling app.</span></span>
| <span data-ttu-id="2b50c-113">MCDRemoteSystemLocalVisibilityKindHideLocalApp</span><span class="sxs-lookup"><span data-stu-id="2b50c-113">MCDRemoteSystemLocalVisibilityKindHideLocalApp</span></span> | <span data-ttu-id="2b50c-114">1</span><span class="sxs-lookup"><span data-stu-id="2b50c-114">1</span></span> | <span data-ttu-id="2b50c-115">호출 응용 프로그램을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b50c-115">Hide the calling application.</span></span>