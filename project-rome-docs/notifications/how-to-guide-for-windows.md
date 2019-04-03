---
title: 그래프 알림에 UWP 앱 통합
description: 알림에 대 한 수신 끝점에 필요한 등록 단계를 수행 하는 방법에 앱 서버에서 게시 합니다.
ms.assetid: c973d534-08e9-4f6e-8b54-bcae97067961
ms.localizationpriority: medium
ms.custom: seodec18
ms.openlocfilehash: 09f32a9869343778712449db04f74e9341fbc5a6
ms.sourcegitcommit: 75680b384946e11257bb2a33044a3172dec5220e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58909525"
---
# <a name="how-to-guide-integrating-with-ms-graph-notifications-windows-uwp"></a>방법 가이드: MS Graph 알림 (Windows UWP)와 통합

Windows에서 그래프 알림을 클라이언트 쪽 SDK를 사용 하 여 Windows UWP 앱에는 수신 하는 끝점에 사용자를 대상으로 앱 서버에서 게시 하는 알림을 수신 하는 데 필요한 등록 단계를 수행할 수 있습니다. 페이로드가이 클라이언트에 도착 하는 새 알림 수신, 알림 상태를 관리 및 알림 기록 검색을 포함 하 여 클라이언트 쪽에서 알림을 관리 하는 SDK 사용 됩니다. MS Graph 알림 및이 통해 사람이 중심 알림을 배달 하는 방법에 대 한 자세한 내용은 참조 하세요. [Microsoft Graph 알림 개요](index.md)

참조 된 [API 참조](api-reference-for-windows/index.md) 알림 시나리오와 관련 된 참조 문서에 대 한 링크는 페이지입니다.

## <a name="preliminary-setup-for-accessing-the-connected-devices-platform-in-order-to-use-graph-notifications"></a>그래프 알림을 사용 하려면 연결 된 장치 플랫폼에 액세스 하기 위한 예비 설치 
몇 단계만 그래프 알림과 함께 통합 하기 위해 취해야 할
* MSA 또는 AAD 앱 등록
* 플랫폼 간 앱 Id를 제공 하는 개발자 센터 등록 하 고 푸시 알림 자격 증명
* SDK를 추가 하 고 연결 된 장치 플랫폼 초기화
* 연결 된 장치 플랫폼 알림 서비스 연결

첫째, MSA 및/또는 AAD 앱 등록이 완료 해야 합니다. 이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.
[!INCLUDE [windows/platform-init](../includes/windows/notifications-app-registration-onboarding.md)]
다음으로 해야 온 보 딩 그래프 알림 사용을 포함 하는 장치 간 환경을 통합 하기 위해 연결 된 장치 플랫폼에 대 한 액세스를 가져오려면 Microsoft Windows 개발자 센터를 사용 하 여 합니다. 이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.
[!INCLUDE [windows/notification-init](../includes/windows/notifications-dev-center-onboarding.md)]
다음으로 프로젝트 로마 SDK 프로젝트를 추가 하 고 연결 된 장치 플랫폼을 초기화 해야 합니다. 이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.
[!INCLUDE [android/notification-init](../includes/android/notifications-platfrom-init.md)]
마지막으로 푸시 알림을 받도록 앱을 활성화 해야 합니다. 이 이미 수행한 경험이 있다면, 다음 섹션으로 건너뜁니다.
[!INCLUDE [android/notification-init](../includes/android/notifications-notification-init.md)]

## <a name="initialize-a-graph-notification-channel"></a>그래프 알림 채널을 초기화 합니다.
높은 수준에서는 SDK에는 앱을을 수신 하 고 다양 한 유형의 사용자 활동 그래프 알림 등을 포함 하 여 사용자 데이터를 관리 하기 위해 다른 채널을 구독할 수 있습니다. 모두 저장 하 고 동기화에서 이들은 **UserDataFeed**합니다. **UserNotification** 사용자 대상 알림 전송 그래프 알림을 통해 해당 클래스 및 데이터 형식입니다. 그래프 알림 및 앱 서버에서 게시 UserNotification 받기 시작와를 통합 하려면 먼저 피드를 만들어서 사용자 데이터를 초기화 하는 **UserNotificationChannel**합니다. 위의 플랫폼 초기화 단계와이 처리 해야 합니다: 확인 및 가능한 경우 응용 프로그램은 전경으로 (하지만 플랫폼 초기화 이전이 아님) 될 때마다 다시 실행 해야 합니다. 

## <a name="create-a-usernotificationreader-to-receive-incoming-usernotifications-and-access-usernotification-history"></a>들어오는 UserNotifications 받고 UserNotification 기록에 액세스 하려면 UserNotificationReader 만들기
만든 후는 **UserNotificationChannel** 참조 해야를 **UserNotificationReader** SDK 서버에서 실제 알림 콘텐츠를 가져올 수 있도록 합니다. UserNotificationReader에는 경우이 데이터 피드에 – 앱 클라이언트의 액세스할 수 있도록 이벤트 수신기를 통해 최신 알림 페이로드 또는 사용자의 알림 기록은의 뷰 모델로 사용할 수 있는 전체 UserNotification 컬렉션에 액세스할 수 있습니다.  

아래 코드 사용자 알림 채널을 인스턴스화하고 사용자 알림 판독기를 만들려면 연결 된 장치 플랫폼 각 동기화를 완료 하 고 새 변경 내용이 될 때 트리거되는 사용자 알림 판독기에서 이벤트 처리기를 추가 하는 단계를 보여 줍니다. 에 대 한 알려 줍니다. 

```C#

public async Task SetupChannel()
{
    var account = m_accoutProvider.SignedInAccount;

    if (m_feed == null)
    {
        await Task.Run(() =>
        {
            lock (this)
            {
                if (m_feed == null)
                {
                    m_platform = new ConnectedDevicesPlatform(m_accoutProvider, this);

                    Logger.Instance.LogMessage($"Create feed for {account.Id} {account.Type}");
                    m_feed = new UserDataFeed(account, m_platform, "graphnotifications.sample.windows.com");
                    m_feed.SyncStatusChanged += Feed_SyncStatusChanged;
                    m_feed.AddSyncScopes(new List<IUserDataFeedSyncScope>
                    {
                        UserNotificationChannel.SyncScope
                    });

                    m_channel = new UserNotificationChannel(m_feed);
                    m_reader = m_channel.CreateReader();
                    m_reader.DataChanged += Reader_DataChanged;
                }
            }
        });
    }
}

```

### <a name="receiving-usernotifications"></a>UserNotifications 받기

위의 섹션에서 사용자 알림 판독기는 이벤트 수신기 추가 되어 있는지을 참조 합니다. 새 알림 및 알림 업데이트를 모든 판독기에서 읽을이 이벤트 수신기를 구현 하 고 이러한 새로운 변화를 처리 하 여 고유한 비즈니스 논리를 구현 해야 합니다. 

> [!TIP] 
> 이 이벤트 수신기에는 기본 비즈니스 논리를 처리 하 고 "사용" 시나리오에 따라 알림 페이로드 콘텐츠 위치는입니다. 현재 WNS의 원시 알림 OS 수준 알림 센터의 로컬 알림 생성을 사용 하는 경우, 일부 앱에서 UI를 업데이트 하려면 알림 영역에서 콘텐츠를 사용 하는 경우 작업을 수행 하는 위치입니다. 

아래 코드 활성 되어 알림이 삭제 되 면 앱에서 보기에 해당 알림 UI를 제거 하는 모든 들어오는 UserNotification에 대 한 로컬 알림 메시지를 발생 시키려면 샘플 앱을 선택 하는 방법을 보여 줍니다. 

```C#

private void Reader_DataChanged(UserNotificationReader sender, object args)
{
    ReadNotifications(sender, true);
}

private async void ReadNotifications(UserNotificationReader reader, bool showToast)
{
    var notifications = await reader.ReadBatchAsync(UInt32.MaxValue);

    foreach (var notification in notifications)
    {

        if (notification.Status == UserNotificationStatus.Active)
        {
            m_newNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            if (notification.UserActionState == UserNotificationUserActionState.NoInteraction)
            {
                // new notification, show this to user using the Windows local toast notification APIs
                m_newNotifications.Add(notification);
                if (!string.IsNullOrEmpty(notification.Content) && showToast)
                {
                    ShowToastNotification(BuildToastNotification(notification.Id, notification.Content));
                }
            }

            m_historicalNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            m_historicalNotifications.Insert(0, notification);
        }
        else
        {
            // Existing notification is marked as deleted, remove from display
            m_newNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            m_historicalNotifications.RemoveAll((n) => { return (n.Id == notification.Id); });
            RemoveToastNotification(notification.Id);
        }
    }
}

```
## <a name="update-the-state-of-an-existing-usernotification"></a>기존 UserNotification의 상태를 업데이트 합니다.
이전 섹션에서 설명한 대로 따라 판독기를 통해 받은 UserNotification 변경 수는 기존 UserNotification –에서 상태 업데이트를으로 표시 되거나 해제 된 읽음으로 표시 되 고 되는지 여부를 합니다. 이 경우 응용 프로그램 클라이언트를 선택할 수를 유니버설 예를 들어이 특정 장치에서 해당 visual 알림을 제거 하 여 해제 합니다. 다시 단계에서 확인 하 고 앱 클라이언트 경우가이 UserNotification 변경 업데이트를 시작 하려면 – 다른 장치에서 시작 하는 합니다. 프로그램 UserNotifications의 상태를 업데이트 하는 시간을 선택할 수 있지만 일반적으로 이러한 업데이트 해당 visual 알림을 해당 장치에서 사용자에 의해 처리 됩니다. 때나 알림을 사용 하도록 설정 하면 일부 앱 내 환경에서 사용자가 추가로 처리 됩니다. . 흐름은 모양을의 예는 다음과 같습니다. 앱 서버 1. 사용자는 자신의 PC 및 앱 클라이언트를 설치할 자신의 휴대폰에서이 알림을 받으면 사용자를 대상으로 알림을 게시 합니다. PC에서 알림을 클릭 하 고 해당 작업 핸들을 앱에가 하는 사용자. 그런 다음이 PC에 앱 클라이언트에 연결 된 장치 플랫폼 SDK이 모든이 사용자의이 장치 간에 동기화이 업데이트를 위해서는 해당 UserNotification의 상태를 업데이트 하려면 호출 합니다. 이 받으면 다른 앱 클라이언트를 실시간으로 업데이트 상태는 다음 해당 시각적 경고가 제거 / 메시지 / 장치의 알림 센터 알림 / 알림 트레이 작업 센터 /입니다. 사용자의 장치에서 알림을 해제 보편적으로 가져오기 방법입니다. 

> [!TIP] 
> UserNotification 클래스에는 현재 두 가지 유형의 상태 업데이트 제공 –는 UserNotificationReadState 또는 UserNotificationUserActionState 수정 하 고 알림을 업데이트 될 때 수행할 동작에 고유한 논리를 정의할 수 있습니다. 예를 들어 UserActionState Activated 또는 해제를 표시할 수 있습니다 및 universal를 구현 하는 값에서 피벗 해제 합니다. 또는 읽기 또는 읽지 않음 ReadState를 표시할 수 있습니다 하 고 그에 따라 동시에 앱 내 알림이 기록 보기에서 알림을 표시할지 결정 합니다. 아래 코드 조각에서는 UserNotificationUserActionState 알림 해제로 표시 하는 방법을 보여 줍니다.

```C#
public async void Dismiss(string id)
{
    var notification = m_newNotifications.Find((n) => { return (n.Id == id); });
    if (notification != null)
    {
        notification.UserActionState = UserNotificationUserActionState.Dismissed;
        await notification.SaveAsync();
    }
}

```
