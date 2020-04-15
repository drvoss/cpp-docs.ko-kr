---
title: lgamma, lgammaf, lgammal
ms.date: 4/2/2020
api_name:
- lgamma
- lgammaf
- lgammal
- _o_lgamma
- _o_lgammaf
- _o_lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: e2bdfbeac7b995be0b589156437a3ded39114adf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342157"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

지정된 값에 대한 감마 함수 절대 값의 자연 로그를 확인합니다.

## <a name="syntax"></a>구문

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
계산할 값입니다.

## <a name="return-value"></a>Return Value

성공하면 *x.* 감마 함수의 절대 값의 자연 로그릿헴을 반환합니다.

|문제|반환 값|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+INFINITY|
|*x*= 음수 정수|+INFINITY|
|±무한대|+INFINITY|
|극 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF 또는 ±HUGE_VALL|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

C++는 오버로드를 허용하므로 **플로트** 및 **긴** 이중 형식을 가져가서 반환하는 **lgamma의** 오버로드를 호출할 수 **있습니다.** C 프로그램에서 **lgamma는** 항상 **이중을**가져와 반환합니다.

x가 합리 숫자인 경우 이 함수는 (x - 1)의 계수의 로거리헴을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**lgamma,** **lgammaf,** **lgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
