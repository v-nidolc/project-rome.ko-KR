---
title: MCDConnectedDevicesAccountType
description: Microsoft에서 제공한 사용자 계정의 유형을 설명 하는 값을 포함 합니다.
keywords: microsoft, windows, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: 5461398e3725b7a1e6937172c40336db60432666
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59801515"
---
# <a name="enum-mcdconnecteddevicesaccounttype"></a>열거형 `MCDConnectedDevicesAccountType`

```
typedef NS_ENUM(NSInteger, MCDConnectedDevicesAccountType)
```  

Microsoft에서 제공한 사용자 계정의 유형을 설명 하는 값을 포함 합니다.

## <a name="fields"></a>필드

| 이름                              | 값 | 설명                    |
|:----------------------------------|:------|:-------------------------------|
| MCDConnectedDevicesAccountTypeAAD       | 0     | Azure Active Directory workplace 계정  |
| MCDConnectedDevicesAccountTypeMSA       | 1     | Microsoft 개인 계정 |
| MCDConnectedDevicesAccountTypeAnonymous | 2     | 익명 (로컬, 인증 되지 않은) 계정 |