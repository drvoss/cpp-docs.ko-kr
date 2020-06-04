---
title: IThreadProxy 구조체
ms.date: 11/04/2016
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
ms.openlocfilehash: fc2fb2df06225a5c963fe39178c1b4a10f77953d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368136"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy 구조체

실행 스레드에 대한 추상화입니다. 직접 만든 스케줄러의 `SchedulerType` 정책 키에 따라 리소스 관리자는 일반 Win32 스레드 또는 UMS(사용자 모드 예약 가능) 스레드 중 하나에서 지원되는 스레드 프록시를 부여합니다. UMS 스레드는 Windows 7 이상 버전의 64비트 운영 체제에서 지원됩니다.

## <a name="syntax"></a>구문

```cpp
struct IThreadProxy;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IThread프록시::GetId](#getid)|스레드 프록시에 대한 고유 식별자를 반환합니다.|
|[IThread프록시::스위치아웃](#switchout)|내부 가상 프로세서 루트에서 컨텍스트의 연결을 끊습니다.|
|[IThread프록시::스위치토](#switchto)|현재 실행 중인 컨텍스트에서 다른 컨텍스트로 협동 컨텍스트 전환을 수행합니다.|
|[IThread프록시::YieldToSystem](#yieldtosystem)|호출 스레드가 현재 프로세서에서 실행할 준비가 되어 있는 다른 스레드에 실행 명령을 내리도록 합니다. 운영 체제는 실행할 다음 스레드를 선택합니다.|

## <a name="remarks"></a>설명

스레드 프록시는 작업을 디스패치하는 수단으로 인터페이스로 `IExecutionContext` 표시되는 실행 컨텍스트에 결합됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IThreadProxy`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

## <a name="ithreadproxygetid-method"></a><a name="getid"></a>IThreadProxy::GetId 메서드

스레드 프록시에 대한 고유 식별자를 반환합니다.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Return Value

고유한 정수 식별자입니다.

## <a name="ithreadproxyswitchout-method"></a><a name="switchout"></a>IThread프록시::스위치아웃 방법

내부 가상 프로세서 루트에서 컨텍스트의 연결을 끊습니다.

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>매개 변수

*스위치 상태*<br/>
스위치를 실행하는 스레드 프록시의 상태를 나타냅니다. 매개 변수는 `SwitchingProxyState`형식입니다.

### <a name="remarks"></a>설명

어떠한 이유로든 실행 중인 가상 프로세서 루트에서 컨텍스트 연결을 끊어야 할 경우 `SwitchOut`을 사용합니다. `switchState` 매개변수에 전달하는 값에 따라 그리고 가상 프로세서 루트에서 실행하는지 여부에 따라 이 호출은 해당 컨텍스트와 연결된 스레드 프록시를 즉시 반환하거나 차단합니다. 매개 변수를 `SwitchOut`로 설정하여 `Idle`을 호출하면 오류가 발생합니다. 이렇게 하면 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외가 발생합니다.

`SwitchOut`은 리소스 관리자의 지시에 따라 또는 일시적으로 초과 구독된 가상 프로세서 루트를 요청했는데 그러한 요청이 처리되어 스케줄러의 가상 프로세서 루트 수를 줄이고자 할 때 유용합니다. 이 경우 매개 변수를 `switchState` 로 설정하여 호출하기 `Blocking` `SwitchOut` 전에 가상 프로세서 루트에서 [IVirtualProcessorRoot::Remove](iexecutionresource-structure.md#remove) 메서드를 호출해야 합니다. 이렇게 하면 스레드 프록시가 차단되고, 스케줄러의 다른 가상 프로세서 루트에서 실행할 수 있을 때 실행이 다시 시작됩니다. 이 스레드 프록시의 실행 컨텍스트로 `SwitchTo` 전환 하는 함수를 호출 하 여 차단 스레드 프록시를 다시 시작할 수 있습니다. 연결된 컨텍스트를 사용하여 가상 프로세서 루트를 활성화하여 스레드 프록시를 다시 시작할 수도 있습니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)를 참조하십시오.

또한 `SwitchOut`은 스레드 프록시를 차단하거나, 스레드 프록시가 실행 중인 가상 프로세서 루트와 스레드 프록시를 디스패칭하는 스케줄러에서 일시적으로 연결을 끊는 동안 나중에 활성화될 수 있도록 가상 프로세서를 다시 초기화하려 할 때도 사용할 수 있습니다. 스레드 프록시를 차단하려는 경우 `SwitchOut` 매개 변수를 `switchState`으로 설정하여 `Blocking`을 사용합니다. 위에서 언급했듯이 `SwitchTo` 또는 `IVirtualProcessorRoot::Activate`을 사용하여 나중에 다시 시작할 수 있습니다. 이 스레드 프록시가 실행 중인 가상 프로세서 루트 및 가상 프로세서가 연결된 스케줄러에서 일시적으로 스레드 프록시의 연결을 끊으려면 매개 변수를 `SwitchOut`으로 설정하여 `Nesting`을 사용합니다. 가상 프로세서 루트에서 실행 중일 때 `SwitchOut` 매개 변수를 `switchState`으로 설정하여 `Nesting`을 호출하면 루트가 다시 초기화되고 현재 스레드 프록시가 다른 루트를 필요로 하지 않고 계속 실행됩니다. 스레드 프록시는 [나중에 IThreadProxy::SwitchOut](#switchout) 메서드를 `Blocking` 호출할 때까지 스케줄러를 떠난 것으로 간주됩니다. 매개 변수를 `SwitchOut`으로 설정하여 `Blocking`을 두 번째로 호출하는 목적은, 컨텍스트를 차단된 상태로 돌려서 `SwitchTo` 또는 컨텍스트 연결을 끊은 스케줄러의 `IVirtualProcessorRoot::Activate`에 의해 다시 시작될 수 있도록 하는 것입니다. 컨텍스트는 가상 프로세서 루트에서 실행되고 있지 않았기 때문에 다시 초기화가 수행되지 않습니다.

다시 초기화된 가상 프로세서 루트는 리소스 관리자가 스케줄러를 부여한 새로운 가상 프로세서 루트와 차이가 없습니다. 이는 `IVirtualProcessorRoot::Activate`를 사용하여 실행 컨텍스트로 가상 프로세서 루트를 활성화함으로써 실행하는 데 사용할 수 있습니다.

`SwitchOut`현재 실행 중인 `IThreadProxy` 스레드를 나타내는 인터페이스에서 호출해야 하거나 결과가 정의되지 않은 경우

Visual Studio 2010과 함께 제공된 헤더 및 라이브러리에서 이 메서드는 매개 변수를 사용하지 않으며 가상 프로세서 루트를 다시 초기화하지 않습니다. 이전 동작을 유지하기 위해 `Blocking`의 기본 매개 변수 값이 제공됩니다.

## <a name="ithreadproxyswitchto-method"></a><a name="switchto"></a>IThread프록시::스위치To 방법

현재 실행 중인 컨텍스트에서 다른 컨텍스트로 협동 컨텍스트 전환을 수행합니다.

```cpp
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
협조적으로 전환할 실행 컨텍스트입니다.

*스위치 상태*<br/>
스위치를 실행하는 스레드 프록시의 상태를 나타냅니다. 매개 변수는 `SwitchingProxyState`형식입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 한 실행 컨텍스트에서 다른 [실행 컨텍스트에서 IExecutionContext::D](iexecutioncontext-structure.md#dispatch) 첫 번째 실행 컨텍스트의 ispatch 메서드에서 전환 합니다. 메서드는 실행 컨텍스트를 `pContext` 스레드 프록시와 연결하지 않은 경우 스레드 프록시와 연결합니다. 현재 스레드 프록시의 소유권은 인수에 대해 지정한 값에 `switchState` 의해 결정됩니다.

현재 실행 `Idle` 중인 스레드 프록시를 리소스 관리자에 반환하려는 경우 값을 사용합니다. 매개 `SwitchTo` 변수를 `switchState` 설정하여 `Idle` 호출하면 `pContext` 실행 컨텍스트가 기본 실행 리소스에서 실행을 시작합니다. 이 스레드 프록시의 소유권은 리소스 관리자로 전송되며 전송을 완료하기 `Dispatch` 위해 반환 `SwitchTo` 직후 실행 컨텍스트의 메서드에서 반환해야 합니다. 스레드 프록시가 디스패치한 실행 컨텍스트는 스레드 프록시에서 분리되며 스케줄러는 스레드 프록시를 다시 사용하거나 적합하다고 판단되는 대로 삭제할 수 있습니다.

이 스레드 `Blocking` 프록시가 차단된 상태로 들어가도록 할 때 값을 사용합니다. 매개 `SwitchTo` 변수를 `switchState` 설정하여 `Blocking` 호출하면 `pContext` 실행 컨텍스트가 실행을 시작하고 다시 시작될 때까지 현재 스레드 프록시를 차단합니다. 스케줄러는 스레드 프록시가 상태에 있을 때 스레드 프록시의 소유권을 `Blocking` 유지합니다. 이 스레드 프록시의 실행 컨텍스트로 `SwitchTo` 전환 하는 함수를 호출 하 여 차단 스레드 프록시를 다시 시작할 수 있습니다. 연결된 컨텍스트를 사용하여 가상 프로세서 루트를 활성화하여 스레드 프록시를 다시 시작할 수도 있습니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)를 참조하십시오.

이 스레드 `Nesting` 프록시가 실행 중인 가상 프로세서 루트와 디스패치 작업중인 스케줄러에서 이 스레드 프록시를 일시적으로 분리하려는 경우 값을 사용합니다. 매개 `SwitchTo` 변수를 `switchState` 설정하여 `Nesting` 호출하면 `pContext` 실행 컨텍스트가 실행을 시작하고 현재 스레드 프록시도 가상 프로세서 루트없이 계속 실행됩니다. 스레드 프록시는 나중에 [IThreadProxy::SwitchOut](#switchout) 메서드를 호출할 때까지 스케줄러를 떠난 것으로 간주됩니다. 메서드는 `IThreadProxy::SwitchOut` 가상 프로세서 루트를 사용하여 일정을 변경할 때까지 스레드 프록시를 차단할 수 있습니다.

`SwitchTo`현재 실행 중인 `IThreadProxy` 스레드를 나타내는 인터페이스에서 호출해야 하거나 결과가 정의되지 않은 경우 매개 변수가 `invalid_argument` `pContext` 로 설정된 경우 `NULL`함수가 throw됩니다.

## <a name="ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a>IThread프록시::yieldToSystem 방법

호출 스레드가 현재 프로세서에서 실행할 준비가 되어 있는 다른 스레드에 실행 명령을 내리도록 합니다. 운영 체제는 실행할 다음 스레드를 선택합니다.

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>설명

일반 Windows `YieldToSystem` 스레드에서 백업하는 스레드 프록시에서 호출하면 Windows 함수와 `SwitchToThread`똑같이 작동합니다. 그러나 UMS(사용자 모드 예약 가능) 스레드에서 호출될 때 함수는 `SwitchToThread` 운영 체제가 아닌 사용자 모드 스케줄러로 실행할 다음 스레드를 선택하는 작업을 위임합니다. 시스템의 다른 준비 스레드로 전환하는 원하는 효과를 얻으려면 `YieldToSystem`을 사용합니다.

`YieldToSystem`현재 실행 중인 `IThreadProxy` 스레드를 나타내는 인터페이스에서 호출해야 하거나 결과가 정의되지 않은 경우

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스](concurrency-namespace.md)<br/>
[IExecutionContext 구조체](iexecutioncontext-structure.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)
