---
title: 컴파일러 경고(수준 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5970aa439a450bda4c1a2036da299d5c3cfbdb7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198902"
---
# <a name="compiler-warning-level-3-c4290"></a>컴파일러 경고(수준 3) C4290

C++함수가 __declspec 되지 않았음을 나타내는 경우를 제외 하 고 예외 사양이 무시 됩니다 (nothrow).

함수는 시각적 C++ 으로 허용 되지만 구현 하지 않는 예외 사양을 사용 하 여 선언 됩니다. 컴파일 중에 무시 되는 예외 사양을 사용 하는 코드는 나중에 예외 사양을 지 원하는 버전에서 다시 사용 하도록 다시 컴파일하거나 연결 해야 할 수 있습니다.

자세한 내용은 [예외 사양 (throw)](../../cpp/exception-specifications-throw-cpp.md) 을 참조 하세요.

[경고](../../preprocessor/warning.md) pragma를 사용 하 여이 경고를 방지할 수 있습니다.

```cpp
#pragma warning( disable : 4290 )
```

다음 코드 샘플에서는 C4290를 생성 합니다.

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```
