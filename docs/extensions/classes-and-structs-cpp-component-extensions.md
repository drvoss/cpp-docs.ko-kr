---
title: ref class 및 ref struct(C++/CLI 및 C++/CX)
ms.date: 05/30/2019
ms.topic: reference
f1_keywords:
- ref class
- value class
- ref struct
- value struct
helpviewer_keywords:
- ref class keyword [C++]
- value class keyword [C++]
- value struct keyword [C++]
- ref struct keyword [C++]
ms.assetid: 5c360764-b229-49c6-9357-66213afbc372
ms.openlocfilehash: 78cf7cf16c4ccf29f72038fd79c5d7a1689c05ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172570"
---
# <a name="ref-class-and-ref-struct--ccli-and-ccx"></a>ref class 및 ref struct(C++/CLI 및 C++/CX)

**ref class** 또는 **ref struct** 확장은 ‘개체 수명’이 자동 관리되는 클래스나 구조체를 선언합니다. 개체에 더 이상 액세스할 수 없거나 개체가 범위를 벗어나면 메모리가 해제됩니다.

## <a name="all-runtimes"></a>모든 런타임

### <a name="syntax"></a>구문

```cpp
      class_access
      ref class
      name
      modifier :  inherit_accessbase_type {};
class_accessref structnamemodifier :  inherit_accessbase_type {};
class_accessvalue classnamemodifier :  inherit_accessbase_type {};
class_accessvalue structnamemodifier :  inherit_accessbase_type {};
```

### <a name="parameters"></a>매개 변수

*class_access*<br/>
(선택 사항) 어셈블리 외부 클래스 또는 구조체의 접근성입니다. 가능한 값은 **public** 및 **private**입니다(**private**이 기본값임). 중첩 클래스 또는 구조체에는 *class_access* 지정자를 사용할 수 없습니다.

*name*<br/>
클래스 또는 구조체의 이름입니다.

*modifier*<br/>
(선택 사항) 유효한 한정자는 [abstract](abstract-cpp-component-extensions.md) 및 [sealed](sealed-cpp-component-extensions.md)입니다.

*inherit_access*<br/>
(선택 사항) *base_type*의 접근성입니다. 허용되는 접근성은 **public**뿐입니다(**public**이 기본값임).

*base_type*<br/>
(선택 사항) 기본 형식입니다. 그러나 값 형식은 기본 형식으로 작동할 수 없습니다.

자세한 내용은 Windows 런타임 및 공용 언어 런타임 섹션에서 이 매개 변수에 대한 언어별 설명을 참조하세요.

### <a name="remarks"></a>설명

**ref class** 또는 **value class**를 사용하여 선언된 개체의 기본 멤버 접근성은 **private**입니다. 또한 **ref struct** 또는 **value struct**를 사용하여 선언된 개체의 기본 멤버 접근성은 **public**입니다.

참조 형식이 다른 참조 형식에서 상속받는 경우 기본 클래스의 가상 함수는 [override](override-cpp-component-extensions.md)를 사용하여 명시적으로 재정의하거나 [new(vtable의 새 슬롯)](new-new-slot-in-vtable-cpp-component-extensions.md)를 사용하여 숨겨야 합니다. 파생 클래스 함수도 **virtual**로 명시적으로 표시해야 합니다.

컴파일 시간에 형식이 **ref class**, **ref struct**, **value class**, **value struct**인지 여부를 검색하려면 `__is_ref_class (type)`, `__is_value_class (type)` 또는 `__is_simple_value_class (type)`를 사용합니다. 자세한 내용은 [형식 특성에 대한 컴파일러 지원](compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하세요.

클래스 및 구조체에 대한 자세한 내용은 다음을 참조하세요.

- [클래스 및 구조체 인스턴스화](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)

- [참조 형식에 대한 C++ 스택 의미 체계](../dotnet/cpp-stack-semantics-for-reference-types.md)

- [클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)

- [방법: 클래스 및 구조체 정의 및 사용 (C++/cli)의 소멸자 및 종료자](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)

- [사용자 정의 연산자(C++/CLI)](../dotnet/user-defined-operators-cpp-cli.md)

- [사용자 정의 변환(C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md)

- [방법: C#에서 사용하기 위해 네이티브 클래스 래핑](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

- [제네릭 클래스(C++/CLI)](generic-classes-cpp-cli.md)

## <a name="windows-runtime"></a>Windows 런타임

### <a name="remarks"></a>설명

[Ref 클래스 및 구조체](../cppcx/ref-classes-and-structs-c-cx.md) 및 [값 클래스 및 구조체](../cppcx/value-classes-and-structs-c-cx.md)를 참조하세요.

### <a name="parameters"></a>매개 변수

*base_type*<br/>
(선택 사항) 기본 형식입니다. **ref class** 또는 **ref struct**는 0개 이상의 인터페이스와 0개 또는 한 개의 **ref** 형식에서 상속받을 수 있습니다. **value class** 또는 **value struct**는 0개 이상의 인터페이스에서만 상속받을 수 있습니다.

**ref class** 또는 **ref struct** 키워드를 사용하여 개체를 선언하면 개체 핸들, 즉 개체에 대한 참조 카운터 포인터가 이 개체에 액세스합니다. 선언된 변수가 범위를 벗어나면 컴파일러가 자동으로 내부 개체를 삭제합니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 핸들이 실제로 전달되거나 저장됩니다.

**value class** 또는 **value struct** 키워드를 사용하여 개체를 선언하면 선언된 개체의 개체 수명이 감독되지 않습니다. 개체는 다른 표준 C++ 클래스 또는 구조체와 같습니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/ZW`

## <a name="common-language-runtime"></a>공용 언어 런타임

### <a name="remarks"></a>설명

다음 표에는 C++/CLI와 관련된, **모든 런타임** 섹션에 표시된 구문과의 차이점이 나와 있습니다.

### <a name="parameters"></a>매개 변수

*base_type*<br/>
(선택 사항) 기본 형식입니다. **ref class** 또는 **ref struct**는 0개 이상의 관리형 인터페이스와 0개 또는 한 개의 ref 형식에서 상속받을 수 있습니다. **value class** 또는 **value struct**는 0개 이상의 관리형 인터페이스에서만 상속받을 수 있습니다.

**ref class** 및 **ref struct** 키워드는 클래스 또는 구조체를 힙에 할당하도록 컴파일러에 지시합니다. 개체가 호출에서 매개 변수로 사용되거나 변수에 저장되면 개체 참조가 실제로 전달되거나 저장됩니다.

**value class** 및 **value struct** 키워드는 할당된 클래스 또는 구조체의 값을 함수에 전달하거나 멤버에 저장하도록 컴파일러에 지시합니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: `/clr`

## <a name="see-also"></a>참고 항목

[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)
