---
title: MCDAppServiceConnection
description: 이 클래스는 특정 원격 앱 서비스에 대 한 연결을 관리합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 22e253f137642ad609a22af33aa62e2ef9543503
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908545"
---
# <a name="class-mcdappserviceconnection"></a><span data-ttu-id="381a0-104">클래스 `MCDAppServiceConnection`</span><span class="sxs-lookup"><span data-stu-id="381a0-104">class `MCDAppServiceConnection`</span></span>

```
@interface MCDAppServiceConnection : NSObject
```
<span data-ttu-id="381a0-105">이 클래스는 특정 원격 앱 서비스에 대 한 연결을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-105">This class manages a connection to a particular remote app service.</span></span>

## <a name="properties"></a><span data-ttu-id="381a0-106">속성</span><span class="sxs-lookup"><span data-stu-id="381a0-106">Properties</span></span>

### <a name="appserviceinfo"></a><span data-ttu-id="381a0-107">appServiceInfo</span><span class="sxs-lookup"><span data-stu-id="381a0-107">appServiceInfo</span></span>
`@property(nonatomic, retain, nonnull) MCDAppServiceInfo* appServiceInfo;`

<span data-ttu-id="381a0-108">연결할 대상 app service에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-108">Provides details about the target app service to connect to.</span></span>

### <a name="requestreceived"></a><span data-ttu-id="381a0-109">requestReceived</span><span class="sxs-lookup"><span data-stu-id="381a0-109">requestReceived</span></span> 
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDAppServiceConnection*, MCDAppServiceRequestReceivedEventArgs*>* requestReceived;`

<span data-ttu-id="381a0-110">원격 앱에서 서비스 요청을 수신 되는 경우에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-110">Event for when a service request is received from a remote app.</span></span>

### <a name="serviceclosed"></a><span data-ttu-id="381a0-111">serviceClosed</span><span class="sxs-lookup"><span data-stu-id="381a0-111">serviceClosed</span></span> 
`@property(nonatomic, readonly, nonnull) MCDEvent<MCDAppServiceConnection*, MCDAppServiceClosedEventArgs*>* serviceClosed;`

<span data-ttu-id="381a0-112">App service에 대 한 연결을 닫을 때에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-112">Event for when connection to the app service closes.</span></span>

## <a name="constructors"></a><span data-ttu-id="381a0-113">생성자</span><span class="sxs-lookup"><span data-stu-id="381a0-113">Constructors</span></span>

### <a name="init"></a><span data-ttu-id="381a0-114">Init</span><span class="sxs-lookup"><span data-stu-id="381a0-114">init</span></span>
`- (nullable instancetype)init;`

<span data-ttu-id="381a0-115">페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-115">Creates and initializes a new instance of this class.</span></span>

#### <a name="returns"></a><span data-ttu-id="381a0-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="381a0-116">Returns</span></span>
<span data-ttu-id="381a0-117">초기화 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-117">The initialized [MCDAppServiceConnection](MCDAppServiceConnection.md) if successful, otherwise nil.</span></span>

### <a name="initwithappserviceinfo"></a><span data-ttu-id="381a0-118">initWithAppServiceInfo</span><span class="sxs-lookup"><span data-stu-id="381a0-118">initWithAppServiceInfo</span></span>
- <span data-ttu-id="381a0-119">(nullable instancetype) initWithAppServiceInfo:(nonnull MCDAppServiceInfo\*) appServiceInfo;</span><span class="sxs-lookup"><span data-stu-id="381a0-119">(nullable instancetype)initWithAppServiceInfo:(nonnull MCDAppServiceInfo\*) appServiceInfo;</span></span>

#### <a name="parameters"></a><span data-ttu-id="381a0-120">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381a0-120">Parameters</span></span>
* <span data-ttu-id="381a0-121">`appServiceInfo` 앱 서비스 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-121">`appServiceInfo` The app service description.</span></span>

#### <a name="returns"></a><span data-ttu-id="381a0-122">반환 값</span><span class="sxs-lookup"><span data-stu-id="381a0-122">Returns</span></span>
<span data-ttu-id="381a0-123">초기화 반환 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-123">Returns the initialized [MCDAppServiceConnection](MCDAppServiceConnection.md) if successful, otherwise nil.</span></span>

### <a name="appserviceconnectionwithappserviceinfo"></a><span data-ttu-id="381a0-124">appServiceConnectionWithAppServiceInfo</span><span class="sxs-lookup"><span data-stu-id="381a0-124">appServiceConnectionWithAppServiceInfo</span></span>
`+ (nullable instancetype)appServiceConnectionWithAppServiceInfo:(nonnull MCDAppServiceInfo*) appServiceInfo;`

<span data-ttu-id="381a0-125">만들고 앱 서비스 정보를 사용 하 여이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-125">Creates and initializes a new instance of this class with app service information.</span></span>

#### <a name="parameters"></a><span data-ttu-id="381a0-126">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381a0-126">Parameters</span></span>
* `appServiceInfo` 

<span data-ttu-id="381a0-127">앱 서비스 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-127">The app service description.</span></span>

#### <a name="returns"></a><span data-ttu-id="381a0-128">반환 값</span><span class="sxs-lookup"><span data-stu-id="381a0-128">Returns</span></span>
<span data-ttu-id="381a0-129">초기화 반환 [MCDAppServiceConnection](MCDAppServiceConnection.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-129">Returns the initialized [MCDAppServiceConnection](MCDAppServiceConnection.md) if successful, otherwise nil.</span></span>

## <a name="methods"></a><span data-ttu-id="381a0-130">메서드</span><span class="sxs-lookup"><span data-stu-id="381a0-130">Methods</span></span>

### <a name="openremoteasync"></a><span data-ttu-id="381a0-131">openRemoteAsync</span><span class="sxs-lookup"><span data-stu-id="381a0-131">openRemoteAsync</span></span>
`- (void)openRemoteAsync:(nonnull MCDRemoteSystemConnectionRequest*)connectionRequest completion:(nonnull void (^)(MCDAppServiceConnectionStatus, NSError* _Nullable))completion;`

<span data-ttu-id="381a0-132">지정 된 원격 장치 또는 응용 프로그램에서 앱 서비스 연결을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-132">Opens the app service connection on the specified remote device or application.</span></span> <span data-ttu-id="381a0-133">연결을 열 수 없으며, 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-133">If the connection fails to open, an exception is thrown.</span></span>

><span data-ttu-id="381a0-134">**참고:** 이 메서드는 다음 중 하나에 해당할 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-134">**Note:** This method will thrown an exception if any of the following are true:</span></span>
> * <span data-ttu-id="381a0-135">연결이 이미 열려 있거나를 여는 동안.</span><span class="sxs-lookup"><span data-stu-id="381a0-135">The connection is already open or is in the process of opening.</span></span>
> * <span data-ttu-id="381a0-136">앱 서비스 설명을 설정 되지 않은 또는 지웠습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-136">The app service description has not been set or has been cleared.</span></span>
> * <span data-ttu-id="381a0-137">플랫폼 초기화 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-137">The platform has not been initialized.</span></span>
> * <span data-ttu-id="381a0-138">앱 메서드는 연결의 "수신한 요청" 이벤트를 구독에 있지만 제공 하지는 **MCDNotificationProvider** 플랫폼을 초기화 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="381a0-138">The app has subscribed a method to the connection's "request received" event but has not provided a **MCDNotificationProvider** when initializing the platform.</span></span> <span data-ttu-id="381a0-139">모든 호스팅 시나리오에 필요는 **MCDNotificationProvider**합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-139">All hosting scenarios require a **MCDNotificationProvider**.</span></span>

#### <a name="parameters"></a><span data-ttu-id="381a0-140">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381a0-140">Parameters</span></span>
* `connectionRequest` 

<span data-ttu-id="381a0-141">원격 시스템 또는 원격 대상 앱을 나타내는 연결 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-141">The connection request indicating which remote system or remote app to target.</span></span>

### <a name="sendmessageasync"></a><span data-ttu-id="381a0-142">sendMessageAsync</span><span class="sxs-lookup"><span data-stu-id="381a0-142">sendMessageAsync</span></span>
`- (void)sendMessageAsync:(nonnull NSDictionary*)message completion:(nonnull void (^)(MCDAppServiceResponse* _Nonnull, NSError* _Nullable))completion;`

<span data-ttu-id="381a0-143">원격 앱 서비스에 메시지를 보내고 응답을 수신 대기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-143">Sends a message to the remote app service and begins listening for a response.</span></span>  <span data-ttu-id="381a0-144">이 메서드는 단일 메시지/응답을 수행 하 고 영구 연결을 설정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-144">This method performs a single message/response and does not establish a persistent connection.</span></span>  <span data-ttu-id="381a0-145">연결이 성공적으로 열린 후에 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-145">It should only be called after the connection was opened successfully.</span></span>

#### <a name="parameters"></a><span data-ttu-id="381a0-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381a0-146">Parameters</span></span>
* `message` 

<span data-ttu-id="381a0-147">App service에 보낼 데이터를 키-값 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-147">The key-value set of data to be sent to the app service.</span></span>

### <a name="close"></a><span data-ttu-id="381a0-148">닫기</span><span class="sxs-lookup"><span data-stu-id="381a0-148">close</span></span>
`- (void)close;`

<span data-ttu-id="381a0-149">원격 앱 서비스에 대 한 연결을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-149">Closes the connection to the remote app service.</span></span> <span data-ttu-id="381a0-150">클라이언트 앱이 종료 되거나 사용자 또는 시스템에 의해 중지 될 때마다이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-150">The client app should call this method whenever it is closed or stopped by the user or system.</span></span>

### <a name="sendstatelessmessageasync"></a><span data-ttu-id="381a0-151">sendStatelessMessageAsync</span><span class="sxs-lookup"><span data-stu-id="381a0-151">sendStatelessMessageAsync</span></span>
```
+ (void)sendStatelessMessageAsync:(nonnull NSDictionary*)message
                     toAppService:(nonnull MCDAppServiceInfo*)appServiceInfo
                connectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connectionRequest
                       completion:(nonnull void (^)(MCDStatelessAppServiceResponse* _Nonnull, NSError* _Nullable))completion;
```

<span data-ttu-id="381a0-152">지정 된 원격 앱 서비스에 메시지를 보내고 응답을 수신 대기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-152">Sends a message to a specified remote app service and begins listening for a response.</span></span>

#### <a name="parameters"></a><span data-ttu-id="381a0-153">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381a0-153">Parameters</span></span>
* <span data-ttu-id="381a0-154">`message` App service에 보낼 데이터를 키-값 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-154">`message` The key-value set of data to be sent to the app service.</span></span>
* <span data-ttu-id="381a0-155">`appServiceInfo` 대상 app service에 대 한 설명이 포함 된 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-155">`appServiceInfo` The descriptive info for the target app service.</span></span>
* <span data-ttu-id="381a0-156">`connectionRequest` 연결 요청 지정 app service에 연결할입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-156">`connectionRequest` The connection request specifying the app service to connect to.</span></span>
* <span data-ttu-id="381a0-157">`completion` 비동기 완료 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="381a0-157">`completion` The async completion callback.</span></span>