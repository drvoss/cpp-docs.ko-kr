---
title: '같음 연산자: == 및 !='
description: C + + 표준 언어는 동일 하 고 같지 않음 연산자 구문과 함께 사용 됩니다.
ms.date: 07/23/2020
f1_keywords:
- '!='
- ==
- not_eq_cpp
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 567b83e99dce0354626f08a4788f1343314493b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227545"
---
# <a name="equality-operators--and-"></a>같음 연산자: == 및 !=

## <a name="syntax"></a>구문

> *식* **`==`** *식*\
> *식* **`!=`** *식*

## <a name="remarks"></a>설명

이항 같음 연산자는 피연산자를 비교하여 완전히 같은지 아니면 같지 않은지를 확인합니다.

같음 연산자 ( **`==`** )와 같지 않음 ()은 **`!=`** 관계 연산자 보다 우선 순위가 낮지만 비슷하게 동작 합니다. 이러한 연산자의 결과 형식은 **`bool`** 입니다.

같음 연산자 ( **`==`** )는 **`true`** 두 피연산자의 값이 같으면를 반환 하 고 그렇지 않으면를 반환 **`false`** 합니다. 같지 않음 연산자 ( **`!=`** )는 피연산자의 값이 같지 않으면를 반환 하 고 그렇지 않으면를 **`true`** 반환 **`false`** 합니다.

## <a name="operator-keyword-for-"></a>! =의 Operator 키워드

C + +는 **`not_eq`** 의 대체 철자를 지정 합니다 **`!=`** . (에 대 한 대체 철자는 없습니다 **`==`** .) C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

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

같음 연산자는 동일한 형식의 멤버에 대한 포인터를 비교할 수 있습니다. 이러한 비교에서는 멤버 포인터 변환이 수행 됩니다. 멤버에 대한 포인터를 0으로 계산되는 상수 식과 비교할 수도 있습니다.

## <a name="see-also"></a>참고 항목

[이항 연산자로 구성된 식](../cpp/expressions-with-binary-operators.md)<br/>
[C + + 기본 제공 연산자, 우선 순위; 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 관계 및 같음 연산자](../c-language/c-relational-and-equality-operators.md)
