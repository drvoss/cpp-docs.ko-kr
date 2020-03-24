---
title: 컴파일러 경고(수준 1) C4081
ms.date: 11/04/2016
f1_keywords:
- C4081
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
ms.openlocfilehash: b882fe9c83f072c06a63733870f610549b209691
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200294"
---
# <a name="compiler-warning-level-1-c4081"></a>컴파일러 경고(수준 1) C4081

'token1'이 필요한데 'token2'가 있습니다.

이 컨텍스트에서는 컴파일러에 다른 토큰이 필요합니다.

## <a name="example"></a>예제

```cpp
// C4081.cpp
// compile with: /W1 /LD
#pragma optimize) "l", on )   // C4081
```
