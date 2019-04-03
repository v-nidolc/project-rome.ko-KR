---
title: MCDConnectedDevicesNotificationRegistration
description: 이 클래스는 푸시 알림 서비스 (일부 프로젝트 로마 시나리오에 필요)를 사용 하 여 앱의 등록을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 38cd140538d6e6dabddda39ba98f736fc708ade7
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908885"
---
# <a name="class-mcdconnecteddevicesnotificationregistration"></a><span data-ttu-id="0742a-104">클래스 `MCDConnectedDevicesNotificationRegistration`</span><span class="sxs-lookup"><span data-stu-id="0742a-104">class `MCDConnectedDevicesNotificationRegistration`</span></span> 

```
@interface MCDConnectedDevicesNotificationRegistration : NSObject
```  
 <span data-ttu-id="0742a-105">이 클래스는 푸시 알림 서비스 (일부 프로젝트 로마 시나리오에 필요)를 사용 하 여 앱의 등록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-105">This class represents the app's registration with a push notification service (necessary for some Project Rome scenarios).</span></span> <span data-ttu-id="0742a-106">연결 된 장치 플랫폼에이 정보를 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-106">It conveys this information to the Connected Devices Platform.</span></span>

## <a name="properties"></a><span data-ttu-id="0742a-107">속성</span><span class="sxs-lookup"><span data-stu-id="0742a-107">Properties</span></span>

### <a name="type"></a><span data-ttu-id="0742a-108">유형</span><span class="sxs-lookup"><span data-stu-id="0742a-108">type</span></span>
`@property(nonatomic, readwrite) MCDConnectedDevicesNotificationType type;`

<span data-ttu-id="0742a-109">이 알림의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-109">The type of notifications in this setup.</span></span>

### <a name="token"></a><span data-ttu-id="0742a-110">token</span><span class="sxs-lookup"><span data-stu-id="0742a-110">token</span></span>
`@property(nonatomic, readwrite, nonnull) NSString* token;`

<span data-ttu-id="0742a-111">등록 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-111">The registration token.</span></span>

### <a name="appid"></a><span data-ttu-id="0742a-112">appId</span><span class="sxs-lookup"><span data-stu-id="0742a-112">appId</span></span>
`@property(nonatomic, readwrite, nonnull) NSString* appId;`

<span data-ttu-id="0742a-113">푸시 알림 등록에 대 한 앱 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-113">The app ID for push notification registration.</span></span>

### <a name="appdisplayname"></a><span data-ttu-id="0742a-114">appDisplayName</span><span class="sxs-lookup"><span data-stu-id="0742a-114">appDisplayName</span></span>
`@property(nonatomic, readwrite, nonnull) NSString* appDisplayName;`

<span data-ttu-id="0742a-115">앱 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-115">The app display name.</span></span> <span data-ttu-id="0742a-116">이 Microsoft 개발자 포털에서 등록에 사용 된 앱의 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0742a-116">This should be the name of the app that was used for registration on the Microsoft dev portal.</span></span>