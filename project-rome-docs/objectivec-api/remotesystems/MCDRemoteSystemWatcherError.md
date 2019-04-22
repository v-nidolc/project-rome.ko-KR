---
title: MCDRemoteSystemWatcherError
description: 검색 프로세스 중에 원격 시스템 감시자 개체에서 발생 한 오류가 describe는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 3f65614396377b154b2a37493b8271ac54afb6fd
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801725"
---
# <a name="enum-mcdremotesystemwatchererror"></a><span data-ttu-id="b09ec-104">열거형 `MCDRemoteSystemWatcherError`</span><span class="sxs-lookup"><span data-stu-id="b09ec-104">enum `MCDRemoteSystemWatcherError`</span></span> 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemWatcherError)
```  
 <span data-ttu-id="b09ec-105">검색 프로세스 중에 원격 시스템 감시자 개체에서 발생 한 오류가 describe는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b09ec-105">Contains values that the describe an error encountered by a remote system watcher object during the discovery process.</span></span>

## <a name="fields"></a><span data-ttu-id="b09ec-106">필드</span><span class="sxs-lookup"><span data-stu-id="b09ec-106">Fields</span></span>

| <span data-ttu-id="b09ec-107">이름</span><span class="sxs-lookup"><span data-stu-id="b09ec-107">Name</span></span>                              | <span data-ttu-id="b09ec-108">값</span><span class="sxs-lookup"><span data-stu-id="b09ec-108">Value</span></span> | <span data-ttu-id="b09ec-109">설명</span><span class="sxs-lookup"><span data-stu-id="b09ec-109">Description</span></span>                    |
|:----------------------------------|:------|:-------------------------------|
| <span data-ttu-id="b09ec-110">MCDRemoteSystemWatcherErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="b09ec-110">MCDRemoteSystemWatcherErrorUnknown</span></span> | <span data-ttu-id="b09ec-111">0</span><span class="sxs-lookup"><span data-stu-id="b09ec-111">0</span></span> | <span data-ttu-id="b09ec-112">감시자 알 수 없는 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b09ec-112">The watcher encountered an unknown error.</span></span> |
| <span data-ttu-id="b09ec-113">MCDRemoteSystemWatcherErrorInternetNotAvailable</span><span class="sxs-lookup"><span data-stu-id="b09ec-113">MCDRemoteSystemWatcherErrorInternetNotAvailable</span></span> | <span data-ttu-id="b09ec-114">1</span><span class="sxs-lookup"><span data-stu-id="b09ec-114">1</span></span> | <span data-ttu-id="b09ec-115">인터넷 연결이 손실 된 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b09ec-115">The error occurred because the Internet connection was lost.</span></span> |
| <span data-ttu-id="b09ec-116">MCDRemoteSystemWatcherErrorAuthenticationError</span><span class="sxs-lookup"><span data-stu-id="b09ec-116">MCDRemoteSystemWatcherErrorAuthenticationError</span></span> | <span data-ttu-id="b09ec-117">2</span><span class="sxs-lookup"><span data-stu-id="b09ec-117">2</span></span> | <span data-ttu-id="b09ec-118">검색을 실행 하는 데 사용 되는 ConnectedDevicesAccount를 인증할 수 없으므로 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b09ec-118">The error occurred because a ConnectedDevicesAccount being used to run the discovery could not be authenticated.</span></span> | 
