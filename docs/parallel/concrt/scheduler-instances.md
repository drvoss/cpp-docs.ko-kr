---
title: Scheduler 인스턴스
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: e9e9b8124254084ac30191d37d49f2ef72bd677e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142289"
---
# <a name="scheduler-instances"></a>Scheduler 인스턴스

이 문서에서는 동시성 런타임의 스케줄러 인스턴스 역할 및 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 및 [Concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 사용 하 여 스케줄러 인스턴스를 만들고 관리 하는 방법에 대해 설명 합니다. 스케줄러 인스턴스는 명시적 일정 정책에 특정 유형의 작업을 연결 하려는 경우에 유용 합니다. 예를 들어 높은 스레드 우선 순위로 일부 작업을 실행하기 위한 스케줄러 인스턴스를 하나 만들고, 기본 스케줄러를 사용하여 보통 스레드 우선 순위로 다른 작업을 실행할 수 있습니다.

> [!TIP]
> 동시성 런타임은 기본 스케줄러를 제공하므로 애플리케이션에서 스케줄러를 만들 필요가 없습니다. 작업 스케줄러는 응용 프로그램의 성능을 미세 조정 하는 데 도움이 되므로 동시성 런타임를 처음 접하는 경우 [PPL (병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 를 사용 하는 것이 좋습니다.

## <a name="top"></a> 섹션

- [Scheduler 및 CurrentScheduler 클래스](#classes)

- [스케줄러 인스턴스 만들기](#creating)

- [스케줄러 인스턴스의 수명 관리](#managing)

- [메서드 및 기능](#features)

- [예제](#example)

## <a name="classes"></a>Scheduler 및 CurrentScheduler 클래스

작업 스케줄러를 사용 하면 응용 프로그램에서 하나 이상의 *스케줄러 인스턴스* 를 사용 하 여 작업을 예약할 수 있습니다. [Concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 클래스는 스케줄러 인스턴스를 나타내며 작업 예약과 관련 된 기능을 캡슐화 합니다.

스케줄러에 연결 된 스레드를 *실행 컨텍스트나* *컨텍스트*라고 합니다. 언제 든 지 현재 컨텍스트에서 하나의 스케줄러를 활성화할 수 있습니다. 활성 스케줄러는 *현재 스케줄러*라고도 합니다. 동시성 런타임 [Concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 사용 하 여 현재 스케줄러에 대 한 액세스를 제공 합니다. 한 컨텍스트의 현재 스케줄러는 다른 컨텍스트의 현재 스케줄러와 다를 수 있습니다. 런타임에서는 현재 스케줄러의 프로세스 수준 표현을 제공 하지 않습니다.

일반적으로 `CurrentScheduler` 클래스를 사용 하 여 현재 스케줄러에 액세스 합니다. `Scheduler` 클래스는 현재가 아닌 스케줄러를 관리 해야 하는 경우에 유용 합니다.

다음 섹션에서는 스케줄러 인스턴스를 만들고 관리 하는 방법을 설명 합니다. 이러한 작업을 설명 하는 전체 예제는 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)를 참조 하세요.

[[맨 위로 이동](#top)]

## <a name="creating"></a>스케줄러 인스턴스 만들기

다음 세 가지 방법으로 `Scheduler` 개체를 만들 수 있습니다.

- 스케줄러가 없으면 런타임에 병렬 알고리즘과 같은 런타임 기능을 사용 하 여 작업을 수행할 때 기본 스케줄러를 만듭니다. 기본 스케줄러는 병렬 작업을 시작 하는 컨텍스트에 대 한 현재 스케줄러가 됩니다.

- [Concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create) 메서드는 특정 정책을 사용 하는 `Scheduler` 개체를 만들고 해당 스케줄러를 현재 컨텍스트와 연결 합니다.

- [Concurrency:: Scheduler:: Create](reference/scheduler-class.md#create) 메서드는 특정 정책을 사용 하지만 현재 컨텍스트와 연결 하지 않는 `Scheduler` 개체를 만듭니다.

런타임이 기본 스케줄러를 만들도록 허용 하면 모든 동시 태스크가 동일한 스케줄러를 공유할 수 있습니다. 일반적으로 PPL ( [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) ) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 에서 제공 하는 기능은 병렬 작업을 수행 하는 데 사용 됩니다. 따라서 해당 정책 또는 수명을 제어 하기 위해 스케줄러와 직접 작업 하지 않아도 됩니다. PPL 또는 에이전트 라이브러리를 사용 하는 경우 런타임에서 기본 스케줄러를 만들어 각 컨텍스트에 대 한 현재 스케줄러로 만듭니다. 스케줄러를 만들어 현재 스케줄러로 설정 하면 런타임에서는 해당 스케줄러를 사용 하 여 작업을 예약 합니다. 특정 일정 예약 정책을 필요로 하는 경우에만 추가 스케줄러 인스턴스를 만듭니다. 스케줄러와 연결 된 정책에 대 한 자세한 내용은 [Scheduler 정책](../../parallel/concrt/scheduler-policies.md)을 참조 하십시오.

[[맨 위로 이동](#top)]

## <a name="managing"></a>스케줄러 인스턴스의 수명 관리

런타임은 참조 횟수 메커니즘을 사용 하 여 `Scheduler` 개체의 수명을 제어 합니다.

`CurrentScheduler::Create` 메서드나 `Scheduler::Create` 메서드를 사용 하 여 `Scheduler` 개체를 만드는 경우 런타임은 해당 스케줄러의 초기 참조 횟수를 1로 설정 합니다. [Concurrency:: Scheduler:: Attach](reference/scheduler-class.md#attach) 메서드를 호출 하면 런타임에서 참조 횟수를 증가 시킵니다. `Scheduler::Attach` 메서드는 `Scheduler` 개체를 현재 컨텍스트와 연결 합니다. 이렇게 하면 현재 스케줄러로 설정 됩니다. `CurrentScheduler::Create` 메서드를 호출 하면 런타임에서 `Scheduler` 개체를 만들어 현재 컨텍스트에 연결 하 고 참조 횟수를 1로 설정 합니다. [Concurrency:: Scheduler:: reference](reference/scheduler-class.md#reference) 메서드를 사용 하 여 `Scheduler` 개체의 참조 횟수를 증가 시킬 수도 있습니다.

[Concurrency:: CurrentScheduler::D etach](reference/currentscheduler-class.md#detach) 메서드를 호출 하 여 현재 스케줄러를 분리 하거나 [Concurrency:: Scheduler:: Release](reference/scheduler-class.md#release) 메서드를 호출 하면 런타임에서 참조 횟수를 감소 시킵니다. 참조 횟수가 0에 도달 하면 런타임은 모든 예약 된 작업이 완료 된 후 `Scheduler` 개체를 소멸 시킵니다. 실행 중인 태스크가 현재 스케줄러의 참조 횟수를 증가 시킬 수 있습니다. 따라서 참조 횟수가 0에 도달 하 고 태스크가 참조 횟수를 증가 시키는 경우 참조 횟수가 0에 도달 하 고 모든 작업이 완료 될 때까지 런타임에서 `Scheduler` 개체를 삭제 하지 않습니다.

런타임은 각 컨텍스트에 대 한 `Scheduler` 개체의 내부 스택을 유지 관리 합니다. `Scheduler::Attach` 또는 `CurrentScheduler::Create` 메서드를 호출 하면 런타임에서 현재 컨텍스트의 스택에 해당 `Scheduler` 개체를 푸시합니다. 이렇게 하면 현재 스케줄러로 설정 됩니다. `CurrentScheduler::Detach`를 호출 하면 런타임에서 현재 컨텍스트의 현재 스케줄러를 팝 하 고 이전 스케줄러를 현재 스케줄러로 설정 합니다.

런타임은 스케줄러 인스턴스의 수명을 관리 하는 여러 가지 방법을 제공 합니다. 다음 표에서는 스케줄러를 만들거나 현재 컨텍스트에 연결 하는 각 메서드에 대 한 현재 컨텍스트에서 스케줄러를 해제 하거나 분리 하는 적절 한 메서드를 보여 줍니다.

|만들기 또는 연결 방법|Release 또는 detach 메서드|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

부적절 한 릴리스 또는 분리 메서드를 호출 하면 런타임에서 지정 되지 않은 동작이 생성 됩니다.

PPL과 같은 기능을 사용 하 여 런타임에서 기본 스케줄러를 만들도록 하면이 스케줄러를 해제 하거나 분리 하지 마십시오. 런타임은 만들어진 모든 스케줄러의 수명을 관리 합니다.

런타임은 모든 작업이 완료 되기 전에 `Scheduler` 개체를 소멸 시 키 지 않으므로 [concurrency:: Scheduler:: RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 메서드 또는 [Concurrency:: Currentscheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 메서드를 사용 하 여 `Scheduler` 개체가 제거 될 때 알림을 받을 수 있습니다. 이는 `Scheduler` 개체에 예약 된 모든 작업이 완료 될 때까지 기다려야 하는 경우에 유용 합니다.

[[맨 위로 이동](#top)]

## <a name="features"></a>메서드 및 기능

이 섹션에서는 `CurrentScheduler` 및 `Scheduler` 클래스의 중요 한 메서드를 요약 합니다.

`CurrentScheduler` 클래스는 현재 컨텍스트에서 사용할 스케줄러를 만들기 위한 도우미로 생각 하면 됩니다. `Scheduler` 클래스를 사용 하면 다른 컨텍스트에 속한 스케줄러를 제어할 수 있습니다.

다음 표에서는 `CurrentScheduler` 클래스에 의해 정의 되는 중요 한 메서드를 보여 줍니다.

|방법|Description|
|------------|-----------------|
|[만들기](reference/currentscheduler-class.md#create)|지정 된 정책을 사용 하 여 현재 컨텍스트와 연결 하는 `Scheduler` 개체를 만듭니다.|
|[Get](reference/currentscheduler-class.md#get)|현재 컨텍스트와 연결 된 `Scheduler` 개체에 대 한 포인터를 검색 합니다. 이 메서드는 `Scheduler` 개체의 참조 횟수를 증가 시 지 않습니다.|
|[분리](reference/currentscheduler-class.md#detach)|현재 컨텍스트에서 현재 스케줄러를 분리 하 고 이전 스케줄러를 현재 스케줄러로 설정 합니다.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|현재 스케줄러가 제거 될 때 런타임에서 설정 하는 이벤트를 등록 합니다.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|현재 스케줄러에 [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 만듭니다.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|현재 스케줄러의 일정 큐에 간단한 작업을 추가 합니다.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|현재 스케줄러에 연결 된 정책의 복사본을 검색 합니다.|

다음 표에서는 `Scheduler` 클래스에 의해 정의 되는 중요 한 메서드를 보여 줍니다.

|방법|Description|
|------------|-----------------|
|[만들기](reference/scheduler-class.md#create)|지정 된 정책을 사용 하는 `Scheduler` 개체를 만듭니다.|
|[연결](reference/scheduler-class.md#attach)|현재 컨텍스트와 함께 `Scheduler` 개체를 연결 합니다.|
|[참조](reference/scheduler-class.md#reference)|`Scheduler` 개체의 참조 카운터를 증가 시킵니다.|
|[릴리스](reference/scheduler-class.md#release)|`Scheduler` 개체의 참조 카운터를 감소 시킵니다.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|`Scheduler` 개체가 제거 될 때 런타임에서 설정 하는 이벤트를 등록 합니다.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|`Scheduler` 개체에 [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체를 만듭니다.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|`Scheduler` 개체에서 간단한 작업을 예약 합니다.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|`Scheduler` 개체와 연결 된 정책의 복사본을 검색 합니다.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|런타임에 기본 스케줄러를 만들 때 사용할 정책을 설정 합니다.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|`SetDefaultSchedulerPolicy`를 호출 하기 전에 활성화 된 정책에 대 한 기본 정책을 복원 합니다. 이 호출 후 기본 스케줄러를 만든 경우 런타임은 기본 정책 설정을 사용 하 여 스케줄러를 만듭니다.|

[[맨 위로 이동](#top)]

## <a name="example"></a> 예제

스케줄러 인스턴스를 만들고 관리 하는 방법에 대 한 기본 예제 [는 방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[스케줄러 정책](../../parallel/concrt/scheduler-policies.md)<br/>
[일정 그룹](../../parallel/concrt/schedule-groups.md)
