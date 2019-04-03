---
title: MCDConnectedDevicesPlatformSettings
description: 연결 된 장치 플랫폼 설정을 특정 위치에 저장할 수 있도록 하는 인터페이스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 9753553cefbbeaff598550687b8dfa5100d2006e
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908895"
---
# <a name="class-mcdconnecteddevicesplatformsettings"></a><span data-ttu-id="b123d-104">클래스 `MCDConnectedDevicesPlatformSettings`</span><span class="sxs-lookup"><span data-stu-id="b123d-104">class `MCDConnectedDevicesPlatformSettings`</span></span> 

```
@interface MCDConnectedDevicesPlatformSettings : NSObject
```  
<span data-ttu-id="b123d-105">연결 된 장치 플랫폼 설정을 특정 위치에 저장할 수 있도록 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b123d-105">An interface to allow Connected Devices Platform settings to be stored in a particular location.</span></span>  

## <a name="properties"></a><span data-ttu-id="b123d-106">속성</span><span class="sxs-lookup"><span data-stu-id="b123d-106">Properties</span></span>

### <a name="storagepath"></a><span data-ttu-id="b123d-107">storagePath</span><span class="sxs-lookup"><span data-stu-id="b123d-107">storagePath</span></span>
`@property (nonatomic, readwrite, nonnull) NSString* storagePath;`

<span data-ttu-id="b123d-108">장치 플랫폼 연결 설정의 저장소 위치에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b123d-108">The path to the storage location of the Connected Devices Platform settings.</span></span>