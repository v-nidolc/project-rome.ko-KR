---
title: MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs
description: MCDConnectedDevicesNotificationRegistration 상태 변경 이벤트에 대 한 이벤트 인수 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 83b59cc884cc0e8d59387b95388b4b7b2b5fa273
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59800695"
---
# <a name="class-mcdconnecteddevicesnotificationregistrationstatechangedeventargs"></a><span data-ttu-id="46e86-104">클래스 `MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs`</span><span class="sxs-lookup"><span data-stu-id="46e86-104">class `MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs`</span></span> 

```
@interface MCDConnectedDevicesNotificationRegistrationStateChangedEventArgs : NSObject
```  
<span data-ttu-id="46e86-105">MCDConnectedDevicesNotificationRegistration 상태 변경 이벤트에 대 한 이벤트 인수 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="46e86-105">Event Args class for the MCDConnectedDevicesNotificationRegistration State Changed event.</span></span> <span data-ttu-id="46e86-106">이 응용 프로그램에 올바른 알림 메커니즘을 통해 새 연결 된 장치 플랫폼 메시지 정보를 가져옵니다는 되도록 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46e86-106">This is used to ensure that the application gets informed about new Connected Devices platform messages via the correct notification mechanism.</span></span>

## <a name="properties"></a><span data-ttu-id="46e86-107">속성</span><span class="sxs-lookup"><span data-stu-id="46e86-107">Properties</span></span>

### <a name="account"></a><span data-ttu-id="46e86-108">계정으로 이동하면</span><span class="sxs-lookup"><span data-stu-id="46e86-108">account</span></span>
`@property(nonatomic, readonly, nonnull) MCDConnectedDevicesAccount* account;`

<span data-ttu-id="46e86-109">알림 등록 상태 변경에는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="46e86-109">The Account for which the notification registration state has changed for.</span></span>

### <a name="registration"></a><span data-ttu-id="46e86-110">등록</span><span class="sxs-lookup"><span data-stu-id="46e86-110">registration</span></span>
`@property(nonatomic, readonly, nonnull) MCDConnectedDevicesNotificationRegistration* registration;`

<span data-ttu-id="46e86-111">상태가 변경 된 등록 인스턴스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="46e86-111">The information for registration instance whose state has changed.</span></span>

### <a name="state"></a><span data-ttu-id="46e86-112">state</span><span class="sxs-lookup"><span data-stu-id="46e86-112">state</span></span>
`@property(nonatomic, readonly) MCDConnectedDevicesNotificationRegistrationState state;`

<span data-ttu-id="46e86-113">새 등록 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="46e86-113">The new registration state.</span></span>