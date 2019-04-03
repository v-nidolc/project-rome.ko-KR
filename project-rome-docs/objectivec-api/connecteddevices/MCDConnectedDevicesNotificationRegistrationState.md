---
title: MCDConnectedDevicesNotificationRegistrationState
description: 클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: be390f4f8e5d3c026d35bb8998e2818b9db05e86
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909235"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstate"></a><span data-ttu-id="6488e-104">클래스 `MCDConnectedDevicesNotificationRegistrationState`</span><span class="sxs-lookup"><span data-stu-id="6488e-104">class `MCDConnectedDevicesNotificationRegistrationState`</span></span> 

```
typedef NS_ENUM(NSUInteger, MCDConnectedDevicesNotificationRegistrationState)
```  
<span data-ttu-id="6488e-105">클라우드 등록의 상태를 통신 하는 데 사용 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6488e-105">Values used to communicate the status of cloud registration.</span></span>

## <a name="fields"></a><span data-ttu-id="6488e-106">필드</span><span class="sxs-lookup"><span data-stu-id="6488e-106">Fields</span></span>

| <span data-ttu-id="6488e-107">이름</span><span class="sxs-lookup"><span data-stu-id="6488e-107">Name</span></span>                              |   <span data-ttu-id="6488e-108">값</span><span class="sxs-lookup"><span data-stu-id="6488e-108">Value</span></span>     | <span data-ttu-id="6488e-109">설명</span><span class="sxs-lookup"><span data-stu-id="6488e-109">Description</span></span> |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="6488e-110">MCDConnectedDevicesNotificationRegistrationStateUnregistered</span><span class="sxs-lookup"><span data-stu-id="6488e-110">MCDConnectedDevicesNotificationRegistrationStateUnregistered</span></span> | <span data-ttu-id="6488e-111">0</span><span class="sxs-lookup"><span data-stu-id="6488e-111">0</span></span> | <span data-ttu-id="6488e-112">등록 시작 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6488e-112">Registration has never been started.</span></span>
| <span data-ttu-id="6488e-113">MCDConnectedDevicesNotificationRegistrationStateRegistered</span><span class="sxs-lookup"><span data-stu-id="6488e-113">MCDConnectedDevicesNotificationRegistrationStateRegistered</span></span> | <span data-ttu-id="6488e-114">1</span><span class="sxs-lookup"><span data-stu-id="6488e-114">1</span></span> | <span data-ttu-id="6488e-115">등록을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6488e-115">Registration has finished.</span></span> |
| <span data-ttu-id="6488e-116">MCDConnectedDevicesNotificationRegistrationStateExpiring</span><span class="sxs-lookup"><span data-stu-id="6488e-116">MCDConnectedDevicesNotificationRegistrationStateExpiring</span></span> | <span data-ttu-id="6488e-117">2</span><span class="sxs-lookup"><span data-stu-id="6488e-117">2</span></span> | <span data-ttu-id="6488e-118">등록 만료 되려고 이며 따라서 앱은 등록 다시 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6488e-118">Registration is about to expire and so the app should perform registration again.</span></span> |
| <span data-ttu-id="6488e-119">MCDConnectedDevicesNotificationRegistrationStateExpired</span><span class="sxs-lookup"><span data-stu-id="6488e-119">MCDConnectedDevicesNotificationRegistrationStateExpired</span></span> | <span data-ttu-id="6488e-120">3</span><span class="sxs-lookup"><span data-stu-id="6488e-120">3</span></span> | <span data-ttu-id="6488e-121">등록 만료 되어 있으므로 앱 등록을 다시 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6488e-121">Registration has expired and so the app must perform registration again.</span></span> |