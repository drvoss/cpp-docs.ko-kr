---
title: 컴파일러 경고(수준 1) C4272
ms.date: 11/04/2016
f1_keywords:
- C4272
helpviewer_keywords:
- C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
ms.openlocfilehash: 747b9e60ad2b8b0036c6eac50d44c2d70277384f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163113"
---
# <a name="compiler-warning-level-1-c4272"></a>컴파일러 경고(수준 1) C4272

' function ': __declspec (dllimport)로 표시 되어 있습니다. 함수를 가져올 때 네이티브 호출 규칙을 지정 해야 합니다.

[__Clrcall](../../cpp/clrcall.md) 호출 규칙으로 표시 된 함수를 내보내는 것은 오류 이며 `__clrcall`표시 된 함수를 가져오려고 하면 컴파일러가이 경고를 발생 시킵니다.

다음 샘플에서는 C4272를 생성 합니다.

```cpp
// C4272.cpp
// compile with: /c /W1 /clr
__declspec(dllimport) void __clrcall Test();   // C4272
__declspec(dllimport) void Test2();   // OK
```
