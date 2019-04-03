---
title: MCDConnectedDevicesNotificationType
description: 알림의 유형 (서비스)를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: eb537450a9e8a970bd07652fe201e94071211d92
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909485"
---
# <a name="enum-mcdconnecteddevicesnotificationtype"></a><span data-ttu-id="ded00-104">열거형 `MCDConnectedDevicesNotificationType`</span><span class="sxs-lookup"><span data-stu-id="ded00-104">enum `MCDConnectedDevicesNotificationType`</span></span>

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesNotificationType)
```  
<span data-ttu-id="ded00-105">알림의 유형 (서비스)를 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-105">Contains values that describe the type (service) of a notification.</span></span>

## <a name="fields"></a><span data-ttu-id="ded00-106">필드</span><span class="sxs-lookup"><span data-stu-id="ded00-106">Fields</span></span>

| <span data-ttu-id="ded00-107">이름</span><span class="sxs-lookup"><span data-stu-id="ded00-107">Name</span></span>                              |   <span data-ttu-id="ded00-108">값</span><span class="sxs-lookup"><span data-stu-id="ded00-108">Value</span></span>     | <span data-ttu-id="ded00-109">설명</span><span class="sxs-lookup"><span data-stu-id="ded00-109">Description</span></span> |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="ded00-110">MCDNotificationTypeUnknown</span><span class="sxs-lookup"><span data-stu-id="ded00-110">MCDNotificationTypeUnknown</span></span> | <span data-ttu-id="ded00-111">0</span><span class="sxs-lookup"><span data-stu-id="ded00-111">0</span></span> | <span data-ttu-id="ded00-112">ConnectedDevicesNotificationType 알려진 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-112">ConnectedDevicesNotificationType is unknown.</span></span> |
| <span data-ttu-id="ded00-113">MCDNotificationTypeWNS</span><span class="sxs-lookup"><span data-stu-id="ded00-113">MCDNotificationTypeWNS</span></span> | <span data-ttu-id="ded00-114">1</span><span class="sxs-lookup"><span data-stu-id="ded00-114">1</span></span> | <span data-ttu-id="ded00-115">Windows 푸시 알림 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-115">Windows Push Notification Services.</span></span> |
| <span data-ttu-id="ded00-116">MCDNotificationTypeGCM</span><span class="sxs-lookup"><span data-stu-id="ded00-116">MCDNotificationTypeGCM</span></span> | <span data-ttu-id="ded00-117">2</span><span class="sxs-lookup"><span data-stu-id="ded00-117">2</span></span> | <span data-ttu-id="ded00-118">Google Cloud Messaging 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-118">Google Cloud Messaging.</span></span> |
| <span data-ttu-id="ded00-119">MCDNotificationTypeFCM</span><span class="sxs-lookup"><span data-stu-id="ded00-119">MCDNotificationTypeFCM</span></span> | <span data-ttu-id="ded00-120">3</span><span class="sxs-lookup"><span data-stu-id="ded00-120">3</span></span> | <span data-ttu-id="ded00-121">Firebase Cloud Messaging 합니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-121">Firebase Cloud Messaging.</span></span>|
| <span data-ttu-id="ded00-122">MCDNotificationTypeAPN</span><span class="sxs-lookup"><span data-stu-id="ded00-122">MCDNotificationTypeAPN</span></span> | <span data-ttu-id="ded00-123">4</span><span class="sxs-lookup"><span data-stu-id="ded00-123">4</span></span> | <span data-ttu-id="ded00-124">Apple Push Notification Service입니다.</span><span class="sxs-lookup"><span data-stu-id="ded00-124">Apple Push Notification Service.</span></span> |
| <span data-ttu-id="ded00-125">MCDNotificationTypePolling</span><span class="sxs-lookup"><span data-stu-id="ded00-125">MCDNotificationTypePolling</span></span> | <span data-ttu-id="ded00-126">5</span><span class="sxs-lookup"><span data-stu-id="ded00-126">5</span></span> | <span data-ttu-id="ded00-127">클라우드 알림 서비스가 없습니다. 대신 들어오는 응답에 대해 폴링하십시오.</span><span class="sxs-lookup"><span data-stu-id="ded00-127">No cloud notification service; instead poll for incoming responses.</span></span> |
