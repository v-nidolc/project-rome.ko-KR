---
title: MCDRemoteSystemAppRegistrationPublishStatus
description: URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 32c3e473938925f12838bf6dc5ccc3e98a3394a6
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800585"
---
# <a name="enum-mcdremotesystemappregistrationpublishstatus"></a><span data-ttu-id="8153f-104">열거형 `MCDRemoteSystemAppRegistrationPublishStatus`</span><span class="sxs-lookup"><span data-stu-id="8153f-104">enum `MCDRemoteSystemAppRegistrationPublishStatus`</span></span>

`typedef NS_ENUM(NSInteger, MCDRemoteSystemAppRegistrationPublishStatus)`

<span data-ttu-id="8153f-105">게시 작업의 상태를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-105">Enumeration indicating the status of the publish operation.</span></span>
<span data-ttu-id="8153f-106">오류 상태에는 게시를 다시 시도 하려면 앱 개발자 저장할 수 있습니다 하는 일시적인 조건을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-106">The error statuses indicate transient conditions where the app developer may want to retry publishing.</span></span>

| <span data-ttu-id="8153f-107">이름</span><span class="sxs-lookup"><span data-stu-id="8153f-107">Name</span></span>    |<span data-ttu-id="8153f-108">값</span><span class="sxs-lookup"><span data-stu-id="8153f-108">Value</span></span>   |<span data-ttu-id="8153f-109">설명</span><span class="sxs-lookup"><span data-stu-id="8153f-109">Description</span></span>   |                  
|------ |------- |--|
|<span data-ttu-id="8153f-110">MCDRemoteSystemAppRegistrationPublishStatusSuccess</span><span class="sxs-lookup"><span data-stu-id="8153f-110">MCDRemoteSystemAppRegistrationPublishStatusSuccess</span></span> | <span data-ttu-id="8153f-111">0</span><span class="sxs-lookup"><span data-stu-id="8153f-111">0</span></span> | <span data-ttu-id="8153f-112">작업이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-112">Operation completed successfully.</span></span>|
|<span data-ttu-id="8153f-113">MCDRemoteSystemAppRegistrationPublishStatusErrorNoNetwork</span><span class="sxs-lookup"><span data-stu-id="8153f-113">MCDRemoteSystemAppRegistrationPublishStatusErrorNoNetwork</span></span> | <span data-ttu-id="8153f-114">1</span><span class="sxs-lookup"><span data-stu-id="8153f-114">1</span></span> | <span data-ttu-id="8153f-115">네트워크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-115">Network was unavailable.</span></span> |
|<span data-ttu-id="8153f-116">MCDRemoteSystemAppRegistrationPublishStatusErrorWebFailure</span><span class="sxs-lookup"><span data-stu-id="8153f-116">MCDRemoteSystemAppRegistrationPublishStatusErrorWebFailure</span></span> | <span data-ttu-id="8153f-117">2</span><span class="sxs-lookup"><span data-stu-id="8153f-117">2</span></span> | <span data-ttu-id="8153f-118">웹 서비스에는 다음이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-118">A web service failed.</span></span>|
|<span data-ttu-id="8153f-119">MCDRemoteSystemAppRegistrationPublishStatusErrorNoTokenRequestSubscriber</span><span class="sxs-lookup"><span data-stu-id="8153f-119">MCDRemoteSystemAppRegistrationPublishStatusErrorNoTokenRequestSubscriber</span></span> | <span data-ttu-id="8153f-120">3</span><span class="sxs-lookup"><span data-stu-id="8153f-120">3</span></span> | <span data-ttu-id="8153f-121">구독자가 없는 토큰 요청에 응답 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-121">No token request subscribers responded.</span></span>|
|<span data-ttu-id="8153f-122">MCDRemoteSystemAppRegistrationPublishStatusErrorTokenRequestFailed</span><span class="sxs-lookup"><span data-stu-id="8153f-122">MCDRemoteSystemAppRegistrationPublishStatusErrorTokenRequestFailed</span></span> | <span data-ttu-id="8153f-123">4</span><span class="sxs-lookup"><span data-stu-id="8153f-123">4</span></span> | <span data-ttu-id="8153f-124">토큰 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-124">The token request failed.</span></span>|
|<span data-ttu-id="8153f-125">MCDRemoteSystemAppRegistrationPublishStatusErrorAccountNotFound</span><span class="sxs-lookup"><span data-stu-id="8153f-125">MCDRemoteSystemAppRegistrationPublishStatusErrorAccountNotFound</span></span> | <span data-ttu-id="8153f-126">5</span><span class="sxs-lookup"><span data-stu-id="8153f-126">5</span></span> | <span data-ttu-id="8153f-127">에 대 한 정보를 게시 하는 계정을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-127">Account to publish information for was not found.</span></span>|
|<span data-ttu-id="8153f-128">MCDRemoteSystemAppRegistrationPublishStatusErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="8153f-128">MCDRemoteSystemAppRegistrationPublishStatusErrorUnknown</span></span> | <span data-ttu-id="8153f-129">6</span><span class="sxs-lookup"><span data-stu-id="8153f-129">6</span></span> | <span data-ttu-id="8153f-130">작업에 알 수 없는 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8153f-130">Operation encountered an unknown error.</span></span>|