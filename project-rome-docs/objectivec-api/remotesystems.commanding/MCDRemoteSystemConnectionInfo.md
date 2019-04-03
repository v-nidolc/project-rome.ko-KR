---
title: MCDRemoteSystemConnectionInfo
description: 추가 지정된 MCDAppServiceConnection 인스턴스에 대 한 정보를 제공 하는 클래스입니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: cdfe9dec49e90013f8c967223803144ad655378e
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907055"
---
# <a name="class-mcdremotesystemconnectioninfo"></a><span data-ttu-id="ecd19-104">클래스 `MCDRemoteSystemConnectionInfo`</span><span class="sxs-lookup"><span data-stu-id="ecd19-104">class `MCDRemoteSystemConnectionInfo`</span></span> 

```
@interface MCDRemoteSystemConnectionInfo : NSObject
```  

<span data-ttu-id="ecd19-105">에 대 한 추가 정보를 제공 하는 클래스는 주어진 **[MCDAppServiceConnection](MCDAppServiceConnection.md)** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ecd19-105">A class that provides further information about a given **[MCDAppServiceConnection](MCDAppServiceConnection.md)** instance.</span></span>

## <a name="properties"></a><span data-ttu-id="ecd19-106">속성</span><span class="sxs-lookup"><span data-stu-id="ecd19-106">Properties</span></span>

### <a name="proximal"></a><span data-ttu-id="ecd19-107">proximal</span><span class="sxs-lookup"><span data-stu-id="ecd19-107">proximal</span></span>
`@property(nonatomic, readonly, getter=isProximal) BOOL proximal;`

<span data-ttu-id="ecd19-108">연결 된 연결이 proximal 연결 되었는지 여부가 표시 됩니다 (**예**) 여부 (**NO**).</span><span class="sxs-lookup"><span data-stu-id="ecd19-108">Displays whether the associated connection is a proximal connection (**YES**) or not (**NO**).</span></span>

## <a name="constructors"></a><span data-ttu-id="ecd19-109">생성자</span><span class="sxs-lookup"><span data-stu-id="ecd19-109">Constructors</span></span>

### <a name="trycreatefromappserviceconnection"></a><span data-ttu-id="ecd19-110">tryCreateFromAppServiceConnection</span><span class="sxs-lookup"><span data-stu-id="ecd19-110">tryCreateFromAppServiceConnection</span></span>
`+ (nullable instancetype)tryCreateFromAppServiceConnection:(nonnull MCDAppServiceConnection*)appServiceConnection;`

<span data-ttu-id="ecd19-111">지정 된 앱 서비스 연결에서이 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecd19-111">Creates an instance of this class from the given app service connection.</span></span>

#### <a name="parameters"></a><span data-ttu-id="ecd19-112">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecd19-112">Parameters</span></span>
* `appServiceConnection` 

<span data-ttu-id="ecd19-113">**MCDAppServiceConnection** 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ecd19-113">An **MCDAppServiceConnection** instance.</span></span>

#### <a name="returns"></a><span data-ttu-id="ecd19-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="ecd19-114">Returns</span></span>
<span data-ttu-id="ecd19-115">앱 서비스 연결에 해당 하는이 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecd19-115">Returns an instance of this class corresponding to the app service connection.</span></span>