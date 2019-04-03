---
title: MCDRemoteLauncherOptions
description: 원격 실행 기능에 대 한 옵션을 나타내는 데 사용 되는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 628bf1659dfb4ce50e20631622d8a78a322bb2f5
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907335"
---
# <a name="class-mcdremotelauncheroptions"></a><span data-ttu-id="49f92-104">클래스 `MCDRemoteLauncherOptions`</span><span class="sxs-lookup"><span data-stu-id="49f92-104">class `MCDRemoteLauncherOptions`</span></span> 

```
@interface MCDRemoteLauncherOptions : NSObject
```  

<span data-ttu-id="49f92-105">원격 실행 기능에 대 한 옵션을 나타내는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-105">A class to represent options for the remote launch feature.</span></span>

## <a name="properties"></a><span data-ttu-id="49f92-106">속성</span><span class="sxs-lookup"><span data-stu-id="49f92-106">Properties</span></span>

### <a name="fallbackuri"></a><span data-ttu-id="49f92-107">fallbackUri</span><span class="sxs-lookup"><span data-stu-id="49f92-107">fallbackUri</span></span>
`@property(nonatomic, copy, nullable) NSString* fallbackUri;`

<span data-ttu-id="49f92-108">대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-108">The fallback URI to launch on the web in case the app launch URI fails.</span></span>

### <a name="preferredpackageids"></a><span data-ttu-id="49f92-109">preferredPackageIds</span><span class="sxs-lookup"><span data-stu-id="49f92-109">preferredPackageIds</span></span>
`@property(nonatomic, copy, nullable) NSArray<NSString*>* preferredPackageIds;`

<span data-ttu-id="49f92-110">목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-110">A list of **NSString** objects representing IDs of the apps that should be able to launch with this URI.</span></span> <span data-ttu-id="49f92-111">Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-111">For Windows apps, the ID will be the app's package family name.</span></span>

## <a name="constructors"></a><span data-ttu-id="49f92-112">생성자</span><span class="sxs-lookup"><span data-stu-id="49f92-112">Constructors</span></span>

### <a name="optionswithfallbackuri"></a><span data-ttu-id="49f92-113">optionsWithFallbackUri</span><span class="sxs-lookup"><span data-stu-id="49f92-113">optionsWithFallbackUri</span></span>
`+ (nullable instancetype)optionsWithFallbackUri: (nullable NSString*)fallbackUri  preferredPackageIds: (nullable NSArray<NSString*>*)preferredPackageIds;`

<span data-ttu-id="49f92-114">페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-114">Creates and initializes a new instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="49f92-115">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49f92-115">Parameters</span></span>
* `fallbackUri` 

<span data-ttu-id="49f92-116">대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-116">The fallback URI to launch on the web in case the app launch URI fails.</span></span>

* `preferredPackageIds` 

<span data-ttu-id="49f92-117">목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-117">A list of **NSString** objects representing IDs of the apps that should be able to launch with this URI.</span></span> <span data-ttu-id="49f92-118">Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-118">For Windows apps, the ID will be the app's package family name.</span></span>

#### <a name="returns"></a><span data-ttu-id="49f92-119">반환 값</span><span class="sxs-lookup"><span data-stu-id="49f92-119">Returns</span></span>
<span data-ttu-id="49f92-120">초기화 반환 [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-120">Returns the initialized [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) if successful, otherwise nil.</span></span>

### <a name="initwithfallbackuri"></a><span data-ttu-id="49f92-121">initWithFallbackUri</span><span class="sxs-lookup"><span data-stu-id="49f92-121">initWithFallbackUri</span></span>
`- (nullable instancetype)initWithFallbackUri:(nullable NSString*)fallbackUri preferredPackageIds:(nullable NSArray<NSString*>*)preferredPackageIds;`

<span data-ttu-id="49f92-122">페이지를 만들고이 클래스의 새 인스턴스를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-122">Creates and initializes a new instance of this class.</span></span>

#### <a name="parameters"></a><span data-ttu-id="49f92-123">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49f92-123">Parameters</span></span>
* `fallbackUri` 

<span data-ttu-id="49f92-124">대체 URI 경우 앱 시작 URI는 웹에서 시작에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-124">The fallback URI to launch on the web in case the app launch URI fails.</span></span>

* `preferredPackageIds` 

<span data-ttu-id="49f92-125">목록을 **NSString** 이 URI를 사용 하 여 시작 하는 일을 할 수 있어야 하는 앱의 Id를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-125">A list of **NSString** objects representing IDs of the apps that should be able to launch with this URI.</span></span> <span data-ttu-id="49f92-126">Windows 앱에 대 한 ID를 앱의 패키지 패밀리 이름 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-126">For Windows apps, the ID will be the app's package family name.</span></span>

#### <a name="returns"></a><span data-ttu-id="49f92-127">반환 값</span><span class="sxs-lookup"><span data-stu-id="49f92-127">Returns</span></span>
<span data-ttu-id="49f92-128">초기화 반환 [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) 성공 하면이 고 그렇지 nil 합니다.</span><span class="sxs-lookup"><span data-stu-id="49f92-128">Returns the initialized [MCDRemoteLauncherOptions](MCDRemoteLauncherOptions.md) if successful, otherwise nil.</span></span>