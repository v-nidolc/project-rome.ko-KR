---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 53cbe2ec68785c257341caf110439d535b8f83be
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804662"
---
### <a name="register-your-app"></a>앱 등록

Microsoft 계정 (MSA) 또는 Azure Active Directory (AAD) 인증이 프로젝트 로마 SDK (제외 하 고 주변 공유 Api)의 거의 모든 기능에 대 한 필요 합니다. MSA가 있지 않으며 하나를 사용 하려는 경우 레지스터 [account.microsoft.com](https://account.microsoft.com/account)합니다.

선택한 인증 방법을 사용 하면 앱을 등록 해야 microsoft 지침에 따라 합니다 [응용 프로그램 등록 포털](https://apps.dev.microsoft.com/)합니다. Microsoft 개발자 계정이 없는 경우 새로 만들려면 해야 합니다.

MSA를 사용 하 여 앱을 등록 하는 경우 클라이언트 ID 문자열을 받게 됩니다. 나중에이 저장 합니다. 앱을 Microsoft의 연결 된 장치 플랫폼 리소스에 액세스할 수 있습니다. AAD를 사용 하는 경우 참조 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 방법은 클라이언트 ID 문자열에 대 한 합니다.

### <a name="add-the-sdk"></a>SDK를 추가 합니다.

사용 하 여 iOS 앱에 연결 된 장치 플랫폼을 추가 하는 가장 간단한 방법은는 [CocoaPods](https://cocoapods.org/) 종속성 관리자입니다. IOS 프로젝트의 이동 *Podfile* 하 고 다음 항목을 삽입 합니다.

```ObjectiveC
platform :ios, "10.0"
workspace 'iOSSample'

target 'iOSSample' do
  # Uncomment the next line if you're using Swift or would like to use dynamic frameworks
  # use_frameworks!

    pod 'ProjectRomeSdk'

  # Pods for iOSSample
```

> [!NOTE]
> CocoaPod를 사용 하려면 사용 해야 합니다 _.xcworkspace 인_ 프로젝트의 파일입니다.
