---
title: 컴파일러 오류 C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: e7d1ce25e13e1b601c4abc85e71db484f7b3f822
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221031"
---
# <a name="compiler-error-c3898"></a>컴파일러 오류 C3898

' var ': 형식 데이터 멤버는 관리 되는 형식의 멤버일 수만 있습니다.

네이티브 클래스에서 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버가 선언 되었습니다.  **`initonly`** 데이터 멤버는 CLR 클래스 에서만 선언할 수 있습니다.

다음 샘플에서는 C3898를 생성 합니다.

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

해결 방법:

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
