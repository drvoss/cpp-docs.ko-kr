---
title: 컴파일러 오류 C2706
description: Microsoft C/c + + 컴파일러 오류 C2706에 대해 설명 합니다.
ms.date: 08/25/2020
f1_keywords:
- C2706
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
ms.openlocfilehash: 11e1e878f82ad59bb712155747696c0d6c6a239e
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898734"
---
# <a name="compiler-error-c2706"></a>컴파일러 오류 C2706

> 짝이 맞지 `__except` 않는 `__try` (블록에 '} '가 없음 `__try` )

컴파일러가 블록의 닫는 중괄호를 찾지 못했습니다 **`__try`** .

다음 샘플에서는 C2706를 생성 합니다.

```cpp
// C2706.cpp
int main() {
   __try {
      void f();
   // C2706  } missing here
   __except(GetExceptionCode() == 0x0) {
   }
}
```
