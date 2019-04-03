---
title: MCDConnectedDevicesProcessNotificationOperation
description: 처리를 위해 로마 플랫폼에 대 한 알림을 제공 하는 결과입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: cb482e7b00cd5fe090de1708388d140cfd45777b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909895"
---
# <a name="class-mcdconnecteddevicesprocessnotificationoperation"></a><span data-ttu-id="d6d48-104">클래스 `MCDConnectedDevicesProcessNotificationOperation`</span><span class="sxs-lookup"><span data-stu-id="d6d48-104">class `MCDConnectedDevicesProcessNotificationOperation`</span></span> 

```
@interface MCDConnectedDevicesProcessNotificationOperation : NSObject
```  
<span data-ttu-id="d6d48-105">처리를 위해 연결 된 장치 플랫폼에 APNS 알림을 제공 하는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d48-105">The result of giving an APNS notification to the Connected Devices platform for processing.</span></span>

> [!NOTE] 
> <span data-ttu-id="d6d48-106">이 클래스는 사용 되지 않습니다. MCDConnectedDevicesNotification를 대신 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6d48-106">This class is deprecated, use MCDConnectedDevicesNotification instead.</span></span> 

## <a name="properties"></a><span data-ttu-id="d6d48-107">속성</span><span class="sxs-lookup"><span data-stu-id="d6d48-107">Properties</span></span>

### <a name="connecteddevicesnotification"></a><span data-ttu-id="d6d48-108">connectedDevicesNotification</span><span class="sxs-lookup"><span data-stu-id="d6d48-108">connectedDevicesNotification</span></span>
`@property(nonatomic, readonly, getter=isConnectedDevicesNotification) BOOL connectedDevicesNotification;`

<span data-ttu-id="d6d48-109">연결 된 장치 플랫폼에 대 한 알림을 할지 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d48-109">This is a flag indicating whether the notification was intended for the Connected Devices platform.</span></span>

## <a name="methods"></a><span data-ttu-id="d6d48-110">메서드</span><span class="sxs-lookup"><span data-stu-id="d6d48-110">Methods</span></span>

### <a name="waitforcompletionasync"></a><span data-ttu-id="d6d48-111">waitForCompletionAsync</span><span class="sxs-lookup"><span data-stu-id="d6d48-111">waitForCompletionAsync</span></span>
`- (void)waitForCompletionAsync:(nonnull void (^)(NSError* _Nullable error))callback;`

 <span data-ttu-id="d6d48-112">알림을 처리 하 고 완료 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d6d48-112">Wait for the notification to finish being handled.</span></span>

#### <a name="parameters"></a><span data-ttu-id="d6d48-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6d48-113">Parameters</span></span> 
* `callback` 

<span data-ttu-id="d6d48-114">알림 완료에 대 한 콜백 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d48-114">The callback result for notification completion.</span></span>
