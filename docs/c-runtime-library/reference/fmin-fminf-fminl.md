---
title: fmin, fminf, fminl
ms.date: 04/05/2018
api_name:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: d6cd16c298c3f4bedb8064d66efd2d4bbe20c22b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216988"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

지정된 두 값 중 더 작은 값을 확인합니다.

## <a name="syntax"></a>구문

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
비교할 첫 번째 값입니다.

*x.y*<br/>
비교할 두 번째 값입니다.

## <a name="return-value"></a>Return Value

성공 하면 *x* 또는 *y*중 더 작은 값을 반환 합니다.

|입력|결과|
|-----------|------------|
|*x* 는 NaN입니다.|*x.y*|
|*y* 는 NaN입니다.|*x*|
|*x* 및 *y* 는 NaN입니다.|NaN|

함수는 [_matherr](matherr.md) 호출 되거나 부동 소수점 예외를 발생 시키거나 **errno**의 값을 변경 하지 않습니다.

## <a name="remarks"></a>설명

C + +에서는 오버 로드를 허용 하므로 및 형식을 사용 하 고 반환 하는 **fmin** 의 오버 로드를 호출할 수 있습니다 **`float`** **`long double`** . C 프로그램에서 **fmin** 은 항상를 사용 하 고 반환 **`double`** 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C\<math.h><br />C + +: \<math.h> 또는\<cmath>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
