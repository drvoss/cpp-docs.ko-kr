---
title: 컴파일러 경고(수준 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: 5e6c945932699119f97bca2d3d118a03665f6f9f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185882"
---
# <a name="compiler-warning-level-1-c4618"></a>컴파일러 경고(수준 1) C4618

pragma 매개 변수에 빈 문자열이 포함 되어 있습니다. pragma가 무시 되었습니다.

**#Pragma**에 대 한 인수로 null 문자열이 지정 되었습니다.

Pragma가 인수 없이 처리 되었습니다.

다음 샘플에서는 C4618를 생성 합니다.

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```
