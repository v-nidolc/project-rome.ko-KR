---
title: MCDLaunchUriProvider
description: ''
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4cbfaa9fd1e88345f4ce35987508b061e479854e
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907465"
---
# <a name="protocol-mcdlaunchuriprovider"></a><span data-ttu-id="98d03-103">protocol `MCDLaunchUriProvider`</span><span class="sxs-lookup"><span data-stu-id="98d03-103">protocol `MCDLaunchUriProvider`</span></span>

```
@protocol MCDLaunchUriProvider <NSObject>
```

<span data-ttu-id="98d03-104">이 클래스를 통해 응용 프로그램을 실행 하는 URI의 처리를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-104">This class manages the handling of a URI through the launching of an application.</span></span>

## <a name="properties"></a><span data-ttu-id="98d03-105">속성</span><span class="sxs-lookup"><span data-stu-id="98d03-105">Properties</span></span> 
### <a name="supportedurischemes"></a><span data-ttu-id="98d03-106">supportedUriSchemes</span><span class="sxs-lookup"><span data-stu-id="98d03-106">supportedUriSchemes</span></span>
`@property(nonatomic, readonly, strong, nullable) NSArray<NSString*>* supportedUriSchemes;`

<span data-ttu-id="98d03-107">지원 되는 URI 스키마를 나타내는 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-107">An array of strings representing supported URI schemes.</span></span>

## <a name="methods"></a><span data-ttu-id="98d03-108">메서드</span><span class="sxs-lookup"><span data-stu-id="98d03-108">Methods</span></span>

### <a name="onlaunchuriasync"></a><span data-ttu-id="98d03-109">onLaunchUriAsync</span><span class="sxs-lookup"><span data-stu-id="98d03-109">onLaunchUriAsync</span></span>
```
- (void)onLaunchUriAsync:(nonnull NSString*)uri
         options:(nullable MCDRemoteLauncherOptions*)options
              completion:(nonnull void (^)(BOOL, NSError* _Nullable))completionBlock;
```

<span data-ttu-id="98d03-110">이 메서드는 원격 장치에서이 장치에서 URI를 시작 하려고 할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-110">This method is called when a remote device attempts to launch a URI on this device.</span></span>

#### <a name="parameters"></a><span data-ttu-id="98d03-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98d03-111">Parameters</span></span> 
* <span data-ttu-id="98d03-112">`uri` 시작 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-112">`uri` The URI to launch.</span></span>
* <span data-ttu-id="98d03-113">`options` 집합 URI를 실행 하기 위한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-113">`options` A set of options for launching the URI.</span></span> <span data-ttu-id="98d03-114">대체 URI는 설정할 수 있는 가능한 옵션 중 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-114">The fallback URI is only one of the possible options that can be set.</span></span>
* <span data-ttu-id="98d03-115">`completionBlock` 완료 될 때 실행할 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="98d03-115">`completionBlock` The code block to execute upon completion.</span></span>