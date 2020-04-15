---
title: 스토리지 클래스(C++)
description: C++에서 정적, 외종 및 thread_local 키워드는 변수 또는 함수의 수명, 연결 및 메모리 위치를 지정합니다.
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 75ccb11689b4863d2d0df5edd6d066be6bd3858c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365354"
---
# <a name="storage-classes"></a>스토리지 클래스

C++ 변수 선언의 컨텍스트에 있는 *저장소 클래스는* 개체의 수명, 연결 및 메모리 위치를 제어하는 형식 지정자입니다. 주어진 개체에는 스토리지 클래스가 하나만 있을 수 있습니다. 블록 내에 정의된 변수는 **외각,** **정적**또는 **thread_local** 지정기를 사용하여 달리 지정하지 않는 한 자동 저장소를 갖습니다. 자동 개체 및 변수는 링크가 없으며 블록 외부의 코드에 표시되지 않습니다. 실행이 블록에 들어갈 때 메모리가 자동으로 할당되고 블록이 종료될 때 할당이 취소됩니다.

**참고**

1. [변경 가능한](../cpp/mutable-data-members-cpp.md) 키워드는 저장소 클래스 지정으로 간주될 수 있습니다. 하지만 클래스 정의의 멤버 목록에만 사용할 수 있습니다.

1. **비주얼 스튜디오 2010 이상 :** **자동** 키워드는 더 이상 C++ 저장소 클래스 지정자가 아니며 **레지스터** 키워드는 더 이상 사용되지 않습니다. **Visual Studio 2017 버전 15.7 이상:** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)사용 가능): **레지스터** 키워드가 C++ 언어에서 제거됩니다.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a><a name="static"></a>정적

**정적** 키워드를 사용하여 전역 범위, 네임스페이스 범위 및 클래스 범위에서 변수 및 함수를 선언할 수 있습니다. 정적 변수는 로컬 범위에서 선언할 수도 있습니다.

정적 생존 기간이란 프로그램이 시작될 때 개체 또는 변수가 할당되고 프로그램이 끝날 때 개체 또는 변수가 할당 취소됨을 의미합니다. 외부 연결은 변수가 선언된 파일 외부에서 변수 이름이 표시됨을 의미합니다. 반대로 내부 연결은 변수가 선언된 파일 외부에 이름이 표시되지 않음을 의미합니다. 기본적으로 전역 네임스페이스에서 정의된 개체 또는 변수에는 정적 지속 기간 및 외부 링크가 있습니다. **정적** 키워드는 다음과 같은 상황에서 사용할 수 있습니다.

1. 파일 범위(전역 및/또는 네임스페이스 범위)에서 변수 또는 함수를 선언할 때 **정적** 키워드는 변수 또는 함수에 내부 연결이 있음을 지정합니다. 변수를 선언할 때 변수가 정적 생존 기간을 가지며, 다른 값을 지정하지 않으면 컴파일러가 0으로 초기화합니다.

1. 함수에서 변수를 선언할 때 **정적** 키워드는 해당 함수에 대한 호출 사이에 변수가 상태를 유지하도록 지정합니다.

1. 클래스 선언에서 데이터 멤버를 선언할 때 **정적** 키워드는 클래스의 모든 인스턴스에서 멤버의 복사본 한 복사본이 공유되도록 지정합니다. 정적 데이터 멤버는 파일 범위에서 정의되어야 합니다. **const static로** 선언하는 정수 데이터 멤버에는 초기화가 있을 수 있습니다.

1. 클래스 선언에서 멤버 함수를 선언할 때 **정적** 키워드는 함수가 클래스의 모든 인스턴스에서 공유되도록 지정합니다. 정적 멤버 함수는 함수에 암시적 **이** 포인터가 없기 때문에 인스턴스 멤버에 액세스할 수 없습니다. 인스턴스 멤버에 액세스하려면 인스턴스 포인터나 참조인 매개 변수로 함수를 선언해야 합니다.

1. 공용 구조체의 멤버는 정적 상태로 선언할 수 없습니다. 그러나 전역적으로 선언된 익명 공용 구조처는 **static**로 명시적으로 선언되어야 합니다.

이 예제에서는 함수에서 **static로** 선언된 변수가 해당 함수에 대한 호출 간에 상태를 유지하는 방법을 보여 주며 있습니다.

```cpp
// static1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void showstat( int curr ) {
   static int nStatic;    // Value of nStatic is retained
                          // between each function call
   nStatic += curr;
   cout << "nStatic is " << nStatic << endl;
}

int main() {
   for ( int i = 0; i < 5; i++ )
      showstat( i );
}
```

```Output
nStatic is 0
nStatic is 1
nStatic is 3
nStatic is 6
nStatic is 10
```

이 예제에서는 클래스에서 **정적** 사용을 보여 주며 있습니다.

```cpp
// static2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CMyClass {
public:
   static int m_i;
};

int CMyClass::m_i = 0;
CMyClass myObject1;
CMyClass myObject2;

int main() {
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject1.m_i = 1;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject2.m_i = 2;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   CMyClass::m_i = 3;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;
}
```

```Output
0
0
1
1
2
2
3
3
```

이 예제에서는 멤버 함수에서 **static으로** 선언된 로컬 변수를 보여 주습니다. 정적 변수는 전체 프로그램에서 사용할 수 있으며 해당 형식의 모든 인스턴스는 정적 변수의 동일한 복사본을 공유합니다.

```cpp
// static3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
struct C {
   void Test(int value) {
      static int var = 0;
      if (var == value)
         cout << "var == value" << endl;
      else
         cout << "var != value" << endl;

      var = value;
   }
};

int main() {
   C c1;
   C c2;
   c1.Test(100);
   c2.Test(100);
}
```

```Output
var != value
var == value
```

C++11부터 정적 지역 변수 초기화는 스레드로부터 안전이 보장됩니다. 이 기능을 *매직 정적이라고도 합니다.* 그러나 다중 스레드 애플리케이션에서는 모든 후속 할당을 동기화해야 합니다. 스레드 안전 정적 초기화 기능은 CRT에 대한 종속성을 사용하지 않도록 [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) 플래그를 사용하여 비활성화할 수 있습니다.

## <a name="extern"></a><a name="extern"></a>Extern

**extern으로** 선언된 개체 및 변수는 다른 변환 단위 또는 둘러싸는 범위에서 외부 연결이 있는 것으로 정의된 개체를 선언합니다. 자세한 내용은 [외장](extern-cpp.md) 및 [번역 단위 및 연결을](program-and-linkage-cpp.md)참조하십시오.

## <a name="thread_local-c11"></a><a name="thread_local"></a>thread_local (C++11)

**thread_local** 지정기로 선언된 변수는 생성되는 스레드에서만 액세스할 수 있습니다. 변수는 스레드를 만들 때 생성되고 스레드를 제거할 때 제거됩니다. 각 스레드에 변수의 자체 복사본이 있습니다. Windows에서 **thread_local** Microsoft 특정 [__declspec(스레드)](../cpp/thread.md) 특성과 기능적으로 동일합니다.

```cpp
thread_local float f = 42.0; // Global namespace. Not implicitly static.

struct S // cannot be applied to type definition
{
    thread_local int i; // Illegal. The member must be static.
    thread_local static char buf[10]; // OK
};

void DoSomething()
{
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;
}
```

**thread_local** 지정기에 대해 주의해야 할 사항:

- DLL의 동적으로 초기화된 스레드 로컬 변수는 모든 호출 스레드에서 올바르게 초기화되지 않을 수 있습니다. 자세한 내용은 [스레드](thread.md)를 참조하세요.

- **thread_local** 지정기는 **정적** 또는 **외종과**결합될 수 있습니다.

- 데이터 선언 및 정의에만 **thread_local** 적용할 수 있습니다. **함수** 선언이나 정의에는 사용할 수 thread_local 없습니다.

- 정적 저장 기간이 있는 데이터 항목에만 **thread_local** 지정할 수 있습니다. 여기에는 전역 데이터 **개체(정적** 및 **외종),** 로컬 정적 개체 및 클래스의 정적 데이터 멤버가 포함됩니다. **thread_local** 선언된 모든 로컬 변수는 다른 저장소 클래스가 제공되지 않으면 암시적으로 정적입니다. 즉, 블록 범위에서 **thread_local** `thread_local static`.

- 선언및 정의가 동일한 파일에서 발생하든 별도의 파일에서 발생하는지 여부에 관계없이 선언 및 스레드 로컬 개체의 정의모두에 **대해 thread_local** 지정해야 합니다.

Windows에서 **thread_local** [__declspec(스레드)를](../cpp/thread.md) 형식 정의에 적용할 수 있고 C 코드에서 유효하다는 점을 제외하면 **__declspec(스레드)과** 기능적으로 동일합니다. 가능하면 C++ 표준의 일부이므로 **thread_local** 사용하십시오.

## <a name="register"></a><a name="register"></a>등록

**Visual Studio 2017 버전 15.3** [이상(/std:c++17](../build/reference/std-specify-language-standard-version.md)사용 가능): **레지스터** 키워드는 더 이상 지원되는 저장소 클래스가 아닙니다. 키워드는 나중에 사용할 수 있는 표준에 여전히 예약되어 있습니다.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>예: 자동 및 정적 초기화

로컬 자동 개체나 변수는 컨트롤의 흐름이 정의에 도달할 때마다 초기화됩니다. 로컬 정적 개체 또는 변수는 컨트롤의 흐름이 정의에 처음 도달할 때 초기화됩니다.

다음 예제에서는 개체의 초기화 및 개체의 초기화와 소멸을 기록한 후 `I1`, `I2` 및 `I3` 객체를 정의합니다.

```cpp
// initialization_of_objects.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>
using namespace std;

// Define a class that logs initializations and destructions.
class InitDemo {
public:
    InitDemo( const char *szWhat );
    ~InitDemo();

private:
    char *szObjName;
    size_t sizeofObjName;
};

// Constructor for class InitDemo
InitDemo::InitDemo( const char *szWhat ) :
    szObjName(NULL), sizeofObjName(0) {
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {
        // Allocate storage for szObjName, then copy
        // initializer szWhat into szObjName, using
        // secured CRT functions.
        sizeofObjName = strlen( szWhat ) + 1;

        szObjName = new char[ sizeofObjName ];
        strcpy_s( szObjName, sizeofObjName, szWhat );

        cout << "Initializing: " << szObjName << "\n";
    }
    else {
        szObjName = 0;
    }
}

// Destructor for InitDemo
InitDemo::~InitDemo() {
    if( szObjName != 0 ) {
        cout << "Destroying: " << szObjName << "\n";
        delete szObjName;
    }
}

// Enter main function
int main() {
    InitDemo I1( "Auto I1" ); {
        cout << "In block.\n";
        InitDemo I2( "Auto I2" );
        static InitDemo I3( "Static I3" );
    }
    cout << "Exited block.\n";
}
```

```Output
Initializing: Auto I1
In block.
Initializing: Auto I2
Initializing: Static I3
Destroying: Auto I2
Exited block.
Destroying: Auto I1
Destroying: Static I3
```

이 예제에서는 개체 `I1`의 `I2`방법과 시기를 보여 주며 `I3` 초기화되고 언제 소멸되는지 보여 줍니다.

프로그램에 대해 주의해야 할 몇 가지 사항이 있습니다.

- 첫째, 제어 흐름이 정의된 블록을 종료할 때 `I1` 및 `I2`가 자동으로 제거됩니다.

- 둘째, C++에서는 블록의 시작 부분에서 개체나 변수를 선언할 필요가 없습니다. 또한 제어 흐름이 정의에 도달해야 이 개체가 초기화됩니다. `I2` (이러한 `I3` 정의의 예입니다.) 출력은 초기화될 때 정확하게 표시됩니다.

- 마지막으로 `I3`과 같은 정적 지역 변수는 프로그램 지속 시간 동안 값을 보유하지만 프로그램이 종료되면 제거됩니다.

## <a name="see-also"></a>참고 항목

[선언 및 정의](../cpp/declarations-and-definitions-cpp.md)
