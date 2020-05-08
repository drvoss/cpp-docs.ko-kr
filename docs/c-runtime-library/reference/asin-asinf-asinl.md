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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: cfee30270b8ed0daa5d600fec65659fbf07162fd
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909263"
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

**Asin** 함수는-π/2 ~ π/2 라디안 범위에서 *x* 의 아크사인 (역 사인 함수)을 반환 합니다.

기본적으로 *x* 가-1 보다 작거나 1 보다 큰 경우 **asin** 는 무한을 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± ∞|**올바르지 않음**|**_DOMAIN**|
|± **QNAN**, **IND**|없음|**_DOMAIN**|
|&#124;x&#124;>1|**올바르지 않음**|**_DOMAIN**|

## <a name="remarks"></a>설명

C + +에서는 오버 로드를 허용 하므로 **float** 및 **long** **double** 값을 사용 하 여 **asin** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **asin** 은 항상 **double**을 사용 하 고 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="example"></a>예제

자세한 내용은 [acos, acosf, acosl](acos-acosf-acosl.md)을 참조하세요.

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
