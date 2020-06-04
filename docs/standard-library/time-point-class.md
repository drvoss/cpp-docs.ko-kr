---
title: time_point 클래스
ms.date: 03/27/2019
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
helpviewer_keywords:
- std::chrono [C++], time_point
ms.openlocfilehash: e1de674d4a13ba465100923bffe6cba76e61ab4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368026"
---
# <a name="time_point-class"></a>time_point 클래스

`time_point`는 시점을 나타내는 형식을 설명합니다. 이 클래스는 템플릿 인수 `Clock`으로 표시되는 epoch 이후 경과된 시간을 저장하는 [duration](../standard-library/duration-class.md) 형식의 개체를 포함합니다.

## <a name="syntax"></a>구문

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|`time_point::clock`|템플릿 매개 변수 `Clock`과 동일한 의미입니다.|
|`time_point::duration`|템플릿 매개 변수 `Duration`과 동일한 의미입니다.|
|`time_point::period`|중첩된 형식 이름 `duration::period`와 동일한 의미입니다.|
|`time_point::rep`|중첩된 형식 이름 `duration::rep`와 동일한 의미입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[time_point](#time_point)|`time_point` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[최대](#max)|`time_point::ref`의 상한을 지정합니다.|
|[분](#min)|`time_point::ref`의 하한을 지정합니다.|
|[time_since_epoch](#time_since_epoch)|저장된 `duration` 값을 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[time_point::연산자+=](#op_add_eq)|저장된 기간에 지정된 값을 더합니다.|
|[time_point::operator-=](#operator-_eq)|저장된 기간에서 지정된 값을 뺍니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<크로노>

**네임스페이스:** std::chrono

## <a name="time_pointmax"></a><a name="max"></a>time_point:최대

형식 `time_point::ref`의 값에 대한 상한을 반환하는 정적 메서드입니다.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Return Value

실제로 `time_point(duration::max())`를 반환합니다.

## <a name="time_pointmin"></a><a name="min"></a>time_point:분

`time_point::ref` 형식의 값에 대한 하한값을 반환하는 정적 메서드입니다.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Return Value

실제로 `time_point(duration::min())`를 반환합니다.

## <a name="time_pointoperator"></a><a name="op_add_eq"></a>time_point::연산자+=

저장된 [duration](../standard-library/duration-class.md) 값에 지정된 값을 더합니다.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>매개 변수

*Dur*\
`duration` 개체입니다.

### <a name="return-value"></a>Return Value

더하기가 수행된 후의 `time_point` 개체입니다.

## <a name="time_pointoperator-"></a><a name="operator-_eq"></a>time_point::연산자-=

저장된 [duration](../standard-library/duration-class.md) 값에서 지정된 값을 뺍니다.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>매개 변수

*Dur*\
`duration` 개체입니다.

### <a name="return-value"></a>Return Value

빼기가 수행된 후의 `time_point` 개체입니다.

## <a name="time_pointtime_point-constructor"></a><a name="time_point"></a>time_point::time_point 생성자

`time_point` 개체를 생성합니다.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>매개 변수

*Dur*\
[duration](../standard-library/duration-class.md) 개체입니다.

*Tp*\
`time_point` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 저장된 `duration` 값이 [duration::zero](../standard-library/duration-class.md#zero)와 같은 개체를 생성합니다.

두 번째 생성자는 저장된 기간 값이 *Dur와*같은 개체를 생성합니다. true가 아닌 경우 `is_convertible<Duration2, duration>` 두 번째 생성자는 오버로드 해결에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

세 번째 생성자는 `Tp.time_since_epoch()`를 사용하여 `duration` 값을 초기화합니다.

## <a name="time_pointtime_since_epoch"></a><a name="time_since_epoch"></a>time_point:time_since_epoch

저장된 [duration](../standard-library/duration-class.md) 값을 검색합니다.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<크로노>](../standard-library/chrono.md)
