---
title: asin, asinf, asinl
ms.date: 4/2/2020
api_name:
- asinf
- asinl
- asin
- _o_asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 424fee6995fae4a7f878054ede1bb85d33d1706d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334125"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

아크사인을 계산합니다.

## <a name="syntax"></a>구문

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
아크사인을 계산해야 하는 값입니다.

## <a name="return-value"></a>Return Value

**아신** 함수는 *x의* 아크신(역 사인 함수)을 x 범위 -π/2에서 π/2 라디안으로 반환합니다.

기본적으로 *x가* -1 보다 작거나 1보다 큰 경우 **asin은** 무기한을 반환합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± ∞|**올바르지 않음**|**_DOMAIN**|
|± **QNAN,** **IND**|없음|**_DOMAIN**|
|&#124;x&#124;>1|**올바르지 않음**|**_DOMAIN**|

## <a name="remarks"></a>설명

C++는 오버로드를 허용하므로 **부동 부동** 값과 긴 **이중** 값으로 **asin의** **오버로드를** 호출할 수 있습니다. C 프로그램에서 **asin은** 항상 **이중을**가져와 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**아신,** **아신프,** **아신**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="example"></a>예제

자세한 내용은 [acos, acosf, acosl](acos-acosf-acosl.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
