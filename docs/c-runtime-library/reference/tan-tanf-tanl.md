---
title: tan, tanf, tanl
ms.date: 4/2/2020
api_name:
- tan
- tanf
- tanl
- _o_tan
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
- tan
- tanf
- _tanl
- tanl
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
ms.openlocfilehash: 73a519614f17b6a8f8b26b5eae2172c87ea7f817
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362639"
---
# <a name="tan-tanf-tanl"></a>tan, tanf, tanl

접선을 계산합니다.

## <a name="syntax"></a>구문

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
각도(라디안)입니다.

## <a name="return-value"></a>반환 값

**황갈색** 함수는 *x의*접선을 반환합니다. *x가* 263보다 크거나 같거나 -263보다 크거나 같으면 결과에서 유의성이 손실됩니다.

|입력|SEH 예외|**마테르 (동음이의)** 예외|
|-----------|-------------------|-------------------------|
|± QNAN,IND|없음|_DOMAIN|
|± INF|**올바르지 않음**|_DOMAIN|

## <a name="remarks"></a>설명

C++는 오버로드를 허용하므로 **플로트** 또는 긴 **이중** 값을 가져가고 반환하는 **tan의** **오버로드를** 호출할 수 있습니다. C 프로그램에서 **tan은** 항상 **두 배를**차지하고 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**황갈색,** **탄프,** **탄**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_tan.c
// This program displays the tangent of pi / 4
// Compile by using: cl crt_tan.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x;

   x = tan( pi / 4 );
   printf( "tan( %f ) = %f\n", pi/4, x );
}
```

```Output
tan( 0.785398 ) = 1.000000
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[_CItan](../../c-runtime-library/citan.md)<br/>
