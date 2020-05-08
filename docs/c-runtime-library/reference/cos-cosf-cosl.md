---
title: cos, cosf, cosl
ms.date: 4/2/2020
api_name:
- cos
- cosf
- cosl
- _o_cos
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
- cos
- cosf
- cosl
helpviewer_keywords:
- cosines
- cosl function
- calculating cosine
- cosf function
- cos function
- trigonometric functions
- cosines, calculating
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
ms.openlocfilehash: 1aae123de5ef03af8bcaf8480a84327f88c457c5
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917239"
---
# <a name="cos-cosf-cosl"></a>cos, cosf, cosl

코사인을 계산 합니다.

## <a name="syntax"></a>구문

```C
double cos( double x );
float cosf( float x );
long double cosl( long double x );
```

```cpp
float cos( float x );  // C++ only
long double cos( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
각도(라디안)입니다.

## <a name="return-value"></a>Return Value

*X*의 코사인입니다. *X* 가 263 보다 크거나 같은 경우 또는-263 보다 작거나 같은 경우 결과에 중요 한 손실이 발생 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± QNAN, IND|없음|**_DOMAIN**|
|± INF|**올바르지 않음**|**_DOMAIN**|

## <a name="remarks"></a>설명

C + +에서는 오버 로드를 허용 하므로 **float** 또는 **long** **double** 값을 사용 하 고 반환 하는 **cos** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **cos** 는 항상 **double**을 사용 하 고 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|
|-------------|---------------------|-|
|**cos**, **cosh**, **cosh**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[Sin, sinf, sinf](sin-sinf-sinl.md)의 예제를 참조 하세요.

## <a name="see-also"></a>참조

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIcos](../../c-runtime-library/cicos.md)<br/>
