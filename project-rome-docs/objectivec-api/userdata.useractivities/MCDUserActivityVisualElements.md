---
title: MCDUserActivityVisualElements
description: 이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: c969b8a52bc6d2a22fd0a00808f9bb374c63cd8a
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801065"
---
# <a name="class-mcduseractivityvisualelements"></a><span data-ttu-id="85bbb-104">클래스 `MCDUserActivityVisualElements`</span><span class="sxs-lookup"><span data-stu-id="85bbb-104">class `MCDUserActivityVisualElements`</span></span>

```
@interface MCDUserActivityVisualElements : NSObject 
```

<span data-ttu-id="85bbb-105">이 클래스는 MCDUserActivity "details" 타일에 표시 될 수 있는 아이콘 및 설명과 같은 시각적 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-105">This class contains the visual information, such as the description and icon, that can be shown in the "details" tile for a MCDUserActivity.</span></span>

## <a name="properties"></a><span data-ttu-id="85bbb-106">속성</span><span class="sxs-lookup"><span data-stu-id="85bbb-106">Properties</span></span>

### <a name="displaytext"></a><span data-ttu-id="85bbb-107">displayText</span><span class="sxs-lookup"><span data-stu-id="85bbb-107">displayText</span></span>
`@property(nonatomic, copy, nonnull) NSString* displayText;`

<span data-ttu-id="85bbb-108">작업의 "세부 정보" 타일에 대 한 표시 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-108">The display text for the "details" tile of the activity.</span></span>

### <a name="descriptiontext"></a><span data-ttu-id="85bbb-109">descriptionText</span><span class="sxs-lookup"><span data-stu-id="85bbb-109">descriptionText</span></span>
`@property(nonatomic, copy, nullable) NSString* descriptionText;`

<span data-ttu-id="85bbb-110">작업의 "세부 정보" 타일에 대 한 설명 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-110">The description text for the "details" tile of the activity.</span></span>

### <a name="backgroundcolor"></a><span data-ttu-id="85bbb-111">backgroundColor</span><span class="sxs-lookup"><span data-stu-id="85bbb-111">backgroundColor</span></span>
`@property(nonatomic, copy, nullable) SKColor* backgroundColor;`

<span data-ttu-id="85bbb-112">활동의 타일에 대 한 배경색입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-112">The background color for the tile of the activity.</span></span>

### <a name="attribution"></a><span data-ttu-id="85bbb-113">Attribution</span><span class="sxs-lookup"><span data-stu-id="85bbb-113">attribution</span></span>
`@property(nonatomic, retain, nullable) MCDUserActivityAttribution* attribution;`

<span data-ttu-id="85bbb-114">작업에 대 한 그래픽 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-114">The graphical information about the activity.</span></span>

### <a name="adaptivecardjson"></a><span data-ttu-id="85bbb-115">adaptiveCardJson</span><span class="sxs-lookup"><span data-stu-id="85bbb-115">adaptiveCardJson</span></span>
`@property(nonatomic, copy, nullable) NSString* adaptiveCardJson;`

<span data-ttu-id="85bbb-116">작업의 "세부 정보" 타일에 대 한 텍스트 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-116">The content text for the "details" tile of the activity.</span></span>

### <a name="attributiondisplaytext"></a><span data-ttu-id="85bbb-117">attributionDisplayText</span><span class="sxs-lookup"><span data-stu-id="85bbb-117">attributionDisplayText</span></span>
`@property(nonatomic, copy, nullable) NSString* attributionDisplayText;`

<span data-ttu-id="85bbb-118">활동 카드의 맨 위 배너에 표시 되는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="85bbb-118">The text that is shown in the top banner of the activity card.</span></span>