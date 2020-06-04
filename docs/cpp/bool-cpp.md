---
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: db246cda79c778f37c5afbfda4a68c191c474e12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190497"
---
# <a name="bool-c"></a>bool (C++)

이 키워드는 기본 제공 형식입니다. 이 형식의 변수는 [true](../cpp/true-cpp.md) 및 [false](../cpp/false-cpp.md)값을 가질 수 있습니다. 조건식의 형식은 **bool** 이며 **bool**형식의 값을 포함 합니다. 예를 들어 `i!=0` `i`의 값에 따라 TRUE 또는 FALSE가 됩니다.

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): 후 위 또는 전위 증가 또는 감소 연산자의 피연산자는 **bool**형식일 수 없습니다. 즉, **bool**형식의 변수 `b` 지정 된 경우 이러한 식은 더 이상 허용 되지 않습니다.

```cpp
    b++;
    ++b;
    b--;
    --b;
```

TRUE 및 FALSE 값의 관계는 다음과 같습니다.

```cpp
!false == true
!true == false
```

다음 문에서

```cpp
if (condexpr1) statement1;
```

`condexpr1` TRUE 이면 `statement1` 항상 실행 됩니다. `condexpr1` FALSE 이면 `statement1` 실행 되지 않습니다.

후 위 또는 접두사 **++** 연산자를 **bool**형식의 변수에 적용 하면 변수가 TRUE로 설정 됩니다.
**Visual Studio 2017 버전 15.3 이상**: **bool** 의 operator + +는 언어에서 제거 되었으며 더 이상 지원 되지 않습니다.

후 위 또는 접두사 **--** 연산자를이 형식의 변수에 적용할 수 없습니다.

**Bool** 형식은 정수 계열 확장에 참여 합니다. **Bool** 형식의 r 값은 **int**형식의 r 값으로 변환 될 수 있으며 FALSE는 0이 되 고 TRUE는 1이 됩니다. 고유 형식으로 서, **bool** 은 오버 로드 확인에 참여 합니다.

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[기본 제공 형식](../cpp/fundamental-types-cpp.md)
