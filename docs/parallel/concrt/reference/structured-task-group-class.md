---
title: structured_task_group 클래스
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: 93dd79b755f79dcb4857c1b1c4856362b0bd45dd
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427364"
---
# <a name="structured_task_group-class"></a>structured_task_group 클래스

`structured_task_group` 클래스는 구조화된 병렬 작업 컬렉션을 나타냅니다. `structured_task_group` 개체를 사용하여 개별 병렬 작업을 `task_handle`에 대기시킨 다음 완료되기를 기다리거나 실행이 완료되기 전에 작업 그룹을 취소합니다. 이 경우 실행이 시작되지 않은 작업이 모두 중단됩니다.

## <a name="syntax"></a>구문

```cpp
class structured_task_group;
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[structured_task_group](#ctor)|오버로드되었습니다. 새 `structured_task_group` 개체를 생성합니다.|
|[~ structured_task_group 소멸자](#dtor)|`structured_task_group` 개체를 제거합니다. 소멸자가 예외로 인해 스택 해제의 결과로 실행 되는 경우가 아니면 소멸자를 실행 하기 전에 개체에 대해 `wait` 또는 `run_and_wait` 메서드를 호출 해야 합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[cancel](#cancel)|이 작업 그룹을 기반으로 하는 작업의 하위 트리를 취소 하려고 하는 것이 가장 좋습니다. 작업 그룹에 대해 예약 된 모든 작업은 가능 하면 전이적으로 취소 됩니다.|
|[is_canceling](#is_canceling)|작업 그룹이 현재 취소를 진행 중인지 여부를 호출자에 게 알립니다. 이는 `cancel` 메서드가 `structured_task_group` 개체에 대해 호출 되었음을 나타내는 것은 아닙니다 .이는이 메서드가 **true**를 반환 하도록 하는 것입니다. `structured_task_group` 개체가 인라인으로 실행 중이 고 작업 트리에서 추가 된 작업 그룹이 취소 된 경우에 발생할 수 있습니다. 런타임에서 취소가이 `structured_task_group` 개체를 통해 전달 되는 시간을 미리 확인할 수 있는 경우에도 **true** 가 반환 됩니다.|
|[run](#run)|오버로드되었습니다. `structured_task_group` 개체에 대 한 작업을 예약 합니다. 호출자는 `_Task_handle` 매개 변수에 전달 된 `task_handle` 개체의 수명을 관리 합니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.|
|[run_and_wait](#run_and_wait)|오버로드되었습니다. 전체 취소 지원에 대 한 `structured_task_group` 개체의 지원을 사용 하 여 호출 컨텍스트에서 인라인으로 실행할 작업을 예약 합니다. `task_handle` 개체가 `run_and_wait`에 매개 변수로 전달 되는 경우 호출자는 `task_handle` 개체의 수명을 관리 하는 일을 담당 합니다. 그러면 함수는 `structured_task_group` 개체의 모든 작업이 완료 되거나 취소 될 때까지 대기 합니다.|
|[대기한](#wait)|`structured_task_group`의 모든 작업이 완료 되거나 취소 될 때까지 대기 합니다.|

## <a name="remarks"></a>설명

성능 향상을 위해 `structured_task_group` 개체 사용에 대 한 몇 가지 심각한 제한 사항이 있습니다.

- 단일 `structured_task_group` 개체는 여러 스레드에서 사용할 수 없습니다. 개체를 만든 스레드에서 `structured_task_group` 개체에 대 한 모든 작업을 수행 해야 합니다. 이 규칙에 대 한 두 가지 예외는 `cancel` 및 `is_canceling`멤버 함수입니다. 태스크가 취소 작업 중 하나를 사용 하지 않는 경우 개체는 람다 식의 캡처 목록에 있지 않고 작업 내에서 사용 될 수 있습니다.

- `structured_task_group` 개체에 예약 된 모든 작업은의 수명을 명시적으로 관리 해야 하는 `task_handle` 개체를 사용 하 여 예약 됩니다.

- 여러 그룹은 절대 중첩 된 순서로만 사용할 수 있습니다. 두 개의 `structured_task_group` 개체가 선언 되 면 선언 되는 두 번째 개체 (내부 항목)는 `cancel` 또는 `is_canceling`를 제외한 모든 메서드가 첫 번째 개체 (외부)에서 호출 되기 전에 소멸 되어야 합니다. 이 조건은 동일 하거나 기능이 중첩 된 범위 내에서 여러 `structured_task_group` 개체를 선언 하는 경우와 `run` 또는 `run_and_wait` 메서드를 통해 `structured_task_group`에 큐에 대기 된 작업의 경우에만 적용 됩니다.

- 일반 `task_group` 클래스와 달리 `structured_task_group` 클래스의 모든 상태는 최종입니다. 그룹에 작업을 큐 대기하고 완료되기를 기다린 후에 다시 같은 그룹을 사용할 수 없습니다.

자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`structured_task_group`

## <a name="requirements"></a>요구 사항

**헤더:** ppl. h

**네임스페이스:** 동시성

## <a name="cancel"></a>취소

이 작업 그룹을 기반으로 하는 작업의 하위 트리를 취소 하려고 하는 것이 가장 좋습니다. 작업 그룹에 대해 예약 된 모든 작업은 가능 하면 전이적으로 취소 됩니다.

```cpp
void cancel();
```

### <a name="remarks"></a>설명

자세한 내용은 [취소](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)를 참조 하세요.

## <a name="is_canceling"></a>is_canceling

작업 그룹이 현재 취소를 진행 중인지 여부를 호출자에 게 알립니다. 이는 `cancel` 메서드가 `structured_task_group` 개체에 대해 호출 되었음을 나타내는 것은 아닙니다 .이는이 메서드가 **true**를 반환 하도록 하는 것입니다. `structured_task_group` 개체가 인라인으로 실행 중이 고 작업 트리에서 추가 된 작업 그룹이 취소 된 경우에 발생할 수 있습니다. 런타임에서 취소가이 `structured_task_group` 개체를 통해 전달 되는 시간을 미리 확인할 수 있는 경우에도 **true** 가 반환 됩니다.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Return Value

`structured_task_group` 개체가 취소 중에 있는지 여부를 표시 하는 것을 나타냅니다.

### <a name="remarks"></a>설명

자세한 내용은 [취소](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)를 참조 하세요.

## <a name="run"></a>실행할지

`structured_task_group` 개체에 대 한 작업을 예약 합니다. 호출자는 `_Task_handle` 매개 변수에 전달 된 `task_handle` 개체의 수명을 관리 합니다. `_Placement` 매개 변수를 사용하는 버전은 이 매개 변수로 지정된 위치에서 작업이 실행되도록 합니다.

```cpp
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>매개 변수

*_Function*<br/>
작업 핸들의 본문을 실행 하기 위해 호출 될 함수 개체의 형식입니다.

*_Task_handle*<br/>
예약 중인 작업에 대 한 핸들입니다. 호출자는이 개체의 수명에 대 한 책임이 있습니다. 이 `structured_task_group` 개체에 대해 `wait` 또는 `run_and_wait` 메서드가 호출 될 때까지 런타임은 지속 될 것으로 간주 합니다.

*_Placement*<br/>
`_Task_handle` 매개 변수가 나타내는 작업을 실행해야 할 위치에 대한 참조입니다.

### <a name="remarks"></a>설명

런타임은이 메서드에 전달 하는 작업 함수의 복사본을 만듭니다. 이 메서드에 전달 하는 함수 개체에서 발생 하는 모든 상태 변경은 해당 함수 개체의 복사본에 표시 되지 않습니다.

예외에서 스택 해제의 결과로 `structured_task_group` destructs 면 `wait` 또는 `run_and_wait` 메서드가 호출 되는 것을 보장할 필요가 없습니다. 이 경우 소멸자는 적절히 취소 하 고 `_Task_handle` 매개 변수가 나타내는 작업이 완료 될 때까지 기다립니다.

`_Task_handle` 매개 변수에 지정 된 작업 핸들이 `run` 메서드를 통해 작업 그룹 개체에 이미 예약 되어 있고 해당 작업 그룹의 `wait` 또는 `run_and_wait` 메서드에 대해 중간에 호출 되지 않은 경우 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) 예외를 throw 합니다.

## <a name="run_and_wait"></a>run_and_wait

전체 취소 지원에 대 한 `structured_task_group` 개체의 지원을 사용 하 여 호출 컨텍스트에서 인라인으로 실행할 작업을 예약 합니다. `task_handle` 개체가 `run_and_wait`에 매개 변수로 전달 되는 경우 호출자는 `task_handle` 개체의 수명을 관리 하는 일을 담당 합니다. 그러면 함수는 `structured_task_group` 개체의 모든 작업이 완료 되거나 취소 될 때까지 대기 합니다.

```cpp
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>매개 변수

*_Function*<br/>
작업을 실행하기 위해 호출될 함수 개체의 형식입니다.

*_Task_handle*<br/>
호출 컨텍스트에서 인라인으로 실행 될 작업에 대 한 핸들입니다. 호출자는이 개체의 수명에 대 한 책임이 있습니다. 런타임은 `run_and_wait` 메서드가 실행을 완료할 때까지 계속 해 서 작동 합니다.

*_Func*<br/>
작업 본문을 호출 하기 위해 호출 되는 함수입니다. `void operator()()`시그니처와 함께 함수 호출 연산자의 버전을 지 원하는 람다 또는 다른 개체 일 수 있습니다.

### <a name="return-value"></a>Return Value

명시적 취소 작업이 나 작업 중 하나에서 throw 되는 예외로 인해 대기가 충족 되었거나 작업 그룹이 취소 되었는지 여부를 나타냅니다. 자세한 내용은 [task_group_status](concurrency-namespace-enums.md) 를 참조 하세요.

### <a name="remarks"></a>설명

이 `structured_task_group` 개체에 대해 예약 된 작업 중 하나 이상이 호출 컨텍스트에서 인라인으로 실행 될 수 있습니다.

이 `structured_task_group` 개체에 예약 된 작업 중 하나 이상이 예외를 throw 하는 경우 런타임은 이러한 예외를 선택 하 고 `run_and_wait` 메서드에 대 한 호출에서 전파 합니다.

이 함수가 반환된 후 `structured_task_group` 개체는 최종 상태로 간주되므로 사용할 수 없습니다. `run_and_wait` 메서드가 반환 된 후에 사용 하면 정의 되지 않은 동작이 발생 합니다.

실행의 비 예외 경로에서는 `structured_task_group`의 소멸자가 실행 되기 전에이 메서드 또는 `wait` 메서드를 호출 해야 합니다.

## <a name="ctor"></a>structured_task_group

새 `structured_task_group` 개체를 생성합니다.

```cpp
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>매개 변수

*_CancellationToken*<br/>
이 구조화 된 작업 그룹과 연결할 취소 토큰입니다. 토큰이 취소 되 면 구조화 된 작업 그룹이 취소 됩니다.

### <a name="remarks"></a>설명

취소 토큰을 사용하는 생성자는 토큰에 연결된 소스가 취소될 때 취소될 `structured_task_group`을 만듭니다. 명시적 취소 토큰을 제공 하면이 구조화 된 작업 그룹이 다른 토큰을 사용 하거나 토큰 없이 부모 그룹에서 암시적 취소에 참여 하지 않도록 격리 됩니다.

## <a name="dtor"></a>~ structured_task_group

`structured_task_group` 개체를 제거합니다. 소멸자가 예외로 인해 스택 해제의 결과로 실행 되는 경우가 아니면 소멸자를 실행 하기 전에 개체에 대해 `wait` 또는 `run_and_wait` 메서드를 호출 해야 합니다.

```cpp
~structured_task_group();
```

### <a name="remarks"></a>설명

소멸자가 정상적인 실행의 결과로 실행 되는 경우 (예: 예외로 인해 스택 해제 되지 않음) `wait` 및 `run_and_wait` 메서드가 호출 되지 않은 경우 소멸자는 [missing_wait](missing-wait-class.md) 예외를 throw 할 수 있습니다.

## <a name="wait"></a>대기한

`structured_task_group`의 모든 작업이 완료 되거나 취소 될 때까지 대기 합니다.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Return Value

명시적 취소 작업이 나 작업 중 하나에서 throw 되는 예외로 인해 대기가 충족 되었거나 작업 그룹이 취소 되었는지 여부를 나타냅니다. 자세한 내용은 [task_group_status](concurrency-namespace-enums.md) 를 참조 하세요.

### <a name="remarks"></a>설명

이 `structured_task_group` 개체에 대해 예약 된 작업 중 하나 이상이 호출 컨텍스트에서 인라인으로 실행 될 수 있습니다.

이 `structured_task_group` 개체에 예약 된 작업 중 하나 이상이 예외를 throw 하는 경우 런타임은 이러한 예외를 선택 하 고 `wait` 메서드에 대 한 호출에서 전파 합니다.

이 함수가 반환된 후 `structured_task_group` 개체는 최종 상태로 간주되므로 사용할 수 없습니다. `wait` 메서드가 반환 된 후에 사용 하면 정의 되지 않은 동작이 발생 합니다.

실행의 비 예외 경로에서는 `structured_task_group`의 소멸자가 실행 되기 전에이 메서드 또는 `run_and_wait` 메서드를 호출 해야 합니다.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[task_group 클래스](task-group-class.md)<br/>
[task_handle 클래스](task-handle-class.md)
