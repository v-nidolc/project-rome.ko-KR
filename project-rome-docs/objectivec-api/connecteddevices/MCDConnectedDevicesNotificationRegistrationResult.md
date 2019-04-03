---
title: MCDConnectedDevicesNotificationRegistrationResult
description: 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9ee253ff1c07f498b42ccf0cd0edeb9937f31f59
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907745"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationresult"></a><span data-ttu-id="8e9fa-104">클래스 `MCDConnectedDevicesNotificationRegistrationResult`</span><span class="sxs-lookup"><span data-stu-id="8e9fa-104">class `MCDConnectedDevicesNotificationRegistrationResult`</span></span> 

```
@interface MCDConnectedDevicesNotificationRegistrationResult : NSObject
```  
<span data-ttu-id="8e9fa-105">MCDConnectedDevicesNotificationRegistrationResult 계정에 대 한 알림 정보를 등록 하는 비동기 결과 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9fa-105">MCDConnectedDevicesNotificationRegistrationResult communicates the async result of registering notification information for an account.</span></span> <span data-ttu-id="8e9fa-106">이 결과 통해 통신 하는 오류 상태를 사용할 수 없는 네트워크와 같은 특정 일시적인 장애가 발생할 경우 등록을 다시 시도 하는 앱에서 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9fa-106">The error statuses communicated through this result should be used by the app to retry registration in the event of certain transient conditions like the network being unavailable.</span></span>

## <a name="properties"></a><span data-ttu-id="8e9fa-107">속성</span><span class="sxs-lookup"><span data-stu-id="8e9fa-107">Properties</span></span>

### <a name="status"></a><span data-ttu-id="8e9fa-108">상태</span><span class="sxs-lookup"><span data-stu-id="8e9fa-108">status</span></span>

`@property(nonatomic, readonly) MCDConnectedDevicesNotificationRegistrationStatus status;`

<span data-ttu-id="8e9fa-109">등록 작업의 상태 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9fa-109">Status enum of the registration operation.</span></span>