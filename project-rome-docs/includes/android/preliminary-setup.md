---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: e2a3dcbff4594a7886a14f90058bb814e85ff39d
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804659"
---
## <a name="preliminary-setup-for-the-connected-devices-platform-and-notifications"></a>알림과 연결 된 장치 플랫폼에 대 한 예비 설치

원격 연결을 구현 하기 전에 Android 앱 뿐만 아니라 원격 장치에 연결 하 고, 전송 하 고, 알림을 수신 하는 기능을 제공 하는 데 해야 하는 몇 가지 단계가 있습니다.

### <a name="register-your-app"></a>앱 등록

Microsoft 계정 (MSA) 또는 Azure Active Directory (AAD) 인증이 프로젝트 로마 SDK (제외 하 고 주변 공유 Api)의 거의 모든 기능에 대 한 필요 합니다. MSA가 있지 않으며 하나를 사용 하려는 경우 레지스터 [account.microsoft.com](https://account.microsoft.com/account)합니다.

선택한 인증 방법을 사용 하면 앱을 등록 해야 microsoft 지침에 따라 합니다 [응용 프로그램 등록 포털](https://apps.dev.microsoft.com/)합니다. Microsoft 개발자 계정이 없는 경우 새로 만들려면 해야 합니다.

MSA를 사용 하 여 앱을 등록 하는 경우 클라이언트 ID 문자열을 받게 됩니다. 나중에이 저장 합니다. 앱을 Microsoft의 연결 된 장치 플랫폼 리소스에 액세스할 수 있습니다. AAD를 사용 하는 경우 참조 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 방법은 클라이언트 ID 문자열에 대 한 합니다.

### <a name="add-the-sdk"></a>SDK를 추가 합니다.

에 다음 리포지토리 참조를 삽입 합니다 *build.gradle* 프로젝트의 루트에 있는 파일입니다.

```Java
allprojects {
    repositories {
        jcenter()
    }
}
```
그런 다음에 다음 종속성을 삽입 합니다 _build.gradle_ 프로젝트 폴더에 있는 파일입니다.

```Java
dependencies { 
    ...
    implementation 'com.microsoft.connecteddevices:connecteddevices-sdk:+'
}
```

프로젝트의 *AndroidManifest.xml* 파일에서 내에서 다음 사용 권한을 추가 `<manifest>` 요소 (없습니다 이미 존재할 경우). 인터넷에 연결 하 고 장치에서 Bluetooth 검색을 사용 하도록 앱 권한을 제공 합니다.

Bluetooth 검색;을 사용 하는 데 필요한 Bluetooth 관련 권한 개만 note 연결 된 장치 플랫폼의 다른 기능이 필요 하지 않습니다. 또한 `ACCESS_COARSE_LOCATION` Android Sdk 21에 필요 하 고 이상만 됩니다. Android Sdk 23 이상, 개발자는 런타임 시 위치 액세스 권한을 부여할 사용자를 요청도 해야 합니다.


```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

다음으로 이동 활동 클래스 live에 연결 된 장치 기능 하려는 합니다. 가져오기는 다음 패키지 있습니다.

```java
import com.microsoft.connecteddevices;
import com.microsoft.connecteddevices.remotesystems;
import com.microsoft.connecteddevices.remotesystems.commanding;
```
