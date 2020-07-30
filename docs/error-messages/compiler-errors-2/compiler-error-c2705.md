---
title: 컴파일러 오류 C2705
ms.date: 11/04/2016
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 65d9ed2458f43e6c9a697be02ffc9b831259624c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225438"
---
# <a name="compiler-error-c2705"></a>컴파일러 오류 C2705

' label ': ' exception handler block ' 범위로 잘못 점프 했습니다.

실행은, 블록 내의 레이블로 이동 **`try`** / **`catch`** `__try` / **`__except`** `__try` / **`__finally`** 합니다. 자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조하세요.

다음 샘플에서는 C2705를 생성 합니다.

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
