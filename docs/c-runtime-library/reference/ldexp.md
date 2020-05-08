---
title: ldexp, ldexpf, ldexpl
ms.date: 4/2/2020
api_name:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
- _o_ldexp
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
helpviewer_keywords:
- calculating real numbers
- computing real numbers
- mantissas, floating-point variables
- ldexp function
- ldexpf function
- ldexpl function
- exponent, floating-point numbers
- floating-point functions, mantissa and exponent
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
ms.openlocfilehash: 95eb1eb3ca18e0e7d3450951c930a07f954bc299
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82916536"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp, ldexpf, ldexpl

부동 소수점 수에 2의 정수 거듭제곱을 곱합니다.

## <a name="syntax"></a>구문

```C
double ldexp(
   double x,
   int exp
);
float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*.exp*<br/>
정수 지수입니다.

## <a name="return-value"></a>Return Value

**Ldexp** 함수는 성공한 경우 *x* \* 2<sup>*exp*</sup> 의 값을 반환 합니다. 오버플로 시와 *x*의 부호에 따라 **ldexp** 는 +/- **HUGE_VAL**을 반환 합니다. **errno** 값은 **ERANGE**로 설정 됩니다.

**Errno** 및 가능한 오류 반환 값에 대 한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조 하세요.

## <a name="remarks"></a>설명

C + +에서는 오버 로드를 허용 하므로 **float** 또는 **long** **double** 형식을 사용 하는 **ldexp** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **ldexp** 는 항상 **double** 과 **int** 를 사용 하 고 **double**을 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|C 헤더|C++ 헤더|
|-------------|--------------|------------------|
|**ldexp**, **ldexp**, **ldexp**|\<math.h>|\<cmath>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ldexp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 4.0, y;
   int p = 3;

   y = ldexp( x, p );
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );
}
```

## <a name="output"></a>출력

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
