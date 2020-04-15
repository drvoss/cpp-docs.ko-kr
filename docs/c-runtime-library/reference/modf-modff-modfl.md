---
title: modf, modff, modfl
ms.date: 4/2/2020
api_name:
- modff
- modf
- modfl
- _o_modf
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
ms.openlocfilehash: b509da5f18ea1f606b8a3b47ab66a78e4f595558
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338692"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

부동 소수점 값을 소수 부분과 정수 부분으로 분할합니다.

## <a name="syntax"></a>구문

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

*Intptr*<br/>
저장된 정수 부분에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

이 함수는 *x*의 부호 있는 소수 부분을 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

**modf** 함수는 부동 소수점 값 *x를* 소수 및 정수 부분으로 나누며 각 부분은 *x와*동일한 기호를 가짐을 가짐을 가시고 있습니다. *x의* 서명된 소수 부분이 반환됩니다. 정수 부분은 *intptr에서*부동 점 값으로 저장됩니다.

**modf에는** 스트리밍 SIMD 확장 2(SSE2)를 사용하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

C++는 오버로드를 허용하므로 **플로트** 또는 **긴** **이중** 매개변수를 가져 와서 반환하는 **modf의** 오버로드를 호출할 수 있습니다. C 프로그램에서 **modf는** 항상 두 개의 이중 값을 취하고 이중 값을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**모드,** **모드,** **모드 플**|C: \<math.h><br /><br /> C++: , \<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
