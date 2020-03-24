---
title: 컴파일러 경고 C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: ca80e847174bbe225acaf8631c646d8c6a94c50a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164835"
---
# <a name="compiler-warning-c4972"></a>컴파일러 경고 C4972

왼쪽 항의 값(l-value)을 확인할 수 없어 unboxing 작업의 결과를 직접 수정하거나 처리하고 있습니다.

핸들을 값 형식으로 역참조(unboxing이라고도 함)한 후 할당하는 작업을 확인할 수 없습니다.

자세한 내용은 [boxing](../../extensions/boxing-cpp-component-extensions.md)에 정의된 인터페이스의 private C++ 관련 구현입니다.

## <a name="example"></a>예제

다음 샘플에서는 C4972를 생성합니다.

```cpp
// C4972.cpp
// compile with: /clr:safe
using namespace System;
ref struct R {
   int ^ p;   // a value type
};

int main() {
   R ^ r = gcnew R;
   *(r->p) = 10;   // C4972

   // OK
   r->p = 10;
   Console::WriteLine( r->p );
   Console::WriteLine( *(r->p) );
}
```
