---
title: 컴파일러 경고(수준 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: 72483b734a1463b7b211c49ef21a01536ffa0ea1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185726"
---
# <a name="compiler-warning-level-1-c4731"></a>컴파일러 경고(수준 1) C4731

' pointer ': 프레임 포인터의 ' register ' 레지스터가 인라인 어셈블리 코드에 의해 수정 되었습니다.

프레임 포인터 레지스터가 수정 되었습니다. 인라인 어셈블리 블록 또는 프레임 변수 (수정 된 레지스터에 따라 로컬 또는 매개 변수)에 등록을 저장 하 고 복원 해야 합니다. 그렇지 않으면 코드가 제대로 작동 하지 않을 수 있습니다.

다음 샘플에서는 C4731를 생성 합니다.

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP는 프레임 포인터 (FPO는 허용 되지 않음)이 고 수정 되 고 있습니다. `p` 나중에 참조 되는 경우 `EBP`을 기준으로 참조 됩니다. 그러나 코드에서 `EBP`를 덮어쓰므로 프로그램이 제대로 작동 하지 않으며 오류가 발생할 수 있습니다.
