---
title: MCDAppServiceConnectionOpenedInfo
description: 이 클래스는 원격 장치 로컬 앱 서비스에 대 한 연결을 열 때 발생 하는 MCDAppServiceProvider.connectionDidOpen 이벤트에 대 한 데이터를 제공 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b700c95d7ab093b47a94c856c25b946fc5df12d7
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907555"
---
# <a name="class-mcdappserviceconnectionopenedinfo"></a><span data-ttu-id="f1708-104">클래스 `MCDAppServiceConnectionOpenedInfo`</span><span class="sxs-lookup"><span data-stu-id="f1708-104">class `MCDAppServiceConnectionOpenedInfo`</span></span> 

```
@interface MCDAppServiceConnectionOpenedInfo : NSObject
```  

<span data-ttu-id="f1708-105">이 클래스는 원격 장치 로컬 앱 서비스에 대 한 연결을 열 때 발생 하는 MCDAppServiceProvider.connectionDidOpen 이벤트에 대 한 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1708-105">This class provides data for the MCDAppServiceProvider.connectionDidOpen event, which is raised when a remote device opens a connection to a local app service.</span></span>

## <a name="properties"></a><span data-ttu-id="f1708-106">속성</span><span class="sxs-lookup"><span data-stu-id="f1708-106">Properties</span></span>

### <a name="appserviceconnection"></a><span data-ttu-id="f1708-107">appServiceConnection</span><span class="sxs-lookup"><span data-stu-id="f1708-107">appServiceConnection</span></span>
`@property(nonatomic, readonly, nonnull) MCDAppServiceConnection* appServiceConnection;`

<span data-ttu-id="f1708-108">로컬 app service와 원격 장치 간의 연결을 나타내는 MCDAppServiceConnection 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f1708-108">An MCDAppServiceConnection instance representing the connection between the local app service and the remote device.</span></span>

### <a name="remotesystemapp"></a><span data-ttu-id="f1708-109">remoteSystemApp</span><span class="sxs-lookup"><span data-stu-id="f1708-109">remoteSystemApp</span></span>
`@property(nonatomic, readonly, nullable) MCDRemoteSystemApp* remoteSystemApp;`

<span data-ttu-id="f1708-110">MCDRemoteSystemApp 원격 응용 프로그램 로컬 app service에 대 한 연결을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1708-110">The MCDRemoteSystemApp remote application that initiated a connection to the local app service.</span></span>