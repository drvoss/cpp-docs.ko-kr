---
title: 컴파일러 경고(수준 1) C4925
ms.date: 11/04/2016
f1_keywords:
- C4925
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
ms.openlocfilehash: defd60d02a8725b114b3901f8d70af87e27445c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174637"
---
# <a name="compiler-warning-level-1-c4925"></a>컴파일러 경고(수준 1) C4925

'method': 스크립트에서 dispinterface 메서드를 호출할 수 없습니다.

스크립트 언어에서 VT_BYREF 'in' 매개 변수를 만들 수 없습니다. VT_BYREF 'out' 매개 변수만 만들 수 있습니다.

이 경고를 해결하는 다른 방법은 매개 변수(정의 및 구현)를 포인터 형식으로 설정하지 않는 것입니다.

다음 샘플에서는 C4925를 생성합니다.

```cpp
// C4925.cpp
// compile with: /LD /W1
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[ module(name="Test")];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IDisp {
   [id(9)] void f([in] int*);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]
struct CDisp : IDisp {   // C4925
   void f(int*) {}
};
```
