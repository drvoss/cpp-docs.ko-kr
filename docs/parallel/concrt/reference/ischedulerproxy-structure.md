---
title: ISchedulerProxy 구조체
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: f4a9e79c2da56406610ad6da08fb438e2f92923d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368158"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 구조체

스케줄러가 리소스 할당을 협상하기 위해 동시성 런타임의 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IScheduler프록시::바인드 컨텍스트](#bindcontext)|실행 컨텍스트가 아직 스레드 프록시와 연결되지 않은 경우 실행 컨텍스트를 스레드 프록시와 연결합니다.|
|[IScheduler프록시::만들기 초과 구독자](#createoversubscriber)|기존 실행 리소스와 연결된 하드웨어 스레드에 새 가상 프로세서 루트를 만듭니다.|
|[IScheduler프록시::요청초기가상프로세서](#requestinitialvirtualprocessors)|가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대한 작업을 수행할 수 있는 하나의 스레드를 실행하는 기능을 나타냅니다.|
|[IScheduler프록시::종료](#shutdown)|리소스 관리자에 스케줄러가 종료되고 있음을 지정합니다. 이렇게 하면 리소스 관리자가 스케줄러에 부여된 모든 리소스를 즉시 회수합니다.|
|[IScheduler프록시::구독전류 스레드](#subscribecurrentthread)|현재 스레드를 리소스 관리자에 등록하여 이 스케줄러와 연결합니다.|
|[IScheduler프록시:바인딩되지 않은 컨텍스트](#unbindcontext)|매개 변수에 의해 지정된 실행 컨텍스트에서 `pContext` 스레드 프록시를 분리 하 고 스레드 프록시 팩터리의 사용 되지 않는 풀에 반환 합니다. 이 메서드는 [ISchedulerProxy::BindContext](#bindcontext) 메서드를 통해 바인딩된 실행 컨텍스트에서만 호출될 수 `pContext` 있으며 [아직 IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) 메서드 호출의 매개 변수를 통해 시작되지 않았습니다.|

## <a name="remarks"></a>설명

리소스 관리자는 `ISchedulerProxy` [IResourceManager:RegisterScheduler](iresourcemanager-structure.md#registerscheduler) 메서드를 사용하여 등록하는 모든 스케줄러에 인터페이스를 제공합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISchedulerProxy`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>IScheduler프록시::바인드컨텍스트 메서드

실행 컨텍스트가 아직 스레드 프록시와 연결되지 않은 경우 실행 컨텍스트를 스레드 프록시와 연결합니다.

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
스레드 프록시와 연결할 실행 컨텍스트에 대한 인터페이스입니다.

### <a name="remarks"></a>설명

일반적으로 [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) 메서드는 필요에 따라 실행 컨텍스트에 스레드 프록시를 바인딩합니다. 그러나 `SwitchTo` 메서드가 이미 바인딩된 컨텍스트로 전환되도록 컨텍스트를 미리 바인딩해야 하는 상황이 있습니다. 이는 메모리를 할당하는 메서드를 호출할 수 없고 스레드 프록시를 바인딩하는 경우 스레드 프록시를 스레드 프록시 팩터의 사용 가능한 풀에서 쉽게 사용할 수 없는 경우 메모리 할당이 포함될 수 있으므로 UMS 스케줄링 컨텍스트의 경우입니다.

`invalid_argument`매개 변수에 `pContext` 값이 `NULL`있는 경우 throw됩니다.

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>ISchedulerProxy::만들기 초과 구독자 메서드

기존 실행 리소스와 연결된 하드웨어 스레드에 새 가상 프로세서 루트를 만듭니다.

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>매개 변수

*p실행리소스*<br/>
초과 `IExecutionResource` 구독하려는 하드웨어 스레드를 나타내는 인터페이스입니다.

### <a name="return-value"></a>Return Value

`IVirtualProcessorRoot` 인터페이스입니다.

### <a name="remarks"></a>설명

스케줄러가 제한된 시간 동안 특정 하드웨어 스레드를 초과 구독하려는 경우 이 방법을 사용합니다. 가상 프로세서 루트를 완료하면 `IVirtualProcessorRoot` 인터페이스에서 [Remove](iexecutionresource-structure.md#remove) 메서드를 호출하여 리소스 관리자에게 반환해야 합니다.

`IVirtualProcessorRoot` 인터페이스가 `IExecutionResource` 인터페이스에서 상속하기 때문에 기존 가상 프로세서 루트를 초과 구독할 수도 있습니다.

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>ISchedulerProxy::요청초기가상 프로세서 방법

가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 스케줄러에 대한 작업을 수행할 수 있는 하나의 스레드를 실행하는 기능을 나타냅니다.

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>매개 변수

*do구독전류스레드*<br/>
리소스 할당 중에 현재 스레드를 구독하고 이를 고려할지 여부입니다.

### <a name="return-value"></a>Return Value

매개 `IExecutionResource` 변수에 `doSubscribeCurrentThread` **true**값이 있는 경우 현재 스레드에 대한 인터페이스입니다. 값이 **false이면**메서드는 NULL을 반환합니다.

### <a name="remarks"></a>설명

스케줄러가 작업을 실행하기 전에 이 메서드를 사용하여 리소스 관리자에서 가상 프로세서 루트를 요청해야 합니다. 리소스 관리자는 [IScheduler::GetPolicy를](ischeduler-structure.md#getpolicy) 사용하여 스케줄러의 정책에 액세스하고 정책 `MinConcurrency`키에 `MaxConcurrency` `TargetOversubscriptionFactor` 대한 값을 사용하고 처음에 스케줄러에 할당할 하드웨어 스레드 수와 모든 하드웨어 스레드에 대해 만들 가상 프로세서 루트 수를 결정합니다. 스케줄러 정책을 사용하여 스케줄러의 초기 할당을 결정하는 방법에 대한 자세한 내용은 [PolicyElementKey](concurrency-namespace-enums.md)를 참조하십시오.

리소스 관리자는 [메서드 IScheduler::AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) 가상 프로세서 루트 목록을 호출 하 여 일정에 리소스를 부여 합니다. 메서드는 이 메서드가 반환되기 전에 스케줄러에 콜백으로 호출됩니다.

스케줄러가 매개 변수를 `doSubscribeCurrentThread` **true로**설정하여 현재 스레드에 대한 `IExecutionResource` 구독을 요청한 경우 메서드는 인터페이스를 반환합니다. [구독은 IExecutionResource::Remove](iexecutionresource-structure.md#remove) 메서드를 사용하여 나중에 종료해야 합니다.

어떤 하드웨어 스레드를 선택할지 결정할 때 리소스 관리자는 프로세서 노드 선호도에 맞게 최적화하려고 시도합니다. 현재 스레드에 대한 구독이 요청된 경우 현재 스레드가 이 스케줄러에 할당된 작업에 참여하려는 것을 나타냅니다. 이러한 경우 할당된 가상 프로세서 루트는 가능하면 현재 스레드가 실행 중인 프로세서 노드에 있습니다.

스레드를 구독하는 행위는 기본 하드웨어 스레드의 구독 수준을 하나씩 증가시킵니다. 구독이 종료되면 구독 수준이 하나씩 줄어듭니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](iexecutionresource-structure.md#currentsubscriptionlevel)을 참조하십시오.

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a>IScheduler프록시::종료 방법

리소스 관리자에 스케줄러가 종료되고 있음을 지정합니다. 이렇게 하면 리소스 관리자가 스케줄러에 부여된 모든 리소스를 즉시 회수합니다.

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>설명

메서드를 `IExecutionContext` `ISchedulerProxy::RequestInitialVirtualProcessors` 사용하여 외부 스레드를 구독한 결과로 받은 모든 인터페이스 또는 `ISchedulerProxy::SubscribeCurrentThread` 스케줄러 자체를 종료하기 `IExecutionResource::Remove` 전에 사용하여 리소스 관리자로 반환해야 합니다.

스케줄러에 비활성화된 가상 프로세서 루트가 있는 경우 [IVirtualProcessorRoot::Activate를](ivirtualprocessorroot-structure.md#activate)사용하여 활성화하고 스레드 프록시가 실행 중인 `Dispatch` 경우 스케줄러 프록시를 호출하기 전에 디스패치하는 `Shutdown` 실행 컨텍스트의 메서드를 남겨두어야 합니다.

모든 가상 프로세서 루트는 종료 시 리소스 관리자로 반환되기 때문에 리소스 관리자가 `Remove` 메서드 호출을 통해 부여한 모든 가상 프로세서 루트를 스케줄러가 개별적으로 반환할 필요는 없습니다.

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>IScheduler프록시::구독전류 스레드 방법

현재 스레드를 리소스 관리자에 등록하여 이 스케줄러와 연결합니다.

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Return Value

런타임의 현재 스레드를 나타내는 `IExecutionResource` 인터페이싱입니다.

### <a name="remarks"></a>설명

리소스 관리자가 현재 스레드를 설명하는 동시에 스케줄러 및 기타 스케줄러에 리소스를 할당하도록 하려면 이 메서드를 사용합니다. 스레드가 스케줄러에 큐에 대기된 작업에 참여할 계획과 리소스 관리자에서 받는 가상 프로세서 루트를 계획할 때 특히 유용합니다. 리소스 관리자는 정보를 사용하여 시스템에서 하드웨어 스레드의 불필요한 초과 구독을 방지합니다.

이 메서드를 통해 받은 실행 리소스는 [IExecutionResource:Remove](iexecutionresource-structure.md#remove) 메서드를 사용하여 리소스 관리자에 반환되어야 합니다. 메서드를 `Remove` 호출하는 스레드는 이전에 `SubscribeCurrentThread` 메서드를 호출한 스레드와 같아야 합니다.

스레드를 구독하는 행위는 기본 하드웨어 스레드의 구독 수준을 하나씩 증가시킵니다. 구독이 종료되면 구독 수준이 하나씩 줄어듭니다. 구독 수준에 대한 자세한 내용은 [IExecutionResource::현재 구독 수준](iexecutionresource-structure.md#currentsubscriptionlevel)을 참조하십시오.

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>IScheduler프록시::바인딩되지 않은 컨텍스트 메서드

매개 변수에 의해 지정된 실행 컨텍스트에서 `pContext` 스레드 프록시를 분리 하 고 스레드 프록시 팩터리의 사용 되지 않는 풀에 반환 합니다. 이 메서드는 [ISchedulerProxy::BindContext](#bindcontext) 메서드를 통해 바인딩된 실행 컨텍스트에서만 호출될 수 `pContext` 있으며 [아직 IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) 메서드 호출의 매개 변수를 통해 시작되지 않았습니다.

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
스레드 프록시에서 연결을 해제하는 실행 컨텍스트입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 구조체](iresourcemanager-structure.md)
