---
title: 컴파일러 경고(수준 1) C4537
ms.date: 08/27/2018
f1_keywords:
- C4537
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
ms.openlocfilehash: 81058f153228d3d8fbf4097c140962d0cb9677e5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186363"
---
# <a name="compiler-warning-level-1-c4537"></a>컴파일러 경고(수준 1) C4537

> '*object*': '*OPERATOR*'가 UDT 형식이 아닌 형식에 적용 되었습니다.

## <a name="remarks"></a>주의

개체 (사용자 정의 형식)가 필요한 위치에 참조가 전달 되었습니다. 참조는 개체가 아니지만 인라인 어셈블러 코드는이를 구분할 수 없습니다. 컴파일러는 *개체가* 인스턴스인 것 처럼 코드를 생성 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4537를 생성 하 고 수정 하는 방법을 보여 줍니다.

```cpp
// C4537.cpp
// compile with: /W1 /c
// processor: x86
struct S {
    int member;
};

void f1(S &s) {
    __asm mov eax, s.member;   // C4537
    // try the following code instead
    // or, make the declaration "void f1(S s)"
    /*
    mov eax, s
    mov eax, [eax]s.member
    */
}
```
