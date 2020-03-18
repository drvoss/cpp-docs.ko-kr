---
title: new 및 delete 연산자
ms.date: 11/19/2019
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 2fd665ce2570bbe7750684057cdf7f517f6f64f3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445452"
---
# <a name="new-and-delete-operators"></a>new 및 delete 연산자

C++[new](new-operator-cpp.md) 및 [delete](delete-operator-cpp.md) 연산자를 사용 하 여 개체의 동적 할당 및 할당 취소를 지원 합니다. 이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다. **New** 연산자는 특수 함수 [operator new](new-operator-cpp.md)를 호출 하 고 **delete** 연산자는 특수 함수 [operator delete](delete-operator-cpp.md)를 호출 합니다.

표준 라이브러리의 **새** 함수는 C++ 표준에 지정 된 동작을 지원 합니다 .이는 메모리 할당이 실패 하는 경우 std:: bad_alloc 예외를 throw 하는 것입니다. C++ 예외가 발생 하지 않는 **새**버전을 계속 사용 하려면 프로그램을 nothrownew에 연결 합니다. 그러나 nothrownew를 사용 하 여 연결 하면 C++ 표준 라이브러리의 기본 **operator new** 가 더 이상 작동 하지 않습니다.

C 런타임 라이브러리와 C++ 표준 라이브러리를 구성 하는 라이브러리 파일의 목록은 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)을 참조 하세요.

##  <a id="new_operator"> </a> New 연산자

프로그램에서 다음과 같은 문이 발견 되 면 함수 **operator new**에 대 한 호출로 변환 됩니다.

```cpp
char *pch = new char[BUFFER_SIZE];
```

요청이 0 바이트의 저장소에 대 한 요청인 경우 **operator new** 는 고유 개체에 대 한 포인터를 반환 합니다. 즉, **operator new** 에 대 한 반복 호출은 다른 포인터를 반환 합니다. 할당 요청을 위한 메모리가 부족 한 경우 **operator new** 는 `std::bad_alloc` 예외를 throw 하거나, 비 throw **연산자 새** 지원에 연결 된 경우 **nullptr** 를 반환 합니다.

메모리를 확보 하 고 할당을 다시 시도 하는 루틴을 작성할 수 있습니다. 자세한 내용은 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 를 참조 하세요. 복구 체계에 대 한 자세한 내용은이 항목의 메모리 부족 처리 섹션을 참조 하십시오.

**Operator new** 함수에 대 한 두 범위는 다음 표에 설명 되어 있습니다.

### <a name="scope-for-operator-new-functions"></a>Operator 새 함수의 범위

|연산자|범위|
|--------------|-----------|
|**:: operator new**|Global|
|*클래스-이름* **:: operator new**|클래스|

**Operator new** 의 첫 번째 인수는 `size_t` 형식 이어야 하며 (\<stddef. h >에 정의 된 형식) 반환 형식은 항상 **void** <strong>\*</strong>입니다.

Global **operator new** 함수는 **new** 연산자를 사용 하 여 기본 제공 형식의 개체, 사용자 정의 **operator 새** 함수를 포함 하지 않는 클래스 형식의 개체 및 모든 형식의 배열을 할당할 때 호출 됩니다. **New 연산자를** 사용 하 여 **operator new** 가 정의 된 클래스 형식의 개체를 할당 하는 경우 해당 클래스의 **operator new** 가 호출 됩니다.

클래스에 대해 정의 된 **operator new** 함수는 해당 클래스 형식의 개체에 대 한 전역 **operator new** 함수를 숨기는 정적 멤버 함수 (따라서 가상 일 수 없음)입니다. **새** 를 사용 하 여 메모리를 할당 하 고 지정 된 값으로 설정 하는 경우를 고려 합니다.

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

**New** 에 대 한 괄호에 제공 된 인수는 `Blanks::operator new` `chInit` 인수로 전달 됩니다. 그러나 전역 **operator new** 함수가 숨겨져 있어 다음과 같은 코드가 오류를 발생 시킵니다.

```cpp
Blanks *SomeBlanks = new Blanks;
```

컴파일러는 클래스 선언에서 멤버 배열 **new** 및 **delete** 연산자를 지원 합니다. 다음은 그 예입니다.

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

실패 한 메모리 할당에 대 한 테스트는 다음과 같이 수행할 수 있습니다.

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

실패 한 메모리 할당 요청을 처리 하는 또 다른 방법이 있습니다. 이러한 오류를 처리 하는 사용자 지정 복구 루틴을 작성 한 다음 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 함수를 호출 하 여 함수를 등록 합니다.

##  <a id="delete_operator"> </a> Delete 연산자

**New** 연산자를 사용 하 여 동적으로 할당 되는 메모리는 **delete** 연산자를 사용 하 여 해제할 수 있습니다. Delete 연산자는 사용 가능한 풀로 메모리를 다시 확보 하는 **operator delete** 함수를 호출 합니다. **Delete** 연산자를 사용 하면 클래스 소멸자 (있는 경우)도 호출 됩니다.

전역 및 클래스 범위의 **operator delete** 함수가 있습니다. 지정 된 클래스에 대해 하나의 **operator delete** 함수만 정의할 수 있습니다. 정의 된 경우 전역 **operator delete** 함수를 숨깁니다. 전역 **operator delete** 함수는 항상 모든 형식의 배열에 대해 호출 됩니다.

전역 **operator delete** 함수입니다. 전역 **operator delete** 및 클래스 멤버 **operator delete** 함수에는 두 가지 형태가 있습니다.

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

지정 된 클래스에 대해 앞의 두 형태 중 하나만 있을 수 있습니다. 첫 번째 폼은 할당을 취소할 개체에 대 한 포인터를 포함 하는 `void *`형식의 단일 인수를 사용 합니다. 두 번째 형태 (크기 할당 취소)는 두 개의 인수를 사용 합니다. 첫 번째는 할당을 취소할 메모리 블록에 대 한 포인터이 고 두 번째는 할당을 취소할 바이트 수입니다. 두 폼의 반환 형식은 **void** 입니다 (**operator delete** 는 값을 반환할 수 없음).

두 번째 폼의 목적은 삭제할 개체의 올바른 크기 범주에 대 한 검색 속도를 높이는 것입니다 .이는 할당 자체 근처에 저장 되지 않는 경우가 캐시 되지 않은 가능성이 높습니다. 두 번째 형태는 기본 클래스의 **operator delete** 함수를 사용 하 여 파생 클래스의 개체를 삭제 하는 경우에 유용 합니다.

**Operator delete** 함수는 정적입니다. 따라서 가상 일 수 없습니다. **Operator delete** 함수는 [멤버 Access Control](member-access-control-cpp.md)에 설명 된 대로 access control을 따르는 합니다.

다음 예에서는 할당을 기록 하 고 메모리 할당을 취소 하기 위해 설계 된 사용자 정의 **operator new** 및 **operator delete** 함수를 보여 줍니다.

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

앞의 코드를 사용하여 "메모리 누수"를 검색할 수 있습니다. 메모리 누수는 사용 가능한 저장소에 할당되었지만 비워지지 않은 메모리를 의미합니다. 이 검색을 수행 하기 위해 global **new** 및 **delete** 연산자를 다시 정의 하 여 메모리 할당 및 할당 취소를 계산 합니다.

컴파일러는 클래스 선언에서 멤버 배열 **new** 및 **delete** 연산자를 지원 합니다. 다음은 그 예입니다.

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
