---
title: 컴파일러 오류 C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 944eaeadb038e6466d65859f72900db164cfe34d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221161"
---
# <a name="compiler-error-c2507"></a>컴파일러 오류 C2507

' identifier ': 기본 클래스에 가상 한정자가 너무 많습니다.

클래스 또는 구조체가 두 번 이상 선언 되었습니다 **`virtual`** . **`virtual`** 기본 클래스 목록에는 각 클래스에 대 한 한정자가 하나만 표시 될 수 있습니다.

다음 샘플에서는 C2507를 생성 합니다.

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
