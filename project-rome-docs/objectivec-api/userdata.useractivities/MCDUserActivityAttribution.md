---
title: MCDUserActivityAttribution
description: 이 클래스는 사용자 활동의 그래픽 요소를 관리합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 94ae2f5afef24a1f4e320014ac930d67b657b0d7
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801545"
---
# <a name="class-mcduseractivityattribution"></a><span data-ttu-id="ae4a3-104">클래스 `MCDUserActivityAttribution`</span><span class="sxs-lookup"><span data-stu-id="ae4a3-104">class `MCDUserActivityAttribution`</span></span>

```
@interface MCDUserActivityAttribution : NSObject
```

<span data-ttu-id="ae4a3-105">이 클래스는 사용자 활동의 그래픽 요소를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-105">This class manages the graphical elements of a user activity.</span></span>

## <a name="properties"></a><span data-ttu-id="ae4a3-106">속성</span><span class="sxs-lookup"><span data-stu-id="ae4a3-106">Properties</span></span>

### <a name="iconuri"></a><span data-ttu-id="ae4a3-107">iconUri</span><span class="sxs-lookup"><span data-stu-id="ae4a3-107">iconUri</span></span>
`+ (nullable instancetype)attributionWithIconUri:(nonnull NSString*)iconUri;`

<span data-ttu-id="ae4a3-108">아이콘 이미지에 대 한 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-108">The URI for the icon image.</span></span>

### <a name="alternatetext"></a><span data-ttu-id="ae4a3-109">alternateText</span><span class="sxs-lookup"><span data-stu-id="ae4a3-109">alternateText</span></span>
`@property(nonatomic, copy, nonnull) NSString* alternateText;`

<span data-ttu-id="ae4a3-110">아이콘 이미지 (를 사용 하 여 화면 판독기를 사용 하 여) 설명 하는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-110">The text that describes the icon image (for use with screen readers).</span></span>

### <a name="addimagequery"></a><span data-ttu-id="ae4a3-111">addImageQuery</span><span class="sxs-lookup"><span data-stu-id="ae4a3-111">addImageQuery</span></span>
`@property(nonatomic, assign) BOOL addImageQuery;`

<span data-ttu-id="ae4a3-112">Windows 이미지에서 제공 된 URI에 쿼리 문자열을 추가 하도록 허용 여부를 결정 **IconUri** 이미지를 검색 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-112">Determines whether to allow Windows to append a query string to the image URI supplied from **IconUri** when retrieving the image.</span></span> <span data-ttu-id="ae4a3-113">쿼리 문자열에는 사용자의 표시, 고대비 설정 및 사용자의 언어의 DPI를 기준으로 이상적인 이미지를 선택 하는 데 도움이 되는 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-113">The query string includes information that can help select the ideal image based on the DPI of the user's display, the high contrast setting, and the user's language.</span></span> <span data-ttu-id="ae4a3-114">이 쿼리 문자열 확장, 대비 설정 및 언어를 지정합니다. 예를 들어를 **IconUri** "www.website.com/images/hello.png"의 값이 됩니다 "www.website.com/images/hello.png?ms-scale=100 및 ms 대비 표준 ms lang = = en-우리"입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-114">This query string specifies scale, contrast setting, and language; for instance, an **IconUri** value of "www.website.com/images/hello.png" becomes "www.website.com/images/hello.png?ms-scale=100&ms-contrast=standard&ms-lang=en-us".</span></span>

## <a name="constructors"></a><span data-ttu-id="ae4a3-115">생성자</span><span class="sxs-lookup"><span data-stu-id="ae4a3-115">Constructors</span></span>

### <a name="useractivityattributionwithiconuri"></a><span data-ttu-id="ae4a3-116">userActivityAttributionWithIconUri</span><span class="sxs-lookup"><span data-stu-id="ae4a3-116">userActivityAttributionWithIconUri</span></span>
`+ (nullable instancetype)userActivityAttributionWithIconUri:(nonnull NSString*)iconUri;`

<span data-ttu-id="ae4a3-117">아이콘 URI를 사용 하 여이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-117">Creates an instance of this class with an Icon URI.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ae4a3-118">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae4a3-118">Parameters</span></span>
* `iconUri` 

<span data-ttu-id="ae4a3-119">만든 인스턴스에 속한 아이콘 URI의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-119">A string value of an Icon URI to belong to the created instance.</span></span>

#### <a name="returns"></a><span data-ttu-id="ae4a3-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae4a3-120">Returns</span></span>
<span data-ttu-id="ae4a3-121">아이콘 uri를 사용 하 여 초기화 MCDUserActivityAttribution 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-121">Returns an MCDUserActivityAttribution object initialized with an icon uri.</span></span>

### <a name="attributionwithiconuri"></a><span data-ttu-id="ae4a3-122">attributionWithIconUri</span><span class="sxs-lookup"><span data-stu-id="ae4a3-122">attributionWithIconUri</span></span>
`+ (nullable instancetype)attributionWithIconUri:(nonnull NSString*)iconUri;`

<span data-ttu-id="ae4a3-123">아이콘 uri 특성을 사용 하 여이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-123">Creates an instance of this class with attribution to a icon uri.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ae4a3-124">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae4a3-124">Parameters</span></span>
* `iconUri` 

<span data-ttu-id="ae4a3-125">만든 인스턴스에 속한 아이콘 URI의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-125">A string value of an Icon URI to belong to the created instance.</span></span>

#### <a name="returns"></a><span data-ttu-id="ae4a3-126">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae4a3-126">Returns</span></span>
<span data-ttu-id="ae4a3-127">아이콘 uri를 사용 하 여 MCDUserActivityAttribution 개체 특성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4a3-127">Returns an MCDUserActivityAttribution object attributing with an icon uri.</span></span>