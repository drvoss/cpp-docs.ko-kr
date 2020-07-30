---
title: '논리 부정 연산자: !'
description: C + + 표준 언어 논리 부정 연산자 구문 및를 사용 합니다.
ms.date: 07/23/2020
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: fdd2e7a71b791375f898372d058a5eeb2afc59f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223683"
---
# <a name="logical-negation-operator-"></a>논리 부정 연산자: !

## <a name="syntax"></a>구문

> **`!`***cast 식*

## <a name="remarks"></a>설명

논리 부정 연산자 ( **`!`** )는 피연산자의 의미를 반대로 합니다. 피연산자는 산술 형식, 포인터 형식 또는 산술/포인터 형식으로 계산되는 식이어야 합니다. 피연산자는 암시적으로 형식으로 변환 됩니다 **`bool`** . 변환 된 피연산자가 이면 결과는이 **`true`** **`false`** 고, 변환 된 **`false`** 피연산자가 이면입니다 **`true`** . 결과는 형식입니다 **`bool`** .

식의 경우 `e` 단항 식은 `!e` `(e == 0)` 오버 로드 된 연산자가 포함 된 경우를 제외 하 고는 식과 같습니다.

## <a name="operator-keyword-for-"></a>!의 Operator 키워드

C + +는 **`not`** 의 대체 철자를 지정 합니다 **`!`** . C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)<br/>
