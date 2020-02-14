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
ms.openlocfilehash: 45d65a5e16121d39233c3ceb801933aa1f5a5f8e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138910"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 구조체

지정된 가상 프로세서에서 실행되고 협조적으로 컨텍스트가 전환될 수 있는 실행 컨텍스트에 대한 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
struct IExecutionContext;
```

## <a name="members"></a>구성원

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IExecutionContext::D ispatch](#dispatch)|스레드 프록시가 특정 실행 컨텍스트를 실행 하기 시작할 때 호출 되는 메서드입니다. 스케줄러에 대 한 기본 작업자 루틴이 되어야 합니다.|
|[IExecutionContext:: GetId](#getid)|실행 컨텍스트에 대 한 고유 식별자를 반환 합니다.|
|[IExecutionContext:: GetProxy](#getproxy)|이 컨텍스트를 실행 하는 스레드 프록시에 대 한 인터페이스를 반환 합니다.|
|[IExecutionContext:: GetScheduler](#getscheduler)|이 실행 컨텍스트가 속한 스케줄러에 대 한 인터페이스를 반환 합니다.|
|[IExecutionContext:: SetProxy](#setproxy)|스레드 프록시를이 실행 컨텍스트에 연결 합니다. 연결 된 스레드 프록시는 컨텍스트의 `Dispatch` 메서드 실행을 시작 하기 바로 전에이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

동시성 런타임의 리소스 관리자와 상호 작용 하는 사용자 지정 스케줄러를 구현 하는 경우에는 `IExecutionContext` 인터페이스를 구현 해야 합니다. 리소스 관리자에서 생성 된 스레드는 `IExecutionContext::Dispatch` 메서드를 실행 하 여 스케줄러를 대신 하 여 작업을 수행 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`IExecutionContext`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm. h

**네임스페이스:** 동시성

## <a name="dispatch"></a>IExecutionContext::D ispatch 메서드

스레드 프록시가 특정 실행 컨텍스트를 실행 하기 시작할 때 호출 되는 메서드입니다. 스케줄러에 대 한 기본 작업자 루틴이 되어야 합니다.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>매개 변수

*pDispatchState*<br/>
이 실행 컨텍스트가 디스패치되는 상태에 대 한 포인터입니다. 디스패치 상태에 대 한 자세한 내용은 [Dispatchstate](dispatchstate-structure.md)를 참조 하세요.

## <a name="getid"></a>IExecutionContext:: GetId 메서드

실행 컨텍스트에 대 한 고유 식별자를 반환 합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

고유한 정수 식별자입니다.

### <a name="remarks"></a>설명

리소스 관리자에서 제공 하는 메서드에 대 한 매개 변수로 인터페이스를 사용 하기 전에 메서드 `GetExecutionContextId`를 사용 하 여 `IExecutionContext` 인터페이스를 구현 하는 개체의 고유 식별자를 가져와야 합니다. `GetId` 함수가 호출 될 때 동일한 식별자를 반환할 것으로 예상 됩니다.

다른 소스에서 가져온 식별자로 인해 정의 되지 않은 동작이 발생할 수 있습니다.

## <a name="getproxy"></a>IExecutionContext:: GetProxy 메서드

이 컨텍스트를 실행 하는 스레드 프록시에 대 한 인터페이스를 반환 합니다.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Return Value

`IThreadProxy` 인터페이스입니다. 실행 컨텍스트의 스레드 프록시가 `SetProxy`를 호출 하 여 초기화 되지 않은 경우 함수는 `NULL`를 반환 해야 합니다.

### <a name="remarks"></a>설명

리소스 관리자는 컨텍스트의에 `Dispatch` 메서드를 입력 하기 전에 `IThreadProxy` 인터페이스를 매개 변수로 사용 하 여 실행 컨텍스트에서 `SetProxy` 메서드를 호출 합니다. 이 인수를 저장 하 고 `GetProxy()`에 대 한 호출에 반환 해야 합니다.

## <a name="getscheduler"></a>IExecutionContext:: GetScheduler 메서드

이 실행 컨텍스트가 속한 스케줄러에 대 한 인터페이스를 반환 합니다.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Return Value

`IScheduler` 인터페이스입니다.

### <a name="remarks"></a>설명

올바른 `IScheduler` 인터페이스를 사용 하 여 실행 컨텍스트를 초기화 해야 리소스 관리자에서 제공 하는 메서드에 대 한 매개 변수로 사용할 수 있습니다.

## <a name="setproxy"></a>IExecutionContext:: SetProxy 메서드

스레드 프록시를이 실행 컨텍스트에 연결 합니다. 연결 된 스레드 프록시는 컨텍스트의 `Dispatch` 메서드 실행을 시작 하기 바로 전에이 메서드를 호출 합니다.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>매개 변수

*pThreadProxy*<br/>
이 실행 컨텍스트에 `Dispatch` 메서드를 입력 하려고 하는 스레드 프록시에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

`pThreadProxy` 매개 변수를 저장 하 고 `GetProxy` 메서드에 대 한 호출을 통해 반환 해야 합니다. 리소스 관리자은 스레드 프록시가 `Dispatch` 메서드를 실행 하는 동안 실행 컨텍스트와 연결 된 스레드 프록시가 변경 되지 않도록 보장 합니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)
