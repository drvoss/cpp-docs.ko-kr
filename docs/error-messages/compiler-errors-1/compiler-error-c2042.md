---
title: 컴파일러 오류 C2042
ms.date: 11/04/2016
f1_keywords:
- C2042
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
ms.openlocfilehash: 9851d952c4a07eacd223394f10183d0ec9c369bc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212893"
---
# <a name="compiler-error-c2042"></a>컴파일러 오류 C2042

signed/unsigned 키워드는 함께 사용할 수 없습니다.

및 키워드 **`signed`** 는 **`unsigned`** 단일 선언에 사용 됩니다.

다음 샘플에서는 C2042를 생성합니다.

```cpp
// C2042.cpp
unsigned signed int i;   // C2042
```

해결 방법:

```cpp
// C2042b.cpp
// compile with: /c
unsigned int i;
signed int ii;
```
