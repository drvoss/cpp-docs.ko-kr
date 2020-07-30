---
title: 컴파일러 오류 C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: 38cfb3ff81073a123f2d8c3c83c29c42c27d9dc7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225568"
---
# <a name="compiler-error-c2128"></a>컴파일러 오류 C2128

' function ': alloc_text/same_seg는 C 링크가 있는 함수에만 적용할 수 있습니다.

`#pragma alloc_text`는 C 링크를 포함 하도록 선언 된 함수에만 사용할 수 있습니다.

다음 샘플에서는 C2128를 생성 합니다.

```cpp
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```
