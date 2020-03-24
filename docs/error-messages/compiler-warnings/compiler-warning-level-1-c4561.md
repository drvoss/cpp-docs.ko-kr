---
title: 컴파일러 경고(수준 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 11a1bcdc8396b1eb74121c27154b8c6c24fa92a6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162285"
---
# <a name="compiler-warning-level-1-c4561"></a>컴파일러 경고(수준 1) C4561

' __fastcall '이 (가) '/clr ' 옵션과 호환 되지 않습니다. '\__stdcall ' (으)로 변환 합니다.

[__Fastcall](../../cpp/fastcall.md) 함수 호출 규칙은 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션과 함께 사용할 수 없습니다. 컴파일러는 `__fastcall`에 대 한 호출을 무시 합니다. 이 경고를 해결 하려면 **__fastcall** 에 대 한 호출을 제거 하거나 **/clr**없이 컴파일합니다.

다음 샘플에서는 C4561를 생성 합니다.

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
