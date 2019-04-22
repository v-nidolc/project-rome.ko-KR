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
# <a name="enum-mcdremotesystemwatchererror"></a>열거형 `MCDRemoteSystemWatcherError` 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemWatcherError)
```  
 검색 프로세스 중에 원격 시스템 감시자 개체에서 발생 한 오류가 describe는 값을 포함 합니다.

## <a name="fields"></a>필드

| 이름                              | 값 | 설명                    |
|:----------------------------------|:------|:-------------------------------|
| MCDRemoteSystemWatcherErrorUnknown | 0 | 감시자 알 수 없는 오류가 발생 했습니다. |
| MCDRemoteSystemWatcherErrorInternetNotAvailable | 1 | 인터넷 연결이 손실 된 오류가 발생 했습니다. |
| MCDRemoteSystemWatcherErrorAuthenticationError | 2 | 검색을 실행 하는 데 사용 되는 ConnectedDevicesAccount를 인증할 수 없으므로 오류가 발생 합니다. | 
