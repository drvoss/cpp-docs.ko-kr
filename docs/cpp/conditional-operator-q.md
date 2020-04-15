---
title: '조건부 연산자: &quest; :'
ms.date: 11/04/2016
f1_keywords:
- '?:'
- '?'
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
ms.openlocfilehash: 4ba4c80d40450fd5975b047a1a4fca63146c5773
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337258"
---
# <a name="conditional-operator-quest-"></a>조건부 연산자: &quest; :

## <a name="syntax"></a>구문

```
expression ? expression : expression
```

## <a name="remarks"></a>설명

조건부 연산자 **(: :**) 는 삼차 연산자입니다 (세 개의 나연이 걸립니다). 조건 연산자는 다음과 같이 사용됩니다.

- 첫 번째 오연산은 암시적으로 **bool로**변환됩니다. 계속하기 전에 피연산자가 계산되고 의도하지 않은 모든 결과가 완료됩니다.

- 첫 번째 피연산이 **true** true(1)로 평가되면 두 번째 피연산이 평가됩니다.

- 첫 번째 피연산이 **false** false(0)로 평가되면 세 번째 피연산이 평가됩니다.

조건 연산자의 결과는 두 번째 또는 세 번째 피연산자가 계산된 결과입니다. 마지막 피연산자 2개 중 1개만 조건식에서 계산됩니다.

조건식은 오른쪽과 왼쪽이 연결되어 있습니다. 첫 번째 피연산자는 정수 계열 또는 포인터 형식이어야 합니다. 다음 규칙이 두 번째 피연산자와 세 번째 피연산자에 적용됩니다.

- 두 피연산자의 형식이 동일할 경우 결과도 해당 형식입니다.

- 두 피연산자가 산술 또는 열거 형인 경우 일반적인 산술 [변환(표준 변환에서](standard-conversions.md)다루어도 있음)이 수행되어 공통 유형으로 변환됩니다.

- 두 피연산자가 모두 포인터 형식이거나 하나는 포인터 형식이고 나머지 하나는 0으로 계산된 상수 식일 경우 공용 형식으로 변환하기 위해 포인터 변환이 수행됩니다.

- 두 피연산자가 모두 참조 형식일 경우 공용 형식으로 변환하기 위해 참조 변환이 수행됩니다.

- 두 피연산자가 모두 void 형식일 경우 공용 형식이 void 형식입니다.

- 두 피연산자의 형식이 동일한 사용자 정의 형식인 경우 공통 형식이 해당 형식입니다.

- 피연산자의 형식이 다르고 피연산자 중 하나 이상의 형식이 사용자 지정 형식인 경우 공통 형식을 결정하기 위한 언어 규칙이 사용됩니다. 아래의 경고를 참조하세요.

위의 목록에 없는 두 번째 피연산자와 세 번째 피연산자의 조합은 부적합합니다. 결과의 형식은 공용 형식이며, 두 번째 피연산자와 세 번째 피연산자가 같은 형식이고 둘 다 l-value일 경우 l-value입니다.

> [!WARNING]
> 두 번째와 세 번째 피연산자의 형식이 같지 않으면 C++ 표준에 지정된 복합 형식 변환 규칙이 호출됩니다. 이러한 변환이 수행되면 임시 개체 생성 및 제거를 비롯한 예기치 않은 동작이 발생할 수 있습니다. 그러므로 조건부 연산자와 함께 사용자 정의 형식을 피연산자로 사용하지 않거나, 사용자 정의 형식을 사용하는 경우에는 명시적으로 각 피연산자를 공용 형식으로 캐스팅하는 것이 좋습니다.

## <a name="example"></a>예제

```cpp
// expre_Expressions_with_the_Conditional_Operator.cpp
// compile with: /EHsc
// Demonstrate conditional operator
#include <iostream>
using namespace std;
int main() {
   int i = 1, j = 2;
   cout << ( i > j ? i : j ) << " is greater." << endl;
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[조건식 연산자](../c-language/conditional-expression-operator.md)
