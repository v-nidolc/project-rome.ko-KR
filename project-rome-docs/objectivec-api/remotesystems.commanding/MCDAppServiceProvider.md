---
title: MCDAppServiceProvider
description: 이 프로토콜에는 로컬 앱 서비스를 원격 장치에 액세스할 수 있도록 하는 것에 대 한 메서드가 포함 됩니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: f5af56a2c87e3b4335a2a59a0130ef3622af6c26
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58908665"
---
# <a name="protocol-mcdappserviceprovider"></a><span data-ttu-id="05597-104">protocol `MCDAppServiceProvider`</span><span class="sxs-lookup"><span data-stu-id="05597-104">protocol `MCDAppServiceProvider`</span></span>

```
@protocol MCDAppServiceProvider<NSObject>
```

<span data-ttu-id="05597-105">이 프로토콜에는 로컬 앱 서비스를 원격 장치에 액세스할 수 있도록 하는 것에 대 한 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-105">This protocol contains methods for making a local app service accessible to remote devices.</span></span> <span data-ttu-id="05597-106">개발자는 앱 서비스를 원격 연결에 사용할 수 있도록 하기 위해이 프로토콜을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05597-106">Developers must implement this protocol to make their app services available for remote connectivity.</span></span>

## <a name="properties"></a><span data-ttu-id="05597-107">속성</span><span class="sxs-lookup"><span data-stu-id="05597-107">Properties</span></span>
 
### <a name="appserviceinfo"></a><span data-ttu-id="05597-108">appServiceInfo</span><span class="sxs-lookup"><span data-stu-id="05597-108">appServiceInfo</span></span>
`@property(nonatomic, readonly, strong, nonnull) MCDAppServiceInfo* appServiceInfo;`

<span data-ttu-id="05597-109">이 app service에 대 한 설명 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="05597-109">The descriptive information about this app service.</span></span>

## <a name="methods"></a><span data-ttu-id="05597-110">메서드</span><span class="sxs-lookup"><span data-stu-id="05597-110">Methods</span></span>

### <a name="connectiondidopen"></a><span data-ttu-id="05597-111">connectionDidOpen</span><span class="sxs-lookup"><span data-stu-id="05597-111">connectionDidOpen</span></span>
`- (void)connectionDidOpen:(nonnull MCDAppServiceConnectionOpenedInfo*)openedInfo;`

<span data-ttu-id="05597-112">이 메서드는이 app service에는 원격 앱 서비스 연결이 열릴 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05597-112">This method is called when a remote app service connection is opened to this app service.</span></span>

#### <a name="parameters"></a><span data-ttu-id="05597-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05597-113">Parameters</span></span> 
* `openedInfo`

<span data-ttu-id="05597-114">App service를 사용 하 여 원격 메시징에 대 한 정보를 포함 하는 MDCAppServiceConnectionOpenedInfo 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="05597-114">A MDCAppServiceConnectionOpenedInfo instance containing information for remote messaging with the app service.</span></span>