---
title: '방법: 명시적으로 boxing 요청'
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, explicitly requesting
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
ms.openlocfilehash: 721a57219c7216cb57f497011da1733c9e3eb7f2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545314"
---
# <a name="how-to-explicitly-request-boxing"></a>방법: 명시적으로 boxing 요청

`Object`형식의 변수에 변수를 할당 하 여 명시적으로 boxing을 요청할 수 있습니다.

## <a name="example"></a>예제

```cpp
// vcmcppv2_explicit_boxing3.cpp
// compile with: /clr
using namespace System;

void f(int i) {
   Console::WriteLine("f(int i)");
}

void f(Object ^o) {
   Console::WriteLine("f(Object^ o)");
}

int main() {
   int i = 5;
   Object ^ O = i;   // forces i to be boxed
   f(i);
   f(O);
   f( (Object^)i );  // boxes i
}
```

```Output
f(int i)
f(Object^ o)
f(Object^ o)
```

## <a name="see-also"></a>참고 항목

[Boxing](../extensions/boxing-cpp-component-extensions.md)
