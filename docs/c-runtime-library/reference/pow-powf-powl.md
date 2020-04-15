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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b181959ac05814a673ab11f33e4cfc5a39e3869e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333112"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

*y의*힘으로 제기 된 *x를* 계산합니다.

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

*Y*<br/>
지수입니다.

## <a name="return-value"></a>Return Value

*x*<sup>*y*</sup>의 값을 반환합니다. 오버플로 또는 언더플로 시 오류 메시지는 인쇄되지 않습니다.

|x 및 y의 값|pow의 반환 값|
|-----------------------|-------------------------|
|*x!=* 0.0 및 *y* =0.0|1|
|*x* == 0.0 및 *y* =0.0|1|
|*x* == 0.0 및 *y* < 0|INF|

## <a name="remarks"></a>설명

**pow는** 2<sup>64보다</sup> 큰 정수 부동 점 값을 인식하지 못합니다(예: 1.0E100).

**pow에는** 스트리밍 SIMD 확장 2(SSE2)를 사용하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

C++는 오버로드를 허용하므로 **다양한 pow**오버로드를 호출할 수 있습니다. C 프로그램에서 **pow는** 항상 두 **개의 이중** 값을 취하고 **이중** 값을 반환합니다.

`pow(int, int)` 오버로드는 더 이상 사용할 수 없습니다. 이 오버로드를 사용하는 경우 컴파일러는 [C2668을](../../error-messages/compiler-errors-2/compiler-error-c2668.md)내보사할 수 있습니다. 이 문제를 방지하려면 첫 번째 매개 변수를 **double,** **float**또는 **long** **double로**캐스팅합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-|-|-|
|**파우,** **파우,** **폴**|\<math.h>|\<math.h> 또는 \<cmath>|

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
