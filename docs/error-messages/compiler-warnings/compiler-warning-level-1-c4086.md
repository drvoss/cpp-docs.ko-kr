---
title: 컴파일러 경고(수준 1) C4086
ms.date: 11/04/2016
f1_keywords:
- C4086
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
ms.openlocfilehash: 596d70e08694b50b7aa6b743bce11f03a47df822
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200150"
---
# <a name="compiler-warning-level-1-c4086"></a>컴파일러 경고(수준 1) C4086

pragma 매개 변수는 '1', '2', '4', '8' 또는 '16'이어야 합니다.

pragma 매개 변수에 필수 값(1, 2, 4, 8 또는 16)이 없습니다.

## <a name="example"></a>예제

```cpp
// C4086.cpp
// compile with: /W1 /LD
#pragma pack( 3 ) // C4086
```
