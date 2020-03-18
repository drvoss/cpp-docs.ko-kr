---
title: '논리 부정 연산자: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 06142ef15fcdbafdbae4b892772a04b117c087f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446545"
---
# <a name="logical-negation-operator-"></a>논리 부정 연산자: !

## <a name="syntax"></a>구문

```
! cast-expression
```

## <a name="remarks"></a>설명

논리 부정 연산자 ( **!** )는 해당 피연산자의 의미를 반대로 합니다. 피연산자는 산술 형식, 포인터 형식 또는 산술/포인터 형식으로 계산되는 식이어야 합니다. 피연산자는 암시적으로 **bool**형식으로 변환 됩니다. 변환된 피연산자가 FALSE이면 결과는 TRUE이고 변환된 피연산자가 TRUE이면 결과는 FALSE입니다. 결과는 **bool**형식입니다.

식 *e*의 경우 `!e` 단항 식은 오버 로드 된 연산자가 포함 된 경우를 제외 하 고는 식 `(e == 0)`와 동일 합니다.

## <a name="operator-keyword-for-"></a>!에 대한 연산자 키워드

**Not** 연산자는 **!** 의 대체 철자입니다. 프로그램에서 **not** 연산자에 액세스 하는 방법에는 두 가지가 있습니다. iso646 > \<헤더 파일을 포함 하거나 [/za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장 사용 안 함) 컴파일러 옵션을 사용 하 여 컴파일합니다.

## <a name="example"></a>예제

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)<br/>
