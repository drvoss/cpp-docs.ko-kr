---
title: 컴파일러 오류 C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 3e445b52c2a0abbfca198c4cb0f4108dd5ba5ffb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233433"
---
# <a name="compiler-error-c2886"></a>컴파일러 오류 C2886

' class:: identifier ':-선언을 사용 하 여 기호를 멤버에 사용할 수 없습니다.

선언에는 **`using`** 네임 스페이스 이름과 같은 기호가 사용 됩니다. **`using`** 선언은 기본 클래스 멤버를 선언 하는 데 사용할 수 있습니다.

다음 샘플에서는 C2886를 생성 합니다.

```cpp
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```
