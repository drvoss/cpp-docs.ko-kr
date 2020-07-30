---
title: pow, powf, powl
ms.date: 4/2/2020
api_name:
- powl
- pow
- powf
- _o_pow
- _o_powf
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
- powl
- pow
- _powl
- powf
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
ms.openlocfilehash: 16038cbb2c572575a9424065825697eb4115e43f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232445"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

*Y*의 거듭제곱으로 계산 되는 *x* 를 계산 합니다.

## <a name="syntax"></a>구문

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
밑입니다.

*x.y*<br/>
지수입니다.

## <a name="return-value"></a>Return Value

*X*<sup>*y*</sup>의 값을 반환 합니다. 오버플로 또는 언더플로 시 오류 메시지는 인쇄되지 않습니다.

|x 및 y의 값|pow의 반환 값|
|-----------------------|-------------------------|
|*x* ! = 0.0 및 *y* = = 0.0|1|
|*x* = = 0.0 및 *y* = = 0.0|1|
|*x* = = 0.0 및 *y* < 0|INF|

## <a name="remarks"></a>설명

**pow** 는 2<sup>64</sup> 보다 큰 정수 부동 소수점 값을 인식 하지 않습니다 (예: 1.0 e100).

**pow** 에는 SSE2 (스트리밍 SIMD 확장 2)를 사용 하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

C + +에서는 오버 로드를 허용 하므로 **pow**의 다양 한 오버 로드를 호출할 수 있습니다. C 프로그램에서 **pow** 은 항상 두 값을 사용 **`double`** 하 고 값을 반환 **`double`** 합니다.

`pow(int, int)` 오버로드는 더 이상 사용할 수 없습니다. 이 오버 로드를 사용 하는 경우 컴파일러는 [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)를 내보낼 수 있습니다. 이 문제를 방지 하려면 첫 번째 매개 변수를 **`double`** , **`float`** 또는로 캐스팅 **`long double`** 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-|-|-|
|**pow**, **powf**, **powl**|\<math.h>|\<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
