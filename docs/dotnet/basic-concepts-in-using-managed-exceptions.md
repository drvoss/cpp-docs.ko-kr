---
title: 관리되는 예외 사용의 기본 개념
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: 6bc1e9c6d40599ae9a821179dcf56dbb7e21bf10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372522"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>관리되는 예외 사용의 기본 개념

이 항목에서는 관리되는 응용 프로그램의 예외 처리에 대해 설명합니다. 즉, **/clr** 컴파일러 옵션으로 컴파일되는 응용 프로그램입니다.

## <a name="in-this-topic"></a>항목 내용

- [/clr에서 예외 던지기](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR 확장을 위한 시도/캐치 블록](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>설명

**/clr** 옵션을 사용 하 여 컴파일하는 경우 CLR 예외를 처리할 수 있을 뿐만 아니라 표준 <xref:System.Exception> 클래스는 CLR 예외를 처리하는 데 유용한 많은 메서드를 제공하며 사용자 정의 예외 클래스의 기본 클래스로 권장됩니다.

인터페이스에서 파생 된 예외 형식을 catch **/clr**에서 지원 되지 않습니다. 또한 공통 언어 런타임에서는 스택 오버플로 예외를 catch할 수 없습니다. 스택 오버플로 예외가 프로세스를 종료합니다.

관리 및 관리되지 않는 응용 프로그램의 예외 처리 차이점에 대한 자세한 내용은 [C++에 대한 관리되는 확장에서 예외 처리 동작의 차이점을](../dotnet/differences-in-exception-handling-behavior-under-clr.md)참조하십시오.

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/clr에서 예외 던지기

C++ throw 식은 CLR 형식에 핸들을 throw하도록 확장됩니다. 다음 예제는 사용자 지정 예외 형식을 만들고 해당 형식의 인스턴스를 throw합니다.

```cpp
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

값 형식은 throw하기 전에 boxed여야 합니다.

```cpp
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR 확장을 위한 시도/캐치 블록

동일한 **try**/**catch** 블록 구조를 사용하여 CLR 및 네이티브 예외를 모두 catch할 수 있습니다.

```cpp
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>출력

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>C++ 오브젝트에 대한 해제 순서

해제는 throw 함수와 처리 함수 사이의 런타임 스택에 있을 수 있는 소멸자가 있는 C++ 개체에 대해 발생합니다. CLR 형식은 힙에 할당되므로 해제는 적용되지 않습니다.

throw된 예외에 대 한 이벤트의 순서는 다음과 같습니다.

1. 런타임은 스택에서 적절한 catch 절을 찾거나 SEH에 대한 필터를 제외한 SEH의 경우 예외를 catch합니다. Catch 절은 먼저 어휘 순서로 검색된 다음 호출 스택아래로 동적으로 검색됩니다.

1. 올바른 처리기를 발견하면 스택이 해당 지점으로 해제됩니다. 스택의 각 함수 호출에 대해 해당 로컬 개체가 소멸되고 대부분의 중첩된 바깥쪽에서 __finally 블록이 실행됩니다.

1. 스택이 해제되면 catch 절이 실행됩니다.

### <a name="catching-unmanaged-types"></a>관리되지 않는 형식 잡기

관리되지 않는 개체 형식이 throw되면 형식은 <xref:System.Runtime.InteropServices.SEHException>제외하여 래핑됩니다. 적절한 **catch** 절을 검색할 때 두 가지 가능성이 있습니다.

- 네이티브 C++ 형식이 발생하면 예외가 래핑해제되고 발생한 형식과 비교됩니다. 이 비교를 통해 기본 C++ 형식을 정상적인 방식으로 잡을 수 있습니다.

- 그러나 **SEHException** 형식또는 기본 클래스의 **catch** 절이 먼저 검사되는 경우 절은 예외를 가로챌 수 있습니다. 따라서 CLR 형식의 catch 절 보다 먼저 네이티브 C ++ 형식을 catch 하는 모든 catch 절을 배치 해야 합니다.

다음 사항에 유의하세요.

```
catch(Object^)
```

and

```
catch(...)
```

둘 다 SEH 예외를 포함하여 throw된 형식을 잡을 것입니다.

관리되지 않는 형식이 catch(Object^)에 의해 catch되는 경우 throw된 개체가 파괴되지 않습니다.

관리되지 않는 예외를 throw하거나 catch할 때 **/EHs** 또는 **/EHa**대신 [/EHsc](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[예외 처리](../cpp/exception-handling-in-visual-cpp.md)
