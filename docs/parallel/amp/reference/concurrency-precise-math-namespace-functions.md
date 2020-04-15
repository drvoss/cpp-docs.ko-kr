---
title: Concurrency::precise_math 네임스페이스 함수
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::precise_math::acos
- amp_math/Concurrency::precise_math::acosh
- amp_math/Concurrency::precise_math::acoshf
- amp_math/Concurrency::precise_math::asinf
- amp_math/Concurrency::precise_math::asinh
- amp_math/Concurrency::precise_math::atan
- amp_math/Concurrency::precise_math::atan2
- amp_math/Concurrency::precise_math::atanf
- amp_math/Concurrency::precise_math::atanh
- amp_math/Concurrency::precise_math::cbrt
- amp_math/Concurrency::precise_math::cbrtf
- amp_math/Concurrency::precise_math::ceilf
- amp_math/Concurrency::precise_math::copysign
- amp_math/Concurrency::precise_math::cos
- amp_math/Concurrency::precise_math::cosf
- amp_math/Concurrency::precise_math::coshf
- amp_math/Concurrency::precise_math::cospi
- amp_math/Concurrency::precise_math::erf
- amp_math/Concurrency::precise_math::erfc
- amp_math/Concurrency::precise_math::erfcinv
- amp_math/Concurrency::precise_math::erfcinvf
- amp_math/Concurrency::precise_math::erfinv
- amp_math/Concurrency::precise_math::erfinvf
- amp_math/Concurrency::precise_math::exp10
- amp_math/Concurrency::precise_math::exp10f
- amp_math/Concurrency::precise_math::exp2f
- amp_math/Concurrency::precise_math::expf
- amp_math/Concurrency::precise_math::expm1f
- amp_math/Concurrency::precise_math::fabs
- amp_math/Concurrency::precise_math::floor
- amp_math/Concurrency::precise_math::fdim
- amp_math/Concurrency::precise_math::floorf
- amp_math/Concurrency::precise_math::fmaf
- amp_math/Concurrency::precise_math::fmaxf
- amp_math/Concurrency::precise_math::fmin
- amp_math/Concurrency::precise_math::fmod
- amp_math/Concurrency::precise_math::fmodf
- amp_math/Concurrency::precise_math::frexp
- amp_math/Concurrency::precise_math::frexpf
- amp_math/Concurrency::precise_math::hypotf
- amp_math/Concurrency::precise_math::ilogb
- amp_math/Concurrency::precise_math::isfinite
- amp_math/Concurrency::precise_math::isinf
- amp_math/Concurrency::precise_math::isnormal
- amp_math/Concurrency::precise_math::ldexp
- amp_math/Concurrency::precise_math::lgamma
- amp_math/Concurrency::precise_math::lgammaf
- amp_math/Concurrency::precise_math::log10
- amp_math/Concurrency::precise_math::log10f
- amp_math/Concurrency::precise_math::log1pf
- amp_math/Concurrency::precise_math::log2
- amp_math/Concurrency::precise_math::logb
- amp_math/Concurrency::precise_math::logbf
- amp_math/Concurrency::precise_math::modf
- amp_math/Concurrency::precise_math::modff
- amp_math/Concurrency::precise_math::nanf
- amp_math/Concurrency::precise_math::nearbyint
- amp_math/Concurrency::precise_math::nextafter
- amp_math/Concurrency::precise_math::nextafterf
- amp_math/Concurrency::precise_math::phif
- amp_math/Concurrency::precise_math::pow
- amp_math/Concurrency::precise_math::probit
- amp_math/Concurrency::precise_math::probitf
- amp_math/Concurrency::precise_math::rcbrtf
- amp_math/Concurrency::precise_math::remainder
- amp_math/Concurrency::precise_math::remquo
- amp_math/Concurrency::precise_math::remquof
- amp_math/Concurrency::precise_math::roundf
- amp_math/Concurrency::precise_math::rsqrt
- amp_math/Concurrency::precise_math::scalb
- amp_math/Concurrency::precise_math::scalbf
- amp_math/Concurrency::precise_math::scalbnf
- amp_math/Concurrency::precise_math::signbit
- amp_math/Concurrency::precise_math::sin
- amp_math/Concurrency::precise_math::sincos
- amp_math/Concurrency::precise_math::sinf
- amp_math/Concurrency::precise_math::sinh
- amp_math/Concurrency::precise_math::sinpi
- amp_math/Concurrency::precise_math::sinpif
- amp_math/Concurrency::precise_math::sqrtf
- amp_math/Concurrency::precise_math::tan
- amp_math/Concurrency::precise_math::tanh
- amp_math/Concurrency::precise_math::tanhf
- amp_math/Concurrency::precise_math::tanpif
- amp_math/Concurrency::precise_math::tgamma
- amp_math/Concurrency::precise_math::trunc
- amp_math/Concurrency::precise_math::truncf
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
ms.openlocfilehash: ee6ab2313fbdc288ebba1b3fdacf192b7b578eb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321845"
---
# <a name="concurrencyprecise_math-namespace-functions"></a>Concurrency::precise_math 네임스페이스 함수

||||
|-|-|-|
|[Acos](#acos)|[acosf](#acosf)|[acosh](#acosh)|
|[acoshf](#acoshf)|[Asin](#asin)|[asinf](#asinf)|
|[asinh](#asinh)|[asinhf](#asinhf)|[Atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[atanh](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[Ceil](#ceil)|[ceilf](#ceilf)|
|[카피 사인](#copysign)|[copysignf](#copysignf)|[Cos](#cos)|
|[cosf](#cosf)|[cosh](#cosh)|[coshf](#coshf)|
|[코스피](#cospi)|[코스피](#cospif)|[erf](#erf)|
|[erfc](#erfc)|[erfcf](#erfcf)|[에르프신프](#erfcinv)|
|[에르프신프](#erfcinvf)|[erff](#erff)|[에르핀프](#erfinv)|
|[에르핀프](#erfinvf)|[특급](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[바닥](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[Fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[프렉스프 ()프렉스프 (](#frexpf)|[저혈압](#hypot)|[hypotf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[이스피니트](#isfinite)|
|[이신프](#isinf)|[이산 (isnan)](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[로그](#log)|[log10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[log2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[nan](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|
|[다음 후](#nextafterf)|[피](#phi)|[IF](#phif)|
|[pow](#pow)|[powf](#powf)|[프로비트](#probit)|
|[프로비트프](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[remainder](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[라운드](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[rsqrtf](#rsqrtf)|[스칼브 ()스칼브 ()](#scalb)|
|[스칼bf](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[사인비트프](#signbitf)|[죄](#sin)|
|[신코스](#sincos)|[신코스프](#sincosf)|[sinf](#sinf)|
|[sinh](#sinh)|[sinhf](#sinhf)|[신피 (것)들](#sinpi)|
|[죄피프](#sinpif)|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|
|[탄](#tan)|[tanf](#tanf)|[Tanh](#tanh)|
|[tanhf](#tanhf)|[탄피 (것)와 함께](#tanpi)|[탄피프](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[트렁크는](#trunc)|
|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>Acos

인수의 아크코신계산

```cpp
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
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

## <a name="acosh"></a><a name="acosh"></a>아코시 (것)와 같은

인수의 역 하이퍼볼릭 코사인 값을 계산합니다.

```cpp
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 코사인 값을 반환합니다.

## <a name="acoshf"></a><a name="acoshf"></a>아코시프

인수의 역 하이퍼볼릭 코사인 값을 계산합니다.

```cpp
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 코사인 값을 반환합니다.

## <a name="asin"></a><a name="asin"></a>Asin

인수의 호신을 계산합니다.

```cpp
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
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

## <a name="asinh"></a><a name="asinh"></a>아신 (것)과

인수의 역 하이퍼볼릭 사인 값을 계산합니다.

```cpp
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 사인 값을 반환합니다.

## <a name="asinhf"></a><a name="asinhf"></a>아신프

인수의 역 하이퍼볼릭 사인 값을 계산합니다.

```cpp
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 사인 값을 반환합니다.

## <a name="atan"></a><a name="atan"></a>Atan

인수의 아크탄젠트를 계산합니다.

```cpp
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
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

inline double atan2(
    double _Y,
    double _X) restrict(amp);
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

## <a name="atanh"></a><a name="atanh"></a>아탄 (것)에

인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.

```cpp
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 탄젠트 값을 반환합니다.

## <a name="atanhf"></a><a name="atanhf"></a>아탄프 ()아탄프 (것)

인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.

```cpp
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 하이퍼볼릭 탄젠트 값을 반환합니다.

## <a name="cbrt"></a><a name="cbrt"></a>바트 (것)중 대

인수의 실제 세제곱근을 계산

```cpp
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 실제 세제곱근을 반환합니다.

## <a name="cbrtf"></a><a name="cbrtf"></a>바트프 ()의

인수의 실제 세제곱근을 계산

```cpp
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 실제 세제곱근을 반환합니다.

## <a name="ceil"></a><a name="ceil"></a>Ceil

인수의 천장을 계산합니다.

```cpp
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
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

## <a name="copysign"></a><a name="copysign"></a>카피 사인

_X 크기 및 _Y 부호 값을 생성합니다.

```cpp
inline float copysign(
    float _X,
    float _Y) restrict(amp);

inline double copysign(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X 크기 및 _Y 부호 값을 반환합니다.

## <a name="copysignf"></a><a name="copysignf"></a>카피사인프

_X 크기 및 _Y 부호 값을 생성합니다.

```cpp
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X 크기 및 _Y 부호 값을 반환합니다.

## <a name="cos"></a><a name="cos"></a>Cos

인수의 코사인을 계산합니다.

```cpp
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 코사인 값을 반환합니다.

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

## <a name="cosh"></a><a name="cosh"></a>코시 (주)

인수의 쌍곡선 코신 값을 계산합니다.

```cpp
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 하이퍼볼릭 코사인 값을 반환합니다.

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

## <a name="cospi"></a><a name="cospi"></a>코스피

파이 \* _X 코사네 값을 계산합니다.

```cpp
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

파이 \* _X 코사네 값을 반환합니다.

## <a name="cospif"></a><a name="cospif"></a>코스피

파이 \* _X 코사네 값을 계산합니다.

```cpp
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

파이 \* _X 코사네 값을 반환합니다.

## <a name="erf"></a><a name="erf"></a>Erf

_X의 오류 함수를 계산합니다.

```cpp
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 오류 함수를 반환합니다.

## <a name="erfc"></a><a name="erfc"></a>Erfc

_X의 상보 오류 함수 계산

```cpp
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 상보 오류 함수를 반환합니다.

## <a name="erfcf"></a><a name="erfcf"></a>erfcf

_X의 상보 오류 함수 계산

```cpp
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 상보 오류 함수를 반환합니다.

## <a name="erfcinv"></a><a name="erfcinv"></a>에르프신프

_X의 역 상보 오류 함수를 계산합니다.

```cpp
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 역 상보 오류 함수를 반환합니다.

## <a name="erfcinvf"></a><a name="erfcinvf"></a>에르프신프

_X의 역 상보 오류 함수를 계산합니다.

```cpp
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 역 상보 오류 함수를 반환합니다.

## <a name="erff"></a><a name="erff"></a>erff

_X의 오류 함수를 계산합니다.

```cpp
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 오류 함수를 반환합니다.

## <a name="erfinv"></a><a name="erfinv"></a>에르핀프

_X의 역 오류 함수를 계산합니다.

```cpp
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 역 오류 함수를 반환합니다.

## <a name="erfinvf"></a><a name="erfinvf"></a>에르핀프

_X의 역 오류 함수를 계산합니다.

```cpp
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 역 오류 함수를 반환합니다.

## <a name="exp10"></a><a name="exp10"></a>exp10

인수의 기본 10 지수를 계산합니다.

```cpp
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 기본-10 지수를 반환합니다.

## <a name="exp10f"></a><a name="exp10f"></a>exp10f

인수의 기본 10 지수를 계산합니다.

```cpp
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 기본-10 지수를 반환합니다.

## <a name="expm1"></a><a name="expm1"></a>expm1

인수의 밑이 e인 지수 값 - 1을 계산합니다.

```cpp
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*지*<br/>
수학적 `e`식 <sup>n의</sup>지수 용어 `e` *n은* 자연 로그림의 기초입니다.

### <a name="return-value"></a>Return Value

인수의 밑이 e인 지수 값 - 1을 반환합니다.

## <a name="expm1f"></a><a name="expm1f"></a>expm1f

인수의 밑이 e인 지수 값 - 1을 계산합니다.

```cpp
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*지*<br/>
수학적 `e`식 <sup>n의</sup>지수 용어 `e` *n은* 자연 로그림의 기초입니다.

### <a name="return-value"></a>Return Value

인수의 밑이 e인 지수 값 - 1을 반환합니다.

## <a name="exp"></a><a name="exp"></a>특급

인수의 기본 e 지수를 계산합니다.

```cpp
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 e인 지수 값을 반환합니다.

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

## <a name="exp2"></a><a name="exp2"></a>exp2

인수의 기본 2 지수를 계산합니다.

```cpp
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
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

## <a name="fabs"></a><a name="fabs"></a>팹

인수의 절대 값을 반환합니다.

```cpp
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

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

## <a name="fdim"></a><a name="fdim"></a>프딤 (것)이

인수 간의 양수 차이를 계산합니다.

```cpp
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 점 값 *_Y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X _Y 보다 큰 경우 _X _Y 차이; 그렇지 않으면 +0.

## <a name="fdimf"></a><a name="fdimf"></a>fdimf

인수 간의 양수 차이를 계산합니다.

```cpp
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 점 값 *_Y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X _Y 보다 큰 경우 _X _Y 차이; 그렇지 않으면 +0.

## <a name="floor"></a><a name="floor"></a>바닥

인수의 바닥을 계산합니다.

```cpp
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
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

## <a name="a-namefma-fma"></a><a name="fma">Fma

첫 번째 및 두 번째 지정된 인수의 곱을 계산한 다음 세 번째 지정된 인수를 결과에 추가합니다. 전체 계산은 단일 작업으로 수행됩니다.

```cpp
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.
*_y*<br/>
두 번째 부동 점 인수입니다.
*_Z*<br/>
세 번째 부동 점 인수입니다.

### <a name="return-value"></a>Return Value

식의 결과(_X \* _Y) + _Z. 전체 계산은 단일 작업으로 수행됩니다. 즉, 하위 표현식은 무한 정밀도로 계산되고 최종 결과만 반올림됩니다.

## <a name="fmaf"></a><a name="fmaf"></a>fmaf

첫 번째 및 두 번째 지정된 인수의 곱을 계산한 다음 세 번째 지정된 인수를 결과에 추가합니다. 전체 계산은 단일 작업으로 수행됩니다.

```cpp
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.
*_y*<br/>
두 번째 부동 점 인수입니다.
*_Z*<br/>
세 번째 부동 점 인수입니다.

### <a name="return-value"></a>Return Value

식의 결과(_X \* _Y) + _Z. 전체 계산은 단일 작업으로 수행됩니다. 즉, 하위 표현식은 무한 정밀도로 계산되고 최종 결과만 반올림됩니다.

## <a name="fmax"></a><a name="fmax"></a>fmax

인수의 최대 숫자 값 결정

```cpp
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

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
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

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

## <a name="fmod-function-c-amp"></a><a name="fmod"></a>fmod 기능 (C ++ AMP)

첫 번째 지정된 인수의 나머지 부분을 두 번째 지정된 인수로 나눈 계산합니다.

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.

*_y*<br/>
두 번째 부동 점 인수입니다.

### <a name="return-value"></a>Return Value

나머지 를 `_X` 나눈 `_Y`값; `_X`  -  `_Y`즉, n의 값이 *n의*크기보다 크기가 적도록 `_X`  -  `_Y` *n* `_Y` *n의* 값이 전체 정수인 경우입니다.

## <a name="fmodf"></a><a name="fmodf"></a>fmodf

첫 번째 지정된 인수의 나머지 부분을 두 번째 지정된 인수로 나눈 계산합니다.

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.

*_y*<br/>
두 번째 부동 점 인수입니다.

### <a name="return-value"></a>Return Value

나머지 를 `_X` 나눈 `_Y`값; `_X`  -  `_Y`즉, n의 값이 *n의*크기보다 크기가 적도록 `_X`  -  `_Y` *n* `_Y` *n의* 값이 전체 정수인 경우입니다.

## <a name="fpclassify"></a><a name="fpclassify"></a>fpclassify

인수 값을 NaN, infinite, normal, subnormal, 0으로 분류합니다.

```cpp
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수 값에 적절한 번호 분류 매크로의 값을 반환합니다.

## <a name="frexp"></a><a name="frexp"></a>frexp

_X 의 사마증과 지수를 가져옵니다

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
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

## <a name="hypot"></a><a name="hypot"></a>저혈압

_X 및 _Y 제곱합의 제곱근 계산

```cpp
inline float hypot(
    float _X,
    float _Y) restrict(amp);

inline double hypot(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X 및 _Y 제곱합의 제곱근을 반환합니다.

## <a name="hypotf"></a><a name="hypotf"></a>hypotf

_X 및 _Y 제곱합의 제곱근 계산

```cpp
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X 및 _Y 제곱합의 제곱근을 반환합니다.

## <a name="ilogb"></a><a name="ilogb"></a>아이로그 (것)들

부호 있는 정수 값으로 _X 지수를 추출합니다.

```cpp
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

부호 있는 정수 값으로 _X 지수를 반환합니다.

## <a name="ilogbf"></a><a name="ilogbf"></a>일로그bf

부호 있는 정수 값으로 _X 지수를 추출합니다.

```cpp
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

부호 있는 정수 값으로 _X 지수를 반환합니다.

## <a name="isfinite"></a><a name="isfinite"></a>이스피니트

인수에 유한 값이 있는지 여부를 결정합니다.

```cpp
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
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

inline int isinf(double _X) restrict(amp);
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

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수가 NaN 값을 갖는 경우에만 0이 아닌 값을 반환합니다.

## <a name="isnormal"></a><a name="isnormal"></a>이스노멀

인수가 정상인지 여부를 결정합니다.

```cpp
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수가 정상 값을 가진 경우에만 0이 아닌 값을 반환합니다.

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

지정된 가사 및 지수에서 실제 숫자를 계산합니다.

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 점 값, 사마증

*_Exp*<br/>
정수 값, 지수

### <a name="return-value"></a>Return Value

_X \* 2^_Exp 반환

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

지정된 가사 및 지수에서 실제 숫자를 계산합니다.

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 점 값, 사마증

*_Exp*<br/>
정수 값, 지수

### <a name="return-value"></a>Return Value

_X \* 2^_Exp 반환

## <a name="lgamma"></a><a name="lgamma"></a>lg암마 (것)군

감마 인수의 절대 값 자연 로그 계산

```cpp
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Sign*<br/>
부호를 반환합니다.

### <a name="return-value"></a>Return Value

감마 인수의 절대 값의 자연 로그를 반환합니다.

## <a name="lgammaf"></a><a name="lgammaf"></a>lg크림프

감마 인수의 절대 값 자연 로그 계산

```cpp
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Sign*<br/>
부호를 반환합니다.

### <a name="return-value"></a>Return Value

감마 인수의 절대 값의 자연 로그를 반환합니다.

## <a name="log"></a><a name="log"></a>로그

인수의 기본 e 로그릿헴을 계산합니다.

```cpp
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
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

inline double log10(double _X) restrict(amp);
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

## <a name="log1p"></a><a name="log1p"></a>log1p

인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.

```cpp
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수에 1을 더한 값의 밑이 e인 로그 값을 반환합니다.

## <a name="log1pf"></a><a name="log1pf"></a>log1pf

인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.

```cpp
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수에 1을 더한 값의 밑이 e인 로그 값을 반환합니다.

## <a name="log2"></a><a name="log2"></a>log2

인수의 기본 2 로그릿헴을 계산합니다.

```cpp
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 밑이 10인 로그 값을 반환합니다.

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

## <a name="logb"></a><a name="logb"></a>로그

부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.

```cpp
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 부호 있는 지수를 반환합니다.

## <a name="logbf"></a><a name="logbf"></a>로그 bf

부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.

```cpp
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 부호 있는 지수를 반환합니다.

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

지정된 인수를 소수 및 정수 부분으로 분할합니다.

```cpp
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Iptr*<br/>
【아웃】 `_X`의 정수 부분을 부동 점 값으로 합니다.

### <a name="return-value"></a>Return Value

의 서명된 소수 `_X`부분입니다.

## <a name="modff"></a><a name="modff"></a>모드 프

지정된 인수를 소수 및 정수 부분으로 분할합니다.

```cpp
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_Iptr*<br/>
`_X`의 정수 부분을 부동 점 값으로 합니다.

### <a name="return-value"></a>Return Value

의 `_X`서명된 소수 부분을 반환합니다.

## <a name="nan"></a><a name="nan"></a>Nan

자동 NaN을 반환합니다.

```cpp
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
정수 값

### <a name="return-value"></a>Return Value

사용 가능할 경우 _X에 표시된 내용과 함께 자동 NaN을 반환합니다.

## <a name="nanf"></a><a name="nanf"></a>난프 ()난프 ()

자동 NaN을 반환합니다.

```cpp
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
정수 값

### <a name="return-value"></a>Return Value

사용 가능할 경우 _X에 표시된 내용과 함께 자동 NaN을 반환합니다.

## <a name="nearbyint"></a><a name="nearbyint"></a>인근

인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.

```cpp
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

반올림된 정수 값을 반환합니다.

## <a name="nearbyintf"></a><a name="nearbyintf"></a>인근 인트tf

인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.

```cpp
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

반올림된 정수 값을 반환합니다.

## <a name="nextafter"></a><a name="nextafter"></a>다음 후

함수 의 방향으로 _X 후 함수 의 형식에서 다음 표현 가능한 값을 결정합니다_Y

```cpp
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

함수의 _X 방향으로 다음 표현 가능한 값을 반환합니다_Y

## <a name="nextafterf"></a><a name="nextafterf"></a>다음 후

함수 의 방향으로 _X 후 함수 의 형식에서 다음 표현 가능한 값을 결정합니다_Y

```cpp
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

함수의 _X 방향으로 다음 표현 가능한 값을 반환합니다_Y

## <a name="phi"></a><a name="phi"></a>피

인수의 누적 배포 함수를 반환합니다.

```cpp
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 누적 배포 함수를 반환합니다.

## <a name="phif"></a><a name="phif"></a>IF

인수의 누적 배포 함수를 반환합니다.

```cpp
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 누적 배포 함수를 반환합니다.

## <a name="pow"></a><a name="pow"></a>포로

_Y 힘으로 제기 _X 계산

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값, 밑

*_y*<br/>
부동 소수점 값, 지수

### <a name="return-value"></a>Return Value

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

## <a name="probit"></a><a name="probit"></a>프로비트

인수의 역 누적 분포 함수를 반환합니다.

```cpp
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 누적 분포 함수를 반환합니다.

## <a name="probitf"></a><a name="probitf"></a>프로비트프

인수의 역 누적 분포 함수를 반환합니다.

```cpp
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 역 누적 분포 함수를 반환합니다.

## <a name="rcbrt"></a><a name="rcbrt"></a>rcbrt

인수의 큐브 루트의 상호를 반환합니다.

```cpp
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 큐브 루트의 상호를 반환합니다.

## <a name="rcbrtf"></a><a name="rcbrtf"></a>rcbrtf

인수의 큐브 루트의 상호를 반환합니다.

```cpp
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

인수의 큐브 루트의 상호를 반환합니다.

## <a name="remainder"></a><a name="remainder"></a>나머지

나머지 _X REM _Y를 계산합니다.

```cpp
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X REM _Y를 반환합니다.

## <a name="remainderf"></a><a name="remainderf"></a>나머지

나머지 _X REM _Y를 계산합니다.

```cpp
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X REM _Y를 반환합니다.

## <a name="remquo"></a><a name="remquo"></a>렘쿠오

첫 번째 지정된 인수의 나머지 부분을 두 번째 지정된 인수로 나눈 계산합니다. 또한 significicand 두 번째 지정된 인수의 significand로 나눈 첫 번째 지정된 인수의 몫을 계산하고 세 번째 인수에 지정된 위치를 사용하여 몫을 반환합니다.

```cpp
inline float remquo(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);

inline double remquo(
    double _X,
    double _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.

*_y*<br/>
두 번째 부동 점 인수입니다.

*_Quo*<br/>
【아웃】 의 소수 비트로 나눈 소수 비트의 몫을 반환하는 데 사용되는 `_X` 정수의 `_Y`주소입니다.

### <a name="return-value"></a>Return Value

`_X` 나머지 를 로 `_Y`반환합니다.

## <a name="remquof"></a><a name="remquof"></a>렘쿠피 (렘쿠오)

첫 번째 지정된 인수의 나머지 부분을 두 번째 지정된 인수로 나눈 계산합니다. 또한 significicand 두 번째 지정된 인수의 significand로 나눈 첫 번째 지정된 인수의 몫을 계산하고 세 번째 인수에 지정된 위치를 사용하여 몫을 반환합니다.

```cpp
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
첫 번째 부동 점 인수입니다.

*_y*<br/>
두 번째 부동 점 인수입니다.

*_Quo*<br/>
【아웃】 의 소수 비트로 나눈 소수 비트의 몫을 반환하는 데 사용되는 `_X` 정수의 `_Y`주소입니다.

### <a name="return-value"></a>Return Value

`_X` 나머지 를 로 `_Y`반환합니다.

## <a name="round"></a><a name="round"></a>라운드

가장 가까운 정수로 _X

```cpp
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
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

inline double rsqrt(double _X) restrict(amp);
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

## <a name="scalb"></a><a name="scalb"></a>스칼브 ()스칼브 ()

_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.

```cpp
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

반품 \* _X(FLT_RADIX ^ _Y)

## <a name="scalbf"></a><a name="scalbf"></a>스칼bf

_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.

```cpp
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

반품 \* _X(FLT_RADIX ^ _Y)

## <a name="scalbn"></a><a name="scalbn"></a>스칼빈 (주)

_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.

```cpp
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
정수 값

### <a name="return-value"></a>Return Value

반품 \* _X(FLT_RADIX ^ _Y)

## <a name="scalbnf"></a><a name="scalbnf"></a>스칼비엔프

_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.

```cpp
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

*_y*<br/>
정수 값

### <a name="return-value"></a>Return Value

반품 \* _X(FLT_RADIX ^ _Y)

## <a name="signbit"></a><a name="signbit"></a>사인 비트

_X의 부호가 음수인지 결정합니다.

```cpp
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
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

inline double sin(double _X) restrict(amp);
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
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);

inline void sincos(
    double _X,
    _Out_ double* _S,
    _Out_ double* _C) restrict(amp);
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
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
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

inline double sinh(double _X) restrict(amp);
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

## <a name="sinpi"></a><a name="sinpi"></a>신피 (것)들

파이 \* _X 의 사소이 값을 계산합니다.

```cpp
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

파이 \* _X 의 사이프 값을 반환합니다.

## <a name="sinpif"></a><a name="sinpif"></a>죄피프

파이 \* _X 의 사소이 값을 계산합니다.

```cpp
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

파이 \* _X 의 사이프 값을 반환합니다.

## <a name="sqrt"></a><a name="sqrt"></a>Sqrt

인수의 제곱근을 계산합니다.

```cpp
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
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

inline double tan(double _X) restrict(amp);
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

inline double tanh(double _X) restrict(amp);
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

## <a name="tanpi"></a><a name="tanpi"></a>탄피 (것)와 함께

파이 \* _X 접선 값을 계산합니다.

```cpp
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

pi \* _X 접선 값을 반환합니다.

## <a name="tanpif"></a><a name="tanpif"></a>탄피프

파이 \* _X 접선 값을 계산합니다.

```cpp
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

pi \* _X 접선 값을 반환합니다.

## <a name="tgamma"></a><a name="tgamma"></a>감마 ()감마 (것)감마

_X의 감마 함수 계산

```cpp
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 감마 함수의 결과를 반환합니다.

## <a name="tgammaf"></a><a name="tgammaf"></a>트감마프 (것)감마프

_X의 감마 함수 계산

```cpp
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_x*<br/>
부동 소수점 값

### <a name="return-value"></a>Return Value

_X의 감마 함수의 결과를 반환합니다.

## <a name="trunc"></a><a name="trunc"></a>트렁크는

인수를 정수 구성 요소로 연결합니다.

```cpp
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
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

## <a name="see-also"></a>참고 항목

[동시성::precise_수학 네임스페이스](concurrency-precise-math-namespace.md)
