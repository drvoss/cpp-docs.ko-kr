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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 92e3a744ef8069d45733c06b7a2681905c3eab55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338586"
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

성공하면 [fegetround에서](fegetround-fesetround2.md)보고한 현재 반올림 형식을 사용하여 x를 가장 가까운 정수로 반올림합니다. *x* 그렇지 않은 경우에는 함수가 다음 값 중 하나를 반환할 수 있습니다.

|문제|반환 값|
|-----------|------------|
|*x* = ±무한대|±무한대, 수정되지 않은|
|*x* = ±0|±0, 수정되지 않은|
|*x* = NaN|NaN|

오류는 [_matherr](matherr.md)통해 보고되지 않습니다. 특히 이 함수는 **FE_INEXACT** 예외를 보고하지 않습니다.

## <a name="remarks"></a>설명

이 함수와 [rint의](rint-rintf-rintl.md) 주요 차이점은 이 함수가 부정확한 부동 점 예외를 발생시키지 않는다는 것입니다.

최대 부동 소수점 값은 정확한 정수이므로 이 함수 자체는 오버플로되지 않으며, 사용하는 함수의 버전에 따라 출력이 반환 값을 오버플로할 수는 있습니다.

C++는 오버로드를 허용하므로 **플로트** 또는 **긴** **이중** 매개변수를 가져가고 반환하는 **nearbyint의** 오버로드를 호출할 수 있습니다. C 프로그램에서 **nearbyint는** 항상 두 개의 이중 값을 취하고 이중 값을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**인근,** **인근intf,** **인근intl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[수학식 및 부동 소수점 지원](../floating-point-support.md)<br/>
