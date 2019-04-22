---
title: MCDUserActivityChannel
description: 이 클래스에 추가 하 고 응용 프로그램에 대 한 사용자 활동의 쿼리 처리 합니다.
keywords: microsoft, windows, 사용자 활동, iOS, iPhone, objectiveC, 연결 된 장치, 프로젝트 로마
ms.openlocfilehash: b047af1da3ba79be88a53cf589c3894892b01ef4
ms.sourcegitcommit: 945a0f4bda02e3b4eb9a665379c2af9bd5285a53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58907805"
---
# <a name="class-mcduseractivitychannel"></a>클래스 `MCDUserActivityChannel`

```
@interface MCDUserActivityChannel : NSObject
```

이 클래스에 추가 하 고 응용 프로그램에 대 한 사용자 활동의 쿼리 처리 합니다.

## <a name="properties"></a>속성

### <a name="syncscope"></a>syncScope
`@property(class, readonly, nonnull) MCDUserDataFeedSyncScope* syncScope;`

사용자 활동에 대 한 사용자 데이터 동기화 범위 값을 가져옵니다.

### <a name="appdisplayname"></a>appDisplayName
`@property(nonatomic, copy, nullable) NSString* appDisplayName;`

모든 활동에 대 한 앱의 표시 이름입니다.

## <a name="constructors"></a>생성자

### <a name="channelwithuserdatafeed"></a>channelWithUserDataFeed
`+ (nullable instancetype)channelWithUserDataFeed:(nonnull MCDUserDataFeed*)userDataFeed;`

사용자 데이터 피드를 사용 하 여이 클래스의 인스턴스를 만듭니다.

#### <a name="parameters"></a>매개 변수
* `userDataFeed` 이 채널에서 작업과 관련 된 사용자 데이터입니다.

#### <a name="returns"></a>반환 값
이 클래스의 새 인스턴스를 반환합니다.

## <a name="methods"></a>메서드

### <a name="getorcreateuseractivityasync"></a>getOrCreateUserActivityAsync
`- (void)getOrCreateUserActivityAsync:(nonnull NSString*)activityId
                          completion:(nonnull void (^)(MCDUserActivity* _Nonnull, NSError* _Nullable))completionBlock;`

지정 된 사용자 활동을 만들거나 이미 있는 경우에 대 한 참조를 가져옵니다.

#### <a name="parameters"></a>매개 변수
* `activityId` 이 작업의 ID입니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다. 이 검색된 작업에 대 한 액세스를 제공합니다.

### <a name="deleteactivityasync"></a>deleteActivityAsync
`- (void)deleteActivityAsync:(nonnull NSString*)activityId completion:(nonnull void (^)(NSError* _Nullable))completionBlock;`

지정 된 사용자 활동을 삭제합니다.

#### <a name="parameters"></a>매개 변수
* `activityId` 삭제 작업의 ID입니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다.

### <a name="deleteallactivitiesasync"></a>deleteAllActivitiesAsync
`- (void)deleteAllActivitiesAsync:(nonnull void (^)(NSError* _Nullable))completionBlock;`

모든 사용자 활동을 삭제합니다.

#### <a name="parameters"></a>매개 변수
* `completionBlock` 완료 될 때 실행할 코드 블록입니다.

### <a name="getrecentuseractivitiesasync"></a>getRecentUserActivitiesAsync
`- (void)getRecentUserActivitiesAsync:(NSInteger)maxUniqueActivities
                          completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull, NSError* _Nullable))completionBlock;`

최근 사용자 활동의 기록을 가져옵니다. 

#### <a name="parameters"></a>매개 변수
* `maxUniqueActivities` 검색할 사용자 작업의 최대 수입니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다. 작업 기록에 대 한 액세스를 제공합니다.

### <a name="getsessionhistoryitemsforuseractivityasync"></a>getSessionHistoryItemsForUserActivityAsync
`- (void)getSessionHistoryItemsForUserActivityAsync:(nonnull NSString*)activityId
                                     withStartTime:(nonnull NSDate*)startTime
                                        completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull, NSError* _Nullable))completionBlock;`

지정된 된 활동에 대 한 세션 기록 항목을 가져옵니다.

#### <a name="parameters"></a>매개 변수
* `activityId` 에 대 한 기록 가져오기 작업의 ID입니다.
* `startTime` 세션 기록을 고려 하는 시간입니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다. 작업 기록에 대 한 액세스를 제공합니다.

### <a name="getrecentsessionhistoryitemsfortimerangeasync"></a>getRecentSessionHistoryItemsForTimeRangeAsync
`- (void)getRecentSessionHistoryItemsForTimeRangeAsync:(nonnull NSDate*)startTime
                                 endTime:(nonnull NSDate*)endTime
                                 maxActivities:(NSInteger)maxActivities
                                 completion:(void (^_Nonnull)(NSArray<MCDUserActivitySessionHistoryItem*>* _Nonnull,
                                                       NSError* _Nullable))completionBlock;`

지정된 된 활동에 대 한 세션 기록 항목을 가져옵니다.

#### <a name="parameters"></a>매개 변수
* `startTime` 세션 기록을 고려 시작 하는 시간입니다.
* `endTime` 세션 기록 고려 종료 하는 시간입니다.
* `maxActivities` 검색할 사용자 작업의 최대 수입니다.
* `completion` 완료 될 때 실행할 코드 블록입니다.
* `completionBlock` 완료 될 때 실행할 코드 블록입니다. 작업 기록에 대 한 액세스를 제공합니다.