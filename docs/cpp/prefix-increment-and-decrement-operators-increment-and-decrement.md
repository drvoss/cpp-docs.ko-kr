---
title: '접두사 증가 및 감소 연산자: ++ 및 --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
ms.openlocfilehash: ce066a3349d56b278739f586fe851b020da78885
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366215"
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>접두사 증가 및 감소 연산자: ++ 및 --

## <a name="syntax"></a>구문

```
++ unary-expression
-- unary-expression
```

## <a name="remarks"></a>설명

접두사 증분 연산자 ()**++** 는 해당 방사체에 하나를 추가합니다. 이 증분 값은 식의 결과입니다. 진연은 형식 **const가**아닌 l 값이어야 합니다. 결과는 피연산자와 동일한 형식의 l-value입니다.

접두사 감소 연산자 ()**--** 는 픽스처 증분 연산자와 유사하지만, 진부한 생성물은 하나에 의해 감소되고 그 결과는 이 감소값입니다.

**Visual Studio 2017 버전 15.3** [이상(/std:c++17](../build/reference/std-specify-language-standard-version.md)사용 가능): 증분 또는 감소 연산자의 사용자는 **bool**형식이 아닐 수 있습니다.

전위 및 후위 증가 및 감소 연산자는 피연산자에 영향을 줍니다. 두 처리자의 주요 차이점은 식의 계산에서 증가 또는 감소가 수행되는 순서입니다. 자세한 내용은 [후두점 증분 및 감산 연산자](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)를 참조하십시오. 접두사 양식에서 값이 식 평가에 사용되기 전에 증분 또는 감소가 수행되므로 식의 값이 발화값과 다릅니다. 후위 형식에서는 식 계산에서 값이 사용된 후에 증가 또는 감소가 발생하므로 식 값은 피연산자 값과 동일합니다. 예를 들어 다음 프로그램은 "`++i = 6`"을 인쇄합니다.

```cpp
// expre_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   int i = 5;
   cout << "++i = " << ++i << endl;
}
```

정수 계열 또는 부동 형식의 피연산자는 정수 값 1만큼 증가하거나 감소합니다. 결과 형식은 피연산자 형식과 동일합니다. 포인터 형식의 피연산자는 자신이 처리하는 개체의 크기만큼 증가하거나 감소합니다. 증가한 포인터는 다음 개체를 가리키고, 감소한 포인터는 이전 개체를 가리킵니다.

증분 및 감소 연산자는 부작용이 있기 때문에 [프로세서 전매크로에서](../preprocessor/macros-c-cpp.md) 증분 또는 감소 연산자가 있는 식을 사용하면 바람직하지 않은 결과를 만들 수 있습니다. 다음 예를 살펴보세요.

```cpp
// expre_Increment_and_Decrement_Operators2.cpp
#define max(a,b) ((a)<(b))?(b):(a)

int main()
{
   int i = 0, j = 0, k;
   k = max( ++i, j );
}
```

매크로는 다음과 같이 확장됩니다.

```cpp
k = ((++i)<(j))?(j):(++i);
```

`i`가 `j`보다 크거나 같거나 `j`보다 1만큼 작은 경우 두 번 증가합니다.

> [!NOTE]
> 이곳에서 설명한 것과 같은 부작용을 제거하고 언어를 사용하여 보다 완벽한 형식 검사를 수행할 수 있기 때문에 대부분 매크로보다는 C++ 인라인 함수를 사용하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[접두사 증가 및 감소 연산자](../c-language/prefix-increment-and-decrement-operators.md)
