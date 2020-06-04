---
title: 컴파일러 오류 C2372
ms.date: 03/23/2020
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: 4d60f93def9bfe8359496803c8aede1ec698b465
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150942"
---
# <a name="compiler-error-c2372"></a>컴파일러 오류 C2372

> '*identifier*': 재정의 서로 다른 유형의 간접 참조

식별자가 이미 다른 파생 형식으로 정의 되어 있습니다.

다음 샘플에서는 C2372를 생성 합니다.

```cpp
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```
