---
title: IExecutionContext 구조체
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 532247ca1776452ad32476d2bcdfafcee3481058
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358797"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 구조체

지정된 가상 프로세서에서 실행되고 협조적으로 컨텍스트가 전환될 수 있는 실행 컨텍스트에 대한 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
struct IExecutionContext;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I실행컨텍스트::Dispatch](#dispatch)|스레드 프록시가 특정 실행 컨텍스트를 실행하기 시작할 때 호출되는 메서드입니다. 이 루틴은 스케줄러의 기본 작업자 루틴이어야 합니다.|
|[I실행 컨텍스트::GetId](#getid)|실행 컨텍스트에 대한 고유 식별자를 반환합니다.|
|[I실행 컨텍스트::GetProxy](#getproxy)|이 컨텍스트를 실행하는 스레드 프록시에 인터페이스를 반환합니다.|
|[I실행 컨텍스트::GetScheduler](#getscheduler)|이 실행 컨텍스트가 속한 스케줄러에 인터페이스를 반환합니다.|
|[I실행컨텍스트::세트프록시](#setproxy)|스레드 프록시를 이 실행 컨텍스트와 연결합니다. 연결된 스레드 프록시는 컨텍스트의 `Dispatch` 메서드 실행을 시작하기 직전에 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

동시성 런타임의 리소스 관리자와 인터페이스하는 사용자 지정 스케줄러를 구현하는 경우 인터페이스를 `IExecutionContext` 구현해야 합니다. 리소스 관리자에서 만든 스레드는 `IExecutionContext::Dispatch` 메서드를 실행하여 스케줄러를 대신하여 작업을 수행합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IExecutionContext`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a>I실행컨텍스트::D디스패치 방법

스레드 프록시가 특정 실행 컨텍스트를 실행하기 시작할 때 호출되는 메서드입니다. 이 루틴은 스케줄러의 기본 작업자 루틴이어야 합니다.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>매개 변수

*p디스패치상태*<br/>
이 실행 컨텍스트가 디스패치되는 상태에 대한 포인터입니다. 디스패치 상태에 대한 자세한 내용은 [DispatchState](dispatchstate-structure.md)를 참조하십시오.

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a>I실행 컨텍스트::GetId 메서드

실행 컨텍스트에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

고유한 정수 식별자입니다.

### <a name="remarks"></a>설명

이 메서드를 `GetExecutionContextId` 사용하여 `IExecutionContext` 인터페이스를 구현하는 개체에 대한 고유 식별자를 구한 다음 리소스 관리자에서 제공하는 메서드에 대한 매개 변수로 사용해야 합니다. `GetId` 함수가 호출될 때 동일한 식별자를 반환해야 합니다.

다른 소스에서 가져온 식별자는 정의되지 않은 동작이 발생할 수 있습니다.

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>I실행 컨텍스트::GetProxy 메서드

이 컨텍스트를 실행하는 스레드 프록시에 인터페이스를 반환합니다.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Return Value

`IThreadProxy` 인터페이스입니다. 실행 컨텍스트의 스레드 프록시가 호출로 `SetProxy`초기화되지 않은 경우 함수가 반환되어야 `NULL`합니다.

### <a name="remarks"></a>설명

리소스 관리자는 컨텍스트에서 메서드를 `SetProxy` 입력하기 전에 인터페이스를 `IThreadProxy` 매개 변수로 사용하여 `Dispatch` 실행 컨텍스트에서 메서드를 호출합니다. 이 인수를 저장하고 호출시 반환해야 `GetProxy()`합니다.

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>I실행 컨텍스트::GetScheduler 메서드

이 실행 컨텍스트가 속한 스케줄러에 인터페이스를 반환합니다.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Return Value

`IScheduler` 인터페이스입니다.

### <a name="remarks"></a>설명

리소스 관리자에서 제공하는 메서드에 대한 `IScheduler` 매개 변수로 사용하기 전에 유효한 인터페이스로 실행 컨텍스트를 초기화해야 합니다.

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>I실행컨텍스트:SetProxy 메서드

스레드 프록시를 이 실행 컨텍스트와 연결합니다. 연결된 스레드 프록시는 컨텍스트의 `Dispatch` 메서드 실행을 시작하기 직전에 이 메서드를 호출합니다.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>매개 변수

*p스레드 프록시*<br/>
이 실행 컨텍스트에서 메서드를 입력하려고 `Dispatch` 하는 스레드 프록시에 대한 인터페이스입니다.

### <a name="remarks"></a>설명

매개 변수를 `pThreadProxy` 저장 하고 `GetProxy` 메서드에 대 한 호출에 반환 해야 합니다. 리소스 관리자는 스레드 프록시가 `Dispatch` 메서드를 실행하는 동안 실행 컨텍스트와 연결된 스레드 프록시가 변경되지 않도록 합니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)
