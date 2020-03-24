---
title: 컴파일러 경고(수준 2) C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: 138344be8d70866583214a9c5a26f10c972a7889
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161844"
---
# <a name="compiler-warning-level-2-c4308"></a>컴파일러 경고(수준 2) C4308

음수 정수 계열 상수가 부호 없는 형식으로 변환 되었습니다.

식은 음의 정수 상수를 부호 없는 형식으로 변환 합니다. 식의 결과는 의미가 없을 수 있습니다.

## <a name="example"></a>예제

```cpp
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```
