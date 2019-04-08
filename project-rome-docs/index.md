---
title: 디바이스 간 애플리케이션 빌드
description: 프로젝트 로마를 사용하여 Windows 10 애플리케이션용으로 활성화된 디바이스 간 기능과 플랫폼 간 기능에 대해 알아봅니다.
ms.topic: overview
ms.custom: seodec2018, RS5
ms.openlocfilehash: 57f6ce29730bd296ee623251d8ef619b114f944b
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58906745"
---
# <a name="project-rome"></a>프로젝트 로마

[프로젝트 로마](https://developer.microsoft.com/en-us/windows/project-rome)는 Microsoft의 앱용 디바이스 간 환경 플랫폼입니다. 

이 사이트에서 프로젝트 로마용 개발자 설명서와 다른 유용한 리소스에 대한 링크를 볼 수 있습니다.

프로젝트 로마에 대한 뉴스, 블로그 게시물 및 비디오를 보려면 [프로젝트 로마 방문 페이지](https://developer.microsoft.com/windows/project-rome)를 방문하세요.

프로젝트 로마를 사용하는 샘플 애플리케이션을 보려면 아래 SDK 표를 확인하거나 [프로젝트 로마 샘플 리포지토리](https://github.com/Microsoft/project-rome)를 방문하세요.

## <a name="about-project-rome"></a>프로젝트 로마 정보

개발자는 프로젝트 로마를 사용하여 여러 디바이스에서 실행할 수 있고, 사용자가 디바이스를 전환할 때 사용자와 함께 이동할 수 있는 앱을 작성할 수 있습니다.

프로젝트 로마에는 Microsoft Graph 및 플랫폼별 네이티브 SDK를 통해 제공되는 기능이 포함되어 있습니다. 이러한 기능은 디바이스 간 연결형 디바이스 기능 여러 개를 구현하여 로그인한 사용자 ID를 기준으로 앱을 중앙 집중화할 수 있게 해줍니다. 프로젝트 로마와 관련된 기능은 사용자 활동, 알림, 디바이스 및 근러기 공유를 포함하되 이에 국한되지 않습니다.

## <a name="choosing-between-native-apis-and-graph-apis"></a>네이티브 API와 Graph API 중 선택

일부 시나리오는 네이티브 플랫폼 SDK와 Microsoft Graph를 사용한 REST API *모두*를 통해 지원됩니다. 일반적으로 REST API는 프로젝트 로마 기능의 빠르고 단순한 구현을 지원합니다. 그러나 플랫폼별 구현을 사용할 경우 몇 가지 이점이 있습니다.

* 플랫폼 SDK는 네이티브 언어로 작성된 객체 모델, 로컬 스토리지 및 서버 쪽 정보가 변경될 때 앱을 업데이트하는 게시-구독 패턴을 제공합니다.
* 앱이 Windows(UWP 또는 Win32 앱)에서 실행되는 경우 플랫폼 SDK는 사용자의 기본 계정 사용 및 사용자 참여 자동 추적과 같은 여러 가지 추가 기능을 제공합니다.
* 플랫폼 SDK를 통해서만 사용 가능한 다른 프로젝트 로마 기능을 사용하려면 각 기능을 동일한 방식으로 구현하는 것이 좋습니다.

Microsoft Graph API와 클라이언트 SDK의 조합을 사용하면 다른 몇 가지 시나리오도 지원됩니다. 이러한 예로 알림이 있습니다. 이 경우 MS Graph API를 사용하여 앱 서버 쪽의 알림이 게시되고, 네이티브 플랫폼 클라이언트 SDK를 사용하여 각 클라이언트 쪽 네이티브 앱의 알림이 수신되고 관리됩니다.

## <a name="sdk"></a>SDK

프로젝트 로마는 현재 아래 플랫폼용으로 구현되어 있습니다. 샘플 및 SDK 다운로드에 대한 링크를 따르세요.

[windows-sdk]:             https://developer.microsoft.com/en-us/windows/downloads
[windows-sdk-badge]:       https://img.shields.io/badge/sdk-April%202018%20Update-brightgreen.svg
[windows-drsample]:        https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/RemoteSystems
[windows-afsample]:        https://github.com/Microsoft/Windows-universal-samples/tree/master/Samples/UserActivity 

[winredist-sdk]:           https://www.nuget.org/packages/Microsoft.ConnectedDevices.UserNotifications
[winredist-sdk-badge]:     https://img.shields.io/nuget/v/Microsoft.ConnectedDevices.UserNotifications.svg
[winredist-sample]:        https://github.com/Microsoft/project-rome/tree/release/1.0.0/Windows/samples

[xamarin-sdk]:             https://www.nuget.org/packages/Microsoft.ConnectedDevices.Xamarin.Droid
[xamarin-sdk-badge]:       https://img.shields.io/nuget/v/Microsoft.ConnectedDevices.Xamarin.Droid.svg
[xamarin-sample]:          https://github.com/Microsoft/project-rome/tree/0.8.1/Xamarin/samples

[ios-sdk]:                 https://cocoapods.org/pods/ProjectRomeSdk
[ios-sdk-badge]:           https://img.shields.io/cocoapods/v/ProjectRomeSdk.svg
[ios-sample]:              https://github.com/Microsoft/project-rome/tree/release/1.0.0/iOS/samples

[android-sdk]:             https://bintray.com/connecteddevices/maven/com.microsoft.connecteddevices:connecteddevices-sdk?version=1.1.0
[android-sdk-badge]:       https://img.shields.io/bintray/v/connecteddevices/maven/com.microsoft.connecteddevices:connecteddevices-sdk.svg
[android-sample]:          https://github.com/Microsoft/project-rome/tree/release/1.0.0/Android/samples

[graph-relay]:             https://developer.microsoft.com/graph/docs/api-reference/beta/resources/project_rome_overview
[graph-activities]:        https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/activity-feed-api-overview
[graph-notification]:      https://developer.microsoft.com/graph/docs/api-reference/beta/resources/notifications-api-overview

[graph-relay-badge]:       https://img.shields.io/badge/Device_Relay-Beta-orange.svg
[graph-activities-badge]:  https://img.shields.io/badge/Activities-1.0-brightgreen.svg
[graph-notification-badge]:https://img.shields.io/badge/Graph_Notifications-Beta-orange.svg

[graph-relay-sample]:        https://developer.microsoft.com/graph/docs/api-reference/beta/resources/project_rome_overview
[graph-activities-sample]:   https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/activity-feed-api-overview
[graph-notification-sample]: https://developer.microsoft.com/graph/docs/api-reference/beta/resources/notifications-api-overview



|   플랫폼                        | 기능                                                         |           SDK 패키지                          |   샘플                                       |
| :-------------------------------- | :--------------------------------------------------------------- |:---------------------------------------------- | :---------------------------------------------- |
| **Windows SDK**                   | 장치 릴레이, 활동/타임라인                                | [![SDK][windows-sdk-badge]][windows-sdk]       | [디바이스 릴레이용 프로젝트 로마 Windows 샘플][windows-drsample] <br> [활동용 프로젝트 로마 Windows 샘플][windows-afsample]
| **Windows(미리 보기)**             |                                    Microsoft Graph 알림 | [![Nuget][winredist-sdk-badge]][winredist-sdk] | [Windows용 Graph 알림 샘플][winredist-sample] 
| **Android**             | 디바이스 릴레이, 활동/타임라인, Microsoft Graph 알림 | [![Maven][android-sdk-badge]][android-sdk]     | [Android용 프로젝트 로마 샘플][android-sample]
| **iOS**                 | 디바이스 릴레이, 활동/타임라인, Microsoft Graph 알림 | [![CocoaPod][ios-sdk-badge]][ios-sdk]          | [iOS용 프로젝트 로마 샘플][ios-sample]
| **Android용 Xamarin(미리 보기)** | 장치 릴레이                                                     | [![Nuget][xamarin-sdk-badge]][xamarin-sdk]     | [Android용 Xamarin 샘플][xamarin-sample]
| **MSGraph**                       | 디바이스 릴레이, 활동/타임라인, Microsoft Graph 알림 | [![REST][graph-relay-badge]][graph-relay]<br> [![REST][graph-activities-badge]][graph-activities]<br>[![REST][graph-notification-badge]][graph-notification]          | [디바이스 릴레이][graph-relay-sample]<br>[활동/타임라인][graph-activities-sample]<br>[Graph 알림][graph-notification-sample]

## <a name="project-rome-blog-posts"></a>프로젝트 로마 블로그 게시물
* [프로젝트 로마를 통한 장치 간 환경](https://blogs.windows.com/buildingapps/2016/10/11/cross-device-experience-with-project-rome/#iQTseFlAMJRopU9k.97)

* [소셜 지원: 프로젝트 로마, 지도 및 소셜 네트워크 통합](https://blogs.windows.com/buildingapps/2016/10/27/going-social-project-rome-maps-social-network-integration-app-dev-on-xbox-series/#SCfoEZ1q8c1yBMei.97)

* [프로젝트 로마 Android SDK 알림](https://blogs.windows.com/buildingapps/2017/02/08/announcing-project-rome-android-sdk/#obDkvwkXOGa3tcTx.97)

* [Android 업데이트용 프로젝트 로마: App Services 지원 추가](https://blogs.windows.com/buildingapps/2017/03/23/project-rome-android-update-now-app-services-support/#DBm1Ic4JX8vXv2h0.97)

* [프로젝트 로마의 Android용 원격 제어 컴패니언 앱 만들기](https://blog.xamarin.com/building-remote-control-companion-app-android-project-rome/)

* [Windows 10 크리에이터스 업데이트의 새로운 공유 환경](https://blogs.windows.com/buildingapps/2017/04/06/new-share-experience-windows-10-creators-update/#OGskrWcLLlrCTCSH.97)

* [AppUriHandlers를 통한 웹과 앱 연결](https://blogs.windows.com/buildingapps/2016/10/14/web-to-app-linking-with-appurihandlers/#fIh7USaxBYS8JqfT.97)

## <a name="other-resources"></a>다른 리소스

* [웹과 앱 연결](https://docs.microsoft.com/en-us/windows/uwp/launch-resume/web-to-app-linking)

* [//Build 2016 논의](https://channel9.msdn.com/Events/Build/2016/B831)

* [MS Dev Show 팟캐스트](http://msdevshow.com/2016/11/project-rome-with-shawn-henry/)

## <a name="give-feedback"></a>피드백 제공

|[UserVoice](https://wpdev.uservoice.com/forums/110705-universal-windows-platform/category/183208-connected-apps-and-devices-project-rome)|[피드백 허브](https://support.microsoft.com/en-us/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub-app)|[사용자 문의](mailto:projectrometeam@microsoft.com)|
|-----|-----|-----|
