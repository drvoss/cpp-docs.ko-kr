---
title: 컴파일러 경고(수준 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f932b1bcdf011678d4f85e0edf1e116a954b59fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367372"
---
# <a name="compiler-warning-level-1-c4744"></a>컴파일러 경고(수준 1) C4744

'var'은 'file1' 및 'file2'에서 'type1' 및 'type2'에서 다른 형식을 가합니다.

두 파일에서 참조하거나 정의된 외부 변수에는 해당 파일에 다른 형식이 있습니다.  해결하려면 형식 정의를 동일하게 만들거나 파일 중 하나에서 변수 이름을 변경합니다.

C4744는 파일이 /GL로 컴파일될 때만 내보내됩니다.  자세한 내용은 [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)을 참조하세요.

> [!NOTE]
> C ++에서 변수 이름이 형식 정보로 장식되어 있기 때문에 C4744는 일반적으로 C (C ++가 아닌) 파일에서 발생합니다.  샘플(아래)이 C++로 컴파일되면 링커 오류 LNK2019가 표시됩니다.

## <a name="example"></a>예제

이 샘플에는 첫 번째 정의가 포함되어 있습니다.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>예제

다음 샘플은 C4744를 생성합니다.

```c
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```
