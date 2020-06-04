---
title: 컴파일러 경고(수준 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: e0a13761b0657d054065358994638779817dad6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163026"
---
# <a name="compiler-warning-level-1-c4325"></a>컴파일러 경고(수준 1) C4325

> '*section*' 표준 섹션의 특성이 무시 되었습니다.

## <a name="remarks"></a>설명

표준 섹션의 특성을 변경할 수 없습니다. 다음은 그 예입니다.

```cpp
#pragma section(".sdata", long)
```

이는 **long** 데이터 형식의 **short** 데이터 형식을 사용 하는 `.sdata` 표준 섹션을 덮어씁니다.

특성을 변경 하지 않을 수 있는 표준 섹션에는 다음이 포함 됩니다.

- .data

- .sdata

- . bss

- . .sbss

- .text

- .const

- .sconst

- .rdata

- .srdata

추가 섹션은 나중에 추가할 수 있습니다.

## <a name="see-also"></a>참고 항목

[section](../../preprocessor/section.md)
