---
title: 컴파일러 오류 C2712
ms.date: 11/04/2016
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: a25c59fa5c9ba0102666f6c8922a61b063e7627a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202308"
---
# <a name="compiler-error-c2712"></a>컴파일러 오류 C2712

> 개체 해제 기능이 사용되는 함수에서는 __try를 사용할 수 없습니다.

## <a name="remarks"></a>주의

[/Ehsc](../../build/reference/eh-exception-handling-model.md)를 사용 하 고 구조화 된 예외 처리를 사용 하는 함수에 해제 (소멸)가 필요한 개체가 있는 경우 오류 C2712 발생할 수 있습니다.

가능한 해결 방법:

- SEH가 필요한 코드를 다른 함수로 이동합니다.

- SEH를 사용하는 함수를 다시 작성하여 소멸자가 있는 지역 변수 및 매개 변수를 사용하지 않도록 합니다. 생성자 또는 소멸자에 SEH를 사용하지 않습니다.

- /EHsc 없이 컴파일합니다.

[__Event](../../cpp/event.md) 키워드를 사용 하 여 선언 된 메서드를 호출 하는 경우에도 오류 C2712 발생할 수 있습니다. 이 이벤트는 다중 스레드 환경에서 사용 될 수 있기 때문에 컴파일러는 기본 이벤트 개체를 조작할 수 없도록 하는 코드를 생성 한 다음 생성 된 코드를 SEH [try-finally 문으로](../../cpp/try-finally-statement.md)묶습니다. 따라서 이벤트 메서드를 호출하고 해당 형식에 소멸자가 포함된 인수를 값으로 전달하는 경우 C2712 오류가 발생합니다. 이 경우 한 가지 해결 방법은 인수를 상수 참조로 전달하는 것입니다.

C2712는 **/clr: pure** 를 사용 하 여 컴파일하고 `__try` 블록에서 함수에 대 한 포인터의 정적 배열을 선언 하는 경우에도 발생할 수 있습니다. 정적 멤버를 사용 하려면 컴파일러가 예외 처리를 의미 C++ 하는 **/clr: pure**에서 동적 초기화를 사용 해야 합니다. 그러나 C++ 예외 처리는 `__try` 블록에서 허용되지 않습니다.

**/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2712 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2712.cpp
// compile with: /clr:pure /c
struct S1 {
   static int smf();
   void fnc();
};

void S1::fnc() {
   __try {
      static int (*array_1[])() = {smf,};   // C2712

      // OK
      static int (*array_2[2])();
      array_2[0] = smf;
    }
    __except(0) {}
}
```
