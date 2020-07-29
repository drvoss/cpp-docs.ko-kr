---
title: 컴파일러 오류 C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: fd0b11b1500ea448ded4a24db8e6d8ebf9ee9782
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212854"
---
# <a name="compiler-error-c2120"></a>컴파일러 오류 C2120

모든 형식에 ' l o n '이 잘못 되었습니다.

**`void`** 형식은 다른 형식의 선언에서 사용 됩니다.

다음 샘플에서는 C2120를 생성 합니다.

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
