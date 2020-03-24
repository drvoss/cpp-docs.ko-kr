---
title: 컴파일러 경고(수준 1) C4216
ms.date: 11/04/2016
f1_keywords:
- C4216
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
ms.openlocfilehash: 2521366a9f33e8c5b1b7d41951a7cb08adfc2561
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199825"
---
# <a name="compiler-warning-level-1-c4216"></a>컴파일러 경고(수준 1) C4216

비표준 확장이 사용 됨: float long입니다.

기본 Microsoft 확장 (/Ze)은 **float long** 을 **double**로 처리 합니다. ANSI 호환성 ([/za](../../build/reference/za-ze-disable-language-extensions.md))은 그렇지 않습니다. **Double** 을 사용 하 여 호환성을 유지 합니다. 다음 샘플에서는 C4216를 생성 합니다.

```cpp
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```
