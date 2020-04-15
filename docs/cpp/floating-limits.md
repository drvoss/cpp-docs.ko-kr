---
title: 부동 한계
ms.date: 08/03/2018
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
ms.openlocfilehash: ccd395eef319e57cecffad8a5278b6df1397f4cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373374"
---
# <a name="floating-limits"></a>부동 한계

**마이크로소프트 특정**

다음 표에는 부동 소수점 상수의 값에 대한 제한이 나와 있습니다. 이러한 제한은 표준 헤더 파일 \<float.h> 정의됩니다.

## <a name="limits-on-floating-point-constants"></a>부동 소수점 상수에 대한 제한

|상수|의미|값|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|소수 자릿수가 q인 부동 소수점 수가 부동 소수점 표현으로 반올림되고 정밀도의 손실 없이 다시 복원될 수 있는 자릿수 q입니다.|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|x + 1.0이 1.0과 같지 않은 가장 작은 양수 x입니다.|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|부동 소수점 significand에 의해 `FLT_RADIX` 지정된 방사형의 숫자수입니다. 방사상은 2; 따라서 이러한 값은 비트를 지정합니다.|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|최대 표현 가능한 부동 소수점 번호입니다.|3.402823466e+38F<br/>1.7976931348623158e+308<br/>1.7976931348623158e+308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|최대 정수는 10을 해당 숫자로 올리도록 하는 것이 표현 가능한 부동 소수점 번호입니다.|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|해당 숫자로 상승된 `FLT_RADIX` 최대 정수는 표현 가능한 부동 소수점 번호입니다.|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|최소 양수 값입니다.|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|최소 음수 정수(10)가 해당 숫자로 상승하도록 하면 부동 소수점 수를 나타낼 수 있습니다.|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|해당 숫자로 상승된 `FLT_RADIX` 최소 음수 정수는 표현 가능한 부동 소수점 번호입니다.|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|지수를 표현하는 기수입니다.|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|부동 점 추가를위한 반올림 모드.|1(근사값)<br/>1(근사값)<br/>1(근사값)|

> [!NOTE]
> 표의 정보는 제품의 이후 버전에서 달라질 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[정수 제한](../cpp/integer-limits.md)
