---
title: new 및 delete 연산자
ms.date: 11/19/2019
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: fd170c1500e2d80879fdd89f7d825930189ae942
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367880"
---
# <a name="new-and-delete-operators"></a>new 및 delete 연산자

C++는 [새](new-operator-cpp.md) 및 [삭제](delete-operator-cpp.md) 연산자를 사용하여 개체의 동적 할당 및 할당 할당을 지원합니다. 이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다. **새** 연산자는 특수 함수 [연산자 new를](new-operator-cpp.md)호출하고 **delete** 연산자는 특수 함수 [연산자가 delete를](delete-operator-cpp.md)호출합니다.

C++ 표준 라이브러리의 **새** 함수는 메모리 할당에 실패할 경우 std:bad_alloc 예외를 throw하는 C++ 표준에 지정된 동작을 지원합니다. 당신은 여전히 **새로운**의 비 던지기 버전을 원하는 경우 , nothrownew.obj와 프로그램을 연결합니다. 그러나 nothrownew.obj와 연결하면 C++ 표준 라이브러리의 새 기본 **연산자가** 더 이상 작동하지 않습니다.

C 런타임 라이브러리 및 C++ 표준 라이브러리를 구성하는 라이브러리 파일 목록은 [CRT 라이브러리 피처를](../c-runtime-library/crt-library-features.md)참조하십시오.

## <a name="the-new-operator"></a><a id="new_operator"> </a> 새 연산자

프로그램에서 다음과 같은 명령문이 발생하면 **함수 연산자 에**대한 호출이 새로 이어집니다.

```cpp
char *pch = new char[BUFFER_SIZE];
```

저장소의 0바이트에 대한 요청인 경우 **연산자 new는** 고유한 개체에 대한 포인터를 반환합니다(즉, **연산자 새에** 대한 반복 호출은 다른 포인터를 반환합니다). 할당 요청에 대한 메모리가 부족한 경우 새 `std::bad_alloc` **연산자가** 예외를 throw하거나 throw되지 않는 **연산자 새** 지원에 연결된 경우 **nullptr을** 반환합니다.

메모리를 해제하고 할당을 다시 시도하는 루틴을 작성할 수 있습니다. 자세한 내용은 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 참조하십시오. 복구 체계에 대한 자세한 내용은 이 항목의 메모리 부족 처리 섹션을 참조하십시오.

**연산자 새** 함수에 대한 두 범위는 다음 표에 설명되어 있습니다.

### <a name="scope-for-operator-new-functions"></a>연산자 새 함수의 범위

|연산자|범위|
|--------------|-----------|
|**::연산자 신규**|Global|
|*클래스 이름* **::연산자 새**|클래스|

**새 연산자에** 대한 첫 `size_t` 번째 인수는 \<형식(stddef.h> 정의된 형식)이어야 하며 반환 형식은 항상 **void입니다.** <strong>\*</strong>

전역 **연산자 새** 함수는 **새** 연산자가 기본 제공 형식의 개체, 사용자 정의 **연산자 새** 함수를 포함하지 않는 클래스 형식의 개체 및 모든 형식의 배열을 할당하는 데 사용될 때 호출됩니다. **새** 연산자가 **새 연산자가** 정의된 클래스 형식의 개체를 할당하는 데 사용되는 경우 해당 클래스의 **연산자가 새 연산자가** 호출됩니다.

클래스에 대해 정의된 **연산자 새** 함수는 해당 클래스 형식의 개체에 대한 전역 **연산자 새** 함수를 숨기는 정적 멤버 함수(따라서 가상일 수 없음)입니다. **새** 메모리를 할당하고 지정된 값으로 설정하는 데 새 값이 사용되는 경우를 고려하십시오.

```cpp
#include <malloc.h>
#include <memory.h>

class Blanks
{
public:
    Blanks(){}
    void *operator new( size_t stAllocateBlock, char chInit );
};
void *Blanks::operator new( size_t stAllocateBlock, char chInit )
{
    void *pvTemp = malloc( stAllocateBlock );
    if( pvTemp != 0 )
        memset( pvTemp, chInit, stAllocateBlock );
    return pvTemp;
}
// For discrete objects of type Blanks, the global operator new function
// is hidden. Therefore, the following code allocates an object of type
// Blanks and initializes it to 0xa5
int main()
{
   Blanks *a5 = new(0xa5) Blanks;
   return a5 != 0;
}
```

**괄호에서 새** 에 제공된 인수는 `Blanks::operator new` `chInit` 인수로 전달됩니다. 그러나 전역 **연산자 새** 함수가 숨어져 다음과 같은 코드가 오류를 생성합니다.

```cpp
Blanks *SomeBlanks = new Blanks;
```

컴파일러는 클래스 선언에서 멤버 배열 **새** 및 **삭제** 연산자를 지원합니다. 다음은 그 예입니다.

```cpp
class MyClass
{
public:
   void * operator new[] (size_t)
   {
      return 0;
   }
   void   operator delete[] (void*)
   {
   }
};

int main()
{
   MyClass *pMyClass = new MyClass[5];
   delete [] pMyClass;
}
```

### <a name="handling-insufficient-memory"></a>메모리 부족 처리

실패한 메모리 할당에 대한 테스트는 다음과 같이 수행할 수 있습니다.

```cpp
#include <iostream>
using namespace std;
#define BIG_NUMBER 100000000
int main() {
   int *pI = new int[BIG_NUMBER];
   if( pI == 0x0 ) {
      cout << "Insufficient memory" << endl;
      return -1;
   }
}
```

실패한 메모리 할당 요청을 처리하는 또 다른 방법이 있습니다. 이러한 오류를 처리하는 사용자 지정 복구 루틴을 작성한 다음 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 함수를 호출하여 함수를 등록합니다.

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> 삭제 연산자

**새** 연산자사용을 사용하여 동적으로 할당된 메모리는 **delete** 연산자로 해제할 수 있습니다. delete 연산자는 **연산자 삭제** 함수를 호출하여 메모리를 사용 가능한 풀로 다시 해제합니다. **delete** 연산자 사용 으로 인해 클래스 소멸자(있는 경우)가 호출됩니다.

전역 및 클래스 **범위연산자 삭제** 함수가 있습니다. 지정된 클래스에 대해 하나의 **연산자 삭제** 함수만 정의할 수 있습니다. 이 정의된 경우 전역 **연산자 삭제** 함수를 숨깁니다. 전역 **연산자 delete** 함수는 항상 모든 형식의 배열에 대해 호출됩니다.

전역 **연산자가** 함수를 삭제합니다. 전역 **연산자 삭제** 및 클래스 멤버 **연산자 삭제** 함수에 대해 두 가지 양식이 있습니다.

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

지정된 클래스에는 앞의 두 양식 중 하나만 존재할 수 있습니다. 첫 번째 양식은 할당 `void *`할당 할 개체에 대한 포인터를 포함하는 형식의 단일 인수를 취합니다. 두 번째 양식인 크기의 할당 위치는 두 개의 인수를 사용하며, 그 중 첫 번째 는 할당 할 메모리 블록에 대한 포인터이고 두 번째 는 할당 할 바이트 수입니다. 두 양식의 반환 **void** 형식이 무효화됩니다(연산자**삭제는** 값을 반환할 수 없음).

두 번째 양식의 목적은 삭제할 개체의 올바른 크기 범주를 검색하는 속도를 높이는 것입니다. 두 번째 양식은 **연산자가** 기본 클래스에서 함수를 삭제하여 파생 클래스의 개체를 삭제하는 데 사용할 때 유용합니다.

**연산자 삭제** 함수는 정적입니다. 따라서 가상이 될 수 없습니다. **운영자 삭제** 함수는 멤버 액세스 제어 에 설명된 대로 액세스 [제어를](member-access-control-cpp.md)준수합니다.

다음 예제에서는 사용자 정의 **연산자 새** 및 **연산자 삭제** 함수를 할당 및 메모리 할당 할당을 기록하도록 설계되어 보여 주며,

```cpp
#include <iostream>
using namespace std;

int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?
int cBlocksAllocated = 0;  // Count of blocks allocated.

// User-defined operator new.
void *operator new( size_t stAllocateBlock ) {
   static int fInOpNew = 0;   // Guard flag.

   if ( fLogMemory && !fInOpNew ) {
      fInOpNew = 1;
      clog << "Memory block " << ++cBlocksAllocated
          << " allocated for " << stAllocateBlock
          << " bytes\n";
      fInOpNew = 0;
   }
   return malloc( stAllocateBlock );
}

// User-defined operator delete.
void operator delete( void *pvMem ) {
   static int fInOpDelete = 0;   // Guard flag.
   if ( fLogMemory && !fInOpDelete ) {
      fInOpDelete = 1;
      clog << "Memory block " << cBlocksAllocated--
          << " deallocated\n";
      fInOpDelete = 0;
   }

   free( pvMem );
}

int main( int argc, char *argv[] ) {
   fLogMemory = 1;   // Turn logging on
   if( argc > 1 )
      for( int i = 0; i < atoi( argv[1] ); ++i ) {
         char *pMem = new char[10];
         delete[] pMem;
      }
   fLogMemory = 0;  // Turn logging off.
   return cBlocksAllocated;
}
```

앞의 코드를 사용하여 "메모리 누수"를 검색할 수 있습니다. 메모리 누수는 사용 가능한 저장소에 할당되었지만 비워지지 않은 메모리를 의미합니다. 이 검색을 수행하려면 전역 **신규** 및 **삭제** 연산자가 메모리 할당 및 할당 할당을 계산하도록 재정의됩니다.

컴파일러는 클래스 선언에서 멤버 배열 **새** 및 **삭제** 연산자를 지원합니다. 다음은 그 예입니다.

```cpp
// spec1_the_operator_delete_function2.cpp
// compile with: /c
class X  {
public:
   void * operator new[] (size_t) {
      return 0;
   }
   void operator delete[] (void*) {}
};

void f() {
   X *pX = new X[5];
   delete [] pX;
}
```
