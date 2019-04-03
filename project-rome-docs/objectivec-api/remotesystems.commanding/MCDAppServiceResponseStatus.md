---
title: MCDAppServiceResponseStatus
description: 원격 앱 서비스에서 응답 메시지의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 395c2669af7178ef90ff7fd2dc8bafe9b1044028
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908945"
---
# <a name="enum-mcdappserviceresponsestatus"></a><span data-ttu-id="20243-104">열거형 `MCDAppServiceResponseStatus`</span><span class="sxs-lookup"><span data-stu-id="20243-104">enum `MCDAppServiceResponseStatus`</span></span>

```
typedef NS_ENUM(NSInteger, MCDAppServiceResponseStatus)
```

<span data-ttu-id="20243-105">원격 앱 서비스에서 응답 메시지의 상태를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="20243-105">Contains values that describe the status of a response message from a remote app service.</span></span>

|<span data-ttu-id="20243-106">이름</span><span class="sxs-lookup"><span data-stu-id="20243-106">Name</span></span>         | <span data-ttu-id="20243-107">값</span><span class="sxs-lookup"><span data-stu-id="20243-107">Value</span></span>  | <span data-ttu-id="20243-108">설명</span><span class="sxs-lookup"><span data-stu-id="20243-108">Description</span></span>    |                           
|--------|-------------|-----|
|<span data-ttu-id="20243-109">MCDAppServiceResponseStatusSuccess</span><span class="sxs-lookup"><span data-stu-id="20243-109">MCDAppServiceResponseStatusSuccess</span></span> |<span data-ttu-id="20243-110">0</span><span class="sxs-lookup"><span data-stu-id="20243-110">0</span></span>| <span data-ttu-id="20243-111">App service는 성공적으로 수신 하 고 메시지를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="20243-111">The app service successfully received and processed the message.</span></span>|
|<span data-ttu-id="20243-112">MCDAppServiceResponseStatusFailure</span><span class="sxs-lookup"><span data-stu-id="20243-112">MCDAppServiceResponseStatusFailure</span></span> |<span data-ttu-id="20243-113">1</span><span class="sxs-lookup"><span data-stu-id="20243-113">1</span></span>| <span data-ttu-id="20243-114">App service를 받고 메시지를 처리 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="20243-114">The app service failed to receive and process the message.</span></span>|
|<span data-ttu-id="20243-115">MCDAppServiceResponseStatusResourceLimitsExceeded</span><span class="sxs-lookup"><span data-stu-id="20243-115">MCDAppServiceResponseStatusResourceLimitsExceeded</span></span> |<span data-ttu-id="20243-116">2</span><span class="sxs-lookup"><span data-stu-id="20243-116">2</span></span>| <span data-ttu-id="20243-117">App service에는 사용 가능한 리소스가 부족 했기 때문에 종료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20243-117">The app service exited because not enough resources were available.</span></span>|
|<span data-ttu-id="20243-118">MCDAppServiceResponseStatusUnknown</span><span class="sxs-lookup"><span data-stu-id="20243-118">MCDAppServiceResponseStatusUnknown</span></span> |<span data-ttu-id="20243-119">3</span><span class="sxs-lookup"><span data-stu-id="20243-119">3</span></span>| <span data-ttu-id="20243-120">알 수 없는 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="20243-120">An unknown error occurred.</span></span>|
|<span data-ttu-id="20243-121">MCDAppServiceResponseStatusRemoteSystemUnavailable</span><span class="sxs-lookup"><span data-stu-id="20243-121">MCDAppServiceResponseStatusRemoteSystemUnavailable</span></span> |<span data-ttu-id="20243-122">4</span><span class="sxs-lookup"><span data-stu-id="20243-122">4</span></span>| <span data-ttu-id="20243-123">메시지를 보낸 장치를 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="20243-123">The device to which the message was sent is not available.</span></span>|
|<span data-ttu-id="20243-124">MCDAppServiceResponseStatusMessageTooLarge</span><span class="sxs-lookup"><span data-stu-id="20243-124">MCDAppServiceResponseStatusMessageTooLarge</span></span> |<span data-ttu-id="20243-125">5</span><span class="sxs-lookup"><span data-stu-id="20243-125">5</span></span>| <span data-ttu-id="20243-126">App service는 너무 크기 때문에 메시지를 처리 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="20243-126">The app service failed to process the message because it is too large.</span></span>|
|<span data-ttu-id="20243-127">MCDAppServiceResponseStatusAppServiceConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="20243-127">MCDAppServiceResponseStatusAppServiceConnectionClosed</span></span>|<span data-ttu-id="20243-128">6</span><span class="sxs-lookup"><span data-stu-id="20243-128">6</span></span>| <span data-ttu-id="20243-129">앱 서비스 연결에는 응답이 보내지기 전에 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="20243-129">The app service connection was closed before a response was sent.</span></span>|