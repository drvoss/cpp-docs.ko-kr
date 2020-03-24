---
title: 컴파일러 경고(수준 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 414388fc1b9c6a7425d45e2ba92546960cadf404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199617"
---
# <a name="compiler-warning-level-1-c4630"></a>컴파일러 경고(수준 1) C4630

' symbol ': 멤버 정의에는 ' extern ' 저장소 클래스 지정자를 사용할 때 잘못 되었습니다.

데이터 멤버 또는 멤버 함수는 `extern`로 정의 됩니다. 전체 개체가 가능 하더라도 멤버는 외부 일 수 없습니다. 컴파일러는 `extern` 키워드를 무시 합니다. 다음 샘플에서는 C4630를 생성 합니다.

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
