---
title: 특성 매개 변수 형식(C++/CLI 및 C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: b8cb222af2d5b25a90f35d8d32688567bb3fb1d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172648"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>특성 매개 변수 형식(C++/CLI 및 C++/CX)

특성에 전달된 값은 컴파일 타임에 컴파일러에 알려야 합니다.  특성 매개 변수는 다음 형식일 수 있습니다.

- **bool**

- **char**, **unsigned char**

- **short**, **unsigned short**

- **int**, **unsigned int**

- **long**, **unsigned long**

- **__int64**, **unsigned __int64**

- **float**, **double**

- **wchar_t**

- `char*` 또는 `wchar_t*` 또는 `System::String*`

- `System::Type ^`

- `System::Object ^`

- **enum**

## <a name="example"></a>예제

### <a name="code"></a>코드

```cpp
// attribute_parameter_types.cpp
// compile with: /clr /c
using namespace System;
ref struct AStruct {};

[AttributeUsage(AttributeTargets::ReturnValue)]
ref struct Attr : public Attribute {
   Attr(AStruct ^ i){}
   Attr(bool i){}
   Attr(){}
};

ref struct MyStruct {
   static AStruct ^ x = gcnew AStruct;
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104
   [returnvalue:Attr] int Test2() { return 0; }   // OK
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK
};
```

## <a name="example"></a>예제

### <a name="description"></a>Description

특성을 지정할 때 명명되지 않은 모든 (위치) 인수는 모든 명명된 인수 앞에 와야 합니다.

### <a name="code"></a>코드

```cpp
// extending_metadata_c.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // No arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // Named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

## <a name="example"></a>예제

### <a name="description"></a>Description

특성 매개 변수는 이전 형식의 1차원 배열일 수 있습니다.

### <a name="code"></a>코드

```cpp
// extending_metadata_d.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="see-also"></a>참고 항목

[사용자 정의 특성](user-defined-attributes-cpp-component-extensions.md)
