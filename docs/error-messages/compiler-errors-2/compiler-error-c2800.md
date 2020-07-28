---
title: 컴파일러 오류 C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: 8bab5cd015bd28228b9829cb59cb3b6fdf2f3717
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214609"
---
# <a name="compiler-error-c2800"></a>컴파일러 오류 C2800

' operator operator '를 오버 로드할 수 없습니다.

다음 연산자는 오버 로드할 수 없습니다. 클래스 멤버 액세스 ( `.` ), 멤버 포인터 ( `.*` ), 범위 확인 ( `::` ), 조건식 ( `? :` ) 및 **`sizeof`** .

다음 샘플에서는 C2800를 생성 합니다.

```cpp
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```
