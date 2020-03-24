---
title: rint, rintf, rintl
ms.date: 04/05/2018
api_name:
- rintf
- rintl
- rint
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- rintf
- rintl
- rint
helpviewer_keywords:
- rintf function
- rint function
- rintl function
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
ms.openlocfilehash: ac9db3ee5a50bb334754a8a1191638a319829b97
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170893"
---
# <a name="rint-rintf-rintl"></a>rint, rintf, rintl

부동 소수점 값을 부동 소수점 형식의 가장 가까운 정수로 반올림합니다.

## <a name="syntax"></a>구문

```C
double rint( double x );
float rintf( float x );
long double rintl( long double x );
```

```cpp
float rint( float x );  // C++ only
long double rint( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
반올림할 부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**Rint** 함수는 *x*에 가장 가까운 정수를 나타내는 부동 소수점 값을 반환 합니다. 중간 값은 **nearbyint** 함수와 동일한 부동 소수점 반올림 모드의 현재 설정에 따라 반올림 됩니다. **Nearbyint** 함수와 달리 **rint** 함수는 결과가 인수의 값과 다를 경우 **FE_INEXACT** 부동 소수점 예외를 발생 시킬 수 있습니다. 반환되는 오류가 없습니다.

|입력|SEH 예외|**_matherr** 발생할|
|-----------|-------------------|--------------------------|
|± ∞, QNAN, IND|none|none|
|Denormals|EXCEPTION_FLT_UNDERFLOW|none|

## <a name="remarks"></a>주의

는 C++ 오버 로드를 허용 하기 때문에 **float** 및 **long** **double** 값을 사용 하 고 반환 하는 **rint** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **rint** 은 항상 **double**을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**rint**, **rintf**, **rintl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_rint.c
// Build with: cl /W3 /Tc crt_rint.c
// This example displays the rounded results of
// the floating-point values 2.499999, -2.499999,
// 2.8, -2.8, 2.5 and -2.5.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.499999;
   float y = 2.8f;
   long double z = 2.5;

   printf("rint(%f) is %.0f\n", x, rint (x));
   printf("rint(%f) is %.0f\n", -x, rint (-x));
   printf("rintf(%f) is %.0f\n", y, rintf(y));
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));
}
```

```Output
rint(2.499999) is 2
rint(-2.499999) is -2
rintf(2.800000) is 3
rintf(-2.800000) is -3
rintl(2.500000) is 3
rintl(-2.500000) is -3
```

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround, lroundf, lroundl, llround, llroundf, llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint](rint-rintf-rintl.md)<br/>
