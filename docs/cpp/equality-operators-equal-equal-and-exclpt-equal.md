---
title: '같음 연산자: == 및 !='
ms.date: 11/04/2016
f1_keywords:
- '!='
- ==
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 8a0c08f438528caeaac6d5e52e806a36fe56dd25
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189249"
---
# <a name="equality-operators--and-"></a>같음 연산자: == 및 !=

## <a name="syntax"></a>구문

```
expression == expression
expression != expression
```

## <a name="remarks"></a>주의

이항 같음 연산자는 피연산자를 비교하여 완전히 같은지 아니면 같지 않은지를 확인합니다.

같음 연산자에는 같음(`==`)과 같지 않음(`!=`)이 있으며 이러한 연산자는 관계형 연산자보다 우선 순위가 낮지만 비슷하게 동작합니다. 이러한 연산자의 결과 형식은 **bool**입니다.

같음 연산자 (`==`)는 두 피연산자의 값이 같으면 **true** (1)를 반환 합니다. 그렇지 않으면 **false** (0)를 반환 합니다. 같지 않음 연산자 (`!=`)는 피연산자의 값이 같지 않으면 **true** 를 반환 하 고, 그렇지 않으면 **false**를 반환 합니다.

## <a name="operator-keyword-for-"></a>!=에 대한 연산자 키워드

`not_eq` 연산자는 `!=`에 해당하는 텍스트입니다. 프로그램에서 `not_eq` 연산자에 액세스 하는 방법에는 헤더 파일 `iso646.h`포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장 사용 안 함) 컴파일러 옵션으로 컴파일하는 두 가지 방법이 있습니다.

## <a name="example"></a>예제

```cpp
// expre_Equality_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << boolalpha
         << "The true expression 3 != 2 yields: "
         << (3 != 2) << endl
         << "The false expression 20 == 10 yields: "
         << (20 == 10) << endl;
}
```

같음 연산자는 동일한 형식의 멤버에 대한 포인터를 비교할 수 있습니다. 이러한 비교에서는 멤버 포인터 변환(멤버 포인터 변환 참조)이 수행됩니다. 멤버에 대한 포인터를 0으로 계산되는 상수 식과 비교할 수도 있습니다.

## <a name="see-also"></a>참고 항목

[이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 관계 및 같음 연산자](../c-language/c-relational-and-equality-operators.md)
