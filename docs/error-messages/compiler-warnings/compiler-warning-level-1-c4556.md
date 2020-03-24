---
title: 컴파일러 경고(수준 1) C4556
ms.date: 08/27/2018
f1_keywords:
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: 501d79a8a86fcd3e2d8ba08dc2f03488f9abb827
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162311"
---
# <a name="compiler-warning-level-1-c4556"></a>컴파일러 경고(수준 1) C4556

> 내장 직접 인수 *' s a l e*'의 값이 '*lowerbound* - *상한값*' 범위를 벗어났습니다.

## <a name="remarks"></a>설명

내장 함수는 하드웨어 명령과 일치 합니다. 하드웨어 명령에는 상수를 인코딩하기 위한 고정 된 수의 비트가 있습니다. *값* 이 범위를 벗어나는 경우 올바르게 인코딩되지 않습니다. 컴파일러는 추가 비트를 자릅니다.

## <a name="example"></a>예제

다음 샘플에서는 C4556를 생성 합니다.

```cpp
// C4556.cpp
// compile with: /W1
// processor: x86 IPF
#include <xmmintrin.h>

void test()
{
   __m64 m;
   _m_pextrw(m, 5);   // C4556
}

int main()
{
}
```
