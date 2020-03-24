---
title: 컴파일러 경고(수준 4) C4019
ms.date: 11/04/2016
f1_keywords:
- C4019
helpviewer_keywords:
- C4019
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
ms.openlocfilehash: 6245a32aff0769a2f30dfe88ca6111579eda6ea9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185466"
---
# <a name="compiler-warning-level-4-c4019"></a>컴파일러 경고(수준 4) C4019

전역 범위에 빈 문이 있습니다.

전역 범위의 세미콜론 앞에 문이 오지 않습니다.

불필요한 세미콜론을 제거하면 이 경고를 해결할 수 있습니다.

## <a name="example"></a>예제

```c
// C4019.c
// compile with: /Za /W4
#define declint( varname ) int varname;
declint( a );   // C4019, int a;;
declint( b )   // OK, int b;

int main()
{
}
```
