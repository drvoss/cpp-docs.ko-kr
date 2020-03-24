---
title: 컴파일러 경고 C4485
ms.date: 11/04/2016
f1_keywords:
- C4485
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
ms.openlocfilehash: c92f805eb2960336ed34f5da93b6c13f46bf15ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165147"
---
# <a name="compiler-warning-c4485"></a>컴파일러 경고 C4485

' override_function ': 기본 ref 클래스 메서드 ' base_class_function '과 (와) 일치 하지만 ' new ' 또는 ' override '로 표시 되어 있지 않습니다. ' new ' (및 ' virtual ')를 가정 합니다.

접근자는 `virtual` 키워드를 사용 하거나 사용 하지 않고 기본 클래스 접근자 함수를 사용 하 여 재정의 하지만 `override` 또는 `new` 지정자는 재정의 함수 시그니처의 일부가 아닙니다. 이 경고를 해결 하려면 `new` 또는 `override` 지정자를 추가 합니다.

자세한 내용은 [override](../../extensions/override-cpp-component-extensions.md) 및 [new (vtable의 새 슬롯)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) 를 참조 하세요.

C4485는 항상 오류로 실행 됩니다. C4485를 표시 하지 않으려면 [warning](../../preprocessor/warning.md) pragma를 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4485를 생성 합니다.

```cpp
// C4485.cpp
// compile with: /clr
delegate void Del();

ref struct A {
   virtual event Del ^E;
};

ref struct B : A {
   virtual event Del ^E;   // C4485
};

ref struct C : B {
   virtual event Del ^E {
      void raise() override {}
      void add(Del ^) override {}
      void remove(Del^) override {}
   }
};
```
