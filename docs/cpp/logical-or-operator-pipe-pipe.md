---
title: '논리적 OR 연산자:  &#124;&#124;'
description: C + + 표준 언어 논리 OR 연산자 구문 및를 사용 합니다.
ms.date: 07/23/2020
f1_keywords:
- '||'
- or_cpp
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 1845aef59f88d5dd044cefedd21cb618e1102e13
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225997"
---
# <a name="logical-or-operator-124124"></a>논리적 OR 연산자:  &#124;&#124;

## <a name="syntax"></a>구문

> *논리적 or 식* **`||`** *논리 and 식*

## <a name="remarks"></a>설명

논리 OR 연산자 ( **`||`** )는 **`true`** 두 피연산자 중 하나 또는 둘 다 이면 부울 값을 반환 **`true`** 하 고 그렇지 않으면을 반환 합니다 **`false`** . 피연산자는 계산 전에 암시적으로 형식으로 변환 되 **`bool`** 고 결과는 형식입니다 **`bool`** . 논리 OR은 왼쪽에서 오른쪽으로의 결합성을 가집니다.

논리 OR 연산자에 대 한 피연산자는 동일한 형식일 필요는 없지만 부울, 정수 계열 또는 포인터 형식 이어야 합니다. 피연산자는 일반적으로 관계형 또는 동등 식입니다.

첫 번째 피연산자가 완전히 계산되고 모든 파생 작업이 완료된 후에 논리 OR 계산이 시작됩니다.

두 번째 피연산자는 첫 번째 피연산자가로 계산 되는 경우에만 계산 됩니다 **`false`** . 논리 OR 식이 이면 평가가 필요 하지 않기 때문입니다 **`true`** . 이를 *단락* 평가 라고 합니다.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

위의 예제에서 `x` 가, 또는와 같을 경우 `w` `y` `z` 함수에 대 한 두 번째 인수는 `printf` 로 계산 되 고 **`true`** ,이 값은 정수로 승격 되 고 값 1이 출력 됩니다. 그렇지 않으면로 계산 **`false`** 되 고 값 0이 출력 됩니다. 조건 중 하나가로 확인 되 면 **`true`** 계산이 중지 됩니다.

## <a name="operator-keyword-for-124124"></a> &#124;&#124;에 대 한 Operator 키워드

C + +는 **`or`** 의 대체 철자를 지정 합니다 **`||`** . C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>참고 항목

[C + + 기본 제공 연산자, 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 논리 연산자](../c-language/c-logical-operators.md)
