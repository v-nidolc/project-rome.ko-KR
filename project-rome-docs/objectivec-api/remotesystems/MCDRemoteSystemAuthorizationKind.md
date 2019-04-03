---
title: MCDRemoteSystemAuthorizationKind
description: 원격 시스템 검색에 대 한 잠재적인 권한 부여 종류 (사용자 계정 기반 권한 부여 범위)를 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 4f54d187282e946dd2912d1d72eacc02c7ee4077
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907635"
---
# <a name="enum-mcdremotesystemauthorizationkind"></a>열거형 `MCDRemoteSystemAuthorizationKind` 

```
typedef NS_ENUM(NSInteger, MCDRemoteSystemAuthorizationKind)
```  

원격 시스템 검색에 대 한 잠재적인 권한 부여 종류 (사용자 계정 기반 권한 부여 범위)를 설명 하는 값을 포함 합니다. 

## <a name="fields"></a>필드

| 이름                              | 값 | 설명                    |
|:----------------------------------|:------|:-------------------------------|
| MCDRemoteSystemAuthorizationKindSameUser   | 0     | 만 시스템 검색 하 고 동일한 사용자 계정으로 로그온 하는 장치를 연결할 수 있습니다.   |
| MCDRemoteSystemAuthorizationKindAnonymous | 1     | 시스템 검색 하 고 근접에서 되며 익명 검색을 허용 하는 제공 다른 사용자의 장치를 연결할 수 있습니다.  |

