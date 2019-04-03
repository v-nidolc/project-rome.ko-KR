---
title: MCDRemoteSystemAppRegistrationPublishResult
description: 클래스는 계정에 대 한 정보를 게시 원격 시스템 앱의 비동기 결과 통신합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5e28e2533d14839384bcd2cfac2db3fc368a6207
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909925"
---
# <a name="class-mcdremotesystemappregistrationpublishresult"></a><span data-ttu-id="b04c1-104">클래스 `MCDRemoteSystemAppRegistrationPublishResult`</span><span class="sxs-lookup"><span data-stu-id="b04c1-104">class `MCDRemoteSystemAppRegistrationPublishResult`</span></span> 

```
@interface MCDRemoteSystemAppRegistrationPublishResult : NSObject
```  

<span data-ttu-id="b04c1-105">이 클래스는 계정에 대 한 정보를 게시 원격 시스템 앱의 비동기 결과 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="b04c1-105">This class communicates the async result of publishing remote system app information for an account.</span></span> <span data-ttu-id="b04c1-106">이 결과 통해 통신 하는 오류 상태를 사용할 수 없는 네트워크와 같은 특정 일시적인 장애가 발생할 경우 게시를 다시 시도 하는 앱에서 사용할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04c1-106">The error statuses communicated through this result should be used by the app to retry publishing in the event of certain transient conditions like the network being unavailable.</span></span>

## <a name="properties"></a><span data-ttu-id="b04c1-107">속성</span><span class="sxs-lookup"><span data-stu-id="b04c1-107">Properties</span></span>

### <a name="status"></a><span data-ttu-id="b04c1-108">상태</span><span class="sxs-lookup"><span data-stu-id="b04c1-108">status</span></span>
`@property(nonatomic, readonly) MCDRemoteSystemAppRegistrationPublishStatus status;`

<span data-ttu-id="b04c1-109">게시 작업의 상태 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="b04c1-109">Status enum of the publish operation.</span></span>