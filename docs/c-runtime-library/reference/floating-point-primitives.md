---
title: 부동 소수점 기본 형식
ms.date: 4/2/2020
api_name:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
- _o__d_int
- _o__dclass
- _o__dlog
- _o__dnorm
- _o__dpcomp
- _o__dpoly
- _o__dscale
- _o__dsign
- _o__dsin
- _o__dtest
- _o__dunscale
- _o__fd_int
- _o__fdclass
- _o__fdexp
- _o__fdlog
- _o__fdpcomp
- _o__fdpoly
- _o__fdscale
- _o__fdsign
- _o__fdsin
- _o__ld_int
- _o__ldclass
- _o__ldexp
- _o__ldlog
- _o__ldpcomp
- _o__ldpoly
- _o__ldscale
- _o__ldsign
- _o__ldsin
- _o__ldtest
- _o__ldunscale
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: d861fbf2b71d557354a60f65b8a76dc24ca1dd13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346705"
---
# <a name="floating-point-primitives"></a>부동 소수점 기본 형식

일부 표준 C 런타임 라이브러리(CRT) 부동 지점 함수를 구현하는 데 사용되는 Microsoft 별 기본 함수입니다. 완전성을 위해 여기에 문서화되어 있지만 사용하지 않는 것이 좋습니다. 이러한 함수 중 일부는 IEEE-754 동작에 대한 정밀도, 예외 처리 및 준수에 문제가 있는 것으로 알려져 있으므로 사용되지 않는 함수로 기록됩니다. 이전 버전과의 호환성을 위해서만 라이브러리에 존재합니다. 올바른 동작, 이식성 및 표준 준수를 위해 이러한 함수보다 표준 부동 점 함수를 선호합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>구문

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 점 함수 인수입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 부동 점 형식에 대해 CRT 매크로 [fpclassify의](fpclassify.md) C 버전을 구현합니다. 인수 *x의* 분류는 math.h에 정의된 이러한 상수 중 하나로 반환됩니다.

|값|Description|
|-----------|-----------------|
| **FP_NAN** | 자동, 신호 또는 비활성화 상태 NaN |
| **FP_INFINITE** | 양수 또는 음수 무한대 |
| **FP_NORMAL** | 정규화된 0이 아닌 양수 또는 음수 값 |
| **FP_SUBNORMAL** | 양수 또는 음수 비정규값(비정규화) 값 |
| **FP_ZERO** | 양수 또는 음수 0 값 |

자세한 내용은 Microsoft 특정 [_fpclass _fpclassf](fpclass-fpclassf.md) 함수를 사용할 수 있습니다. 이식성을 위해 [fpclassify](fpclassify.md) 매크로 또는 함수를 사용합니다.

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>구문

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 점 함수 인수입니다.

### <a name="remarks"></a>설명

이러한 부동 지점 프리미티브는 CRT에서 [부호비트](signbit.md) 매크로 또는 함수를 구현합니다. 부호 비트가 인수 *x의*significand (mantissa)에 설정된 경우 0이 아닌 값을 반환하고 기호 비트가 설정되지 않은 경우 0을 반환합니다.

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>구문

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>매개 변수

*x*, *y*<br/>
부동 점 함수 인수입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 *x와* *y라는*두 개의 인수를 취하고 math.h에 정의된 비트 또는 이러한 상수로 표현된 순서 관계를 표시하는 값을 반환합니다.

| 값 | Description |
|------------|-----------------|
| **_FP_LT** | *x는* y 미만으로 간주될 수 *있습니다.* |
| **_FP_EQ** | *x는* y와 같게 간주될 수 *있습니다.* |
| **_FP_GT** | *x는* y보다 큰 것으로 간주될 수 *있습니다.* |

이러한 원시인들은 더 [큰, isgreater, isless, islessequal, islessgreater, isunordered](floating-point-ordering.md) 매크로 및 CRT의 기능을 구현합니다.

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>구문

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>매개 변수

*픽셀*<br/>
부동 점 인수에 대한 포인터입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 부동 점 형식에 대해 CRT 함수 [fpclassify의](fpclassify.md) C++ 버전을 구현합니다. 인수 *x가* 평가되고 분류가 math.h에 정의된 이러한 상수 중 하나로 반환됩니다.

|값|Description|
|-----------|-----------------|
| **FP_NAN** | 자동, 신호 또는 비활성화 상태 NaN |
| **FP_INFINITE** | 양수 또는 음수 무한대 |
| **FP_NORMAL** | 정규화된 0이 아닌 양수 또는 음수 값 |
| **FP_SUBNORMAL** | 양수 또는 음수 비정규값(비정규화) 값 |
| **FP_ZERO** | 양수 또는 음수 0 값 |

자세한 내용은 Microsoft 특정 [_fpclass _fpclassf](fpclass-fpclassf.md) 함수를 사용할 수 있습니다. 이식성을 위해 [fpclassify](fpclassify.md) 함수를 사용합니다.

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>구문

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>매개 변수

*픽셀*<br/>
부동 점 인수에 대한 포인터입니다.

*특급*<br/>
적분 유형으로 지수입니다.

### <a name="remarks"></a>설명

이러한 부동 소수점 프리미티브는 부동 소수점 값 *px* 및 지수 값 *exp에*대한 포인터를 취하고 가능하면 지정된 지수 아래의 부동 소수점 값의 소수 부분을 제거합니다. 반환된 값은 NaN 또는 무한대인 경우 *px의* 입력 값과 *px의* 출력 값에 대한 **fpclassify의** 결과입니다.

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>구문

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>매개 변수

*픽셀*<br/>
부동 점 인수에 대한 포인터입니다.

*특급*<br/>
적분 유형으로 지수입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 부동 점 값 *px* 및 지수 값 *exp에*대한 포인터를 취하고 가능하면 *px의* 값을 2<sup>*exp로*</sup>배율조정합니다. 반환된 값은 NaN 또는 무한대인 경우 *px의* 입력 값과 *px의* 출력 값에 대한 **fpclassify의** 결과입니다. 이식성을 위해 [ldexp, ldexpf 및 ldexpl](ldexp.md) 함수를 선호합니다.

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>구문

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>매개 변수

*페xp*<br/>
정수 유형으로 지수에 대한 포인터입니다.

*픽셀*<br/>
부동 점 인수에 대한 포인터입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 *px가* 가리키는 부동 점 값을 가능한 경우 지수(mantissa)와 지수로 나타낸다. 부등화는 절대 값이 0.5보다 크거나 같고 1.0 보다 크도록 배율이 조정됩니다. 지수는 원래 부동점 값이 배율 조정된 significand times 2<sup>*n과*</sup>같은 값 *n입니다.* 이 정수 지수 *n은* *pexp가*가리키는 위치에 저장됩니다. 반환된 값은 NN 또는 무한대인 경우 *px의* 입력 값과 출력 값에 대한 **fpclassify의** 결과입니다. 휴대성을 [위해, frexp, frexpf, frexpl](frexp.md) 기능을 선호합니다.

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>구문

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>매개 변수

*Y*<br/>
부동 점 함수 인수입니다.

*픽셀*<br/>
부동 점 인수에 대한 포인터입니다.

*특급*<br/>
적분 유형으로 지수입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 *y* * 2<sup>*exp와*</sup>동일한 *px로* 가리키는 위치에 부동 점 값을 구성합니다. 반환된 값은 NaN 또는 무한대인 경우 *y의* 입력 값과 *px의* 출력 값에 대한 **fpclassify의** 결과입니다. 이식성을 위해 [ldexp, ldexpf 및 ldexpl](ldexp.md) 함수를 선호합니다.

## <a name="_dnorm-_fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>구문

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>매개 변수

*Ps*<br/>
**부호없는** **짧은**배열로 표현 된 부동 점 값의 비트 표현에 대한 포인터 .

### <a name="remarks"></a>설명

이러한 부동 소수점 프리미티브는 언더플로우 부동 소수점 값의 소수 부분을 정규화하고 *특성*또는 바이어스 지수를 일치하도록 조정합니다. 이 값은 floating point 형식의 비트별 표현으로 전달되며, math.h에 `_double_val` `_ldouble_val`선언된 `_float_val` .. 또는 형식 펀칭 유니온을 통해 **부호없는** **짧은** 배열로 변환됩니다. 반환 값은 NaN 또는 무한대인 경우 입력 부동 점 값과 출력 값에 **대해 fpclassify의** 결과입니다.

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>구문

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 점 함수 인수입니다.

*테이블*<br/>
다항식에 대한 상수 계수 테이블에 대한 포인터입니다.

*N*<br/>
평가할 다항식의 순서입니다.

### <a name="remarks"></a>설명

이러한 부동 소수점 프리미티브는 표의 해당 상수 값으로 계수가 표시되는 순서 *n의* *table*다항식에서 *x의* 평가를 반환합니다. 예를 *들어, 테이블*\[0] = 3.0, *표*\[1] = 4.0, *표*\[2] = 5.0 및 *n* = 2인 경우, 다항식 5.0x<sup>2</sup> + 4.0x + 3.0을 나타낸다. 이 다항식은 x *x* 2.0으로 평가되면 결과는 31.0입니다. 이러한 함수는 내부적으로 사용되지 않습니다.

## <a name="_dlog-_dlog-_dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>구문

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 점 함수 인수입니다.

*base_flag*<br/>
사용할 베이스를 제어하는 플래그, 기본 *e의* 경우 0, 기본 10의 경우 0이 아닌 플래그입니다.

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 *base_flag* 0일 때 *x,* ln(x) 또는 로그*x*<sub>*e*</sub>e(x)의 자연 로그를 반환합니다.*x* *base_flag* 0이 아닌 경우 로그 베이스 10의 *x*또는 로그<sub>10</sub>*(x)을*반환합니다. 이러한 함수는 내부적으로 사용되지 않습니다. 이식성을 위해 함수 [로그, 로그, 로그, log10, log10f 및 log10l을](log-logf-log10-log10f.md)선호합니다.

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>구문

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 점 함수 인수입니다.

*사분면*<br/>
0, 1, 2 또는 3의 사분면 `sin` `cos`오프셋을 사용하여 을 `-sin`생성합니다. `-cos`

### <a name="remarks"></a>설명

이러한 부동 점 프리미티브는 *사분면* modulo 4에 의해 *x* 오프셋의 사위를 반환합니다. *사분면* modulo 4가 각각 0, 1, 2 또는 *3일* 때 x의 사중, 코신, -sine 및 -cosine을 효과적으로 반환합니다. 이러한 함수는 내부적으로 사용되지 않습니다. 휴대성을 위해 [죄, 죄, 죄,](sin-sinf-sinl.md) [코스, 코스프 및 코스레 기능을](cos-cosf-cosl.md) 선호합니다.

## <a name="requirements"></a>요구 사항

헤더: \<math.h>

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 점 지원](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[이신프](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, ldexpf 및 ldexpl](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
