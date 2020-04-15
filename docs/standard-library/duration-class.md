---
title: duration 클래스
ms.date: 03/27/2016
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
helpviewer_keywords:
- std::chrono [C++], duration
ms.openlocfilehash: 3669935bf094f476ca24a8170a0388dff29e0a0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368760"
---
# <a name="duration-class"></a>duration 클래스

두 시점 사이에 경과된 시간을 나타내는 *시간 간격*을 포함하는 형식을 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>설명

템플릿 인수 `Rep`는 간격에 클록 틱 수를 포함하는 데 사용되는 형식을 설명합니다. 템플릿 인수 `Period`는 각 틱이 나타내는 간격 크기를 설명하는 [ratio](../standard-library/ratio.md)의 인스턴스화입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|duration::period Typedef|템플릿 매개 변수 `Period`의 동의어를 나타냅니다.|
|duration::rep Typedef|템플릿 매개 변수 `Rep`의 동의어를 나타냅니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[기간](#duration)|`duration` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[count](#count)|시간 간격의 클록 틱 수를 반환합니다.|
|[최대](#max)|정적. 템플릿 매개 변수 `Ref`의 최대 허용 값을 반환합니다.|
|[분](#min)|정적. 템플릿 매개 변수 `Ref`의 최저 허용 값을 반환합니다.|
|[0](#zero)|정적. 실제로 `Rep`(0)를 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[지속 시간::연산자-](#operator-)|`duration` 개체의 복사본을 부정 틱 개수와 함께 반환합니다.|
|[지속 시간::연산자-](#operator--)|저장된 틱 개수를 줄입니다.|
|[지속 시간::연산자=](#op_eq)|저장된 틱 개수 모듈로를 지정된 값으로 줄입니다.|
|[duration::operator*=](#op_star_eq)|저장된 틱 개수에 지정된 값을 곱합니다.|
|[지속 시간::연산자/=](#op_div_eq)|저장된 틱 개수를 지정된 `duration` 개체의 틱 개수로 나눕니다.|
|[지속 시간::연산자+](#op_add)|`*this`를 반환합니다.|
|[지속 시간:::연산자++](#op_add_add)|저장된 틱 개수를 늘립니다.|
|[지속 시간::연산자+=](#op_add_eq)|지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에 더합니다.|
|[지속 시간::연산자-=](#operator-_eq)|지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에서 뺍니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<크로노>

**네임스페이스:** std::chrono

## <a name="durationcount"></a><a name="count"></a>지속 시간::개수

시간 간격의 클록 틱 수를 검색합니다.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Return Value

시간 간격의 클록 틱 수입니다.

## <a name="durationduration-constructor"></a><a name="duration"></a>지속 시간::d 생성자

`duration` 개체를 생성합니다.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>매개 변수

*담당자 2*\
틱 수를 나타내는 산술 형식입니다.

*기간 2*\
틱 기간(초)을 나타내는 `std::ratio` 템플릿 특수화입니다.

*R*\
기본 기간의 틱 수입니다.

*Dur*\
*Period2에*의해 지정된 기간의 틱 수입니다.

### <a name="remarks"></a>설명

기본 생성자는 초기화되지 않은 개체를 생성합니다. 빈 중괄호를 사용한 값 초기화는 0 클록 틱의 시간 간격을 나타내는 개체를 초기화합니다.

두 번째 템플릿 인수 생성자는 기본 기간인 *R* 클럭 틱의 시간 간격을 `std::ratio<1>`나타내는 개체를 생성합니다. 틱 카운트의 반올림을 방지하려면 부동 점 유형으로 처리 할 수없는 경우 `duration::rep` 부동 점 유형으로 처리 할 수있는 표현 유형 *Rep2에서* duration 개체를 생성하는 오류입니다.

세 번째, 두 개의 템플릿 인수 생성자는 *Dur에*의해 지정된 시간 간격인 시간 간격을 나타내는 개체를 생성합니다. 틱 개수 잘림을 방지하려는 경우, 대상 형식과 *전혀 다른* 형식을 가진 다른 기간 개체에서 기간 개체를 생성하는 것은 오류입니다.

`D2`를 부동 소수점 형식으로 처리할 수 없으며 [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md)이 1이 아닌 경우 기간 형식 `D1`은 또 다른 기간 형식 `D2`와 *전혀 다른* 형식입니다.

*Rep2가* 암시적으로 변환할 `rep` 수 `treat_as_floating_point<rep>`있고 `treat_as_floating_point<Rep2>` *true를 보유하거나* *false를 보유하지*않는 한 두 번째 생성자는 오버로드 해결에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

오버플로가 변환에서 유도되고 `treat_as_floating_point<rep>`*가 true를 포함*하거나, `ratio_divide<Period2, period>::den`가 1과 같고 `treat_as_floating_point<Rep2>`*가 false를 포함*할 경우 세 번째 생성자는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

## <a name="durationmax"></a><a name="max"></a>지속 시간::최대

템플릿 매개 변수 형식 `Ref`의 값에 대한 상한을 반환하는 정적 메서드입니다.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Return Value

실제로 `duration(duration_values<rep>::max())`를 반환합니다.

## <a name="durationmin"></a><a name="min"></a>지속 시간::최소

템플릿 매개 변수 형식 `Ref`의 값에 대한 하한을 반환하는 정적 메서드입니다.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Return Value

실제로 `duration(duration_values<rep>::min())`를 반환합니다.

## <a name="durationoperator-"></a><a name="operator-"></a>지속 시간::연산자-

`duration` 개체의 복사본을 부정 틱 개수와 함께 반환합니다.

```cpp
constexpr duration operator-() const;
```

## <a name="durationoperator--"></a><a name="operator--"></a>지속 시간::연산자-

저장된 틱 개수를 줄입니다.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Return Value

첫 번째 메서드는 `*this`를 반환합니다.

두 번째 메서드는 감소 전에 만들어진 `*this`의 복사본을 반환합니다.

## <a name="durationoperator"></a><a name="op_eq"></a>지속 시간::연산자=

저장된 틱 개수 모듈로를 지정된 값으로 줄입니다.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>매개 변수

*Div*\
첫 번째 방법의 경우 *Div는* 눈금 수를 나타냅니다. 두 번째 방법의 경우 `duration` *Div는* 눈금 수를 포함하는 개체입니다.

### <a name="return-value"></a>Return Value

모듈로 연산이 수행된 후의 `duration` 개체입니다.

## <a name="durationoperator"></a><a name="op_star_eq"></a>지속 시간::연산자*=

저장된 틱 개수에 지정된 값을 곱합니다.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>매개 변수

*복수*\
`duration::rep`로 지정된 형식의 값입니다.

### <a name="return-value"></a>Return Value

곱하기가 수행된 후의 `duration` 개체입니다.

## <a name="durationoperator"></a><a name="op_div_eq"></a>지속 시간::연산자/=

저장된 틱 개수를 지정된 값으로 나눕니다.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>매개 변수

*Div*\
`duration::rep`로 지정된 형식의 값입니다.

### <a name="return-value"></a>Return Value

나누기가 수행된 후의 `duration` 개체입니다.

## <a name="durationoperator"></a><a name="op_add"></a>지속 시간::연산자+

`*this`를 반환합니다.

```cpp
constexpr duration operator+() const;
```

## <a name="durationoperator"></a><a name="op_add_add"></a>지속 시간:::연산자++

저장된 틱 개수를 늘립니다.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Return Value

첫 번째 메서드는 `*this`를 반환합니다.

두 번째 메서드는 증가 전에 만들어진 `*this`의 복사본을 반환합니다.

## <a name="durationoperator"></a><a name="op_add_eq"></a>지속 시간::연산자+=

지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에 더합니다.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>매개 변수

*Dur*\
`duration` 개체입니다.

### <a name="return-value"></a>Return Value

더하기가 수행된 후의 `duration` 개체입니다.

## <a name="durationoperator-"></a><a name="operator-_eq"></a>지속 시간::연산자-=

지정된 `duration` 개체의 틱 개수를 저장된 틱 개수에서 뺍니다.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>매개 변수

*Dur*\
`duration` 개체입니다.

### <a name="return-value"></a>Return Value

빼기가 수행된 후의 `duration` 개체입니다.

## <a name="durationzero"></a><a name="zero"></a>지속 시간::0

`duration(duration_values<rep>::zero())`를 반환합니다.

```cpp
static constexpr duration zero();
```

## <a name="durationoperator-mod"></a><a name="op_mod_eq"></a>지속 시간::연산자 모드 =

저장된 틱 수 모듈로 Div 또는 Div.count()를 줄입니다.

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>매개 변수

*Div*\
기간 개체 또는 틱 수를 나타내는 값인 제수입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 저장된 틱 수 모듈로 Div를 줄이고 *this를 반환합니다. 두 번째 멤버 함수는 저장된 틱 수 모듈로 Div.count()를 줄이고 \*this를 반환합니다.

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[\<크로노>](../standard-library/chrono.md)\
[duration_values 구조체](../standard-library/duration-values-structure.md)
