---
title: 컴파일러 경고 (수준 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7258172c00b1ff4aebb18fa2c715559fd82a2180
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163548"
---
# <a name="compiler-warning-level-1-c4172"></a>컴파일러 경고 (수준 1) C4172

지역 변수 또는 임시 주소 반환

함수는 지역 변수 또는 임시 개체의 주소를 반환 합니다. 지역 변수 및 임시 개체는 함수가 반환 될 때 소멸 되므로 반환 된 주소가 올바르지 않습니다.

로컬 개체의 주소를 반환 하지 않도록 함수를 다시 디자인 합니다.

다음 샘플에서는 C4172를 생성 합니다.

```cpp
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```
