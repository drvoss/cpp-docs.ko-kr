---
title: '방법: 재지정 지정자 선언(C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 9f3f6855f257d0af250b9bbdd2c0360b308ce775
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374445"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>방법: 네이티브 컴파일에 override 지정자 선언(C++/CLI)

[sealed](../extensions/sealed-cpp-component-extensions.md), [[편집]](../extensions/abstract-cpp-component-extensions.md) **/ZW** 또는 [/clr를](../build/reference/clr-common-language-runtime-compilation.md)사용하지 않는 컴파일에서 사용할 수 있습니다. [override](../extensions/override-cpp-component-extensions.md)

> [!NOTE]
> ISO C++11 표준 언어에는 [재정의](../cpp/override-specifier.md) 식별자와 [최종](../cpp/final-specifier.md) 식별자가 있으며 둘 다 `final` 네이티브 `sealed` 전용으로 컴파일되는 코드 대신 Visual Studio Use에서 지원됩니다.

## <a name="example"></a>예제

### <a name="description"></a>Description

다음 예제에서는 `sealed` 네이티브 컴파일에서 유효한 것을 보여 주며 있습니다.

### <a name="code"></a>코드

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example"></a>예제

### <a name="description"></a>Description

다음 예제에서는 `override` 네이티브 컴파일에서 유효한 것을 보여 주며 있습니다.

### <a name="code"></a>코드

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example"></a>예제

### <a name="description"></a>Description

이 예제에서는 `abstract` 네이티브 컴파일에서 유효한 것을 보여 주며 있습니다.

### <a name="code"></a>코드

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>참고 항목

[Override 지정자](../extensions/override-specifiers-cpp-component-extensions.md)
