---
title: IExecutionResource 구조체
ms.date: 11/04/2016
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
ms.openlocfilehash: 4305948aa4e5da36023c1d4fe8b0b84aa4d59e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377307"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource 구조체

하드웨어 스레드에 대한 추상화입니다.

## <a name="syntax"></a>구문

```cpp
struct IExecutionResource;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I실행 리소스::현재 구독 수준](#currentsubscriptionlevel)|활성화된 가상 프로세서 루트 수와 현재 이 실행 리소스가 나타내는 기본 하드웨어 스레드와 연결된 구독된 외부 스레드 수를 반환합니다.|
|[I실행 리소스::실행 리소스 ID](#getexecutionresourceid)|이 실행 리소스가 나타내는 하드웨어 스레드에 대한 고유 식별자를 반환합니다.|
|[I실행 리소스::GetNodeId](#getnodeid)|이 실행 리소스가 속한 프로세서 노드에 대한 고유 식별자를 반환합니다.|
|[I실행 리소스::제거](#remove)|이 실행 리소스를 리소스 관리자에 반환합니다.|

## <a name="remarks"></a>설명

실행 리소스는 독립 실행형이거나 가상 프로세서 루트와 연결될 수 있습니다. 독립 실행 형 실행 리소스는 응용 프로그램의 스레드가 스레드 구독을 만들 때 만들어집니다. 방법 [ISchedulerProxy::구독 스레드](ischedulerproxy-structure.md#subscribecurrentthread) 및 [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 스레드 구독을 `IExecutionResource` 만들고 구독을 나타내는 인터페이스를 반환 합니다. 스레드 구독을 만드는 것은 리소스 관리자에게 지정된 스레드가 스케줄러에 큐에 대기된 작업에 참여하고 리소스 관리자가 스케줄러에 할당하는 가상 프로세서 루트에 참여한다는 것을 리소스 관리자에게 알리는 방법입니다. 리소스 관리자는 이 정보를 사용하여 하드웨어 스레드가 할 수 있는 곳에 과도하게 구독하지 않도록 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IExecutionResource`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>I실행 리소스::현재 구독 수준 방법

활성화된 가상 프로세서 루트 수와 현재 이 실행 리소스가 나타내는 기본 하드웨어 스레드와 연결된 구독된 외부 스레드 수를 반환합니다.

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Return Value

현재 구독 수준입니다.

### <a name="remarks"></a>설명

구독 수준은 하드웨어 스레드와 연결된 실행 중인 스레드 수를 알려줍니다. 여기에는 리소스 관리자가 구독된 스레드 의 형태로 알고 있는 스레드와 스레드 프록시를 적극적으로 실행하는 가상 프로세서 루트만 포함됩니다.

[메서드 ISchedulerProxy:구독현재 스레드](ischedulerproxy-structure.md#subscribecurrentthread)를 호출 하거나 메서드 [ISchedulerProxy::RequestInitialVirtualProcessor값으로](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 설정 된 `doSubscribeCurrentThread` **요청true** 하드웨어 스레드의 구독 수준 하나씩 증가 합니다. 또한 구독을 `IExecutionResource` 나타내는 인터페이스를 반환합니다. [IExecutionResource::Remove하드웨어](#remove) 스레드의 구독 수준을 하나씩 제거하는 해당 호출입니다.

[IVirtualProcessorRoot::Activate를](ivirtualprocessorroot-structure.md#activate) 사용하여 가상 프로세서 루트를 활성화하는 행위는 하드웨어 스레드의 구독 수준을 하나씩 증가시다. 방법 [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate): 또는 [IExecutionResource::제거](#remove) 활성화 된 가상 프로세서 루트에 호출 할 때 하나씩 구독 수준을 제거합니다.

리소스 관리자는 구독 수준 정보를 스케줄러 간에 리소스를 이동하는 시기를 결정하는 방법 중 하나로 사용합니다.

## <a name="iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>I실행 리소스::GetexecutionResourceID 메서드

이 실행 리소스가 나타내는 하드웨어 스레드에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Return Value

이 실행 리소스의 기본하드웨어 스레드에 대한 고유 식별자입니다.

### <a name="remarks"></a>설명

각 하드웨어 스레드는 동시성 런타임에 의해 고유 식별자가 할당됩니다. 여러 실행 리소스가 연결된 하드웨어 스레드인 경우 모두 동일한 실행 리소스 식별자를 갖습니다.

## <a name="iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>I실행 리소스::GetNodeId 메서드

이 실행 리소스가 속한 프로세서 노드에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Return Value

프로세서 노드의 고유 식별자입니다.

### <a name="remarks"></a>설명

동시성 런타임은 프로세서 노드 그룹에서 시스템의 하드웨어 스레드를 나타냅니다. 노드는 일반적으로 시스템의 하드웨어 토폴로지에서 파생됩니다. 예를 들어 특정 소켓 또는 특정 NUMA 노드의 모든 프로세서가 동일한 프로세서 노드에 속할 수 있습니다. 리소스 관리자는 시스템의 총 프로세서 노드 수를 `0` `nodeCount` 나타내는 최대 `nodeCount - 1`및 포함부터 이러한 노드에 고유 식별자를 할당합니다.

노드 의 수는 [함수 GetProcessorNodeCount에서](concurrency-namespace-functions.md)얻을 수 있습니다.

## <a name="iexecutionresourceremove-method"></a><a name="remove"></a>I실행 리소스::제거 방법

이 실행 리소스를 리소스 관리자에 반환합니다.

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>매개 변수

*p스케줄러*<br/>
이 실행 리소스를 제거하도록 요청하는 스케줄러에 대한 인터페이스입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 독립 실행 실행 리소스 뿐만 아니라 가상 프로세서 루트와 관련 된 실행 리소스 리소스 관리자에 반환 합니다.

이 메서드 중 하나에서 받은 독립 실행 리소스 인 경우 [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) 또는 [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)메서드를 호출 `Remove` 하면 리소스를 나타내기 위해 만든 스레드 구독을 종료 합니다. 스케줄러 프록시를 종료하기 전에 모든 스레드 구독을 종료해야 `Remove` 하며 구독을 만든 스레드에서 호출해야 합니다.

인터페이스 `Remove`는 `IVirtualProcessorRoot` 인터페이스에서 상속되기 때문에 `IExecutionResource` 메서드를 호출하여 리소스 관리자에 가상 프로세서 루트도 반환할 수 있습니다. [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) 메서드에 대 한 호출에 대 한 응답으로 가상 프로세서 루트를 반환 해야 할 수 있습니다., 또는 [ISchedulerProxy:CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) 메서드에서 얻은 초과 구독 된 가상 프로세서 루트와 함께 수행 하는 경우. 가상 프로세서 루트의 경우 `Remove` 메서드를 호출할 수 있는 스레드에 제한이 없습니다.

`invalid_argument`매개 변수가 `pScheduler` 로 설정된 `NULL`경우 throw됩니다.

`invalid_operation`매개 변수가 `pScheduler` 이 실행 리소스에 대해 만들어진 스케줄러와 다른 경우 또는 독립 실행 리소스를 사용 하 여 현재 스레드스레드 구독을 만든 스레드와 다른 경우 throw 됩니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)
