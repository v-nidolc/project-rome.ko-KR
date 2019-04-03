---
title: MCDUserActivityVisualElements
description: 이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c969b8a52bc6d2a22fd0a00808f9bb374c63cd8a
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907415"
---
# <a name="class-mcduseractivityvisualelements"></a><span data-ttu-id="b7b9d-104">클래스 `MCDUserActivityVisualElements`</span><span class="sxs-lookup"><span data-stu-id="b7b9d-104">class `MCDUserActivityVisualElements`</span></span>

```
@interface MCDUserActivityVisualElements : NSObject 
```

<span data-ttu-id="b7b9d-105">이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-105">This class contains the visual information, such as the description and icon, that can be shown in the "details" tile for a MCDUserActivity.</span></span>

## <a name="properties"></a><span data-ttu-id="b7b9d-106">속성</span><span class="sxs-lookup"><span data-stu-id="b7b9d-106">Properties</span></span>

### <a name="displaytext"></a><span data-ttu-id="b7b9d-107">displayText</span><span class="sxs-lookup"><span data-stu-id="b7b9d-107">displayText</span></span>
`@property(nonatomic, copy, nonnull) NSString* displayText;`

<span data-ttu-id="b7b9d-108">작업의 "세부 정보" 타일에 대 한 표시 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-108">The display text for the "details" tile of the activity.</span></span>

### <a name="descriptiontext"></a><span data-ttu-id="b7b9d-109">descriptionText</span><span class="sxs-lookup"><span data-stu-id="b7b9d-109">descriptionText</span></span>
`@property(nonatomic, copy, nullable) NSString* descriptionText;`

<span data-ttu-id="b7b9d-110">작업의 "세부 정보" 타일에 대 한 설명 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-110">The description text for the "details" tile of the activity.</span></span>

### <a name="backgroundcolor"></a><span data-ttu-id="b7b9d-111">backgroundColor</span><span class="sxs-lookup"><span data-stu-id="b7b9d-111">backgroundColor</span></span>
`@property(nonatomic, copy, nullable) SKColor* backgroundColor;`

<span data-ttu-id="b7b9d-112">활동의 타일에 대 한 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-112">The background color for the tile of the activity.</span></span>

### <a name="attribution"></a><span data-ttu-id="b7b9d-113">Attribution</span><span class="sxs-lookup"><span data-stu-id="b7b9d-113">attribution</span></span>
`@property(nonatomic, retain, nullable) MCDUserActivityAttribution* attribution;`

<span data-ttu-id="b7b9d-114">작업에 대 한 그래픽 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-114">The graphical information about the activity.</span></span>

### <a name="adaptivecardjson"></a><span data-ttu-id="b7b9d-115">adaptiveCardJson</span><span class="sxs-lookup"><span data-stu-id="b7b9d-115">adaptiveCardJson</span></span>
`@property(nonatomic, copy, nullable) NSString* adaptiveCardJson;`

<span data-ttu-id="b7b9d-116">작업의 "세부 정보" 타일에 대 한 텍스트 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-116">The content text for the "details" tile of the activity.</span></span>

### <a name="attributiondisplaytext"></a><span data-ttu-id="b7b9d-117">attributionDisplayText</span><span class="sxs-lookup"><span data-stu-id="b7b9d-117">attributionDisplayText</span></span>
`@property(nonatomic, copy, nullable) NSString* attributionDisplayText;`

<span data-ttu-id="b7b9d-118">활동 카드의 맨 위 배너에 표시 되는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b7b9d-118">The text that is shown in the top banner of the activity card.</span></span>