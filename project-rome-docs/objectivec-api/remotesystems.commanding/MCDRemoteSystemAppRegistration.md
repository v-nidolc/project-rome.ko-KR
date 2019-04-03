---
title: MCDRemoteSystemAppRegistration
description: 이 클래스는 연결 된 장치 플랫폼에 등록 해야 하는 응용 프로그램을 나타냅니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 2c931d3eeacd4aa48e1ef22d573bf0325eb5b98b
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909915"
---
# <a name="class-mcdremotesystemappregistration"></a><span data-ttu-id="116cc-104">클래스 `MCDRemoteSystemAppRegistration`</span><span class="sxs-lookup"><span data-stu-id="116cc-104">class `MCDRemoteSystemAppRegistration`</span></span> 

```
@interface MCDRemoteSystemAppRegistration : NSObject
```  

<span data-ttu-id="116cc-105">이 클래스는 모든 다른 검색 하 고 사용할 수 있는이 앱에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-105">This class contains all of the information about this app that another could discover and use.</span></span>

> [!NOTE] 
> <span data-ttu-id="116cc-106">다른 앱으로 보내는 모든 통신은 possble MCDRemoteSystemAppRegistration 정보 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-106">MCDRemoteSystemAppRegistration information must be published before any outgoing communication to another app is possble.</span></span> <span data-ttu-id="116cc-107">이 경우 다른 응용 프로그램을 알 수 있도록 해당 통신에 응답 하는 방법</span><span class="sxs-lookup"><span data-stu-id="116cc-107">This is so that the other application can know how to respond to that communication.</span></span>

## <a name="properties"></a><span data-ttu-id="116cc-108">속성</span><span class="sxs-lookup"><span data-stu-id="116cc-108">Properties</span></span>

### <a name="account"></a><span data-ttu-id="116cc-109">계정으로 이동하면</span><span class="sxs-lookup"><span data-stu-id="116cc-109">account</span></span>
`@property(nonatomic, readonly, nullable) MCDConnectedDevicesAccount* account;`

<span data-ttu-id="116cc-110">이 등록 속해 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-110">Account that this registration belongs to.</span></span>

### <a name="attributes"></a><span data-ttu-id="116cc-111">특성</span><span class="sxs-lookup"><span data-stu-id="116cc-111">attributes</span></span>
`@property(nonatomic, copy, nullable) NSDictionary<NSString*, NSString*>* attributes;`

 <span data-ttu-id="116cc-112">이 앱의 특성을 설명 하는 문자열의 사전입니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-112">Dictionary of strings that describe the attributes of this app.</span></span>

### <a name="appserviceproviders"></a><span data-ttu-id="116cc-113">appServiceProviders</span><span class="sxs-lookup"><span data-stu-id="116cc-113">appServiceProviders</span></span>
`@property(nonatomic, copy, nullable) NSArray<id<MCDAppServiceProvider>>* appServiceProviders;`

<span data-ttu-id="116cc-114">이 앱을 지 원하는 AppServiceProviders의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-114">Array of AppServiceProviders that this app supports.</span></span>

> [!NOTE] 
> <span data-ttu-id="116cc-115">App service 공급자는 들어오는 연결을 수신 하려면이 배열에 있는 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-115">An app service provider must be present in this array in order to receive incoming connections.</span></span>  <span data-ttu-id="116cc-116">MCDRemoteSystemAppRegistration.publishAsync() 요청을 수신 하도록 app service 공급자에 대해 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-116">MCDRemoteSystemAppRegistration.publishAsync() does not need to be called for the app service provider to receive requests.</span></span>  

### <a name="launchuriprovider"></a><span data-ttu-id="116cc-117">launchUriProvider</span><span class="sxs-lookup"><span data-stu-id="116cc-117">launchUriProvider</span></span>
`@property(nonatomic, readwrite, nullable) id<MCDLaunchUriProvider> launchUriProvider;`

<span data-ttu-id="116cc-118">이 앱에 대 한 Uri 공급자를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-118">Launch Uri provider for this app.</span></span>

> [!NOTE] 
> <span data-ttu-id="116cc-119">시작 uri 공급자는 들어오는 요청을 수신 하기 위해이 속성에 저장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-119">A launch uri provider must be stored in this property in order to receive incoming requests.</span></span>  <span data-ttu-id="116cc-120">MCDRemoteSystemAppRegistration.publishAsync() 요청을 수신 하도록 app service 공급자에 대해 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-120">MCDRemoteSystemAppRegistration.publishAsync() does not need to be called for the app service provider to receive requests.</span></span>  

## <a name="constructors"></a><span data-ttu-id="116cc-121">생성자</span><span class="sxs-lookup"><span data-stu-id="116cc-121">Constructors</span></span>

### <a name="getforaccount"></a><span data-ttu-id="116cc-122">getForAccount</span><span class="sxs-lookup"><span data-stu-id="116cc-122">getForAccount</span></span>
`+(nullable instancetype) getForAccount:(MCDConnectedDevicesAccount* _Nonnull) account
                              platform:(MCDConnectedDevicesPlatform* _Nonnull) platform;`

<span data-ttu-id="116cc-123">계정의 현재 원격 시스템 앱 등록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-123">Gets the current remote system app registration for the account.</span></span>

#### <a name="parameters"></a><span data-ttu-id="116cc-124">매개 변수</span><span class="sxs-lookup"><span data-stu-id="116cc-124">Parameters</span></span>
* `account` 

<span data-ttu-id="116cc-125">에 대 한 등록을 검색 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-125">Account to retrieve the registration for.</span></span>

* `platform` 

<span data-ttu-id="116cc-126">등록을 가져올 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-126">Platform to get registration from.</span></span>

#### <a name="returns"></a><span data-ttu-id="116cc-127">반환 값</span><span class="sxs-lookup"><span data-stu-id="116cc-127">Returns</span></span>
<span data-ttu-id="116cc-128">제공 된 계정에 대 한 MCDRemoteSystemAppRegistration 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-128">Returns an MCDRemoteSystemAppRegistration object for the provided Account.</span></span>

## <a name="methods"></a><span data-ttu-id="116cc-129">메서드</span><span class="sxs-lookup"><span data-stu-id="116cc-129">Methods</span></span>

### <a name="saveasync"></a><span data-ttu-id="116cc-130">saveAsync</span><span class="sxs-lookup"><span data-stu-id="116cc-130">saveAsync</span></span>
`- (void)saveAsync:(nonnull void (^)(BOOL, NSError* _Nullable))callback  __attribute__((deprecated("Use publishAsync instead")));`

<span data-ttu-id="116cc-131">현재 저장 된 정보는 RemoteSystemAppRegistration 다른 응용 프로그램에서 검색할 수 있도록 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-131">Saves the information currently stored in the RemoteSystemAppRegistration such that other applications can discover it.</span></span>

> [!NOTE] 
> <span data-ttu-id="116cc-132">MCDConnectedDevicesNotificationRegistration 되려면이 호출에 대 한 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-132">MCDConnectedDevicesNotificationRegistration must be registered for this call to succeed.</span></span>

> [!WARNING] 
> <span data-ttu-id="116cc-133">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-133">Deprecated.</span></span> <span data-ttu-id="116cc-134">PublishAsync를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-134">Use publishAsync instead.</span></span>

#### <a name="parameters"></a><span data-ttu-id="116cc-135">매개 변수</span><span class="sxs-lookup"><span data-stu-id="116cc-135">Parameters</span></span>

* `callback`

<span data-ttu-id="116cc-136">콜백 정보를 저장 하는 결과 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-136">The callback indicates the result of saving the information.</span></span>

### <a name="publishasync"></a><span data-ttu-id="116cc-137">publishAsync</span><span class="sxs-lookup"><span data-stu-id="116cc-137">publishAsync</span></span>
`- (void)publishAsync:(nonnull void (^)(MCDRemoteSystemAppRegistrationPublishResult* _Nonnull, NSError* _Nullable))completionBlock;`

<span data-ttu-id="116cc-138">현재 저장 된 정보는 MCDRemoteSystemAppRegistration 다른 응용 프로그램에서 검색할 수 있도록 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-138">Publishes the information currently stored in the MCDRemoteSystemAppRegistration such that other applications can discover it.</span></span>

> [!NOTE] 
> <span data-ttu-id="116cc-139">MCDConnectedDevicesNotificationRegistration 되려면이 호출에 대 한 등록 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-139">MCDConnectedDevicesNotificationRegistration must be registered for this call to succeed.</span></span>

#### <a name="parameters"></a><span data-ttu-id="116cc-140">매개 변수</span><span class="sxs-lookup"><span data-stu-id="116cc-140">Parameters</span></span>

* `callback`

<span data-ttu-id="116cc-141">콜백 정보를 저장 하는 결과 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="116cc-141">The callback indicates the result of saving the information.</span></span>
