---
title: 컴파일러 오류 C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: e4163d68e0fbfea062279ba91e2c902855245e4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220394"
---
# <a name="compiler-error-c2272"></a>컴파일러 오류 C2272

' function ': 정적 멤버 함수에는 한정자를 사용할 수 없습니다.

**`static`** 멤버 함수는 [const](../../cpp/const-cpp.md) 또는 [volatile](../../cpp/volatile-cpp.md)과 같은 메모리 모델 지정자를 사용 하 여 선언 되며, 이러한 한정자는 멤버 함수에서 허용 되지 않습니다 **`static`** .

다음 샘플에서는 C2272를 생성 합니다.

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
