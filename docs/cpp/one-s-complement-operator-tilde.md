---
title: '1의 보수 연산자: ~'
description: C + + 표준 언어 one의 보수 연산자 구문 및 사용.
ms.date: 07/23/2020
f1_keywords:
- "~"
- compl_cpp
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 89c67855cd67df2af315cea941b487e7462889b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227246"
---
# <a name="ones-complement-operator-"></a>1의 보수 연산자: ~

## <a name="syntax"></a>구문

```cpp
~ cast-expression
```

## <a name="remarks"></a>설명

비트 보수 연산자 라고도 하는 1의 보수 연산자 ( **`~`** )는 해당 피연산자에 대 한 비트 1의 보수를 생성 합니다. *bitwise complement* 즉, 피연산자의 1인 모든 비트는 결과적으로 0입니다. 반대로 피연산자의 0인 모든 비트는 결과적으로 1입니다. 1의 보수 연산자의 피연산자는 정수 계열 형식이어야 합니다.

## <a name="operator-keyword-for-"></a>~의 Operator 키워드

C + +는 **`compl`** 의 대체 철자를 지정 합니다 **`~`** . C에서 대체 철자는 헤더에 매크로로 제공 됩니다 \<iso646.h> . C + +에서 대체 철자는 키워드입니다. \<iso646.h>또는이에 해당 하는 c + +는 사용 \<ciso646> 되지 않습니다. Microsoft c + +에서 [`/permissive-`](../build/reference/permissive-standards-conformance.md) 또는 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션은 대체 철자를 사용 하도록 설정 하는 데 필요 합니다.

## <a name="example"></a>예제

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

이 예제에서 `y`에 할당된 새 값은 부호 없는 값인 0xFFFF의 1의 보수이거나 0x0000입니다.

정수 계열 확장은 정수 계열 피연산자를 대상으로 수행됩니다. 피연산자가 승격 되는 형식은 결과 형식입니다. 정수 계열 확장에 대 한 자세한 내용은 [표준 변환](standard-conversions.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](expressions-with-unary-operators.md)<br/>
[C + + 기본 제공 연산자, 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)
