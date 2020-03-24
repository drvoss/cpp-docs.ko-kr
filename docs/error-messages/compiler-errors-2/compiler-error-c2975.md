---
title: 컴파일러 오류 C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 70fc648de8bcf4f1e85edf3a12cc0b7d3d70625f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201567"
---
# <a name="compiler-error-c2975"></a>컴파일러 오류 C2975

> '*argument*': '*type*'의 템플릿 인수가 잘못 되었습니다. 컴파일 타임 상수 식이 필요 합니다.

템플릿 인수가 템플릿 선언과 일치 하지 않습니다. 상수 식은 꺾쇠 괄호 안에 표시 되어야 합니다. 변수는 템플릿 실제 인수로 사용할 수 없습니다. 템플릿 정의를 확인하여 올바른 형식을 찾습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2975를 생성 하 고 올바른 사용법도 보여 줍니다.

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

&#95; &#95;C2975는 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)를 사용 하 여&#95; &#95; 컴파일 시간 상수로 줄을 사용 하는 경우에도 발생 합니다. 한 가지 해결 방법은 **/zi**대신 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) 를 사용 하 여 컴파일하는 것입니다.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```
