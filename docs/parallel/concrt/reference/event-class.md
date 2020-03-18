---
title: event 클래스
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 3d645cc09c61402059e9a86679c10ee703ee8031
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443731"
---
# <a name="event-class"></a>event 클래스

동시성 런타임을 명시적으로 인식하는 수동 다시 설정 이벤트입니다.

## <a name="syntax"></a>구문

```cpp
class event;
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[~ 이벤트 소멸자](#dtor)|이벤트를 소멸 시킵니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[reset](#reset)|이벤트를 신호를 받지 않는 상태로 다시 설정 합니다.|
|[set](#set)|이벤트에 신호를 보냅니다.|
|[대기한](#wait)|이벤트가 신호를 받을 때까지 기다립니다.|
|[wait_for_multiple](#wait_for_multiple)|여러 이벤트가 신호를 받을 때까지 대기 합니다.|

### <a name="public-constants"></a>공용 상수

|속성|Description|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|대기 시간이 초과되지 않아야 함을 나타내는 값입니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`event`

## <a name="requirements"></a>요구 사항

**헤더:** concrt .h

**네임스페이스:** 동시성

## <a name="ctor"></a>이벤트

새 이벤트를 생성 합니다.

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>설명

## <a name="dtor"></a>~ 이벤트

이벤트를 소멸 시킵니다.

```cpp
~event();
```

### <a name="remarks"></a>설명

소멸자가 실행 될 때 이벤트를 대기 하는 스레드가 없는 것으로 예상 됩니다. 이벤트가 해당 이벤트를 계속 대기 중인 스레드와 함께 소멸할 수 있도록 허용하면 정의되지 않은 동작이 발생합니다.

## <a name="reset"></a>다시 설정

이벤트를 신호를 받지 않는 상태로 다시 설정 합니다.

```cpp
void reset();
```

## <a name="set"></a>설정

이벤트에 신호를 보냅니다.

```cpp
void set();
```

### <a name="remarks"></a>설명

이벤트에 신호를 보내면 이벤트를 대기하고 있는 임의 수의 컨텍스트가 실행 가능하게 됩니다.

## <a name="timeout_infinite"></a>timeout_infinite

대기 시간이 초과되지 않아야 함을 나타내는 값입니다.

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a>대기한

이벤트가 신호를 받을 때까지 기다립니다.

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_Timeout*<br/>
대기 시간이 초과 되기 전 까지의 시간 (밀리초)을 나타냅니다. 값 `COOPERATIVE_TIMEOUT_INFINITE`는 시간 제한이 없음을 나타냅니다.

### <a name="return-value"></a>Return Value

대기가 충족 되는 경우 `0` 값이 반환 됩니다. 그렇지 않은 경우 값은 이벤트가 신호를 받지 않고 대기 시간이 초과 되었음을 나타내는 `COOPERATIVE_WAIT_TIMEOUT` 합니다.

> [!IMPORTANT]
> UWP (유니버설 Windows 플랫폼) 앱에서이 호출이 현재 스레드를 차단 하 고 앱이 응답 하지 않을 수 있으므로 ASTA 스레드에서 `wait`를 호출 하지 마세요.

## <a name="wait_for_multiple"></a>wait_for_multiple

여러 이벤트가 신호를 받을 때까지 대기 합니다.

```cpp
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_PPEvents*<br/>
대기할 이벤트의 배열입니다. 배열 내의 이벤트 수는 `count` 매개 변수로 표시 됩니다.

*count*<br/>
`_PPEvents` 매개 변수에 제공 된 배열 내의 이벤트 수입니다.

*_FWaitAll*<br/>
값을 **true**로 설정 하면 매개 변수는 대기를 충족 하기 위해 `_PPEvents` 매개 변수에 제공 된 배열 내의 모든 이벤트가 신호를 받도록 지정 합니다. **False**값으로 설정 된 경우 `_PPEvents` 매개 변수에 제공 된 배열 내에서 신호를 전달 하는 모든 이벤트가 대기를 충족 하도록 지정 합니다.

*_Timeout*<br/>
대기 시간이 초과 되기 전 까지의 시간 (밀리초)을 나타냅니다. 값 `COOPERATIVE_TIMEOUT_INFINITE`는 시간 제한이 없음을 나타냅니다.

### <a name="return-value"></a>Return Value

대기가 충족 된 경우 대기 조건을 충족 하는 `_PPEvents` 매개 변수에 제공 된 배열 내의 인덱스입니다. 그렇지 않으면 값은 충족 되는 조건을 제외 하 고 대기 시간이 초과 되었음을 나타내는 `COOPERATIVE_WAIT_TIMEOUT` 합니다.

### <a name="remarks"></a>설명

`_FWaitAll` 매개 변수를 `true` 값으로 설정 하 여 대기를 충족 하기 위해 모든 이벤트가 신호를 받을 수 있어야 함을 나타내려면 함수에서 반환 되는 인덱스는 `COOPERATIVE_WAIT_TIMEOUT`값이 아니라 특별 한 의미가 없습니다.

> [!IMPORTANT]
> UWP (유니버설 Windows 플랫폼) 앱에서이 호출이 현재 스레드를 차단 하 고 앱이 응답 하지 않을 수 있으므로 ASTA 스레드에서 `wait_for_multiple`를 호출 하지 마세요.

## <a name="see-also"></a>참고 항목

[concurrency 네임스페이스](concurrency-namespace.md)
