---
title: chars_format 열거형
ms.date: 07/22/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: 4c1d495c943be02b66d52d1986a783b29a8009c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230184"
---
# <a name="chars_format-enum"></a>chars_format 열거형

라이브러리와 함께 사용 되어 [\<charconv>](charconv.md) 기본 숫자 변환에 대 한 부동 소수점 형식을 지정 합니다.

## <a name="syntax"></a>구문

```cpp
enum class chars_format {
    scientific = unspecified,
    fixed = unspecified,
    hex = unspecified,
    general = fixed | scientific
};
```

### <a name="members"></a>멤버

|요소|설명|
|-|-|
| `scientific` | 에서 `from_chars()` 지 수를 예측 하 고 구문 분석 합니다. 이 `'e'` `printf()` 지정자는와 같은 과학적 표기법의 형식을 지정 하는 서식 지정자와 같습니다.`"1.729e+01"` |
| `fixed` | `from_chars()`는 지 수를 예측 하거나 구문 분석 하지 않습니다. `'f'` `printf()` 과 같은 부동 소수점 형식을 지정 하는 서식 지정자와 비슷합니다 `"17.29"` .|
| `hex` | 는 `from_chars()` 앞에 "0x"가 없는 16 진수 형식의 수를 표시 합니다. |
| `general` | `from_chars()`에서 지수가 허용 되지만 필요 하지는 않습니다. 의 경우 `to_chars()` 이는 `g` 과학적 표기법 또는 fixed로 전환 되는 printf () 서식 지정자와 비슷합니다. 합리적인 출력을 생성할 수 있도록 지수가 무엇 인지 고려 합니다. 예: `1e-5` 의 결과 `"1e-05"` 는 이지만이 `1e-4` 발생 `"0.001"` 합니다. `1e5`에서 결과 `100000` 를 반환 `1e6` `1e+06` 합니다. `1e0``1`을 생성 합니다.|

## <a name="remarks"></a>설명

[From_chars](charconv-functions.md#from_chars) 함수의 경우이 열거형은 필요한 입력의 종류를 설명 합니다.
[To_chars](charconv-functions.md#to_chars) 함수의 경우 내보낼 출력의 종류를 설명 합니다.

## <a name="see-also"></a>참고 항목

[\<charconv>](../standard-library/charconv.md)  
[printf () 서식 지정자](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
