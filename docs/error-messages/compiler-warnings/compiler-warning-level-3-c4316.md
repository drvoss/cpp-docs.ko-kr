---
title: 컴파일러 경고 (수준 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 0d920cb3dc967854d1a507d06ce31fde6a670434
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198850"
---
# <a name="compiler-warning-level-3-c4316"></a>컴파일러 경고 (수준 3) C4316

힙에 할당 된 개체는이 형식에 대해 정렬 되지 않을 수 있습니다.

`operator new`를 사용 하 여 할당 된 오버 정렬 된 개체는 지정 된 맞춤을 가질 수 없습니다. 정렬 된 할당 루틴 (예: [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 및 [_aligned_free](../../c-runtime-library/reference/aligned-free.md))을 사용 하도록 오버 정렬 된 형식에 대해 [operator new](../../c-runtime-library/operator-new-crt.md) 및 [operator delete](../../c-runtime-library/operator-delete-crt.md) 를 재정의 합니다. 다음 샘플에서는 C4316를 생성 합니다.

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
