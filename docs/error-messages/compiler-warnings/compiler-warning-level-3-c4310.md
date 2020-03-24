---
title: 컴파일러 경고(수준 3) C4310
ms.date: 11/04/2016
f1_keywords:
- C4310
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
ms.openlocfilehash: 1a6088d3d95eada30507ceddbb97701bd3347d93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198837"
---
# <a name="compiler-warning-level-3-c4310"></a>컴파일러 경고(수준 3) C4310

캐스트할 때 상수 값이 잘립니다.

상수 값은 더 작은 형식으로 캐스팅 됩니다. 컴파일러는 데이터를 잘라내는 캐스트를 수행 합니다. 다음 샘플에서는 C4310를 생성 합니다.

```cpp
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```
