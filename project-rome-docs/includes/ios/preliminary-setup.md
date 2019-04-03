---
title: 파일 포함
description: 파일 포함
ms.topic: include
ms.assetid: ''
ms.localizationpriority: medium
ms.openlocfilehash: 53cbe2ec68785c257341caf110439d535b8f83be
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907625"
---
### <a name="register-your-app"></a><span data-ttu-id="fab23-103">앱 등록</span><span class="sxs-lookup"><span data-stu-id="fab23-103">Register your app</span></span>

<span data-ttu-id="fab23-104">Microsoft 계정 (MSA) 또는 Azure Active Directory (AAD) 인증이 프로젝트 로마 SDK (제외 하 고 주변 공유 Api)의 거의 모든 기능에 대 한 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-104">Microsoft Account (MSA) or Azure Active Directory (AAD) authentication is required for almost all features of the Project Rome SDK (the exception being the nearby sharing APIs).</span></span> <span data-ttu-id="fab23-105">MSA가 있지 않으며 하나를 사용 하려는 경우 레지스터 [account.microsoft.com](https://account.microsoft.com/account)합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-105">If you do not already have an MSA and wish to use one, register on [account.microsoft.com](https://account.microsoft.com/account).</span></span>

<span data-ttu-id="fab23-106">선택한 인증 방법을 사용 하면 앱을 등록 해야 microsoft 지침에 따라 합니다 [응용 프로그램 등록 포털](https://apps.dev.microsoft.com/)합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-106">Using your chosen authentication method, you must register your app with Microsoft by following the instructions on the [Application Registration Portal](https://apps.dev.microsoft.com/).</span></span> <span data-ttu-id="fab23-107">Microsoft 개발자 계정이 없는 경우 새로 만들려면 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-107">If you do not have a Microsoft developer account, you will need to create one.</span></span>

<span data-ttu-id="fab23-108">MSA를 사용 하 여 앱을 등록 하는 경우 클라이언트 ID 문자열을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-108">When you register an app using an MSA, you should receive a client ID string.</span></span> <span data-ttu-id="fab23-109">나중에이 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-109">Save this for later.</span></span> <span data-ttu-id="fab23-110">앱을 Microsoft의 연결 된 장치 플랫폼 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-110">This will allow your app to access Microsoft's Connected Devices Platform resources.</span></span> <span data-ttu-id="fab23-111">AAD를 사용 하는 경우 참조 [Azure Active Directory 인증 라이브러리](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) 방법은 클라이언트 ID 문자열에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-111">If you're using AAD, see [Azure Active Directory Authentication Libraries](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) for instructions on getting the client ID string.</span></span>

### <a name="add-the-sdk"></a><span data-ttu-id="fab23-112">SDK를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-112">Add the SDK</span></span>

<span data-ttu-id="fab23-113">사용 하 여 iOS 앱에 연결 된 장치 플랫폼을 추가 하는 가장 간단한 방법은는 [CocoaPods](https://cocoapods.org/) 종속성 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-113">The simplest way to add the Connected Devices Platform to your iOS app is by using the [CocoaPods](https://cocoapods.org/) dependency manager.</span></span> <span data-ttu-id="fab23-114">IOS 프로젝트의 이동 *Podfile* 하 고 다음 항목을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-114">Go to your iOS project's *Podfile* and insert the following entry:</span></span>

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
> <span data-ttu-id="fab23-115">CocoaPod를 사용 하려면 사용 해야 합니다 _.xcworkspace 인_ 프로젝트의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="fab23-115">In order to consume CocoaPod, you must use the _.xcworkspace_ file in your project.</span></span>
