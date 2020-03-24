---
title: 컴파일러 경고(수준 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: d33e5c60bac657060ffef2a43686a5f737eb11cc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161310"
---
# <a name="compiler-warning-level-4-c4212"></a>컴파일러 경고(수준 4) C4212

비표준 확장이 사용 됨: 함수 선언에서 줄임표를 사용 했습니다.

함수 프로토타입에는 다양 한 수의 인수가 있습니다. 함수 정의는 그렇지 않습니다.

다음 샘플에서는 C4212를 생성 합니다.

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```
