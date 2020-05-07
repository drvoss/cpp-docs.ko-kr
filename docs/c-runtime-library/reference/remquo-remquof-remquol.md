---
title: remquo, remquof, remquol
ms.date: 4/2/2020
api_name:
- remquof
- remquo
- remquol
- _o_remquo
- _o_remquof
- _o_remquol
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
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: 774a35f257b02c67b22618224a60ed501476a6f4
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917829"
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

두 정수값의 나머지를 계산하고, 몫의 대략적인 크기와 부호가 포함된 정수값을 매개 변수에 지정된 위치에 저장합니다.

## <a name="syntax"></a>구문

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*숫자로*<br/>
분자입니다.

*denom*<br/>
분모입니다.

*현상*<br/>
몫의 대략적인 크기와 부호가 포함된 값을 저장하는 정수에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**remquo** 는 *x* / *y*의 부동 소수점 나머지를 반환 합니다. *Y* 값이 0.0 이면 **Remquo** 는 자동 NaN을 반환 합니다. **Printf** 패밀리의 자동 NaN 표현에 대 한 자세한 내용은 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)를 참조 하세요.

## <a name="remarks"></a>설명

**Remquo** 함수는 x*i*  / *y* \* *y* =  *x* + *f*인 x y의 부동 소수점 나머지 *f* 를 계산 합니다. 여기서 *i* 는 정수이 고 *f* 는 *x*와 같으며 *f의 절대값은* *y*의 절대값 보다 작은 *값입니다.*

C + +에서는 오버 로드를 허용 하므로 **float** 또는 **long** **double** 값을 사용 하 고 반환 하는 **remquo** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **remquo** 은 항상 두 개의 **double** 인수를 사용 하 고 **double**을 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
