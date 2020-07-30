---
title: 컴파일러 오류 C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: c2c7de919181cd0e89526f8ffacabaec73fb8f89
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223436"
---
# <a name="compiler-error-c3274"></a>컴파일러 오류 C3274

짝이 되는 try 없이 __finally/finally만 있습니다.

일치 하지 않고 [__finally](../../cpp/try-finally-statement.md) 또는 [finally](../../dotnet/finally.md) 문을 찾았습니다 **`try`** . 이 문제를 해결 하려면 문을 삭제 **`__finally`** 하거나 **`try`** 에 대 한 문을 추가 **`__finally`** 합니다.

다음 샘플에서는 C3274를 생성합니다.

```cpp
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```
