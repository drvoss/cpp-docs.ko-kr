---
title: for each, in
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: f1f5523eb22bd8a839da9b3f73dd6c3718b4fd63
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825797"
---
# <a name="for-each-in"></a>for each, in

배열 또는 컬렉션을 반복합니다. 이 비표준 키워드는 C++/CLI 및 네이티브 C++ 프로젝트에서 사용할 수 있습니다. 그러나 사용하지 않는 것이 좋습니다. 표준 [범위 기반 For 문 (c + +)](../cpp/range-based-for-statement-cpp.md) 을 대신 사용 하는 것이 좋습니다.

## <a name="all-runtimes"></a>모든 런타임

### <a name="syntax"></a>구문

> **for each (** *식* **의** *형식* *식별자* **) {**\
> &nbsp;&nbsp;&nbsp;&nbsp;*할당문*\
> **}**

### <a name="parameters"></a>매개 변수

*type*<br/>
`identifier`의 형식입니다.

*identifier*<br/>
반복 변수는 컬렉션 요소를 나타냅니다.  가 `identifier` [추적 참조 연산자](../extensions/tracking-reference-operator-cpp-component-extensions.md)인 경우 요소를 수정할 수 있습니다.

*expression*<br/>
배열 식 또는 컬렉션입니다. 컬렉션 요소는 컴파일러가 `identifier` 형식으로 변환할 수 있어야 합니다.

*할당문*<br/>
실행할 하나 이상의 문입니다.

### <a name="remarks"></a>설명

`for each` 문은 컬렉션을 반복하는 데 사용됩니다. 컬렉션의 요소를 수정할 수 있지만 요소를 추가하거나 삭제할 수 없습니다.

*문은* 배열 또는 컬렉션의 각 요소에 대해 실행 됩니다. 컬렉션의 모든 요소에 대해 반복이 완료된 후 제어가 `for each` 블록 다음 문으로 전달됩니다.

`for each`및 `in` 은 [상황에 맞는 키워드](../extensions/context-sensitive-keywords-cpp-component-extensions.md)입니다.

추가 정보는 다음 항목을 참조하세요.

- [for each를 사용하여 C++ 표준 라이브러리 컬렉션 반복](../dotnet/iterating-over-stl-collection-by-using-for-each.md)

- [방법: for each로 배열 반복](../dotnet/how-to-iterate-over-arrays-with-for-each.md)

- [방법: for each로 제네릭 컬렉션 반복](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)

- [방법: for each로 사용자 정의 컬렉션 반복](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)

## <a name="windows-runtime"></a>Windows 런타임

### <a name="requirements"></a>요구 사항

컴파일러 옵션: **/Zw**

### <a name="example"></a>예제

이 예제는 `for each`를 사용해서 문자열을 반복하는 방법을 보여줍니다.

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

**출력**

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>공용 언어 런타임

**주의**

CLR 구문은 다음을 제외한 **모든 런타임** 구문과 같습니다.

*expression*<br/>
관리되는 배열 식 또는 컬렉션입니다. 컬렉션 요소는 컴파일러에서 <xref:System.Object> *식별자* 형식으로 변환할 수 있어야 합니다.

*식은* <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>을 구현 하는 형식 또는에 `GetEnumerator` <xref:System.Collections.IEnumerator> `IEnumerator`정의 된 모든 메서드를 구현 하거나 선언 하는 형식을 반환 하는 메서드를 정의 하는 형식으로 계산 됩니다.

### <a name="requirements"></a>요구 사항

컴파일러 옵션: **/clr**

### <a name="example"></a>예제

이 예제는 `for each`를 사용해서 문자열을 반복하는 방법을 보여줍니다.

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

**출력**

```Output
abcd

Testing
```

## <a name="see-also"></a>참고 항목

[런타임 플랫폼용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)
