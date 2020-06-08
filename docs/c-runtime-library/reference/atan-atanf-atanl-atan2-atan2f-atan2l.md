---
title: atan, atanf, atanl, atan2, atan2f, atan2l
ms.date: 6/5/2020
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 41007e08884da6ccac09c7dc98cef12381e4b45a
ms.sourcegitcommit: fe146adb3a02872538637196bb3c45aeeeaaf5c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84506782"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

**X** (**atan**, **atanf**및 **atanf**)의 아크탄젠트 또는 **y** / **x** (**atan2**, **atan2f**및 **atan2l**)의 아크탄젠트를 계산 합니다.

## <a name="syntax"></a>구문

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
```

```cpp
float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*, *y*<br/>
임의의 숫자입니다.

## <a name="return-value"></a>반환 값

**atan** 는-π/2 ~ π/2 라디안 범위에서 *x* 의 아크탄젠트를 반환 합니다. **atan2** 는 *y* / -π에서 π 라디안 까지의 y*x* 의 아크탄젠트를 반환 합니다. *X* 가 0 이면 **atan** 는 0을 반환 합니다. **Atan2** 의 두 매개 변수가 모두 0 인 경우 함수는 0을 반환 합니다. 모든 결과는 라디안 단위입니다.

**atan2** 는 두 매개 변수의 부호를 사용 하 여 반환 값의 사분면을 결정 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|없음|**_DOMAIN**|

## <a name="remarks"></a>설명

**Atan** 함수는 *x*의 아크탄젠트 (역 탄젠트 함수)를 계산 합니다. **atan2** 는 *y*x의 아크탄젠트를 계산 / *x* 합니다. *x* 가 0 이면 **atan2** 는 y가 양수인 *경우* π/2를 반환 하 고 y *가* 음수인 경우에는 π/2를 반환 하 고 *y* 가 0 이면 0을 반환 합니다.

**atan** 에는 SSE2 (스트리밍 SIMD 확장 2)를 사용 하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

C + +에서는 오버 로드를 허용 하므로 **float** 또는 **long** **double** 인수를 사용 하는 **atan** 및 **atan2** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **atan** 및 **atan2** 는 항상 **이중** 인수를 사용 하 고 **double**을 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**atan**, **atan2**, **atanf**, **atan2f**, **atanf**, **atan2l**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="example"></a>예제

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
