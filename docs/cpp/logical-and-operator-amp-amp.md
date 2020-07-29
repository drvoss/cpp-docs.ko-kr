---
title: 논리 AND 연산자:&amp;&amp;
description: C + + 표준 언어 논리 AND 연산자 구문 및를 사용 합니다.
ms.date: 07/23/2020
f1_keywords:
- '&&'
- and_cpp
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 431e76a2943c2373d6191f1fbe9f14c54cfaa6c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223696"
---
# <a name="logical-and-operator-ampamp"></a>논리 AND 연산자:&amp;&amp;

## <a name="syntax"></a>구문

> *식* **`&&`** *식*

## <a name="remarks"></a>설명

논리 AND 연산자 ( **&&** )는 **`true`** 두 피연산자가 모두 이면 **`true`** 를 반환 하 고 **`false`** 그렇지 않으면를 반환 합니다. 피연산자는 계산 전에 암시적으로 형식으로 변환 되 **`bool`** 고 결과는 형식입니다 **`bool`** . 논리 AND에는 왼쪽에서 오른쪽으로의 결합성이 있습니다.

논리 AND 연산자에 대 한 피연산자는 동일한 형식일 필요는 없지만 부울, 정수 계열 또는 포인터 형식이 있어야 합니다. 피연산자는 일반적으로 관계형 또는 동등 식입니다.

첫 번째 피연산자는 완전히 계산 되 고 모든 파생 작업이 완료 된 후에 논리적 AND 식의 계산이 계속 됩니다.

두 번째 피연산자는 첫 번째 피연산자가 **`true`** (0이 아닌 값)로 계산 되는 경우에만 평가 됩니다. 이 계산은 논리 AND 식이 인 경우 두 번째 피연산자의 불필요 한 평가를 제거 **`false`** 합니다. 다음 예제와 같이 이 단락(short-circuit) 계산을 사용하여 null 포인터 역참조를 방지할 수 있습니다.

```cpp
char *pch = 0;
// ...
(pch) && (*pch = 'a');
```

`pch`가 null(0)인 경우 식의 오른쪽이 계산되지 않습니다. 이 단락 계산은 null 포인터를 통해 할당을 불가능 하 게 만듭니다.

## <a name="operator-keyword-for-"></a> &&에 대 한 Operator 키워드

C + +는 **`and`** 의 대체 철자를 지정 합니다 **`&&`** . C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_Logical_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate logical AND
#include <iostream>

using namespace std;

int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b && b < c yields "
         << (a < b && b < c) << endl
         << "The false expression "
         << "a > b && b < c yields "
         << (a > b && b < c) << endl;
}
```

## <a name="see-also"></a>참고 항목

[C + + 기본 제공 연산자, 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 논리 연산자](../c-language/c-logical-operators.md)
