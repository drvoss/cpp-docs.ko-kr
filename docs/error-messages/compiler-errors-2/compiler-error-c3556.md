---
title: 컴파일러 오류 C3556
ms.date: 11/04/2016
f1_keywords:
- C3556
helpviewer_keywords:
- C3556
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
ms.openlocfilehash: 50f97c4360080f1271d9decc3b3460c06f3fec0b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230820"
---
# <a name="compiler-error-c3556"></a>컴파일러 오류 C3556

> '*expression*': ' decltype '의 인수가 잘못 되었습니다.

컴파일러가 `decltype(` *식* 형식 지정자의 인수인 식의 형식을 추론할 수 없습니다 `)` .

## <a name="example"></a>예제

다음 코드 예제에서는 `myFunction` 이 오버로드되어 컴파일러가 `myFunction` 인수의 형식을 추론할 수 없습니다. 이 문제를 해결 하려면 **`static_cast`** 를 사용 하 여 식에 지정할 특정 오버 로드 된 함수에 대 한 포인터의 인스턴스를 만들 수 있습니다 **`decltype`** .

```cpp
// C3556.cpp
// compile with: cl /W4 /EHsc C3556.cpp
#include <iostream>

void myFunction(int);
void myFunction(float, float);

void callsMyFunction(decltype(myFunction) fn); // C3556
// One way to fix is to comment out the line above, and
// use static_cast to create specialized function pointer
// instances:
auto myFunctionInt = static_cast<void(*)(int)>(myFunction);
auto myFunctionFloatFloat = static_cast<void(*)(float,float)>(myFunction);
void callsMyFunction(decltype(myFunctionInt) fn, int n);
void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g);

void myFunction(int i) {
    std::cout << "called myFunction(" << i << ")" << std::endl;
}

void myFunction(float f, float g) {
    std::cout << "called myFunction(" << f << ", " << g << ")" << std::endl;
}

void callsMyFunction(decltype(myFunctionInt) fn, int n) {
    fn(n);
}

void callsMyFunction(decltype(myFunctionFloatFloat) fn, float f, float g) {
    fn(f, g);
}

int main() {
    callsMyFunction(myFunction, 42);
    callsMyFunction(myFunction, 0.1f, 2.3f);
}
```
