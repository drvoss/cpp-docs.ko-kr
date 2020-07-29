---
title: 컴파일러 경고(수준 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: 0d3b0aa05ca5fff16b3cd28c11e3bf8290de1b3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225347"
---
# <a name="compiler-warning-level-1-c4806"></a>컴파일러 경고(수준 1) C4806

'operation': 안전하지 않은 연산입니다. 'type' 형식의 값('type' 형식으로 확장)이 주어진 상수와 같을 수 없습니다.

이 메시지는와 같은 코드에 대해 경고 `b == 3` `b` 합니다. 여기서는 형식 **`bool`** 입니다. 승격 규칙으로 인해이 **`bool`** 로 승격 됩니다 **`int`** . 이는 유효 하지만 일 수 없습니다 **`true`** . 다음 샘플에서는 C4806을 생성합니다.

```cpp
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```
