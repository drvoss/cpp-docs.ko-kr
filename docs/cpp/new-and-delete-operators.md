---
title: new 및 delete 연산자
description: C + + language new 및 delete 연산자를 사용 하 여 할당을 제어할 수 있습니다.
ms.date: 07/07/2020
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.openlocfilehash: e609d1fdbd4f945ab8709c554d1396100027c4c1
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127864"
---
# <a name="new-and-delete-operators"></a>`new` 및 `delete` 연산자

C + +에서는 및 연산자를 사용 하 여 개체의 동적 할당 및 할당 취소를 지원 [`new`](new-operator-cpp.md) [`delete`](delete-operator-cpp.md) 합니다. 이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다. **`new`** 연산자는 특수 함수를 호출 [`operator new`](new-operator-cpp.md) 하 고 **`delete`** 연산자는 특수 함수를 호출 합니다 [`operator delete`](delete-operator-cpp.md) .

**`new`** C + + 표준 라이브러리의 함수는 c + + 표준에 지정 된 동작을 지원 합니다 .이는 `std::bad_alloc` 메모리 할당이 실패 하는 경우 예외를 throw 하는 것입니다. 을 throw 하지 않는 버전의를 계속 사용 하려면 **`new`** 프로그램을에 연결 *`nothrownew.obj`* 합니다. 그러나와 연결 하는 경우 *`nothrownew.obj`* **`operator new`** c + + 표준 라이브러리의 기본값은 더 이상 작동 하지 않습니다.

C 런타임 라이브러리 및 c + + 표준 라이브러리의 라이브러리 파일 목록은 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)을 참조 하세요.

## <a name="the-new-operator"></a><a id="new_operator"> </a> `new` 연산자

컴파일러는 다음과 같은 문을 함수 호출로 변환 합니다 **`operator new`** .

```cpp
char *pch = new char[BUFFER_SIZE];
```

요청이 0 바이트의 저장소에 대 한 것 이면는 **`operator new`** 고유 개체에 대 한 포인터를 반환 합니다. 즉, 반복 되는 호출은 **`operator new`** 다른 포인터를 반환 합니다. 할당 요청을 위한 메모리가 부족 한 경우에서 **`operator new`** 예외를 throw `std::bad_alloc` 합니다. 또는 **`nullptr`** throw 되지 않는 지원에 연결 된 경우이 메서드는를 반환 **`operator new`** 합니다.

메모리를 확보 하 고 할당을 다시 시도 하는 루틴을 작성할 수 있습니다. 자세한 내용은 [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)를 참조하세요. 복구 체계에 대 한 자세한 내용은 [메모리 부족 처리](#handling-insufficient-memory) 섹션을 참조 하십시오.

다음 표에서는 함수에 대 한 두 가지 범위에 대해 **`operator new`** 설명 합니다.

### <a name="scope-for-operator-new-functions"></a>함수 범위 `operator new`

| 연산자 | Scope |
|--|--|
| **`::operator new`** | 전역 |
| *클래스-이름***`::operator new`** | 클래스 |

에 대 한 첫 번째 인수는 **`operator new`** `size_t` 에 정의 된 형식 이어야 하며 \<stddef.h> 반환 형식은 항상 **`void*`** 입니다.

전역 **`operator new`** 함수는 **`new`** 연산자를 사용 하 여 기본 제공 형식의 개체, 사용자 정의 함수를 포함 하지 않는 클래스 형식의 개체 **`operator new`** 및 모든 형식의 배열을 할당할 때 호출 됩니다. 연산자를 **`new`** 사용 하 여이 정의 된 클래스 형식의 개체를 할당 하는 경우 **`operator new`** 해당 클래스의 **`operator new`** 가 호출 됩니다.

**`operator new`** 클래스에 대해 정의 된 함수는 **`operator new`** 해당 클래스 형식의 개체에 대 한 전역 함수를 숨기는 정적 멤버 함수 (가상 일 수 없음)입니다. 를 사용 하 여 **`new`** 메모리를 할당 하 고 지정 된 값으로 설정 하는 경우를 고려 합니다.

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

괄호 안에 제공 된 인수가 **`new`** 인수로 전달 됩니다 `Blanks::operator new` `chInit` . 그러나 전역 함수는 **`operator new`** 숨겨져 있으며 다음과 같은 코드를 통해 오류를 생성 합니다.

```cpp
Blanks *SomeBlanks = new Blanks;
```

컴파일러는 **`new`** 클래스 선언에서 멤버 배열 및 연산자를 지원 합니다 **`delete`** . 예를 들면 다음과 같습니다.

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

실패 한 메모리 할당 요청을 처리 하는 다른 방법이 있습니다. 이러한 오류를 처리 하는 사용자 지정 복구 루틴을 작성 한 다음 런타임 함수를 호출 하 여 함수를 등록 [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md) 합니다.

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> `delete` 연산자

연산자를 사용 하 여 동적으로 할당 되는 메모리는 **`new`** 연산자를 사용 하 여 해제할 수 있습니다 **`delete`** . Delete 연산자는 **`operator delete`** 사용 가능한 풀로 메모리를 다시 확보 하는 함수를 호출 합니다. 연산자를 사용 **`delete`** 하면 클래스 소멸자 (있는 경우)도 호출 됩니다.

전역 및 클래스 범위의 **`operator delete`** 함수가 있습니다. 지정 된 **`operator delete`** 클래스에 대 한 함수는 하나만 정의할 수 있습니다. 정의 되 면 전역 함수를 숨깁니다 **`operator delete`** . 전역 **`operator delete`** 함수는 항상 모든 형식의 배열에 대해 호출 됩니다.

전역 **`operator delete`** 함수입니다. 전역 **`operator delete`** 및 클래스 멤버 함수에는 다음과 같은 두 가지 형식이 **`operator delete`** 있습니다.

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

지정 된 클래스에 대해 앞의 두 형태 중 하나만 있을 수 있습니다. 첫 번째 폼은 **`void *`** 할당을 취소할 개체에 대 한 포인터를 포함 하는 형식의 단일 인수를 사용 합니다. 두 번째 형식의 크기 할당 취소는 두 개의 인수를 사용 합니다. 첫 번째 형식은 할당을 취소할 메모리 블록에 대 한 포인터이 고, 두 번째 형식은 할당을 취소할 바이트 수입니다. 두 형식의 반환 형식은 **`void`** ( **`operator delete`** 값을 반환할 수 없음)입니다.

두 번째 폼의 목적은 삭제할 개체의 올바른 크기 범주에 대 한 검색 속도를 높이는 것입니다. 이 정보는 할당 자체 근처에 저장 되지 않으며 캐시 되지 않은 가능성이 높습니다. 두 번째 형태는 **`operator delete`** 기본 클래스의 함수를 사용 하 여 파생 클래스의 개체를 삭제 하는 경우에 유용 합니다.

**`operator delete`** 함수는 정적 이므로 가상 일 수 없습니다. **`operator delete`** 함수는 [멤버 Access Control](member-access-control-cpp.md)에 설명 된 대로 access control을 따르는 합니다.

다음 예에서는 **`operator new`** **`operator delete`** 할당을 기록 하 고 메모리 할당을 취소 하기 위해 디자인 된 사용자 정의 및 함수를 보여 줍니다.

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

위의 코드를 사용 하 여 "메모리 누수", 즉 사용 가능한 저장소에 할당 되었지만 해제 되지 않은 메모리를 검색할 수 있습니다. 누수를 감지 하기 위해 전역 **`new`** 및 **`delete`** 연산자는 메모리의 할당 및 할당 취소를 계산 하도록 다시 정의 됩니다.

컴파일러는 **`new`** 클래스 선언에서 멤버 배열 및 연산자를 지원 합니다 **`delete`** . 예를 들어:

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
