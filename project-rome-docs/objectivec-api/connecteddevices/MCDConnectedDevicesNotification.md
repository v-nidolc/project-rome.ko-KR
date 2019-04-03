---
title: MCDConnectedDevicesNotification
description: 알림을 처리의 결과입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2a60e2cab26c3d2df39314aa5b61a65de1529356
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908715"
---
# <a name="class-mcdconnecteddevicesnotification"></a><span data-ttu-id="46129-104">클래스 `MCDConnectedDevicesNotification`</span><span class="sxs-lookup"><span data-stu-id="46129-104">class `MCDConnectedDevicesNotification`</span></span> 

```
@interface MCDConnectedDevicesNotification : NSObject
```  
<span data-ttu-id="46129-105">알림을 처리의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="46129-105">Result of processing a notification.</span></span>

## <a name="methods"></a><span data-ttu-id="46129-106">메서드</span><span class="sxs-lookup"><span data-stu-id="46129-106">Methods</span></span>

### <a name="tryparse"></a><span data-ttu-id="46129-107">tryParse</span><span class="sxs-lookup"><span data-stu-id="46129-107">tryParse</span></span>

`+ (nullable instancetype)tryParse:(NSDictionary* _Nonnull)dictionary;`

<span data-ttu-id="46129-108">APNS에서 MCDConnectedDevicesNotification 구문 분석 하려고 맵 서식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46129-108">Attempts to parse a MCDConnectedDevicesNotification from an APNS formatted map.</span></span>

#### <a name="parameters"></a><span data-ttu-id="46129-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46129-109">Parameters</span></span> 
* `dictionary` 

<span data-ttu-id="46129-110">처리를 위해 연결 된 장치 플랫폼에서 APNS 알림을 수신 하는 맵.</span><span class="sxs-lookup"><span data-stu-id="46129-110">The map received from the APNS notification to the Connected Devices platform for processing.</span></span>
