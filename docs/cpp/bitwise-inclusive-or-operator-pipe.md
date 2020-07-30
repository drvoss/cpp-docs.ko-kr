---
title: '포괄적 비트 OR 연산자: &#124;'
description: C + + 표준 언어 비트 포함 OR 연산자 구문 및를 사용 합니다.
ms.date: 07/23/2020
f1_keywords:
- '|'
- bitor_cpp
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 76f80c2101b3acfac71dc4d8ad1be4a999f69aa5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229092"
---
# <a name="bitwise-inclusive-or-operator-124"></a>포괄적 비트 OR 연산자: &#124;

## <a name="syntax"></a>구문

> *expression1* **`|`** *expression2*

## <a name="remarks"></a>설명

비트 포함 OR 연산자 ( **`|`** )는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교 합니다. 어느 한쪽 비트가 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.

연산자에 대 한 두 피연산자는 정수 계열 형식 이어야 합니다. [표준 변환](standard-conversions.md) 에서 다루는 일반적인 산술 변환은 피연산자에 적용 됩니다.

## <a name="operator-keyword-for-124"></a>&#124;에 대 한 Operator 키워드

C + +는 **`bitor`** 의 대체 철자를 지정 합니다 **`|`** . C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>참고 항목

[C + + 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 비트 연산자](../c-language/c-bitwise-operators.md)
