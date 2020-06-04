---
title: 컴파일러 경고(수준 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: c0e79dfa4564960a5660f0932b142b436370ac05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173922"
---
# <a name="compiler-warning-level-4-c4232"></a>컴파일러 경고(수준 4) C4232

비표준 확장이 사용 됨: ' identifier ': ' dllimport ' dllimport의 주소가 정적이 아닙니다. id가 보장 되지 않습니다.

Microsoft 확장 (/Ze)에서 비정적 값을 **dllimport** 한정자를 사용 하 여 선언 된 함수의 주소로 지정할 수 있습니다. ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))에서 오류가 발생 합니다.

다음 샘플에서는 C4232를 생성 합니다.

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
