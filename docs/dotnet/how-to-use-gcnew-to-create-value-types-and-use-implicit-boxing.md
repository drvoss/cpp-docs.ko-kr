---
title: '방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
ms.openlocfilehash: 891704d24ca7a7bf8724c8e57faa2aef20a7f982
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544876"
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용

값 형식에 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) 를 사용 하면 boxed 값 형식이 생성 되 고,이 형식은 관리 되는 가비지 수집 힙에 배치 될 수 있습니다.

## <a name="example"></a>예제

```cpp
// vcmcppv2_explicit_boxing4.cpp
// compile with: /clr
public value class V {
public:
   int m_i;
   V(int i) : m_i(i) {}
};

public ref struct TC {
   void do_test(V^ v) {
      if (v != nullptr)
         ;
      else
         ;
   }
};

int main() {
   V^ v = gcnew V(42);
   TC^ tc = gcnew TC;
   tc->do_test(v);
}
```

## <a name="see-also"></a>참고 항목

[Boxing](../extensions/boxing-cpp-component-extensions.md)
