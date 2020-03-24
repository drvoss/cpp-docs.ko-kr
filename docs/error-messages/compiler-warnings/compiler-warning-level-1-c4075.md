---
title: 컴파일러 경고(수준 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: f69d91ee9335201029d6b566b7987df8c267f82b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200228"
---
# <a name="compiler-warning-level-1-c4075"></a>컴파일러 경고(수준 1) C4075

이니셜라이저가 인식할 수 없는 초기화 영역에 있습니다.

[#pragma init_seg](../../preprocessor/init-seg.md) 에서는 인식할 수 없는 섹션 이름을 사용합니다. 컴파일러는 **pragma** 명령을 무시합니다.

다음 샘플에서는 C4075를 생성합니다.

```cpp
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```
