---
title: 컴파일러 오류 C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: 2bf73aa9aee2a45e5271570b4c45c8fecaa4a4bf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225542"
---
# <a name="compiler-error-c2377"></a>컴파일러 오류 C2377

'identifier': 재정의. 다른 기호를 사용하여 형식 정의를 오버로드할 수 없습니다.

식별자가 다시 **`typedef`** 정의 됩니다.

다음 샘플에서는 C2377을 생성합니다.

```cpp
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```
