---
title: nullptr(C++/CLI 및 C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 02da716959deb7fcffa7a63a8308279a765c4569
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172116"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr(C++/CLI 및 C++/CX)

**nullptr** 키워드는 *Null 포인터 값*을 나타냅니다. Null 포인터 값은 개체 핸들, 내부 포인터 또는 네이티브 포인터 형식이 개체를 가리키지 않음을 나타내는 데 사용합니다.

관리 코드 또는 네이티브 코드에 **nullptr**을 사용합니다. 컴파일러는 관리형 및 네이티브 Null 포인터 값에 대해 서로 다른 적절한 명령을 내보냅니다. 이 키워드의 ISO 표준 C++ 버전을 사용하는 방법에 대한 자세한 내용은 [nullptr](../cpp/nullptr.md)을 참조하세요.

**__nullptr** 키워드는 **nullptr**과 의미는 같지만 네이티브 코드에만 적용되는 Microsoft 특정 키워드입니다. 네이티브 C/C++ 코드에 **nullptr**을 사용한 다음, [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션으로 컴파일하면, 컴파일러는 **nullptr**이 네이티브 Null 포인터 값을 나타내는지, 관리형 Null 포인터 값을 나타내는지 확인할 수 없습니다. 컴파일러에 의도를 명확히 나타내려면, **nullptr**을 사용하여 관리형 값을 지정하거나 **__nullptr**을 사용하여 네이티브 값을 지정합니다.

**nullptr** 키워드는 Visual Basic의 **Nothing** 및 C#의 **null**에 해당합니다.

## <a name="usage"></a>사용

**nullptr** 키워드는 핸들, 네이티브 포인터 또는 함수 인수로 사용할 수 있는 곳이면 어디서나 사용할 수 있습니다.

**nullptr** 키워드는 형식이 아니며, 다음 구문에서 사용할 수 없습니다.

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr`(단, `throw (Object^)nullptr;`은 사용 가능함)

**nullptr** 키워드는 다음 포인터 형식의 초기화에 사용할 수 있습니다.

- 네이티브 포인터

- Windows 런타임 핸들

- 관리형 핸들

- 관리형 내부 포인터

참조를 사용하기 전에 포인터 또는 핸들 참조가 Null인지 테스트하는 데 **nullptr** 키워드를 사용할 수 있습니다.

오류 검사에 Null 포인터 값을 사용하는 언어 간의 함수 호출을 올바르게 해석해야 합니다.

핸들을 0으로 초기화할 수 없습니다.**nullptr**만 사용할 수 있습니다. 개체 핸들에 상수 0을 할당하면 boxed `Int32` 및 `Object^`로의 캐스트가 생성됩니다.

## <a name="example"></a>예제

다음 코드 예제에서는 핸들, 네이티브 포인터 또는 함수 인수를 사용할 수 있는 곳이면 어디서나 **nullptr** 키워드를 사용할 수 있음을 보여 줍니다. 또한 예제에서는 참조를 사용하기 전에 확인하는 데 **nullptr** 키워드를 사용할 수 있음을 보여 줍니다.

```cpp
// mcpp_nullptr.cpp
// compile with: /clr
value class V {};
ref class G {};
void f(System::Object ^) {}

int main() {
// Native pointer.
   int *pN = nullptr;
// Managed handle.
   G ^pG = nullptr;
   V ^pV1 = nullptr;
// Managed interior pointer.
   interior_ptr<V> pV2 = nullptr;
// Reference checking before using a pointer.
   if (pN == nullptr) {}
   if (pG == nullptr) {}
   if (pV1 == nullptr) {}
   if (pV2 == nullptr) {}
// nullptr can be used as a function argument.
   f(nullptr);   // calls f(System::Object ^)
}
```

## <a name="example"></a>예제

다음 코드 예제에서는 네이티브 포인터에서 **nullptr**과 0을 서로 바꿔서 사용할 수 있음을 보여 줍니다.

```cpp
// mcpp_nullptr_1.cpp
// compile with: /clr
class MyClass {
public:
   int i;
};

int main() {
   MyClass * pMyClass = nullptr;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");

   pMyClass = 0;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");
}
```

```Output
pMyClass == nullptr

pMyClass == 0

pMyClass == nullptr

pMyClass == 0
```

## <a name="example"></a>예제

다음 코드 예제에서는 **nullptr**이 임의 형식에 대한 핸들 또는 임의 형식에 대한 네이티브 포인터로 해석됨을 보여 줍니다. 여러 형식에 대한 핸들이 있는 함수 오버로드의 경우 모호성 오류가 생성됩니다. 명시적으로 **nullptr**을 한 형식으로 캐스팅해야 합니다.

```cpp
// mcpp_nullptr_2.cpp
// compile with: /clr /LD
void f(int *){}
void f(int ^){}

void f_null() {
   f(nullptr);   // C2668
   // try one of the following lines instead
   f((int *) nullptr);
   f((int ^) nullptr);
}
```

## <a name="example"></a>예제

다음 코드 예제에서는 **nullptr** 캐스팅이 허용되며, **nullptr** 값을 포함하는 캐스트 형식에 대한 포인터 또는 핸들이 반환됨을 보여 줍니다.

```cpp
// mcpp_nullptr_3.cpp
// compile with: /clr /LD
using namespace System;
template <typename T>
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type

int main() {
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)

   // Delete the following line to resolve.
   f(nullptr);

   f(0);   // T = int, call f(int)
}
```

## <a name="example"></a>예제

다음 코드 예제에서는 **nullptr**을 함수 매개 변수로 사용할 수 있음을 보여 줍니다.

```cpp
// mcpp_nullptr_4.cpp
// compile with: /clr
using namespace System;
void f(Object ^ x) {
   Console::WriteLine("test");
}

int main() {
   f(nullptr);
}
```

```Output
test
```

## <a name="example"></a>예제

다음 코드 예제에서는 핸들을 선언하고 명시적으로 초기화하지 않을 경우 기본적으로 **nullptr**로 초기화됨을 보여 줍니다.

```cpp
// mcpp_nullptr_5.cpp
// compile with: /clr
using namespace System;
ref class MyClass {
public:
   void Test() {
      MyClass ^pMyClass;   // gc type
      if (pMyClass == nullptr)
         Console::WriteLine("NULL");
   }
};

int main() {
   MyClass ^ x = gcnew MyClass();
   x -> Test();
}
```

```Output
NULL
```

## <a name="example"></a>예제

다음 코드 예제에서는 **로 컴파일할 때 네이티브 포인터에** nullptr`/clr`을 할당할 수 있음을 보여 줍니다.

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>요구 사항

컴파일러 옵션: (필수 아님, `/ZW` 및 `/clr`를 포함 하 여 모든 코드 생성 옵션에서 지원 됨)

## <a name="see-also"></a>참고 항목

[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)
