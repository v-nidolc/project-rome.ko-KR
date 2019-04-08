---
title: Microsoft Graph 알림
description: 사용자 중심적인 방식으로 사용자를 다시 참여시키려면 애플리케이션에 Microsoft Graph 알림을 포함하세요.
ms.localizationpriority: medium
ms.topic: overview
ms.custom: seodec2018
ms.openlocfilehash: 23aefb0e9f75721977e3ab9f1002bebf264a5b09
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58906765"
---
# <a name="microsoft-graph-notifications"></a>Microsoft Graph 알림
알림은 사용자를 다시 참여시키는 가장 효과적인 방법입니다. 사용자의 관심을 끌고 앱으로 다시 데려올 수 있습니다. 다중 디바이스 환경에서 사용자는 앱이 설치된 여러 플랫폼 및 디바이스 어디서나 앱 및 서비스에 액세스할 수 있습니다.
알림 시나리오는 사용자가 어디에 있든 사용자에게 알리는 것을 주된 목표로 하는 "사용자 중심" 방식으로 설계되어야 합니다. 주요 플랫폼이 제공하는 기존의 알림 솔루션은 대상 디바이스 지정하는 데 뛰어납니다. Microsoft Graph 알림은 개발자가 대상 사용자를 지정할 수 있게 하여 이 기능을 개선합니다. Microsoft Graph 알림은 사용자와 엔드포인트 간 매핑, 사용자의 여러 엔드포인트 간 알림 상태 동기화 등 어려운 과제를 처리합니다.

## <a name="why-integrate-with-microsoft-graph-notifications"></a>Microsoft Graph 알림과 통합해야 하는 이유

### <a name="deliver-notifications-to-a-user-across-different-endpoints"></a>여러 엔드포인트에서 사용자에게 알림 제공
Microsoft Graph에 포함된 알림 API를 사용하면 알림을 제공할 대상 Microsoft 계정이나 회사 또는 학교(Azure Active Directory) 계정을 지정할 수 있습니다. 이 플랫폼은 Windows UWP, Android 및 iOS를 포함한 모든 사용자의 엔드포인트에 이러한 알림을 배포합니다.

### <a name="manage-notifications-across-endpoints"></a>여러 엔드포인트의 알림 관리
Microsoft Graph 알림 API를 사용하면 알림 상태를 업데이트하고 모든 엔드포인트에서 상태를 동기화할 수 있습니다. 예를 들어 사용자가 한 디바이스의 알림에 대한 작업을 수행하면 이러한 알림의 상태를 업데이트(예: 읽음 또는 해제 상태로 표시)할 수 있습니다. 그러면 다른 모든 엔드포인트에 동일한 상태 변경 사항이 배포됩니다. Microsoft Graph 알림 API는 중앙 집중식으로 사용자의 알림 상태를 추적하여 사용자가 어디서나 알림을 한 번에 처리하고, 업데이트하거나 해제할 수 있게 해줍니다.

### <a name="retrieve-notification-history"></a>알림 기록 검색
알림 API를 사용하여 정의된 만료 시간(최대 30일)에 따라 알림 기록을 검색할 수 있습니다. 읽음 또는 해제 상태로 표시된 알림은 여전히 기록에서 검색 가능하므로 알림 기록 및 다른 시나리오의 앱 내 보기를 지원합니다.

## <a name="integrating-with-microsoft-graph-notifications"></a>Microsoft Graph 알림과 통합

### <a name="onboarding"></a>등록
앱 및 서비스의 모바일 푸시 알림 솔루션으로 Graph 알림을 사용하는 방법에 대한 단계별 지침은 각 플랫폼 노드(Windows, Android, iOS)의 방법 가이드를 참조하세요. 여기에 나오는 방법 가이드는 알림 수신을 중점적으로 다룹니다. [MS Graph API를 사용하여 알림 보내기](sending-notifications.md) 페이지에서 알림을 보내는 방법에 대한 정보를 확인할 수 있습니다.

이 가이드에는 플랫폼 간 앱 ID 및 모바일 푸시 자격 증명 등록을 비롯한 Graph 알림 사용 방법에 대한 구체적인 단계가 포함되어 있습니다. Microsoft Graph를 처음 사용하는 사람을 위해 Microsoft 계정(MSA)에 고객용 앱을 등록하거나 회사 및 학교 계정에 Azure Active Directory(AAD)를 등록하는 단계도 포함되어 있습니다. MSA 및 AAD는 Microsoft Graph에서 알림 외에 여러 워크로드를 활용할 수 있게 해줌으로써 더 풍부한 비즈니스 시나리오를 지원하는 사용자 ID입니다. 

### <a name="microsoft-graph-apis"></a>Microsoft Graph API
Graph 알림을 사용할 경우 앱 서버는 Microsoft Graph API(베타)를 사용하여 알림을 보내야 합니다. 서버 쪽 통합에 대한 자세한 내용은 API 사용법에 관한 [API 참조 문서](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/notifications-api-overview)에서 확인하세요. 

### <a name="client-side-sdk"></a>클라이언트 쪽 SDK
클라이언트 쪽 Graph 알림 통합을 시작하고 네이티브 SDK를 사용하여 알림 수신 및 관리를 시작하려면 왼쪽 탐색 창에서 원하는 개발 플랫폼을 선택하세요. 

* [MS Graph API를 사용하여 알림 보내기](sending-notifications.md)
* [프로젝트 로마 SDK를 사용하여 알림 수신](receiving-notifications.md)
