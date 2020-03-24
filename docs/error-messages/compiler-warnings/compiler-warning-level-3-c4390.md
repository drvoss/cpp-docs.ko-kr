---
title: 컴파일러 경고(수준 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 63150f4ca801d3c377c7bc09b58a778bebf02b46
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198681"
---
# <a name="compiler-warning-level-3-c4390"></a>컴파일러 경고(수준 3) C4390

'; ': 제어 되는 빈 문이 있습니다. 이것이 의도 입니까?

명령이 없는 control 문 뒤에 세미콜론이 있습니다.

매크로 때문에 C4390를 가져오는 경우 매크로를 포함 하는 모듈에서 C4390를 사용 하지 않도록 설정 하려면 [warning](../../preprocessor/warning.md) pragma를 사용 해야 합니다.

다음 샘플에서는 C4390를 생성 합니다.

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
