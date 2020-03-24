---
title: 컴파일러 경고(수준 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: e2e1781bf4c1b9ac0ee29d0b5900daa6cfe94b45
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199773"
---
# <a name="compiler-warning-level-1-c4269"></a>컴파일러 경고(수준 1) C4269

' identifier ': 컴파일러에서 생성 된 기본 생성자로 초기화 된 ' const ' 자동 데이터는 불안정 한 결과를 생성 합니다.

특수 하지 않은 클래스의 **const** 자동 인스턴스는 컴파일러 생성 기본 생성자를 사용 하 여 초기화 됩니다.

## <a name="example"></a>예제

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

클래스의이 인스턴스는 스택에서 생성 되므로 `m_data`의 초기 값은 모두 일 수 있습니다. 또한 **const** 인스턴스 이기 때문에 `m_data`의 값은 변경할 수 없습니다.
