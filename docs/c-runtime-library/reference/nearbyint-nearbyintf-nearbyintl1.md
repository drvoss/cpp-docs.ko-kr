---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 4/2/2020
api_name:
- nearbyint
- nearbyintf
- nearbyintl
- _o_nearbyint
- _o_nearbyintf
- _o_nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: d9e7adb321d85c728c5185c1663fd7f945fc4a82
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914572"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

지정된 부동 소수점 값을 정수로 반올림하고 부동 소수점 형식으로 해당 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
반올림할 값입니다.

## <a name="return-value"></a>Return Value

성공 하면 [fegetround](fegetround-fesetround2.md)에서 보고 하는 현재 반올림 형식을 사용 하 여 가장 가까운 정수로 반올림 된 *x*를 반환 합니다. 그렇지 않은 경우에는 함수가 다음 값 중 하나를 반환할 수 있습니다.

|문제|반환 값|
|-----------|------------|
|*x* = ± INFINITY|± INFINITY, 수정 되지 않음|
|*x* = ± 0|± 0, 수정 되지 않음|
|*x* = NaN|NaN|

[_Matherr](matherr.md)를 통해 오류를 보고 하지 않습니다. 특히이 함수는 **FE_INEXACT** 예외를 보고 하지 않습니다.

## <a name="remarks"></a>설명

이 함수와 [rint](rint-rintf-rintl.md) 의 주요 차이점은이 함수는 부정확 한 부동 소수점 예외를 발생 시 키 지 않는다는 것입니다.

최대 부동 소수점 값은 정확한 정수이므로 이 함수 자체는 오버플로되지 않으며, 사용하는 함수의 버전에 따라 출력이 반환 값을 오버플로할 수는 있습니다.

C + +에서는 오버 로드를 허용 하므로 **float** 또는 **long** **double** 매개 변수를 사용 하 고 반환 하는 **nearbyint** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **nearbyint** 은 항상 두 개의 double 값을 사용 하 고 double 값을 반환 합니다.

기본적으로이 함수의 전역 상태는 응용 프로그램으로 범위가 지정 됩니다. 이를 변경 하려면 [CRT의 전역 상태](../global-state.md)를 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참조

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[수학식 및 부동 소수점 지원](../floating-point-support.md)<br/>
