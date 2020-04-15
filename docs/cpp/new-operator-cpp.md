---
title: new 연산자 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
ms.openlocfilehash: ac89bf37b8aaaa9d77393b714a233f8a4c998139
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367868"
---
# <a name="new-operator-c"></a>new 연산자 (C++)

사용 사용 저장소에서 형식 이름 개체 또는 *개체배열에* 대한 메모리를 할당하고 적절하게 입력된 0이 아닌 포인터를 개체에 반환합니다.

> [!NOTE]
> Microsoft C++ 구성 요소 확장은 vtable 슬롯 항목을 추가하는 **새** 키워드에 대한 지원을 제공합니다. 자세한 내용은 [새(vtable의 새 슬롯)를](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md) 참조하십시오.

## <a name="syntax"></a>구문

```
[::] new [placement] new-type-name [new-initializer]
[::] new [placement] ( type-name ) [new-initializer]
```

## <a name="remarks"></a>설명

실패하면 **새** 는 0을 반환하거나 예외를 throw합니다. 자세한 내용은 [새 및 삭제 연산자를](../cpp/new-and-delete-operators.md) 참조하십시오. 사용자 지정 예외 처리 루틴을 작성하고 함수 이름을 인수로 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 라이브러리 함수를 호출하여 이 기본 동작을 변경할 수 있습니다.

관리되는 힙에서 개체를 만드는 방법에 대한 자세한 내용은 [gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md)을 참조하십시오.

**새** 가 C++ 클래스 개체에 대 한 메모리를 할당 하는 데 사용 되는 경우 메모리를 할당 하는 후 개체의 생성자가 호출 됩니다.

[delete](../cpp/delete-operator-cpp.md) 연산자를 사용하여 **새** 연산자로 할당된 메모리를 할당 합니다.

다음 예제에서는 크기가 `dim`의 10배인 2차원 문자 배열을 할당한 다음 해제합니다. 다차원 배열을 할당할 때는 첫 번째를 제외한 모든 차원이 양수 값으로 계산되는 상수 식이어야 합니다. 맨 왼쪽 배열 차원은 양수 값으로 계산되는 임의의 식일 수 있습니다. **새** 연산자사용 배열을 할당할 때 첫 번째 **new** 차원은 0이 될 수 있습니다.

```cpp
char (*pchar)[10] = new char[dim][10];
delete [] pchar;
```

*형식 이름에는* **const,** **volatile,** 클래스 선언 또는 열거형 선언이 포함될 수 없습니다. 따라서 다음 식은 올바르지 않습니다.

```cpp
volatile char *vch = new volatile char[20];
```

**새** 연산자는 개체가 아니므로 참조 형식을 할당하지 않습니다.

**새** 연산자는 함수를 할당하는 데 사용할 수 없지만 함수에 포인터를 할당하는 데 사용할 수 있습니다. 다음 예제에서는 정수를 반환하는 함수에 대한 7개의 포인터 배열을 할당한 다음 해제합니다.

```cpp
int (**p) () = new (int (*[7]) ());
delete *p;
```

추가 인수 없이 **새** 연산자를 사용하고 [/GX](../build/reference/gx-enable-exception-handling.md), [/EHa](../build/reference/eh-exception-handling-model.md)또는 [/EHs](../build/reference/eh-exception-handling-model.md) 옵션을 사용하여 컴파일하는 경우 컴파일러는 생성자가 예외를 throw하면 연산자 **delete를** 호출하는 코드를 생성합니다.

다음 목록은 **new의**문법 요소를 설명합니다.

*배치*<br/>
**새**에 과부하가 걸릴 경우 추가 인수를 전달하는 방법을 제공합니다.

*유형 이름*<br/>
기본 제공 또는 사용자 정의 형식 중에서 할당할 형식을 지정합니다. 형식 사양이 복잡한 경우 괄호로 묶어 바인딩 순서를 강제로 지정할 수 있습니다.

*initializer*<br/>
초기화된 개체의 값을 제공합니다. 배열에 대한 이니셜라이저는 지정할 수 없습니다. **새** 연산자는 클래스에 기본 생성자가 있는 경우에만 개체 배열을 만듭니다.

## <a name="example"></a>예제

다음 코드 예제는 문자 배열 및 `CName` 클래스 개체를 할당한 다음 해제합니다.

```cpp
// expre_new_Operator.cpp
// compile with: /EHsc
#include <string.h>

class CName {
public:
   enum {
      sizeOfBuffer = 256
   };

   char m_szFirst[sizeOfBuffer];
   char m_szLast[sizeOfBuffer];

public:
   void SetName(char* pszFirst, char* pszLast) {
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);
   }

};

int main() {
   // Allocate memory for the array
   char* pCharArray = new char[CName::sizeOfBuffer];
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");

   // Deallocate memory for the array
   delete [] pCharArray;
   pCharArray = NULL;

   // Allocate memory for the object
   CName* pName = new CName;
   pName->SetName("Firstname", "Lastname");

   // Deallocate memory for the object
   delete pName;
   pName = NULL;
}
```

## <a name="example"></a>예제

**새** 연산자의 배치 새 형식을 사용하는 경우 할당 크기 외에 인수가 있는 양식은 생성자가 예외를 throw하는 경우 **delete** 연산자의 배치 양식을 지원하지 않습니다. 다음은 그 예입니다.

```cpp
// expre_new_Operator2.cpp
// C2660 expected
class A {
public:
   A(int) { throw "Fail!"; }
};
void F(void) {
   try {
      // heap memory pointed to by pa1 will be deallocated
      // by calling ::operator delete(void*).
      A* pa1 = new A(10);
   } catch (...) {
   }
   try {
      // This will call ::operator new(size_t, char*, int).
      // When A::A(int) does a throw, we should call
      // ::operator delete(void*, char*, int) to deallocate
      // the memory pointed to by pa2.  Since
      // ::operator delete(void*, char*, int) has not been implemented,
      // memory will be leaked when the deallocation cannot occur.

      A* pa2 = new(__FILE__, __LINE__) A(20);
   } catch (...) {
   }
}

int main() {
   A a;
}
```

## <a name="initializing-object-allocated-with-new"></a>new로 할당된 개체 초기화

선택적 *초기화자* 필드는 **새** 연산자의 문법에 포함됩니다. 사용자 정의 생성자를 사용하여 새 개체를 초기화할 수 있습니다. 초기화가 수행되는 방법에 대한 자세한 내용은 [Initializer s](../cpp/initializers.md). 다음 예제에서는 **새** 연산자와 함께 초기화 식을 사용하는 방법을 보여 줍니다.

```cpp
// expre_Initializing_Objects_Allocated_with_new.cpp
class Acct
{
public:
    // Define default constructor and a constructor that accepts
    //  an initial balance.
    Acct() { balance = 0.0; }
    Acct( double init_balance ) { balance = init_balance; }
private:
    double balance;
};

int main()
{
    Acct *CheckingAcct = new Acct;
    Acct *SavingsAcct = new Acct ( 34.98 );
    double *HowMuch = new double ( 43.0 );
    // ...
}
```

이 예제에서는 `CheckingAcct` **새** 연산자를 사용하여 개체가 할당되지만 기본 초기화가 지정되지 는 않습니다. 따라서 클래스의 기본 생성자인 `Acct()`가 호출됩니다. 그런 다음 명시적으로 34.98로 초기화된다는 점을 제외하고 `SavingsAcct` 개체가 같은 식으로 할당됩니다. 34.98은 **double**형식이므로 해당 형식의 인수를 취하는 생성자가 초기화를 처리하기 위해 호출됩니다. 마지막으로 비클래스 형식 `HowMuch`가 43.0으로 초기화됩니다.

개체가 클래스 형식이고 해당 클래스에 생성자가 있는 경우(앞의 예제와 같이) 다음 조건 중 하나가 충족되는 경우에만 새 연산자가 **개체를** 초기화할 수 있습니다.

- 이니셜라이저에 제공된 인수는 생성자의 인수와 일치합니다.

- 클래스에 기본 생성자(인수 없이 호출할 수 있는 생성자)가 있습니다.

**새** 연산자를 사용하여 배열을 할당할 때 명시적 요소별 초기화를 수행할 수 없습니다. 기본 생성자(있는 경우)만 호출됩니다. 자세한 내용은 [기본 인수를](../cpp/default-arguments.md) 참조하십시오.

메모리 할당이**실패하면(연산자 new가** 값을 0으로 반환함) 초기화가 수행되지 않습니다. 존재하지 않는 데이터를 초기화하려는 시도를 막을 수 있습니다.

함수 호출과 마찬가지로 초기화된 식이 계산되는 순서가 정의되지 않습니다. 또한 메모리 할당을 수행하기 전에 완전히 계산되는 이 식에 의존하지 마십시오. 메모리 할당이 실패하고 **새** 연산자가 0을 반환하면 초기화자의 일부 식이 완전히 평가되지 않을 수 있습니다.

## <a name="lifetime-of-objects-allocated-with-new"></a>new로 할당된 개체 수명

**새** 연산자로 할당된 개체는 정의된 범위가 종료될 때 소멸되지 않습니다. **새** 연산자는 할당된 개체에 대한 포인터를 반환하기 때문에 프로그램은 해당 개체에 액세스하기에 적합한 범위의 포인터를 정의해야 합니다. 다음은 그 예입니다.

```cpp
// expre_Lifetime_of_Objects_Allocated_with_new.cpp
// C2541 expected
int main()
{
    // Use new operator to allocate an array of 20 characters.
    char *AnArray = new char[20];

    for( int i = 0; i < 20; ++i )
    {
        // On the first iteration of the loop, allocate
        //  another array of 20 characters.
        if( i == 0 )
        {
            char *AnotherArray = new char[20];
        }
    }

    delete [] AnotherArray; // Error: pointer out of scope.
    delete [] AnArray;      // OK: pointer still in scope.
}
```

`AnotherArray` 포인터가 예제 범위를 벗어나면 개체를 더 이상 삭제할 수 없습니다.

## <a name="how-new-works"></a>new 작동 방식

*할당 식(새* 연산자가 **new** 포함된 식)은 다음 세 가지 작업을 수행합니다.

- 할당할 개체에 대한 스토리지를 찾고 예약합니다. 이 단계가 완료되면 올바른 양의 스토리지가 할당되지만 아직 개체는 아닙니다.

- 개체를 초기화합니다. 초기화가 완료되면 할당된 스토리지가 개체가 되는 데 충분한 정보가 있습니다.

- *새 형식 이름* 또는 형식 이름에서 파생 된 포인터 형식의 개체에 대 한 *포인터를*반환 합니다. 프로그램에서는 이 포인터를 사용하여 새로 할당된 개체에 액세스합니다.

**새** 연산자는 함수 **연산자 새**를 호출합니다. 모든 형식의 배열과 **클래스,** **구조체**또는 **공용 구조체** 형식이 아닌 개체의 경우 전역 함수 **::operator new가**저장소를 할당하기 위해 호출됩니다. 클래스 형식 개체는 클래스별로 고유한 **연산자 새** 정적 멤버 함수를 정의할 수 있습니다.

컴파일러가 **형식의**개체를 할당하는 **새** 연산자를 만나면 **::연산자 new (sizeof(sizeof)** `type` **) 또는** 사용자 정의 **연산자가** 정의되지 않은 경우 **::연산자 new (sizeof(@sizeof))** `type` **에**대한 호출을 `type`발행합니다. 따라서 **새** 연산자는 개체에 대해 올바른 양의 메모리를 할당할 수 있습니다.

> [!NOTE]
> **새 연산자에** 대한 `size_t`인수는 형식입니다. 이 유형은 \<direct.h \<>, malloc.h \<>, memory.h \<>, \<search.h>, \<stddef.h \<>, stdio.h>, stdlib.h>, \<string.h> 및 \<time.h> 정의됩니다.

문법의 옵션은 *배치* 의 사양을 허용 [(새 연산자의](../cpp/new-operator-cpp.md)문법 참조). *배치* 매개 변수는 **운영자 new의**사용자 정의 구현에만 사용할 수 있습니다. 추가 정보를 운영자 에게 **새 로**전달할 수 있습니다. 클래스 T가 `T *TObject = T::operator new( sizeof( T ), 0x0040 );` 멤버 연산자가 새 경우와 같은 `T *TObject = ::operator new( sizeof( T ), 0x0040 );` `T *TObject = new ( 0x0040 ) T;` *배치* 필드가 있는 식은 에 변환됩니다.

*배치* 필드의 원래 의도는 하드웨어 종속 개체를 사용자 지정 주소에 할당할 수 있도록 하는 것이었습니다.

> [!NOTE]
> 앞의 예제에서는 *배치* 필드에 하나의 인수만 표시되지만 이러한 방식으로 **연산자에게** 전달할 수 있는 추가 인수 수에는 제한이 없습니다.

클래스 형식에 대해 **연산자 new가** 정의된 경우에도 전역 연산자는 이 예제의 형식을 사용하여 사용할 수 있습니다.

```cpp
T *TObject =::new TObject;
```

범위 확인 연산자 ()`::`전역 **새** 연산자의 사용을 강제로 합니다.

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[키워드](../cpp/keywords-cpp.md)<br/>
[연산자 신규 및 삭제](../cpp/new-and-delete-operators.md)
