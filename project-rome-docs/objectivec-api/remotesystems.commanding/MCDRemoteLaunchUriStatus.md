---
title: MCDRemoteLaunchUriStatus
description: URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 1a0302cd570b8cb25476a8188e3bcb1667707461
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801085"
---
# <a name="enum-mcdremotelaunchuristatus"></a><span data-ttu-id="347e3-104">열거형 `MCDRemoteLaunchUriStatus`</span><span class="sxs-lookup"><span data-stu-id="347e3-104">enum `MCDRemoteLaunchUriStatus`</span></span>

`typedef NS_ENUM(NSInteger, MCDRemoteLaunchUriStatus)`

<span data-ttu-id="347e3-105">URI를 사용 하 여 원격 앱 시작의 상태를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-105">Contains values that describe the status of a remote app launch using a URI.</span></span>


| <span data-ttu-id="347e3-106">이름</span><span class="sxs-lookup"><span data-stu-id="347e3-106">Name</span></span>    |<span data-ttu-id="347e3-107">값</span><span class="sxs-lookup"><span data-stu-id="347e3-107">Value</span></span>   |<span data-ttu-id="347e3-108">설명</span><span class="sxs-lookup"><span data-stu-id="347e3-108">Description</span></span>   |                  
|------ |------- |--|
|<span data-ttu-id="347e3-109">MCDRemoteLaunchUriStatusUnknown</span><span class="sxs-lookup"><span data-stu-id="347e3-109">MCDRemoteLaunchUriStatusUnknown</span></span> | <span data-ttu-id="347e3-110">0</span><span class="sxs-lookup"><span data-stu-id="347e3-110">0</span></span>| <span data-ttu-id="347e3-111">상태를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-111">The status is unknown.</span></span>|
|<span data-ttu-id="347e3-112">MCDRemoteLaunchUriStatusSuccess</span><span class="sxs-lookup"><span data-stu-id="347e3-112">MCDRemoteLaunchUriStatusSuccess</span></span> | <span data-ttu-id="347e3-113">1</span><span class="sxs-lookup"><span data-stu-id="347e3-113">1</span></span>| <span data-ttu-id="347e3-114">원격 시작이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-114">The remote launch was successful.</span></span>|
|<span data-ttu-id="347e3-115">MCDRemoteLaunchUriStatusAppUnavailable</span><span class="sxs-lookup"><span data-stu-id="347e3-115">MCDRemoteLaunchUriStatusAppUnavailable</span></span> | <span data-ttu-id="347e3-116">2</span><span class="sxs-lookup"><span data-stu-id="347e3-116">2</span></span> | <span data-ttu-id="347e3-117">대상 앱을 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="347e3-117">The target app is unavailable.</span></span>|
|<span data-ttu-id="347e3-118">MCDRemoteLaunchUriStatusProtocolUnavailable</span><span class="sxs-lookup"><span data-stu-id="347e3-118">MCDRemoteLaunchUriStatusProtocolUnavailable</span></span> | <span data-ttu-id="347e3-119">3</span><span class="sxs-lookup"><span data-stu-id="347e3-119">3</span></span> | <span data-ttu-id="347e3-120">대상 앱에서이 URI를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-120">The target app does not support this URI.</span></span>|
|<span data-ttu-id="347e3-121">MCDRemoteLaunchUriStatusRemoteSystemUnavailable</span><span class="sxs-lookup"><span data-stu-id="347e3-121">MCDRemoteLaunchUriStatusRemoteSystemUnavailable</span></span> | <span data-ttu-id="347e3-122">4</span><span class="sxs-lookup"><span data-stu-id="347e3-122">4</span></span> | <span data-ttu-id="347e3-123">메시지를 보낸 장치를 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="347e3-123">The device to which the message was sent is unavailable.</span></span>|
|<span data-ttu-id="347e3-124">MCDRemoteLaunchUriStatusValueSetTooLarge</span><span class="sxs-lookup"><span data-stu-id="347e3-124">MCDRemoteLaunchUriStatusValueSetTooLarge</span></span> | <span data-ttu-id="347e3-125">5</span><span class="sxs-lookup"><span data-stu-id="347e3-125">5</span></span> | <span data-ttu-id="347e3-126">대상 앱으로 보내는 데이터 번들 너무 큽니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-126">The data bundle sent to the target app was too large.</span></span>|
|<span data-ttu-id="347e3-127">MCDRemoteLaunchUriStatusDeniedByLocalSystem</span><span class="sxs-lookup"><span data-stu-id="347e3-127">MCDRemoteLaunchUriStatusDeniedByLocalSystem</span></span> | <span data-ttu-id="347e3-128">6</span><span class="sxs-lookup"><span data-stu-id="347e3-128">6</span></span> | <span data-ttu-id="347e3-129">클라이언트 시스템 원격 시스템 플랫폼을 사용 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-129">The client system has prevented use of the Remote Systems Platform.</span></span>|
|<span data-ttu-id="347e3-130">MCDRemoteLaunchUriStatusDeniedByRemoteSystem</span><span class="sxs-lookup"><span data-stu-id="347e3-130">MCDRemoteLaunchUriStatusDeniedByRemoteSystem</span></span> | <span data-ttu-id="347e3-131">7</span><span class="sxs-lookup"><span data-stu-id="347e3-131">7</span></span> | <span data-ttu-id="347e3-132">대상 장치를 원격 시스템 플랫폼을 사용 하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="347e3-132">The target device has prevented use of the Remote Systems Platform.</span></span>|