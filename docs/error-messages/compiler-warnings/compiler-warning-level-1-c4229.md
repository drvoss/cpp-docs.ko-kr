---
title: 컴파일러 경고(수준 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: b1cb97c51dca7cf3fdbca024ead969c4d4e1f3eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163286"
---
# <a name="compiler-warning-level-1-c4229"></a>컴파일러 경고(수준 1) C4229

오래 된 사용: 데이터의 한정자는 무시 됩니다.

데이터 선언에 `__cdecl`와 같은 Microsoft 한정자를 사용 하는 것은 오래 된 방법입니다.

## <a name="example"></a>예제

```cpp
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```
