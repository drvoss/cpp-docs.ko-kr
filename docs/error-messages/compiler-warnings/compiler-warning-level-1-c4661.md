---
title: 컴파일러 경고(수준 1) C4661
ms.date: 11/04/2016
f1_keywords:
- C4661
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
ms.openlocfilehash: 43a3287787f831db23423412a9baf959929adfae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199463"
---
# <a name="compiler-warning-level-1-c4661"></a>컴파일러 경고(수준 1) C4661

' identifier ': 명시적 템플릿 인스턴스화 요청에 적합 한 정의가 제공 되지 않았습니다.

템플릿 클래스의 멤버가 정의 되어 있지 않습니다.

## <a name="example"></a>예제

```cpp
// C4661.cpp
// compile with: /W1 /LD
template<class T> class MyClass {
public:
   void i();   // declaration but not definition
};
template MyClass< int >;  // C4661
```
