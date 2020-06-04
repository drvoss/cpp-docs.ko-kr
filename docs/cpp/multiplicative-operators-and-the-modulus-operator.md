---
title: 곱하기 연산자 및 나머지 연산자
ms.date: 11/04/2016
f1_keywords:
- '%'
- /
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
ms.openlocfilehash: 791f18793b49f7d3a986c3271fddef3acef33062
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367919"
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>곱하기 연산자 및 나머지 연산자

## <a name="syntax"></a>구문

```
expression * expression
expression / expression
expression % expression
```

## <a name="remarks"></a>설명

곱하기 연산자는 다음과 같습니다.

- 곱셈 ()<strong>\*</strong>

- 부문**/**()

- 모듈러스 (분할에서 나머지)**%**()

이 이항 연산자는 왼쪽에서 오른쪽으로 연결됩니다.

곱하기 연산자는 산술 형식의 피연산자를 사용합니다. 모듈러스 연산자**%**() 는 그 산각부가 정수 유형이어야한다는 점에서 더 엄격한 요구 사항이 있습니다. 부동 점 분할의 나머지를 얻으려면 런타임 함수 [fmod를](../c-runtime-library/reference/fmod-fmodf.md)사용합니다. [표준 변환에서](standard-conversions.md) 다루는 변환은 피연산자에도 적용되며 결과는 변환된 형식입니다.

곱하기 연산자는 첫 번째 피연산자와 두 번째 피연산자를 곱한 결과를 구합니다.

나누기 연산자는 첫 번째 피연산자를 두 번째 피연산자로 나눈 결과를 구합니다.

모듈러스 연산자는 *e1이* 첫 번째 피연산자이고 *e2가* 두 번째인 다음 식에 의해 주어진 \* 나머지를 산출합니다: *e1* -*(e1* / *e2)* *e2,* 두 피연산자는 모두 정수 유형입니다.

0으로 나누기는 나누기 또는 모듈러스 식에 정의되지 않았으며 런타임 오류를 생성합니다. 따라서 다음 식에서는 정의되지 않은 잘못된 결과가 생성됩니다.

```cpp
i % 0
f / 0.0
```

곱하기, 나누기 또는 모듈러스 식의 두 피연산자 모두 부호가 같고 결과는 양수입니다. 그렇지 않으면 결과는 음수입니다. 모듈러스 연산 부호의 결과는 구현에서 정의됩니다.

> [!NOTE]
> 곱셈 연산자로 수행된 변환은 오버플로 또는 언더플로 조건을 제공하지 않으므로 변환 후 곱셈 연산 결과가 피연산자 형식으로 표현되지 않는 경우 정보가 손실될 수 있습니다.

**마이크로소프트 특정**

Microsoft C++에서 모듈러스 식의 결과가 항상 첫 번째 피연산자의 부호와 같습니다.

**Microsoft 전용 종료**

두 정수의 나누기 계산이 정확하지 않고 피연산자가 한 개만 음수일 경우 나누기 연산에서 구하는 정확한 값보다 작은 최대 정수(부호에 관계 없는 크기)가 결과가 됩니다. 예를 들어 -11/3의 계산된 값은 -3.666666666입니다. 그 적분 분할의 결과는 -3입니다.

곱셈 연산자 간의 관계는 ID *(e1* / *e2)* \* *e2 e1* + *e1e1에**e1* % *e2* == 의해 주어집니다.

## <a name="example"></a>예제

다음 프로그램은 곱셈 연산자를 보여 줍니다. 두 피연산자는 `10 / 3` 분할 전에 유형 **플로트가** 되도록 잘림을 피하기 위해 **플로트** 유형으로 명시적으로 캐스팅해야 합니다.

```cpp
// expre_Multiplicative_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   int x = 3, y = 6, z = 10;
   cout  << "3 * 6 is " << x * y << endl
         << "6 / 3 is " << y / x << endl
         << "10 % 3 is " << z % x << endl
         << "10 / 3 is " << (float) z / x << endl;
}
```

## <a name="see-also"></a>참고 항목

[이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 곱하기 연산자](../c-language/c-multiplicative-operators.md)
