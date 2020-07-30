---
title: 컴파일러 오류 C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: d97722306e5c995a4921c6eb9577d623b21c9517
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216169"
---
# <a name="compiler-error-c2624"></a>컴파일러 오류 C2624

지역 클래스는 ' extern ' 변수를 선언 하는 데 사용할 수 없습니다.

로컬 클래스 또는 구조체는 변수를 선언 하는 데 사용할 수 없습니다 **`extern`** .

다음 샘플에서는 C2624를 생성 합니다.

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```
