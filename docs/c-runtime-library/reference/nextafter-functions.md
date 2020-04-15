---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 4/2/2020
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: 7b1416147ed000dd3dd9a13bd52e41a474a8e9d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338559"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

표현 가능한 다음 부동 소수점 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
시작할 부동 소수점 값입니다.

*Y*<br/>
종료할 부동 소수점 값입니다.

## <a name="return-value"></a>Return Value

*y*방향으로 *x* 다음에 반환 형식의 다음 표현 가능한 부동 점 값을 반환합니다. *x와* *y가* 같으면 함수는 예외 없이 반환 유형으로 변환된 *y를*반환합니다. *x가* *y와*같지 않고 결과가 비정상 또는 0이면 **FE_UNDERFLOW** 및 **FE_INEXACT** 부동점 예외 상태가 설정되고 올바른 결과가 반환됩니다. *x* 또는 *y가* NAN인 경우 반환 값은 입력 된 LAN 중 하나입니다. *x가* 유한하고 결과가 형식에서 무한하거나 표현할 수 없는 경우 올바르게 서명된 무한대 또는 NAN이 반환되고 **FE_OVERFLOW** 및 **FE_INEXACT** 부동 점 예외 상태가 설정되고 **errno가** **ERANGE로**설정됩니다.

## <a name="remarks"></a>설명

**다음 및** **다음toward** 함수 패밀리는 *y의*매개 변수 유형을 제외한 동일합니다. *x와* *y가* 같으면 반환되는 값이 반환 유형으로 *변환됩니다.*

C++는 오버로드를 허용하기 \<때문에 cmath> 포함하는 경우 **다음 단계와** **그 다음에** **플로트** 및 **긴** **이중** 형식을 반환하는 오버로드를 호출할 수 있습니다. C 프로그램에서는 **다음 및** **다음을 향해** 항상 **두 배로**돌아갑니다.

**_nextafter** 및 **_nextafterf** 기능은 Microsoft에 만연합니다. **_nextafterf** 기능은 x64용으로 컴파일할 때만 사용할 수 있습니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------------|-------------------------------|
|**다음,** **다음 후,** **다음 후, 다음 _nextafterf,** **_nextafterf** **다음으로,** **다음으로, 다음으로, 다음으로,** **다음**|\<math.h>|\<math.h> 또는 \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> 또는 \<cfloat>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
