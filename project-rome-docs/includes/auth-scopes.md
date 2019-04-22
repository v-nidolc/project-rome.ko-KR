---
title: 파일 포함
description: 파일 포함
ms.assetid: 93f45482-14e4-4aec-8185-ee05b592215f
ms.localizationpriority: medium
ms.openlocfilehash: d94808ae1e97d12649f24ed89ad17a7962665d5e
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804661"
---
### <a name="set-up-authentication-and-account-management"></a>인증 및 계정 관리 설정

연결 된 장치 플랫폼에는 등록 프로세스에 사용할 유효한 OAuth 토큰에 필요 합니다.  생성 하 고 OAuth 토큰 관리의 기본 방법을 사용할 수 있습니다.  그러나 하는 데 개발자 플랫폼을 사용 하 여 시작, 인증 공급자의 일부로 포함 되어는 [Android 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/Android/samples) 생성 하 고 편의 위해 새로 고침 토큰을 관리 합니다.

구현 하려는 경우는 **[ConnectedDevicesAccountManager](https://docs.microsoft.com/java/api/com.microsoft.connecteddevices.core._user_account_provider)** 인터페이스를 직접, 다음 정보를 기록 합니다. 

MSA를 사용 하는 경우 로그인 요청에 다음과 같은 범위를 포함 해야 합니다: `"wl.offline_access"`, `"ccs.ReadWrite"`를 `"dds.read"`, `"dds.register"`를 `"wns.connect"`를 `"asimovrome.telemetry"`, 및 `"https://activity.windows.com/UserActivity.ReadWrite.CreatedByApp"`합니다. 

대상 사용자를 요청 해야 AAD 계정을 사용 하는 경우: `"https://cdpcs.access.microsoft.com"`, `"https://cs.dds.microsoft.com"`를 `"https://wns.windows.com/"`, 및 `"https://activity.microsoft.com"`합니다.

제공 된 사용할지 **ConnectedDevicesAccountManager** 구현 또는 Azure portal에서 앱의 등록에 다음 사용 권한을 지정 해야 하는 AAD를 사용 하는 경우 not (portal.azure.com > Azure Active Directory > 앱 등록): 
* Microsoft 작업 피드 서비스 
  * 제공 하 고 수정이 앱에 대 한 사용자 알림
  * 읽기 및 피드 사용자의 활동에 앱 활동 작성
* Windows 알림 서비스
  * Windows 알림 서비스에 장치 연결 
* Microsoft 장치 디렉터리 서비스
  * 장치 목록 보기
  * 장치 및 앱 목록에 추가 
* Microsoft Command 서비스
  * 사용자 장치와 통신
  * 사용자 장치 읽기
