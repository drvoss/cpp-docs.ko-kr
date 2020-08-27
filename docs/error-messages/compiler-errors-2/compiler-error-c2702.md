---
title: 컴파일러 오류 C2702
description: Microsoft C/c + + 컴파일러 오류 C2702에 대해 설명 합니다.
ms.date: 08/25/2020
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 83210f6ab261a5ae6dd7320182c3f4c3539ff4d1
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898424"
---
# <a name="compiler-error-c2702"></a>컴파일러 오류 C2702

> `__except` 종료 블록에 표시 되지 않을 수 있습니다.

예외 처리기 ( **`__try`** / **`__except`** )는 블록 내에 중첩 될 수 없습니다 **`__finally`** .

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
