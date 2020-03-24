---
title: 컴파일러 경고(수준 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: c75d2d776537307fd34fa3a55807d303630dbeb5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161974"
---
# <a name="compiler-warning-level-2-c4285"></a>컴파일러 경고(수준 2) C4285

' identifier:: operator-> '의 반환 형식은 중 위 표기법을 사용 하 여 적용할 경우 재귀적입니다.

지정 된 **operator > ()** 함수는 정의 된 형식이 나 정의 된 형식에 대 한 참조를 반환할 수 없습니다.

다음 샘플에서는 C4285를 생성 합니다.

```cpp
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```
