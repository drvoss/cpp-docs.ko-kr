---
title: 컴파일러 오류 C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 022fca01706fefca2a14ea952586ec91b0c5b240
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207684"
---
# <a name="compiler-error-c2094"></a>컴파일러 오류 C2094

'identifier' 레이블이 정의되지 않았습니다.

[goto](../../cpp/goto-statement-cpp.md) 문에서 사용하는 레이블이 함수에 존재하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2094를 생성합니다.

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

가능한 해결 방법:

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```
