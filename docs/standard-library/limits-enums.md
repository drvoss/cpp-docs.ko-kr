---
title: '&lt;limits&gt; 열거형'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425612"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt; 열거형

## <a name="float_denorm_style"></a>float_denorm_style

이 열거형은 구현에서 비정규화된 부동 소수점 값(너무 작아서 정규화된 값으로 나타낼 수 없는 값)을 나타내기 위해 선택할 수 있는 다양한 메서드를 설명합니다.

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Return Value

이 열거형은 다음을 반환합니다.

- 변환 시 비 정규화 된 형식이 있는지 여부를 확인할 수 없는 경우 `denorm_indeterminate` 합니다.

- 비 정규화 된 형식이 없으면를 `denorm_absent` 합니다.

- 비 정규화 된 형식이 있는 경우 `denorm_present` 합니다.

### <a name="example"></a>예제

이 열거형의 값에 액세스할 수 있는 예제는 [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm)을 참조하세요.

## <a name="float_round_style"></a>float_round_style

이 열거형은 구현에서 부동 소수점 값을 정수 값으로 반올림하기 위해 선택할 수 있는 다양한 메서드를 설명합니다.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Return Value

이 열거형은 다음을 반환합니다.

- 반올림 메서드를 확인할 수 없는 경우 `round_indeterminate` 합니다.

- 0에 대 한 반올림을 `round_toward_zero` 합니다.

- 가장 가까운 정수로 반올림 하는 경우 `round_to_nearest` 합니다.

- 이 0에서 벗어나면를 `round_toward_infinity` 합니다.

- 가 보다 음의 정수로 반올림 되는 경우 `round_toward_neg_infinity` 합니다.

### <a name="example"></a>예제

이 열거형의 값에 액세스할 수 있는 예제는 [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style)을 참조하세요.
