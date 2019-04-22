---
title: MCDConnectedDevicesNotificationRegistrationResult
description: 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9ee253ff1c07f498b42ccf0cd0edeb9937f31f59
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801355"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationresult"></a><span data-ttu-id="58e0d-104">클래스 `MCDConnectedDevicesNotificationRegistrationResult`</span><span class="sxs-lookup"><span data-stu-id="58e0d-104">class `MCDConnectedDevicesNotificationRegistrationResult`</span></span> 

```
@interface MCDConnectedDevicesNotificationRegistrationResult : NSObject
```  
<span data-ttu-id="58e0d-105">MCDConnectedDevicesNotificationRegistrationResult 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e0d-105">MCDConnectedDevicesNotificationRegistrationResult communicates the async result of registering notification information for an account.</span></span> <span data-ttu-id="58e0d-106">이 결과 통해 통신 하는 오류 상태를 사용할 수 없는 네트워크와 같은 특정 일시적인 장애가 발생할 경우 등록을 다시 시도 하는 앱에서 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58e0d-106">The error statuses communicated through this result should be used by the app to retry registration in the event of certain transient conditions like the network being unavailable.</span></span>

## <a name="properties"></a><span data-ttu-id="58e0d-107">속성</span><span class="sxs-lookup"><span data-stu-id="58e0d-107">Properties</span></span>

### <a name="status"></a><span data-ttu-id="58e0d-108">상태</span><span class="sxs-lookup"><span data-stu-id="58e0d-108">status</span></span>

`@property(nonatomic, readonly) MCDConnectedDevicesNotificationRegistrationStatus status;`

<span data-ttu-id="58e0d-109">등록 작업의 상태 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="58e0d-109">Status enum of the registration operation.</span></span>