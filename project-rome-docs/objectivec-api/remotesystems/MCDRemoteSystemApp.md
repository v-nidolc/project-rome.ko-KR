---
title: MCDRemoteSystemApp
description: 연결에 사용할 수 있는 원격 시스템에서 응용 프로그램을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 28ec3fbe03150cb45c0a554a0499f1a6b657e50d
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907655"
---
# <a name="class-mcdremotesystemapp"></a><span data-ttu-id="28e67-104">클래스 `MCDRemoteSystemApp`</span><span class="sxs-lookup"><span data-stu-id="28e67-104">class `MCDRemoteSystemApp`</span></span> 

```
@interface MCDRemoteSystemApp : NSObject
```  

<span data-ttu-id="28e67-105">연결에 사용할 수 있는 원격 시스템에서 응용 프로그램을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-105">Represents an application on a remote system that is available for connectivity.</span></span>

## <a name="properties"></a><span data-ttu-id="28e67-106">속성</span><span class="sxs-lookup"><span data-stu-id="28e67-106">Properties</span></span>

### <a name="appid"></a><span data-ttu-id="28e67-107">appId</span><span class="sxs-lookup"><span data-stu-id="28e67-107">appId</span></span>
`@property(nonatomic, readonly, nonnull) NSString* appId;`

<span data-ttu-id="28e67-108">이 응용 프로그램에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-108">A unique identifier for this application.</span></span>

### <a name="displayname"></a><span data-ttu-id="28e67-109">displayName</span><span class="sxs-lookup"><span data-stu-id="28e67-109">displayName</span></span>
`@property(nonatomic, readonly, nonnull) NSString* displayName;`

<span data-ttu-id="28e67-110">이 응용 프로그램에 대 한 친숙 한 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-110">The friendly display name for this application.</span></span> <span data-ttu-id="28e67-111">Bluetooth id에 대 한 장치에서 사용 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-111">This is the name used by the device for Bluetooth identification.</span></span> <span data-ttu-id="28e67-112">이 설정 되지 않은 장치에서 Bluetooth를 지원 하지 않습니다, 경우이 필드는 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-112">If this hasn't been set or the device doesn't support Bluetooth, this field will be empty.</span></span>

### <a name="availablebyproximity"></a><span data-ttu-id="28e67-113">availableByProximity</span><span class="sxs-lookup"><span data-stu-id="28e67-113">availableByProximity</span></span>
`@property(nonatomic, readonly, getter=isAvailableByProximity) BOOL availableByProximity;`

<span data-ttu-id="28e67-114">이 응용 프로그램은 현재 proximal 연결에 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-114">Indicates whether this application is currently available for proximal connection.</span></span>

### <a name="availablebyspatialproximity"></a><span data-ttu-id="28e67-115">availableBySpatialProximity</span><span class="sxs-lookup"><span data-stu-id="28e67-115">availableBySpatialProximity</span></span>
`@property(nonatomic, readonly, getter=isAvailableBySpatialProximity) BOOL availableBySpatialProximity;`

<span data-ttu-id="28e67-116">이 응용 프로그램은 공간 공유 연결에 대 한 현재 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-116">Indicates whether this application is currently available for spatial sharing connection.</span></span>

### <a name="attributes"></a><span data-ttu-id="28e67-117">특성</span><span class="sxs-lookup"><span data-stu-id="28e67-117">attributes</span></span>
`@property(nonatomic, readonly, nonnull) NSDictionary<NSString*, NSString*>* attributes;`

<span data-ttu-id="28e67-118">이 응용 프로그램의 특성을 정의 하는 키/값 쌍의 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-118">A dictionary of key/value pairs defining the attributes of this application.</span></span>

### <a name="appservices"></a><span data-ttu-id="28e67-119">appServices</span><span class="sxs-lookup"><span data-stu-id="28e67-119">appServices</span></span>
`@property(nonatomic, readonly, nullable) NSArray<MCDAppServiceDescription*>* appServices;`

<span data-ttu-id="28e67-120">이 응용 프로그램 원격 연결을 위해 제공 되는 앱 서비스를 설명 하는 MCDAppServiceDescription 인스턴스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-120">An array of MCDAppServiceDescription instances describing the app services that this application provides for remote connectivity.</span></span>

### <a name="accounts"></a><span data-ttu-id="28e67-121">계정</span><span class="sxs-lookup"><span data-stu-id="28e67-121">accounts</span></span>
`@property(nonatomic, readonly, nullable) NSArray<MCDConnectedDevicesAccount*>* accounts;`

<span data-ttu-id="28e67-122">에 대해 알아야 할 권한이 있는 MCDRemoteSystemApp와 연결 된 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-122">The Account associated with the MCDRemoteSystemApp that you have permissions to know about.</span></span> <span data-ttu-id="28e67-123">MCDRemoteSystemWatcher 시작 될 때를 MCDConnectedDevicesAccount는 MCDConnectedDevicesAccountManager에 있는지는 사용 권한을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="28e67-123">What determines permissions is if the MCDConnectedDevicesAccount exists in the MCDConnectedDevicesAccountManager when the MCDRemoteSystemWatcher is started.</span></span>