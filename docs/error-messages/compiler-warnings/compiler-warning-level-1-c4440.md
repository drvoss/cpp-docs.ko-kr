---
title: 컴파일러 경고(수준 1) C4440
ms.date: 11/04/2016
f1_keywords:
- C4440
helpviewer_keywords:
- C4440
ms.assetid: 78b9642a-a93e-401e-9d92-372f6451bc5d
ms.openlocfilehash: dbb10a83e619af04334af268381b2286b037257a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186779"
---
# <a name="compiler-warning-level-1-c4440"></a>컴파일러 경고(수준 1) C4440

' calling_convention1 '에서 ' calling_convention2 ' (으)로의 규칙 재정의 호출이 무시 되었습니다.

호출 규칙을 변경 하려는 시도가 무시 되었습니다.

다음 샘플에서는 C4440를 생성 합니다.

```cpp
// C4440.cpp
// compile with: /W1 /LD /clr
typedef void __clrcall F();
typedef F __cdecl *PFV;   // C4440
```
