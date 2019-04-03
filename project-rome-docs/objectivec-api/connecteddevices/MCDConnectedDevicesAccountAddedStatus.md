---
title: MCDConnectedDevicesAccountAddedStatus
description: 추가 계정 작업 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: d7fadec0c3e69eedab23df18d803ee85fd37644b
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907205"
---
# <a name="enum-mcdconnecteddevicesaccountaddedstatus"></a><span data-ttu-id="30c98-104">열거형 `MCDConnectedDevicesAccountAddedStatus`</span><span class="sxs-lookup"><span data-stu-id="30c98-104">enum `MCDConnectedDevicesAccountAddedStatus`</span></span>

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesAccountAddedStatus)
```  
<span data-ttu-id="30c98-105">추가 계정 작업 상태를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-105">Contains the values that describe the add account operation status.</span></span>

## <a name="fields"></a><span data-ttu-id="30c98-106">필드</span><span class="sxs-lookup"><span data-stu-id="30c98-106">Fields</span></span>

| <span data-ttu-id="30c98-107">이름</span><span class="sxs-lookup"><span data-stu-id="30c98-107">Name</span></span>                              |   <span data-ttu-id="30c98-108">값</span><span class="sxs-lookup"><span data-stu-id="30c98-108">Value</span></span>     | <span data-ttu-id="30c98-109">설명</span><span class="sxs-lookup"><span data-stu-id="30c98-109">Description</span></span> |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="30c98-110">MCDConnectedDevicesAccountAddedStatusSuccess</span><span class="sxs-lookup"><span data-stu-id="30c98-110">MCDConnectedDevicesAccountAddedStatusSuccess</span></span> | <span data-ttu-id="30c98-111">0</span><span class="sxs-lookup"><span data-stu-id="30c98-111">0</span></span> | <span data-ttu-id="30c98-112">플랫폼에 계정을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-112">The account was successfully added to the platform.</span></span> |
| <span data-ttu-id="30c98-113">MCDConnectedDevicesAccountAddedStatusErrorNoNetwork</span><span class="sxs-lookup"><span data-stu-id="30c98-113">MCDConnectedDevicesAccountAddedStatusErrorNoNetwork</span></span> | <span data-ttu-id="30c98-114">1</span><span class="sxs-lookup"><span data-stu-id="30c98-114">1</span></span> | <span data-ttu-id="30c98-115">로마 검색 네트워크 액세스 권한이 없는 계정 작업에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-115">The account operation failed since Rome detected no network access.</span></span> |
| <span data-ttu-id="30c98-116">MCDConnectedDevicesAccountAddedStatusErrorServiceFailed</span><span class="sxs-lookup"><span data-stu-id="30c98-116">MCDConnectedDevicesAccountAddedStatusErrorServiceFailed</span></span> | <span data-ttu-id="30c98-117">2</span><span class="sxs-lookup"><span data-stu-id="30c98-117">2</span></span> | <span data-ttu-id="30c98-118">로마 웹 서비스에 연결할 수 없습니다. 계정 작업에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-118">The account operation failed since Rome was unable to contact web services.</span></span> |
| <span data-ttu-id="30c98-119">MCDConnectedDevicesAccountAddedStatusErrorNoTokenRequestSubscriber</span><span class="sxs-lookup"><span data-stu-id="30c98-119">MCDConnectedDevicesAccountAddedStatusErrorNoTokenRequestSubscriber</span></span> | <span data-ttu-id="30c98-120">3</span><span class="sxs-lookup"><span data-stu-id="30c98-120">3</span></span> | <span data-ttu-id="30c98-121">앱 AccessTokenRequested 이벤트를 구독 하지 않은 계정 작업에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-121">The account operation failed since the app didn't subscribe to the AccessTokenRequested event.</span></span> |
| <span data-ttu-id="30c98-122">MCDConnectedDevicesAccountAddedStatusErrorTokenRequestFailed</span><span class="sxs-lookup"><span data-stu-id="30c98-122">MCDConnectedDevicesAccountAddedStatusErrorTokenRequestFailed</span></span> | <span data-ttu-id="30c98-123">4</span><span class="sxs-lookup"><span data-stu-id="30c98-123">4</span></span> | <span data-ttu-id="30c98-124">앱 토큰을 요청할 때 반환 하지 못했습니다 계정 작업에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-124">The account operation failed since the app failed to return a token when requested.</span></span> |
| <span data-ttu-id="30c98-125">MCDConnectedDevicesAccountAddedStatusErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="30c98-125">MCDConnectedDevicesAccountAddedStatusErrorUnknown</span></span> | <span data-ttu-id="30c98-126">5</span><span class="sxs-lookup"><span data-stu-id="30c98-126">5</span></span> | <span data-ttu-id="30c98-127">알 수 없는 이유로 계정 작업이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="30c98-127">The account operation failed for unknown reasons.</span></span> |
