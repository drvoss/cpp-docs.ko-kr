---
title: '간접 참조 연산자: *'
ms.date: 11/04/2016
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
ms.openlocfilehash: 8f27cfd943455d52b04c41ef2d2d83e6e03a84c0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178281"
---
# <a name="indirection-operator-"></a>간접 참조 연산자: *

## <a name="syntax"></a>구문

```
* cast-expression
```

## <a name="remarks"></a>주의

단항 간접 참조 연산자 (<strong>\*</strong>)는 포인터를 역참조 합니다. 즉, 포인터 값을 l-value로 변환 합니다. 간접 연산자의 피연산자는 형식에 대한 포인터여야 합니다. 간접 참조의 결과는 포인터 형식이 파생된 형식입니다. 이 컨텍스트에서 <strong>\*</strong> 연산자를 사용 하는 것은 이항 연산자 (곱하기)와는 다릅니다.

피연산자가 함수를 가리키는 경우 결과는 함수 지정자입니다. 스토리지 위치를 가리키는 경우 결과는 스토리지 위치를 지정하는 l-value입니다.

포인터에 대한 포인터를 역참조하기 위해 간접 참조 연산자를 누적하여 사용할 수도 있습니다. 예를 들면 다음과 같습니다.

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

포인터 값이 잘못된 경우 결과가 정의되지 않습니다. 다음 목록은 포인터 값을 무효화하는 가장 일반적인 조건의 일부입니다.

- 포인터가 null 포인터입니다.

- 포인터가 참조 시 표시되지 않는 로컬 항목의 주소를 지정합니다.

- 포인터가 가리키는 개체의 형식에 대해 부적절하게 정렬된 주소를 지정합니다.

- 포인터가 실행 중인 프로그램에서 사용되지 않는 주소를 지정합니다.

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[주소 연산자: &](../cpp/address-of-operator-amp.md)<br/>
[연산자 주소 및 간접 참조](../c-language/indirection-and-address-of-operators.md)
