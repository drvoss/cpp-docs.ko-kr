---
title: '1&#39;개의 보수 연산자: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 777f253925caf38647863bdaa93fde8d5a03e3f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177718"
---
# <a name="one39s-complement-operator-"></a>1&#39;개의 보수 연산자: ~

## <a name="syntax"></a>구문

```
~ cast-expression
```

## <a name="remarks"></a>설명

"비트 보수" 연산자라고도 하는 1의 보수 연산자(`~`)는 해당 피연산자의 비트 1의 보수를 생성합니다. 즉, 피연산자의 1인 모든 비트는 결과적으로 0입니다. 반대로 피연산자의 0인 모든 비트는 결과적으로 1입니다. 1의 보수 연산자의 피연산자는 정수 계열 형식이어야 합니다.

## <a name="operator-keyword-for-"></a>~에 대한 연산자 키워드

**Compl** 연산자는 `~`에 해당 하는 텍스트입니다. 프로그램에서 **compl** 연산자에 액세스 하는 두 가지 방법이 있습니다. 헤더 파일 `iso646.h`포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md)를 사용 하 여 컴파일합니다.

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

정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 승격을 수행 하는 방법에 대 한 자세한 내용은 [표준 변환](standard-conversions.md) 을 참조 하세요.

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)
