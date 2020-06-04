---
title: IScheduler 구조체
ms.date: 11/04/2016
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
ms.openlocfilehash: ccd82b5c5112bc322717f2b58d79d4c8f34f5bbd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368170"
---
# <a name="ischeduler-structure"></a>IScheduler 구조체

작업 스케줄러의 추상화에 대한 인터페이스입니다. 동시성 런타임의 리소스 관리자는 이 인터페이스를 사용하여 작업 스케줄러와 통신합니다.

## <a name="syntax"></a>구문

```cpp
struct IScheduler;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IScheduler::가상 프로세서 추가](#addvirtualprocessors)|스케줄러에 사용할 가상 프로세서 루트 집합을 제공합니다. 각 `IVirtualProcessorRoot` 인터페이스는 스케줄러를 대신하여 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.|
|[IScheduler:::GetId](#getid)|스케줄러에 대한 고유 식별자를 반환합니다.|
|[IScheduler::GetPolicy](#getpolicy)|스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대한 자세한 내용은 [SchedulerPolicy](schedulerpolicy-class.md)을 참조하십시오.|
|[IScheduler::알림리소스외부바쁜](#notifyresourcesexternallybusy)|이 스케줄러는 어레이의 `ppVirtualProcessorRoots` 가상 프로세서 루트 집합으로 표시되는 하드웨어 스레드가 이제 다른 스케줄러에서 사용되고 있음을 표시합니다.|
|[IScheduler::알림리소스외부유공자](#notifyresourcesexternallyidle)|이 스케줄러는 어레이의 `ppVirtualProcessorRoots` 가상 프로세서 루트 집합으로 표시되는 하드웨어 스레드가 다른 스케줄러에서 사용되지 않음을 표시합니다.|
|[IScheduler::제거가상 프로세서](#removevirtualprocessors)|이 스케줄러에 이전에 할당된 가상 프로세서 루트의 제거를 시작합니다.|
|[IScheduler::통계](#statistics)|작업 도착 및 완료 율및 스케줄러의 큐 길이 변경과 관련된 정보를 제공합니다.|

## <a name="remarks"></a>설명

리소스 관리자와 통신하는 사용자 지정 스케줄러를 구현하는 경우 인터페이스의 `IScheduler` 구현을 제공해야 합니다. 이 인터페이스는 스케줄러와 리소스 관리자 간의 양방향 통신 채널의 한쪽 끝입니다. 다른 쪽 끝은 `IResourceManager` 리소스 `ISchedulerProxy` 관리자에 의해 구현 되는 및 인터페이스에 의해 표현 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IScheduler`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a>IScheduler::가상 프로세서 추가 방법

스케줄러에 사용할 가상 프로세서 루트 집합을 제공합니다. 각 `IVirtualProcessorRoot` 인터페이스는 스케줄러를 대신하여 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.

```cpp
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*pp가상프로세서뿌리*<br/>
스케줄러에 `IVirtualProcessorRoot` 추가되는 가상 프로세서 루트를 나타내는 인터페이스의 배열입니다.

*count*<br/>
배열의 `IVirtualProcessorRoot` 인터페이스 수입니다.

### <a name="remarks"></a>설명

리소스 관리자는 스케줄러에 `AddVirtualProcessor` 가상 프로세서 루트의 초기 집합을 부여하는 메서드를 호출합니다. 또한 스케줄러 간에 리소스의 균형을 조정할 때 스케줄러에 가상 프로세서 루트를 추가하는 메서드를 호출할 수도 있습니다.

## <a name="ischedulergetid-method"></a><a name="getid"></a>IScheduler::GetId 메서드

스케줄러에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

고유한 정수 식별자입니다.

### <a name="remarks"></a>설명

[GetSchedulerId](concurrency-namespace-functions.md) 함수를 사용 하 여 `IScheduler` 인터페이스를 구현 하는 개체에 대 한 고유 식별자를 가져와야 합니다. `GetId` 함수가 호출될 때 동일한 식별자를 반환해야 합니다.

다른 소스에서 가져온 식별자는 정의되지 않은 동작이 발생할 수 있습니다.

## <a name="ischedulergetpolicy-method"></a><a name="getpolicy"></a>IScheduler::GetPolicy 방법

스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대한 자세한 내용은 [SchedulerPolicy](schedulerpolicy-class.md)을 참조하십시오.

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Return Value

스케줄러 정책의 복사본입니다.

## <a name="ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a>IScheduler::알림자원외부바쁜 방법

이 스케줄러는 어레이의 `ppVirtualProcessorRoots` 가상 프로세서 루트 집합으로 표시되는 하드웨어 스레드가 이제 다른 스케줄러에서 사용되고 있음을 표시합니다.

```cpp
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*pp가상프로세서뿌리*<br/>
다른 스케줄러가 사용 중이 되는 하드웨어 스레드와 연결된 `IVirtualProcessorRoot` 인터페이스 의 배열입니다.

*count*<br/>
배열의 `IVirtualProcessorRoot` 인터페이스 수입니다.

### <a name="remarks"></a>설명

특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수 있습니다. 그 이유 중 하나는 리소스를 공유하지 않고 모든 스케줄러의 최소 동시성을 충족하기 위해 시스템에 하드웨어 스레드가 충분하지 않기 때문입니다. 또 다른 가능성은 소유 스케줄러가 해당 스케줄러를 사용하지 않을 때 해당 하드웨어 스레드의 모든 가상 프로세서 루트가 비활성화되는 경우 리소스가 다른 스케줄러에 일시적으로 할당된다는 것입니다.

하드웨어 스레드의 구독 수준은 해당 하드웨어 스레드와 연결된 구독된 스레드 및 활성화된 가상 프로세서 루트 수로 표시됩니다. 특정 스케줄러의 관점에서 하드웨어 스레드의 외부 구독 수준은 다른 스케줄러가 기여하는 구독의 일부입니다. 하드웨어 스레드의 외부 구독 수준이 0에서 양수 영역으로 이동하면 리소스가 외부에서 사용 중이라는 알림이 스케줄러로 전송됩니다.

이 메서드를 통한 알림은 `MinConcurrency` 정책 키의 값이 `MaxConcurrency` 정책 키의 값과 동일한 정책이 있는 스케줄러에게만 전송됩니다. 스케줄러 정책에 대한 자세한 내용은 [SchedulerPolicy](schedulerpolicy-class.md)을 참조하십시오.

알림을 받을 수 있는 스케줄러는 알림을 만들 때 초기 알림 집합을 수신하여 방금 할당된 리소스가 외부에서 사용 중이거나 유휴 상태인지 여부를 알려줍니다.

## <a name="ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a>IScheduler::알림자원외부유공 방법

이 스케줄러는 어레이의 `ppVirtualProcessorRoots` 가상 프로세서 루트 집합으로 표시되는 하드웨어 스레드가 다른 스케줄러에서 사용되지 않음을 표시합니다.

```cpp
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*pp가상프로세서뿌리*<br/>
다른 스케줄러가 유휴 상태가 된 하드웨어 스레드와 연결된 `IVirtualProcessorRoot` 인터페이스 의 배열입니다.

*count*<br/>
배열의 `IVirtualProcessorRoot` 인터페이스 수입니다.

### <a name="remarks"></a>설명

특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수 있습니다. 그 이유 중 하나는 리소스를 공유하지 않고 모든 스케줄러의 최소 동시성을 충족하기 위해 시스템에 하드웨어 스레드가 충분하지 않기 때문입니다. 또 다른 가능성은 소유 스케줄러가 해당 스케줄러를 사용하지 않을 때 해당 하드웨어 스레드의 모든 가상 프로세서 루트가 비활성화되는 경우 리소스가 다른 스케줄러에 일시적으로 할당된다는 것입니다.

하드웨어 스레드의 구독 수준은 해당 하드웨어 스레드와 연결된 구독된 스레드 및 활성화된 가상 프로세서 루트 수로 표시됩니다. 특정 스케줄러의 관점에서 하드웨어 스레드의 외부 구독 수준은 다른 스케줄러가 기여하는 구독의 일부입니다. 하드웨어 스레드의 외부 구독 수준이 이전 양수 값에서 0으로 떨어지면 리소스가 외부에서 사용 중이라는 알림이 스케줄러로 전송됩니다.

이 메서드를 통한 알림은 `MinConcurrency` 정책 키의 값이 `MaxConcurrency` 정책 키의 값과 동일한 정책이 있는 스케줄러에게만 전송됩니다. 스케줄러 정책에 대한 자세한 내용은 [SchedulerPolicy](schedulerpolicy-class.md)을 참조하십시오.

알림을 받을 수 있는 스케줄러는 알림을 만들 때 초기 알림 집합을 수신하여 방금 할당된 리소스가 외부에서 사용 중이거나 유휴 상태인지 여부를 알려줍니다.

## <a name="ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a>IScheduler::제거가상 프로세서 방법

이 스케줄러에 이전에 할당된 가상 프로세서 루트의 제거를 시작합니다.

```cpp
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*pp가상프로세서뿌리*<br/>
제거할 가상 `IVirtualProcessorRoot` 프로세서 루트를 나타내는 인터페이스 의 배열입니다.

*count*<br/>
배열의 `IVirtualProcessorRoot` 인터페이스 수입니다.

### <a name="remarks"></a>설명

리소스 관리자는 스케줄러에서 `RemoveVirtualProcessors` 가상 프로세서 루트 집합을 다시 가져 오는 메서드를 호출합니다. 스케줄러는 가상 프로세서 루트로 완료되면 각 인터페이스에서 [Remove](iexecutionresource-structure.md#remove) 메서드를 호출해야 합니다. 메서드를 `IVirtualProcessorRoot` 호출한 후에는 인터페이스를 `Remove` 사용하지 마십시오.

매개 `ppVirtualProcessorRoots` 변수는 인터페이스 배열을 가리킵니다. 제거할 가상 프로세서 루트 세트 중에서, 루트는 활성화되지 않은 메서드를 `Remove` 사용하여 즉시 반환될 수 있다. 활성화되어 있고 작업을 실행 중이거나 비활성화되어 작업이 도착하기를 기다리는 루트는 비동기적으로 반환되어야 합니다. 스케줄러는 가능한 한 빨리 가상 프로세서 루트를 제거하려고 모든 시도를해야 합니다. 가상 프로세서 루트를 제거하면 스케줄러 내에서 의도하지 않은 초과 구독이 발생할 수 있습니다.

## <a name="ischedulerstatistics-method"></a><a name="statistics"></a>IScheduler::통계 방법

작업 도착 및 완료 율및 스케줄러의 큐 길이 변경과 관련된 정보를 제공합니다.

```cpp
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>매개 변수

*pTask 완료속도*<br/>
이 메서드에 대한 마지막 호출 이후 스케줄러에서 완료된 작업 수입니다.

*pTask도착레이트*<br/>
이 메서드에 대한 마지막 호출 이후 스케줄러에 도착한 작업 수입니다.

*pNumberOf작업큐어*<br/>
모든 스케줄러 큐의 총 작업 수입니다.

### <a name="remarks"></a>설명

이 메서드는 스케줄러에 대 한 통계를 수집 하기 위해 리소스 관리자에 의해 호출 됩니다. 여기에 수집된 통계는 동적 피드백 알고리즘을 구동하여 스케줄러에 더 많은 리소스를 할당하는 것이 적절한 시기와 리소스를 빼앗는 시기를 결정하는 데 사용됩니다. 스케줄러에서 제공하는 값은 낙관적일 수 있으며 현재 개수를 정확하게 반영할 필요는 없습니다.

리소스 관리자에서 작업 도착 등에 대한 피드백을 사용하여 사용자의 스케줄러와 리소스 관리자에 등록된 다른 스케줄러 간에 리소스 균형을 조정하는 방법을 결정하려면 이 메서드를 구현해야 합니다. 통계를 수집하지 않도록 선택하면 정책 키를 `DynamicProgressFeedback` 스케줄러 `DynamicProgressFeedbackDisabled` 정책의 값으로 설정할 수 있으며 리소스 관리자는 스케줄러에서 이 메서드를 호출하지 않습니다.

통계 정보가 없는 경우 리소스 관리자는 하드웨어 스레드 구독 수준을 사용하여 리소스 할당 및 마이그레이션 을 결정합니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](iexecutionresource-structure.md#currentsubscriptionlevel)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[정책요소키](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy 클래스](schedulerpolicy-class.md)<br/>
[IExecutionContext 구조체](iexecutioncontext-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 구조체](iresourcemanager-structure.md)
