---
title: 파일 포함
description: 파일 포함
ms.assetid: 93f45482-14e4-4aec-8185-ee05b592215f
ms.localizationpriority: medium
ms.openlocfilehash: 1aa6b0d971feb7d2f9f8d31708fda31d05b5aca9
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58907905"
---
### <a name="set-up-authentication-and-account-management"></a><span data-ttu-id="93277-103">인증 및 계정 관리 설정</span><span class="sxs-lookup"><span data-stu-id="93277-103">Set up authentication and account management</span></span>

<span data-ttu-id="93277-104">연결 된 장치 플랫폼에는 등록 프로세스에 사용할 유효한 OAuth 토큰에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="93277-104">The Connected Devices Platform requires a valid OAuth token to be used in the registration process.</span></span>  <span data-ttu-id="93277-105">생성 하 고 OAuth 토큰 관리의 기본 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93277-105">You may use your preferred method of generating and managing the OAuth tokens.</span></span>  <span data-ttu-id="93277-106">그러나 하는 데 개발자 플랫폼을 사용 하 여 시작, 인증 공급자의 일부로 포함 되어는 [iOS 샘플 앱](https://github.com/Microsoft/project-rome/tree/master/iOS/samples/account-provider-sample) 생성 및 관리 앱에서 새로 고침 토큰을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93277-106">However, to help developers get started using the platform, we've included an authentication provider as a part of the [iOS sample app](https://github.com/Microsoft/project-rome/tree/master/iOS/samples/account-provider-sample) that you can use to generate and manage refresh tokens in your app.</span></span>

<span data-ttu-id="93277-107">제공 된 코드를 사용 하지 않는 경우 구현 해야 합니다는 **[MCDConnectedDevicesAccountManager](../objectivec-api/connecteddevices/MCDConnectedDevicesAccountManager.md)** 직접 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="93277-107">If you do not use the provided code, you will need to implement the **[MCDConnectedDevicesAccountManager](../objectivec-api/connecteddevices/MCDConnectedDevicesAccountManager.md)** interface yourself.</span></span>

<span data-ttu-id="93277-108">MSA를 사용 하는 경우 다음과 같은 범위에서 로그인 요청에 포함: `"wl.offline_access"`, `"ccs.ReadWrite"`를 `"dds.read"`, `"dds.register"`를 `"wns.connect"`를 `"asimovrome.telemetry"`, 및 `"https://activity.windows.com/UserActivity.ReadWrite.CreatedByApp"`합니다.</span><span class="sxs-lookup"><span data-stu-id="93277-108">If you're using an MSA, include the following scopes in your sign-in request: `"wl.offline_access"`, `"ccs.ReadWrite"`, `"dds.read"`, `"dds.register"`, `"wns.connect"`, `"asimovrome.telemetry"`, and `"https://activity.windows.com/UserActivity.ReadWrite.CreatedByApp"`.</span></span>

<span data-ttu-id="93277-109">대상 사용자를 요청 해야 AAD 계정을 사용 하는 경우: `"https://cdpcs.access.microsoft.com"`, `"https://cs.dds.microsoft.com"`를 `"https://wns.windows.com/"`, 및 `"https://activity.microsoft.com"`합니다.</span><span class="sxs-lookup"><span data-stu-id="93277-109">If you're using an AAD account, you'll need to request the following audiences: `"https://cdpcs.access.microsoft.com"`, `"https://cs.dds.microsoft.com"`, `"https://wns.windows.com/"`, and `"https://activity.microsoft.com"`.</span></span>

<span data-ttu-id="93277-110">제공 된 사용할지 **MCDConnectedDevicesAccountManager** 구현 또는 Azure portal에서 앱의 등록에 다음 사용 권한을 지정 해야 하는 AAD를 사용 하는 경우 not (portal.azure.com > Azure Active Directory > 앱 등록):</span><span class="sxs-lookup"><span data-stu-id="93277-110">Whether you use the provided **MCDConnectedDevicesAccountManager** implementation or not, if you are using AAD you'll need to specify the following permissions in your app's registration on the Azure portal (portal.azure.com > Azure Active Directory > App registrations):</span></span>
* <span data-ttu-id="93277-111">Microsoft 작업 피드 서비스</span><span class="sxs-lookup"><span data-stu-id="93277-111">Microsoft Activity Feed Service</span></span> 
  * <span data-ttu-id="93277-112">제공 하 고 수정이 앱에 대 한 사용자 알림</span><span class="sxs-lookup"><span data-stu-id="93277-112">Deliver and modify user notifications for this app</span></span>
  * <span data-ttu-id="93277-113">읽기 및 피드 사용자의 활동에 앱 활동 작성</span><span class="sxs-lookup"><span data-stu-id="93277-113">Read and write app activity to users' activity feed</span></span>
* <span data-ttu-id="93277-114">Windows 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="93277-114">Windows Notification Service</span></span>
  * <span data-ttu-id="93277-115">Windows 알림 서비스에 장치 연결</span><span class="sxs-lookup"><span data-stu-id="93277-115">Connect your device to Windows Notification Service</span></span> 
* <span data-ttu-id="93277-116">Microsoft 장치 디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="93277-116">Microsoft Device Directory Service</span></span>
  * <span data-ttu-id="93277-117">장치 목록 보기</span><span class="sxs-lookup"><span data-stu-id="93277-117">See your list of devices</span></span>
  * <span data-ttu-id="93277-118">장치 및 앱 목록에 추가</span><span class="sxs-lookup"><span data-stu-id="93277-118">Be added to your list of devices and apps</span></span> 
* <span data-ttu-id="93277-119">Microsoft Command 서비스</span><span class="sxs-lookup"><span data-stu-id="93277-119">Microsoft Command Service</span></span>
  * <span data-ttu-id="93277-120">사용자 장치와 통신</span><span class="sxs-lookup"><span data-stu-id="93277-120">Communicate with user devices</span></span>
  * <span data-ttu-id="93277-121">사용자 장치 읽기</span><span class="sxs-lookup"><span data-stu-id="93277-121">Read user devices</span></span>
