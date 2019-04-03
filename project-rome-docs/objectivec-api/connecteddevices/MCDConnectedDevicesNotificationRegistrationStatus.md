---
title: MCDConnectedDevicesNotificationRegistrationStatus
description: 클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c7d770c73479afb949a4917b5457b12e23b78698
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909135"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstatus"></a><span data-ttu-id="827e8-104">클래스 `MCDConnectedDevicesNotificationRegistrationStatus`</span><span class="sxs-lookup"><span data-stu-id="827e8-104">class `MCDConnectedDevicesNotificationRegistrationStatus`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesNotificationRegistrationStatus)
```  
<span data-ttu-id="827e8-105">등록 작업의 상태를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-105">Enumeration indicating the status of the registration operation.</span></span>
<span data-ttu-id="827e8-106">오류 상태 위치 앱 개발자 할 등록을 다시 시도 하는 일시적인 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-106">The error statuses indicate transient conditions where the app developer may want to retry registration.</span></span>

## <a name="fields"></a><span data-ttu-id="827e8-107">필드</span><span class="sxs-lookup"><span data-stu-id="827e8-107">Fields</span></span>

| <span data-ttu-id="827e8-108">이름</span><span class="sxs-lookup"><span data-stu-id="827e8-108">Name</span></span>                              |   <span data-ttu-id="827e8-109">값</span><span class="sxs-lookup"><span data-stu-id="827e8-109">Value</span></span>     | <span data-ttu-id="827e8-110">설명</span><span class="sxs-lookup"><span data-stu-id="827e8-110">Description</span></span> |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="827e8-111">MCDConnectedDevicesNotificationRegistrationStatusSuccess</span><span class="sxs-lookup"><span data-stu-id="827e8-111">MCDConnectedDevicesNotificationRegistrationStatusSuccess</span></span> | <span data-ttu-id="827e8-112">0</span><span class="sxs-lookup"><span data-stu-id="827e8-112">0</span></span> | <span data-ttu-id="827e8-113">작업이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-113">Operation completed successfully.</span></span>
| <span data-ttu-id="827e8-114">MCDConnectedDevicesNotificationRegistrationStatusErrorNoNetwork</span><span class="sxs-lookup"><span data-stu-id="827e8-114">MCDConnectedDevicesNotificationRegistrationStatusErrorNoNetwork</span></span> | <span data-ttu-id="827e8-115">1</span><span class="sxs-lookup"><span data-stu-id="827e8-115">1</span></span> | <span data-ttu-id="827e8-116">네트워크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-116">Network was unavailable.</span></span> |
| <span data-ttu-id="827e8-117">MCDConnectedDevicesNotificationRegistrationStatusErrorWebFailure</span><span class="sxs-lookup"><span data-stu-id="827e8-117">MCDConnectedDevicesNotificationRegistrationStatusErrorWebFailure</span></span> | <span data-ttu-id="827e8-118">2</span><span class="sxs-lookup"><span data-stu-id="827e8-118">2</span></span> | <span data-ttu-id="827e8-119">웹 서비스에는 다음이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-119">A web service failed.</span></span> |
| <span data-ttu-id="827e8-120">MCDConnectedDevicesNotificationRegistrationStatusErrorNoTokenRequestSubscriber</span><span class="sxs-lookup"><span data-stu-id="827e8-120">MCDConnectedDevicesNotificationRegistrationStatusErrorNoTokenRequestSubscriber</span></span> | <span data-ttu-id="827e8-121">3</span><span class="sxs-lookup"><span data-stu-id="827e8-121">3</span></span> | <span data-ttu-id="827e8-122">구독자가 없는 토큰 요청에 응답 했습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-122">No token request subscribers responded.</span></span> |
| <span data-ttu-id="827e8-123">MCDConnectedDevicesNotificationRegistrationStatusErrorTokenRequestFailed</span><span class="sxs-lookup"><span data-stu-id="827e8-123">MCDConnectedDevicesNotificationRegistrationStatusErrorTokenRequestFailed</span></span> | <span data-ttu-id="827e8-124">4</span><span class="sxs-lookup"><span data-stu-id="827e8-124">4</span></span> | <span data-ttu-id="827e8-125">토큰 요청이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-125">The token request failed.</span></span> |
| <span data-ttu-id="827e8-126">MCDConnectedDevicesNotificationRegistrationStatusErrorAccountNotFound</span><span class="sxs-lookup"><span data-stu-id="827e8-126">MCDConnectedDevicesNotificationRegistrationStatusErrorAccountNotFound</span></span> | <span data-ttu-id="827e8-127">5</span><span class="sxs-lookup"><span data-stu-id="827e8-127">5</span></span> | <span data-ttu-id="827e8-128">에 대 한 정보를 등록 하는 계정을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-128">Account to register information for was not found.</span></span> |
| <span data-ttu-id="827e8-129">MCDConnectedDevicesNotificationRegistrationStatusErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="827e8-129">MCDConnectedDevicesNotificationRegistrationStatusErrorUnknown</span></span> | <span data-ttu-id="827e8-130">6</span><span class="sxs-lookup"><span data-stu-id="827e8-130">6</span></span> | <span data-ttu-id="827e8-131">작업에 알 수 없는 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="827e8-131">Operation encountered an unknown error.</span></span> |