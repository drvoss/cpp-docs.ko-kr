---
title: '논리 OR 연산자: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 94b2bc024dd7223ac7adacc72924f5ee289bab37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178082"
---
# <a name="logical-or-operator-"></a>논리 OR 연산자: ||

## <a name="syntax"></a>구문

> 논리적 *or 식* **||** *논리적 and 식*

## <a name="remarks"></a>주의

논리 OR 연산자 ( **||** )는 두 피연산자 중 하나 또는 둘 다가 true 이면 부울 값 TRUE를 반환 하 고 그렇지 않으면 FALSE를 반환 합니다. 피연산자는 계산 전에 암시적으로 **bool** 형식으로 변환 되며 결과는 **bool**형식입니다. 논리 OR은 왼쪽에서 오른쪽으로의 결합성을 가집니다.

논리 OR 연산자의 피연산자는 동일한 형식일 필요는 없지만 정수 계열 또는 포인터 형식이어야 합니다. 피연산자는 일반적으로 관계형 또는 동등 식입니다.

첫 번째 피연산자가 완전히 계산되고 모든 파생 작업이 완료된 후에 논리 OR 계산이 시작됩니다.

두 번째 피연산자는 첫 번째 피연산자가 false(0)인 경우에만 계산됩니다. 이는 논리 OR 식이 true일 때 두 번째 피연산자를 불필요하게 계산하지 않게 합니다.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

위의 예제에서 `x`가 `w`, `y` 또는 `z`와 같을 경우 `printf` 함수에 대한 두 번째 인수는 true로 계산되고 값 1이 출력됩니다. 그렇지 않으면 false로 계산되고 값 0이 출력됩니다. 조건 중 하나가 true로 확인되면 계산이 중지됩니다.

## <a name="operator-keyword-for-124124"></a>의 Operator 키워드&#124;&#124;

**Or** 연산자는 **||** 에 해당 하는 텍스트입니다. 프로그램에서 **또는** 연산자에 액세스 하는 방법에는 두 가지가 있습니다. iso646 > \<헤더 파일을 포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장 사용 안 함) 컴파일러 옵션을 사용 하 여 컴파일합니다.

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

[C++기본 제공 연산자 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 논리 연산자](../c-language/c-logical-operators.md)
