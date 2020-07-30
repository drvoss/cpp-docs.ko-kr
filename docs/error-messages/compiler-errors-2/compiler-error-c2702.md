---
title: 컴파일러 오류 C2702
ms.date: 11/04/2016
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: eb8a19bf5d29a2a0c69dc27e9b22f76df63ce8e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216078"
---
# <a name="compiler-error-c2702"></a>컴파일러 오류 C2702

종료 블록에 __except 표시 되지 않을 수 있습니다.

예외 처리기 ( `__try` / **`__except`** )는 블록 내에 중첩 될 수 없습니다 **`__finally`** .

다음 샘플에서는 C2702를 생성 합니다.

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
