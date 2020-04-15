---
title: log1p, log1pf, log1pl2
ms.date: 4/2/2020
api_name:
- log1p
- log1pf
- log1pl
- _o_log1p
- _o_log1pf
- _o_log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: b4e077f5b806dbe38ed4a4f4e8eef0259170cb7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341805"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

1을 더한 지정된 값의 자연 로그를 계산합니다.

## <a name="syntax"></a>구문

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 인수입니다.

## <a name="return-value"></a>Return Value

*성공하면(x* + 1)의 자연(기본-e) 로그를 반환합니다.*e*

그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.

|입력|결과|SEH 예외|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Denormals|입력과 같음|UNDERFLOW||
|±0|입력과 같음|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|입력과 같음|INVALID||
|±QNaN, 무기한|입력과 같음|||

**errno** 값은 *x* = -1인 경우 ERANGE로 설정됩니다. *x* < 경우 **errno** 값은 **EDOM으로** 설정됩니다.

## <a name="remarks"></a>설명

**log1p** 함수는 *x가* 0에 `log(x + 1)` 가까면 사용하는 것보다 더 정확할 수 있습니다.

C++는 오버로드를 허용하므로 **플로트** 및 **긴** 이중 형식을 가져 와서 반환하는 **log1p의** 오버로드를 호출할 수 **있습니다.** C 프로그램에서 **log1p는** 항상 **double을**가져와 반환합니다.

*x가* 자연스러운 숫자인 경우 이 함수는 *(x* - 1)의 계수의 로거리헴을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
