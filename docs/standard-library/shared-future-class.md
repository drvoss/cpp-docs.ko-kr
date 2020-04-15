---
title: shared_future 클래스
ms.date: 11/04/2016
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.openlocfilehash: 65ea01a9ced1ca69cd1b1526e7594c4b54387553
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336776"
---
# <a name="shared_future-class"></a>shared_future 클래스

*비동기 반환 개체에*대해 설명합니다. [future](../standard-library/future-class.md) 개체와는 달리 `shared_future` 개체의 경우 원하는 수만큼 *비동기 공급자*에 연결할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>설명

*비어 있는*`shared_future` 개체에 대해서는 `valid`, `operator=` 및 소멸자 이외의 메서드는 호출하지 마세요.

`shared_future` 개체는 동기화되지 않습니다. 여러 스레드에서 같은 개체에 대해 메서드를 호출하면 결과를 예측할 수 없는 데이터 경쟁이 발생합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[shared_future](#shared_future)|`shared_future` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[get](#get)|*연결된 비동기 상태*에 저장된 결과를 검색합니다.|
|[유효한](#valid)|개체가 비어 있지 않은지 여부를 지정합니다.|
|[기다릴](#wait)|연결된 비동기 상태가 ready로 설정될 때까지 현재 스레드를 차단합니다.|
|[wait_for](#wait_for)|연결된 비동기 상태가 준비로 설정되거나 지정된 시간이 경과할 때까지 차단합니다.|
|[wait_until](#wait_until)|연결된 비동기 상태가 준비로 설정되거나 지정된 시점이 될 때까지 차단합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[shared_future::operator=](#op_eq)|새 연결된 비동기 상태를 할당합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<미래의>

**네임스페이스:** std

## <a name="shared_futureget"></a><a name="get"></a>shared_future::get

*연결된 비동기 상태*에 저장된 결과를 검색합니다.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>설명

결과가 예외이면 메서드는 예외를 다시 throw합니다. 그렇지 않으면 결과가 반환됩니다.

이 메서드는 결과를 검색하기 전에 연결된 비동기 상태가 준비로 설정될 때까지 현재 스레드를 차단합니다.

부분 전문화 `shared_future<Ty&>`에 대 한 저장 된 값은 효과적으로 반환 값으로 *비동기 공급자에* 전달 된 개체에 대 한 참조입니다.

전문화 특성에 `shared_future<void>`대해 저장된 값이 없기 때문에 메서드는 **void를**반환합니다.

## <a name="shared_futureoperator"></a><a name="op_eq"></a>shared_future::연산자=

지정된 개체에서 *연결된 비동기 상태를* 전송합니다.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`shared_future` 개체입니다.

### <a name="return-value"></a>Return Value

`*this`

### <a name="remarks"></a>설명

첫 번째 연산자의 경우 *Right는* 더 이상 작업 후 연결된 비동기 상태가 없습니다.

두 번째 메서드의 경우 *Right는* 연결된 비동기 상태를 유지 관리합니다.

## <a name="shared_futureshared_future-constructor"></a><a name="shared_future"></a>shared_future::shared_future 생성자

`shared_future` 개체를 생성합니다.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
[future](../standard-library/future-class.md) 또는 `shared_future` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 `shared_future` *연결된 비동기 상태가*없는 개체를 생성합니다.

두 번째 및 세 번째 `shared_future` 생성자는 개체를 생성하고 연결된 비동기 상태를 *오른쪽에서*전송합니다. *Right에는* 더 이상 연결된 비동기 상태가 없습니다.

네 번째 생성자는 `shared_future` *Right와*동일한 연결된 비동기 상태를 가지는 개체를 생성합니다.

## <a name="shared_futurevalid"></a><a name="valid"></a>shared_future:::유효

개체에 *연결된 비동기 상태가*있는지 여부를 지정합니다.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Return Value

개체에 연결된 비동기 상태가 있는 경우 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="shared_futurewait"></a><a name="wait"></a>shared_future::대기

연결된 비동기 상태가 *준비될*때까지 현재 스레드를 *차단합니다.*

```cpp
void wait() const;
```

### <a name="remarks"></a>설명

연결된 비동기 상태는 해당 비동기 공급자가 반환 값을 저장했거나 예외를 저장한 경우에만 준비입니다.

## <a name="shared_futurewait_for"></a><a name="wait_for"></a>shared_future:wait_for

연결된 비동기 상태가 *ready*로 설정되거나 지정된 시간이 경과할 때까지 차단합니다.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>매개 변수

*Rel_time*\
스레드가 차단되는 최대 시간 간격을 지정하는 [chrono::duration](../standard-library/duration-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

반환 이유를 나타내는 [future_status](../standard-library/future-enums.md#future_status)입니다.

### <a name="remarks"></a>설명

연결된 비동기 상태는 해당 비동기 공급자가 반환 값을 저장했거나 예외를 저장한 경우에만 *준비*입니다.

## <a name="shared_futurewait_until"></a><a name="wait_until"></a>shared_future:wait_until

연결된 비동기 상태가 *준비*가 되거나 지정된 시점이 지날 때까지 현재 스레드를 차단합니다.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>매개 변수

*Abs_time*\
스레드 차단을 해제할 수 있는 시간을 지정하는 [chrono::time_point](../standard-library/time-point-class.md) 개체입니다.

### <a name="return-value"></a>Return Value

반환 이유를 나타내는 [future_status](../standard-library/future-enums.md#future_status)입니다.

### <a name="remarks"></a>설명

연결된 비동기 상태는 해당 비동기 공급자가 반환 값을 저장했거나 예외를 저장한 경우에만 준비입니다.

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<미래의>](../standard-library/future.md)
