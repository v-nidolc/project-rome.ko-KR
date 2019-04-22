---
title: MCDRemoteLauncher
description: URI를 사용 하 여 원격 장치에 앱을 실행 하는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: aa0211c1edc33e8a277c4954d94fbcbb6565c923
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907385"
---
# <a name="class-mcdremotelauncher"></a><span data-ttu-id="d130a-104">클래스 `MCDRemoteLauncher`</span><span class="sxs-lookup"><span data-stu-id="d130a-104">class `MCDRemoteLauncher`</span></span> 

```
@interface MCDRemoteLauncher : NSObject
```  

<span data-ttu-id="d130a-105">URI를 사용 하 여 원격 장치에 앱을 실행 하는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-105">A class used to launch an app on a remote device using a URI.</span></span>


## <a name="methods"></a><span data-ttu-id="d130a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d130a-106">Methods</span></span>

### <a name="launchuriasync"></a><span data-ttu-id="d130a-107">launchUriAsync</span><span class="sxs-lookup"><span data-stu-id="d130a-107">launchUriAsync</span></span>
```
- (void)launchUriAsync:(nonnull NSString*)uri
 withConnectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connection
            completion:(nullable void (^)(MCDRemoteLaunchUriStatus result, NSError* _Nullable error))completionBlock;
```

<span data-ttu-id="d130a-108">시작에 지정 된 원격 시스템에 대 한 URI를 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-108">Launches a URI against the Remote System specified in an [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md).</span></span>

#### <a name="parameters"></a><span data-ttu-id="d130a-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d130a-109">Parameters</span></span>
* <span data-ttu-id="d130a-110">`uri` 앱을 실행 하는 발생할 수 있는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-110">`uri` The URI which will cause the launching of an app.</span></span>  <span data-ttu-id="d130a-111">대상 Windows를 대상 앱 구성표에 따라 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-111">If the target is Windows, the target app will be chosen based on scheme.</span></span> <span data-ttu-id="d130a-112">대상이 아닌 Windows를 대상 응용 프로그램을 MCDRemoteSystemConnectionRequest에 따라 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-112">If the target is non-Windows, the target app will be chosen based on the MCDRemoteSystemConnectionRequest.</span></span>

* <span data-ttu-id="d130a-113">`connection` 원격 시스템 또는 응용 프로그램에 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-113">`connection` Specifies which remote system or application to connect to.</span></span>
* <span data-ttu-id="d130a-114">`completionBlock` 블록 완료 시 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-114">`completionBlock` The block to invoke upon completion.</span></span>

### <a name="launchuriasync"></a><span data-ttu-id="d130a-115">launchUriAsync</span><span class="sxs-lookup"><span data-stu-id="d130a-115">launchUriAsync</span></span>
```
- (void)launchUriAsync:(nonnull NSString*)uri
 withConnectionRequest:(nonnull MCDRemoteSystemConnectionRequest*)connection
               options:(nullable MCDRemoteLauncherOptions*)options
            completion:(nullable void (^)(MCDRemoteLaunchUriStatus result, NSError* _Nullable error))completionBlock;
```

<span data-ttu-id="d130a-116">시작 옵션에 지정 된 원격 시스템에 대 한 URI를 [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-116">Launches a URI with options against the Remote System specified in an [MCDRemoteSystemConnectionRequest](MCDRemoteSystemConnectionRequest.md).</span></span>

#### <a name="parameters"></a><span data-ttu-id="d130a-117">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d130a-117">Parameters</span></span>
* <span data-ttu-id="d130a-118">`uri` 해당 스키마에 따라 앱을 실행 하는 발생할 수 있는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-118">`uri` The URI which will cause the launching of an app, according to its scheme.</span></span>
* <span data-ttu-id="d130a-119">`connection` 원격 시스템 또는 응용 프로그램에 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-119">`connection` Specifies which remote system or application to connect to.</span></span>
* <span data-ttu-id="d130a-120">`options` 앱에 대 한 시작 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-120">`options` The launch specifications for the app.</span></span>
* <span data-ttu-id="d130a-121">`completionBlock` 블록 완료 시 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="d130a-121">`completionBlock` The block to invoke upon completion.</span></span>