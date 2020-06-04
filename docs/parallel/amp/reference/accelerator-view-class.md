---
title: accelerator_view 클래스
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: f3be8cc3ab9a0f36027cc38c88f026570d1fdb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370885"
---
# <a name="accelerator_view-class"></a>accelerator_view 클래스

C++ AMP 데이터 병렬 가속기에서 가상 장치 추상화를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class accelerator_view;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[accelerator_view 생성자](#ctor)|`accelerator_view` 클래스의 새 인스턴스를 초기화합니다.|
|[~ accelerator_view 소멸자](#dtor)|개체를 `accelerator_view` 삭제합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[create_marker](#create_marker)|미래를 반환하여 이 `accelerator_view` 개체에 지금까지 제출된 모든 명령의 완료를 추적합니다.|
|[플러시](#flush)|실행을 위해 `accelerator_view` 개체에 큐에 대기 중인 모든 보류 중인 명령을 가속기에 제출합니다.|
|[get_accelerator](#get_accelerator)|`accelerator` 개체의 `accelerator_view` 개체를 반환합니다.|
|[get_is_auto_selection](#get_is_auto_selection)|`accelerator_view` 개체가 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)전달될 때 런타임이 자동으로 적절한 가속기를 선택할지 여부를 나타내는 부울 값을 반환합니다.|
|[get_is_debug](#get_is_debug)|`accelerator_view` 개체에 광범위한 오류 보고를 위해 DEBUG 계층을 사용하도록 설정했는지 여부를 나타내는 부울 값을 반환합니다.|
|[get_queuing_mode](#get_queuing_mode)|개체에 대한 큐 모드를 `accelerator_view` 반환합니다.|
|[get_version](#get_version)|의 버전을 반환합니다. `accelerator_view`|
|[기다릴](#wait)|`accelerator_view` 개체에 제출된 모든 명령이 완료될 때까지 기다립니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[연산자!=](#operator_neq)|이 `accelerator_view` 개체를 다른 개체와 비교하고 동일한 경우 **false를** 반환합니다. 그렇지 않으면 **true를 반환합니다.**|
|[연산자 =](#operator_eq)|지정된 `accelerator_view` 개체의 내용을 이 개체에 복사합니다.|
|[연산자==](#operator_eq_eq)|이 `accelerator_view` 개체를 다른 개체와 비교하고 true가 동일한 **경우** true를 반환합니다. 그렇지 않으면 **false**를 반환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[가속기](#accelerator)|`accelerator` 개체에 대한 `accelerator_view` 개체를 가져옵니다.|
|[is_auto_selection](#is_auto_selection)|`accelerator_view` 개체가 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)전달될 때 런타임이 자동으로 적절한 가속기를 선택할지 여부를 나타내는 부울 값을 가져옵니다.|
|[is_debug](#is_debug)|`accelerator_view` 개체에 DEBUG 계층이 광범위한 오류 보고를 사용하도록 설정되었는지 여부를 나타내는 부울 값을 가져옵니다.|
|[queuing_mode](#queuing_mode)|개체에 대한 큐 모드가 `accelerator_view` 가져옵니다.|
|[version](#version)|엑셀러레이터의 버전을 가져옵니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`accelerator_view`

### <a name="remarks"></a>설명

개체는 `accelerator_view` 가속기의 논리적이고 격리된 뷰를 나타냅니다. 단일 물리적 계산 장치에는 논리적이고 `accelerator_view` 격리된 개체가 많을 수 있습니다. 각 가속기에는 기본 `accelerator_view` 개체가 있습니다. 추가 `accelerator_view` 개체를 만들 수 있습니다.

물리적 장치는 많은 클라이언트 스레드 간에 공유할 수 있습니다. 클라이언트 스레드는 가속기의 `accelerator_view` 동일한 개체를 협조적으로 사용하거나 각 클라이언트가 다른 클라이언트 스레드에서 `accelerator_view` 격리하기 위해 독립적인 개체를 통해 계산 장치와 통신할 수 있습니다.

개체는 `accelerator_view` 두 queuing_mode [열거](concurrency-namespace-enums-amp.md#queuing_mode) 상태 중 하나를 가질 수 있습니다. 큐 모드가 `immediate`다음과 같은 경우 `copy` 명령은 `parallel_for_each` 호출자에게 반환되는 즉시 해당 가속기 장치로 전송됩니다. 큐잉 모드인 `deferred`경우 이러한 명령은 `accelerator_view` 개체에 해당하는 명령 큐에 큐에 대기됩니다. 명령이 호출될 때까지 `flush()` 실제로 장치에 전송되지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** 앰프.h

**네임스페이스:** 동시성

## <a name="accelerator"></a><a name="accelerator"></a>가속기

accelerator_view 개체에 대한 가속기 개체를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>accelerator_view

기존 `accelerator_view` 개체를 복사하여 accelerator_view 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
복사할 `accelerator_view` 개체입니다.

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

미래를 반환하여 이 `accelerator_view` 개체에 지금까지 제출된 모든 명령의 완료를 추적합니다.

### <a name="syntax"></a>구문

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Return Value

이 `accelerator_view` 개체에 지금까지 제출된 모든 명령의 완료를 추적하는 미래입니다.

## <a name="flush"></a>flush

accelerator_view 개체의 큐에 대기 중인 모든 보류 중인 명령은 실행을 위한 엑셀러레이터에 전송합니다.

### <a name="syntax"></a>구문

```cpp
void flush();
```

### <a name="return-value"></a>Return Value

`void`를 반환합니다.

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

accelerator_view 개체에 대한 가속기 개체를 반환합니다.

### <a name="syntax"></a>구문

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Return Value

accelerator_view 개체의 가속기 개체입니다.

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)전달될 때 런타임이 자동으로 적절한 가속기를 선택할지 여부를 나타내는 부울 값을 반환합니다.

### <a name="syntax"></a>구문

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Return Value

런타임이 자동으로 적절한 가속기를 선택하는 경우 **true;** 그렇지 **않으면, 거짓**.

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

accelerator_view 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값을 반환합니다.

### <a name="syntax"></a>구문

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Return Value

`accelerator_view` 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값입니다.

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

accelerator_view 개체의 큐 모드를 반환합니다.

### <a name="syntax"></a>구문

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Return Value

`accelerator_view` 개체의 큐 모드입니다.

## <a name="get_version"></a><a name="get_version"></a>get_version

accelerator_view의 버전을 반환합니다.

### <a name="syntax"></a>구문

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Return Value

`accelerator_view`의 버전입니다.

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)전달될 때 런타임이 자동으로 적절한 가속기를 선택할지 여부를 나타내는 부울 값을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

accelerator_view 개체에 확장 오류 보고를 위해 DEBUG 레이어가 활성화되었는지 여부를 나타내는 부울 값을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>연산자!=

이 accelerator_view 개체를 다른 개체와 비교하고 동일한 경우 **false를** 반환합니다. 그렇지 않으면 **true를 반환합니다.**

### <a name="syntax"></a>구문

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>Return Value

두 개체가 동일한 경우 **false입니다.** 그렇지 않으면 **true**.

## <a name="operator"></a><a name="operator_eq"></a>연산자 =

지정된 accelerator_view 개체의 내용을 이 개체에 복사합니다.

### <a name="syntax"></a>구문

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
복사할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>Return Value

수정된 `accelerator_view` 개체에 대한 참조입니다.

## <a name="operator"></a><a name="operator_eq_eq"></a>연산자==

이 accelerator_view 개체를 다른 개체와 비교하고 동일한 경우 **true를** 반환합니다. 그렇지 않으면 **false**를 반환합니다.

### <a name="syntax"></a>구문

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>매개 변수

*다른*<br/>
이것과 비교할 `accelerator_view` 개체입니다.

### <a name="return-value"></a>Return Value

두 개체가 동일한 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

accelerator_view 개체에 대한 큐 모드를 가져옵니다.

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>버전

accelerator_view의 버전을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

accelerator_view 개체에 제출된 모든 명령이 완료될 때까지 기다립니다.

### <a name="syntax"></a>구문

```cpp
void wait();
```

### <a name="return-value"></a>Return Value

`void`를 반환합니다.

### <a name="remarks"></a>설명

[queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) 경우 `immediate`이 메서드는 차단 하지 않고 즉시 반환 됩니다.

## <a name="accelerator_view"></a><a name="dtor"></a>~accelerator_view

accelerator_view 개체를 삭제합니다.

### <a name="syntax"></a>구문

```cpp
~accelerator_view();
```

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
