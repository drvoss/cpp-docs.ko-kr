---
title: tgamma, tgammaf, tgammal
ms.date: 4/2/2020
api_name:
- tgamma
- tgammaf
- tgammal
- _o_tgamma
- _o_tgammaf
- _o_tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: 6f3eb1bd791e645407b09a99a8c8e96025ca47e3
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912237"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

지정된 값의 감마 함수를 결정합니다.

## <a name="syntax"></a>구문

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
감마를 찾을 값입니다.

## <a name="return-value"></a>Return Value

성공 하면 *x*의 감마를 반환 합니다.

*X* 의 크기가 너무 크거나 너무 작아서 데이터 형식에 대해 범위 오류가 발생할 수 있습니다. *X* <= 0 인 경우 도메인 오류 또는 범위 오류가 발생할 수 있습니다.

|문제|반환 값|
|-----------|------------|
|x = ± 0|± INFINITY|
|x = 음의 정수|NaN|
|x =-INFINITY|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|도메인 오류|NaN|
|극 오류|± HUGE_VAL, ± HUGE_VALF 또는 ± HUGE_VALL|
|오버플로 범위 오류|± HUGE_VAL, ± HUGE_VALF 또는 ± HUGE_VALL|
|언더플로 범위 오류|반올림 후의 올바른 값|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C + +는 오버 로드를 허용 하기 때문에 **float** 및 **long** **double** 형식을 사용 하 고 반환 하는 **tgamma** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **tgamma** 는 항상 **double**을 사용 하 고 반환 합니다.

X가 자연수인 경우 이 함수는 (x-1)의 계승을 반환합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참조

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
