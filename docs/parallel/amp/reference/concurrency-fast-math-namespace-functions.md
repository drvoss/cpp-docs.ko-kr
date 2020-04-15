---
title: Concurrency::fast_math 네임스페이스 함수
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
ms.openlocfilehash: cd0882b072cfe26cd83e63024ae6837dc962ebf9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376404"
---
# <a name="concurrencyfast_math-namespace-functions"></a>Concurrency::fast_math 네임스페이스 함수

||||
|-|-|-|
|[Acos](#acos)|[acosf](#acosf)|[Asin](#asin)|
|[asinf](#asinf)|[Atan](#atan)|[atan2](#atan2)|
|[atan2f](#atan2f)|[atanf](#atanf)|[Ceil](#ceil)|
|[ceilf](#ceilf)|[Cos](#cos)|[cosf](#cosf)|
|[cosh](#cosh)|[coshf](#coshf)|[특급](#exp)|
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|
|[fabs](#fabs)|[fabsf](#fabsf)|[바닥](#floor)|
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|
|[fmin](#fmin)|[fminf](#fminf)|[Fmod](#fmod)|
|[fmodf](#fmodf)|[frexp](#frexp)|[프렉스프 ()프렉스프 (](#frexpf)|
|[이스피니트](#isfinite)|[이신프](#isinf)|[이산 (isnan)](#isnan)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[로그](#log)|
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[pow](#pow)|[powf](#powf)|
|[라운드](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[사인비트프](#signbitf)|
|[죄](#sin)|[신코스](#sincos)|[신코스프](#sincosf)|
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|
|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|[탄](#tan)|
|[tanf](#tanf)|[Tanh](#tanh)|[tanhf](#tanhf)|
|[트렁크는](#trunc)|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>Acos

인수의 아크코신계산

```cpp
inline float acos(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크코사인 값을 반환합니다.

## <a name="acosf"></a><a name="acosf"></a>아코스프 ()에이코스프

인수의 아크코신계산

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크코사인 값을 반환합니다.

## <a name="asin"></a><a name="asin"></a>Asin

인수의 호신을 계산합니다.

```cpp
inline float asin(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크사인 값을 반환합니다.

## <a name="asinf"></a><a name="asinf"></a>아신프

인수의 호신을 계산합니다.

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크사인 값을 반환합니다.

## <a name="atan"></a><a name="atan"></a>Atan

인수의 아크탄젠트를 계산합니다.

```cpp
inline float atan(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크탄젠트 값을 반환합니다.

## <a name="atan2"></a><a name="atan2"></a>아탄2

_Y/_X 아크탠젠트를 계산합니다.

```cpp
inline float atan2(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_y*<br/>
부동 소수점 값

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_Y/_X의 아크탄젠트 값을 반환합니다.

## <a name="atan2f"></a><a name="atan2f"></a>아탄2f

_Y/_X 아크탠젠트를 계산합니다.

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_y*<br/>
부동 소수점 값

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_Y/_X의 아크탄젠트 값을 반환합니다.

## <a name="atanf"></a><a name="atanf"></a>아탄프 (동안)

인수의 아크탄젠트를 계산합니다.

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 아크탄젠트 값을 반환합니다.

## <a name="ceil"></a><a name="ceil"></a>Ceil

인수의 천장을 계산합니다.

```cpp
inline float ceil(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 한계를 반환합니다.

## <a name="ceilf"></a><a name="ceilf"></a>실프 (것)에 프실프 (것

인수의 천장을 계산합니다.

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 한계를 반환합니다.

## <a name="cosf"></a><a name="cosf"></a>코스프 ()코스프

인수의 코사인을 계산합니다.

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 코사인 값을 반환합니다.

## <a name="coshf"></a><a name="coshf"></a>코스프 ()에프 ()에프 (

인수의 쌍곡선 코신 값을 계산합니다.

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 코사인 값을 반환합니다.

## <a name="cos"></a><a name="cos"></a>Cos

인수의 코사인을 계산합니다.

```cpp
inline float cos(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 코사인 값을 반환합니다.

## <a name="cosh"></a><a name="cosh"></a>코시 (주)

인수의 쌍곡선 코신 값을 계산합니다.

```cpp
inline float cosh(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 코사인 값을 반환합니다.

## <a name="exp"></a><a name="exp"></a>특급

인수의 기본 e 지수를 계산합니다.

```cpp
inline float exp(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 e인 지수 값을 반환합니다.

## <a name="exp2"></a><a name="exp2"></a>exp2

인수의 기본 2 지수를 계산합니다.

```cpp
inline float exp2(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 2인 지수 값을 반환합니다.

## <a name="exp2f"></a><a name="exp2f"></a>exp2f

인수의 기본 2 지수를 계산합니다.

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 2인 지수 값을 반환합니다.

## <a name="expf"></a><a name="expf"></a>expf

인수의 기본 e 지수를 계산합니다.

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 e인 지수 값을 반환합니다.

## <a name="fabs"></a><a name="fabs"></a>팹

인수의 절대 값을 반환합니다.

```cpp
inline float fabs(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
정수 값

### <a name="return-value"></a>Return Value

인수의 절대 값을 반환합니다.

## <a name="fabsf"></a><a name="fabsf"></a>팹스프 (것)

인수의 절대 값을 반환합니다.

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 절대 값을 반환합니다.

## <a name="floor"></a><a name="floor"></a>바닥

인수의 바닥을 계산합니다.

```cpp
inline float floor(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑을 반환합니다.

## <a name="floorf"></a><a name="floorf"></a>플로어프

인수의 바닥을 계산합니다.

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑을 반환합니다.

## <a name="fmax"></a><a name="fmax"></a>fmax

인수의 최대 숫자 값 결정

```cpp
inline float max(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
정수 값

*_y*<br/>
정수 값

### <a name="return-value"></a>Return Value

인수의 최대 숫자 값을 반환합니다.

## <a name="fmaxf"></a><a name="fmaxf"></a>fmaxf

인수의 최대 숫자 값 결정

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 최대 숫자 값을 반환합니다.

## <a name="fmin"></a><a name="fmin"></a>fmin

인수의 최소 숫자 값 결정

```cpp
inline float min(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
정수 값

*_y*<br/>
정수 값

### <a name="return-value"></a>Return Value

인수의 최소 숫자 값을 반환합니다.

## <a name="fminf"></a><a name="fminf"></a>fminf

인수의 최소 숫자 값 결정

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 최소 숫자 값을 반환합니다.

## <a name="fmod"></a><a name="fmod"></a>Fmod

_X/_Y 부동점 나머지 를 계산합니다.

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X/_Y의 부동 소수점 나머지를 반환합니다.

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

_X/_Y의 부동 소수점 나머지를 계산합니다.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X/_Y의 부동 소수점 나머지를 반환합니다.

## <a name="frexp"></a><a name="frexp"></a>frexp

_X 의 사마증과 지수를 가져옵니다

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Exp*<br/>
부동 소수점 값의 _X의 정수 지수를 반환합니다.

### <a name="return-value"></a>Return Value

_X의 가수를 반환합니다.

## <a name="frexpf"></a><a name="frexpf"></a>프렉스프 ()프렉스프 (

_X 의 사마증과 지수를 가져옵니다

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Exp*<br/>
부동 소수점 값의 _X의 정수 지수를 반환합니다.

### <a name="return-value"></a>Return Value

_X의 가수를 반환합니다.

## <a name="isfinite"></a><a name="isfinite"></a>이스피니트

인수에 유한 값이 있는지 여부를 결정합니다.

```cpp
inline int isfinite(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수가 유한인 값인 경우에만 0이 아닌 값을 반환합니다.

## <a name="isinf"></a><a name="isinf"></a>이신프

인수가 무한대인지 여부를 결정합니다.

```cpp
inline int isinf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수가 무한대 값인 경우에 0이 아닌 값을 반환합니다.

## <a name="isnan"></a><a name="isnan"></a>이산 (isnan)

인수가 NaN인지 여부를 결정합니다.

```cpp
inline int isnan(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수가 NaN 값을 갖는 경우에만 0이 아닌 값을 반환합니다.

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

가사 및 지수에서 실제 숫자를 계산합니다.

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값, 가수

*_Exp*<br/>
정수 지수

### <a name="return-value"></a>Return Value

_X \* 2^_Exp 반환

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

가사 및 지수에서 실제 숫자를 계산합니다.

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값, 가수

*_Exp*<br/>
정수 지수

### <a name="return-value"></a>Return Value

_X \* 2^_Exp 반환

## <a name="log"></a><a name="log"></a>로그

인수의 기본 e 로그릿헴을 계산합니다.

```cpp
inline float log(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 e인 로그 값을 반환합니다.

## <a name="log10"></a><a name="log10"></a>log10

인수의 기본 10 로그릿헴을 계산합니다.

```cpp
inline float log10(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 10인 로그 값을 반환합니다.

## <a name="log10f"></a><a name="log10f"></a>log10f

인수의 기본 10 로그릿헴을 계산합니다.

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 10인 로그 값을 반환합니다.

## <a name="log2"></a><a name="log2"></a>log2

인수의 기본 2 로그릿헴을 계산합니다.

```cpp
inline float log2(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 기본 2 로그림을 반환합니다.

## <a name="log2f"></a><a name="log2f"></a>log2f

인수의 기본 2 로그릿헴을 계산합니다.

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 10인 로그 값을 반환합니다.

## <a name="logf"></a><a name="logf"></a>로그 (것)로

인수의 기본 e 로그릿헴을 계산합니다.

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 e인 로그 값을 반환합니다.

## <a name="modf"></a><a name="modf"></a>모드

_X 소수 및 정수 부분으로 분할합니다.

```cpp
inline float modf(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Ip*<br/>
값의 정수 부분을 받습니다.

### <a name="return-value"></a>Return Value

_X의 부호 있는 소수 부분을 반환합니다.

## <a name="modff"></a><a name="modff"></a>모드 프

_X 소수 및 정수 부분으로 분할합니다.

```cpp
inline float modff(
    float _X,
    float* _Ip) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Ip*<br/>
값의 정수 부분을 받습니다.

### <a name="return-value"></a>Return Value

_X의 부호 있는 소수 부분을 반환합니다.

## <a name="pow"></a><a name="pow"></a>포로

_Y 힘으로 제기 _X 계산

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값, 밑

*_y*<br/>
부동 소수점 값, 지수

### <a name="return-value"></a>Return Value

_Y 힘으로 제기된 _X 값을 반환합니다.

## <a name="powf"></a><a name="powf"></a>포프 ()와 포프 (것)

_Y 힘으로 제기 _X 계산

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값, 밑

*_y*<br/>
부동 소수점 값, 지수

### <a name="return-value"></a>Return Value

## <a name="round"></a><a name="round"></a>라운드

가장 가까운 정수로 _X

```cpp
inline float round(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 가장 가까운 정수를 반환합니다.

## <a name="roundf"></a><a name="roundf"></a>라운드프

가장 가까운 정수로 _X

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 가장 가까운 정수를 반환합니다.

## <a name="rsqrt"></a><a name="rsqrt"></a>rsqrt

인수의 제곱근의 호수를 반환합니다.

```cpp
inline float rsqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 제곱근의 호수를 반환합니다.

## <a name="rsqrtf"></a><a name="rsqrtf"></a>rsqrtf

인수의 제곱근의 호수를 반환합니다.

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 제곱근의 호수를 반환합니다.

## <a name="signbit"></a><a name="signbit"></a>사인 비트

_X의 부호가 음수인지 결정합니다.

```cpp
inline int signbit(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 부호가 음수인 경우에만 0이 아닌 값을 반환합니다.

## <a name="signbitf"></a><a name="signbitf"></a>사인비트프

_X의 부호가 음수인지 결정합니다.

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 부호가 음수인 경우에만 0이 아닌 값을 반환합니다.

## <a name="sin"></a><a name="sin"></a>죄

인수의 사이가지 값을 계산합니다.

```cpp
inline float sin(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 사인 값을 반환합니다.

## <a name="sinf"></a><a name="sinf"></a>죄프

인수의 사이가지 값을 계산합니다.

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 사인 값을 반환합니다.

## <a name="sincos"></a><a name="sincos"></a>신코스

_X 의 사네 값과 코사네 값을 계산합니다.

```cpp
inline void sincos(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_s*<br/>
_X의 사인 값을 반환합니다.

*_C*<br/>
_X의 코사인 값을 반환합니다.

## <a name="sincosf"></a><a name="sincosf"></a>신코스프

_X 의 사네 값과 코사네 값을 계산합니다.

```cpp
inline void sincosf(
    float _X,
    float* _S,
    float* _C) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_s*<br/>
_X의 사인 값을 반환합니다.

*_C*<br/>
_X의 코사인 값을 반환합니다.

## <a name="sinh"></a><a name="sinh"></a>Sinh

인수의 쌍곡선 사절 값을 계산합니다.

```cpp
inline float sinh(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 사인 값을 반환합니다.

## <a name="sinhf"></a><a name="sinhf"></a>신프 ()와 같은

인수의 쌍곡선 사절 값을 계산합니다.

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 사인 값을 반환합니다.

## <a name="sqrt"></a><a name="sqrt"></a>Sqrt

인수의 제곱근을 계산합니다.

```cpp
inline float sqrt(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 제곱근을 반환합니다.

## <a name="sqrtf"></a><a name="sqrtf"></a>sqrtf

인수의 제곱근을 계산합니다.

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 제곱근을 반환합니다.

## <a name="tan"></a><a name="tan"></a>탄

인수의 접선 값을 계산합니다.

```cpp
inline float tan(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 탄젠트 값을 반환합니다.

## <a name="tanf"></a><a name="tanf"></a>탄프 (것)와 함께

인수의 접선 값을 계산합니다.

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 탄젠트 값을 반환합니다.

## <a name="tanh"></a><a name="tanh"></a>Tanh

인수의 쌍탄값 계산

```cpp
inline float tanh(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 탄젠트 값을 반환합니다.

## <a name="tanhf"></a><a name="tanhf"></a>탄프 ()탄프 (것

인수의 쌍탄값 계산

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 탄젠트 값을 반환합니다.

## <a name="trunc"></a><a name="trunc"></a>트렁크는

인수를 정수 구성 요소로 연결합니다.

```cpp
inline float trunc(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 정수 구성 요소를 반환합니다.

## <a name="truncf"></a><a name="truncf"></a>트렁그어

인수를 정수 구성 요소로 연결합니다.

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 정수 구성 요소를 반환합니다.

## <a name="requirements"></a>요구 사항

**헤더:** amp_math.h **네임스페이스:** 동시성:fast_math

## <a name="see-also"></a>참고 항목

[Concurrency::fast_math 네임스페이스](concurrency-fast-math-namespace.md)
