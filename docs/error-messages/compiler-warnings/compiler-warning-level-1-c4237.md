---
title: 컴파일러 경고(수준 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: 31ceb972edf975055f930d4ff70a6663a5760922
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163260"
---
# <a name="compiler-warning-level-1-c4237"></a>컴파일러 경고(수준 1) C4237

' keyword ' 키워드는 아직 지원 되지 않지만 나중에 사용할 수 있도록 예약 되었습니다.

C++ 사양의 키워드는 Microsoft C++ 컴파일러에서 구현 되지 않지만 키워드는 사용자 정의 기호로 사용할 수 없습니다.

다음 샘플에서는 C4237를 생성 합니다.

```cpp
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```
