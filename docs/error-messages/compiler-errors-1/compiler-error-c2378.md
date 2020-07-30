---
title: 컴파일러 오류 C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: c72a46bbc5778bf95ddc49426f97df0320b22a30
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218236"
---
# <a name="compiler-error-c2378"></a>컴파일러 오류 C2378

'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.

식별자가로 다시 정의 되었습니다 **`typedef`** .

다음 샘플에서는 C2378을 생성합니다.

```cpp
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```
