---
title: 컴파일러 오류 C3541
ms.date: 11/04/2016
f1_keywords:
- C3541
helpviewer_keywords:
- C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
ms.openlocfilehash: 32926d0ef9343bad9ed73458e4d52d317b628109
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221044"
---
# <a name="compiler-error-c3541"></a>컴파일러 오류 C3541

' type ': ' auto '가 포함 된 형식에는 typeid를 적용할 수 없습니다.

지정 된 형식에는 지정자를 포함 하므로 [typeid](../../extensions/typeid-cpp-component-extensions.md) 연산자를 적용할 수 없습니다 **`auto`** .

## <a name="example"></a>예제

다음 예에서는 C3541를 생성 합니다.

```cpp
// C3541.cpp
// Compile with /Zc:auto
#include <typeinfo>
int main() {
    auto x = 123;
    typeid(x);    // OK
    typeid(auto); // C3541
    return 0;
}
```

## <a name="see-also"></a>참조

[auto 키워드](../../cpp/auto-keyword.md)<br/>
[/Zc: auto (변수 형식 추론)](../../build/reference/zc-auto-deduce-variable-type.md)<br/>
[typeid](../../extensions/typeid-cpp-component-extensions.md)
