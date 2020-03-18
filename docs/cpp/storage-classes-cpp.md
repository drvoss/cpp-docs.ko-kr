---
title: 스토리지 클래스(C++)
description: 에서 C++static, extern 및 thread_local 키워드는 변수 또는 함수의 수명, 링크 및 메모리 위치를 지정 합니다.
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: 5b30fe7bc6665da9172f093f8ea6a2130cb900b2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447323"
---
# <a name="storage-classes"></a>스토리지 클래스

변수 선언 컨텍스트의 *저장소 클래스* 는 개체의 수명, 링크 및 메모리 위치를 제어 하는 형식 지정자입니다. C++ 주어진 개체에는 스토리지 클래스가 하나만 있을 수 있습니다. **Extern**, **static**또는 **thread_local** 지정자를 사용 하 여 지정 하지 않는 한 블록 내에 정의 된 변수에 자동 저장소가 있습니다. 자동 개체 및 변수는 링크가 없으며 블록 외부의 코드에 표시되지 않습니다. 블록이 종료 될 때 실행이 블록에 입력 되 고 할당 취소 되 면 메모리가 자동으로 할당 됩니다.

**참고 사항**

1. [Mutable](../cpp/mutable-data-members-cpp.md) 키워드는 저장소 클래스 지정자로 간주 될 수 있습니다. 하지만 클래스 정의의 멤버 목록에만 사용할 수 있습니다.

1. **Visual Studio 2010 이상:** **Auto** 키워드는 더 이상 C++ 저장소 클래스 지정 자가 아니므로 **register** 키워드는 더 이상 사용 되지 않습니다. **Visual Studio 2017 버전 15.7 이상:** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): **register** 키워드가 C++ 언어에서 제거 되었습니다.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a>정적인

**Static** 키워드는 전역 범위, 네임 스페이스 범위 및 클래스 범위에서 변수와 함수를 선언 하는 데 사용할 수 있습니다. 정적 변수는 로컬 범위에서 선언할 수도 있습니다.

정적 생존 기간이란 프로그램이 시작될 때 개체 또는 변수가 할당되고 프로그램이 끝날 때 개체 또는 변수가 할당 취소됨을 의미합니다. 외부 연결은 변수가 선언된 파일 외부에서 변수 이름이 표시됨을 의미합니다. 반대로 내부 연결은 변수가 선언된 파일 외부에 이름이 표시되지 않음을 의미합니다. 기본적으로 전역 네임스페이스에서 정의된 개체 또는 변수에는 정적 지속 기간 및 외부 링크가 있습니다. **Static** 키워드는 다음과 같은 경우에 사용할 수 있습니다.

1. 파일 범위 (전역 및/또는 네임 스페이스 범위)에서 변수나 함수를 선언 하는 경우 **static** 키워드는 변수나 함수에 내부 링크가 있음을 지정 합니다. 변수를 선언할 때 변수가 정적 생존 기간을 가지며, 다른 값을 지정하지 않으면 컴파일러가 0으로 초기화합니다.

1. 함수에서 변수를 선언 하는 경우 **static** 키워드는 변수가 해당 함수 호출 간에 상태를 유지 하도록 지정 합니다.

1. 클래스 선언에서 데이터 멤버를 선언 하는 경우 **static** 키워드는 멤버의 복사본 하나가 클래스의 모든 인스턴스에서 공유 되도록 지정 합니다. 정적 데이터 멤버는 파일 범위에서 정의되어야 합니다. **Const static** 으로 선언 하는 정수 계열 데이터 멤버에는 이니셜라이저가 있을 수 있습니다.

1. 클래스 선언에서 멤버 함수를 선언 하는 경우 **static** 키워드는 함수가 클래스의 모든 인스턴스에 공유 되도록 지정 합니다. 함수에 암시적 **this** 포인터가 없기 때문에 정적 멤버 함수는 인스턴스 멤버에 액세스할 수 없습니다. 인스턴스 멤버에 액세스하려면 인스턴스 포인터나 참조인 매개 변수로 함수를 선언해야 합니다.

1. 공용 구조체의 멤버는 정적 상태로 선언할 수 없습니다. 그러나 전역적으로 선언 된 익명 공용 구조체는 **정적**으로 명시적으로 선언 되어야 합니다.

이 예제에서는 함수에서 **static** 으로 선언 된 변수가 해당 함수 호출 간에 상태를 유지 하는 방법을 보여 줍니다.

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

이 예제에서는 클래스에서 **static** 을 사용 하는 방법을 보여 줍니다.

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

이 예제에서는 멤버 함수에서 **static** 으로 선언 된 지역 변수를 보여 줍니다. 정적 변수는 전체 프로그램에서 사용할 수 있으며 해당 형식의 모든 인스턴스는 정적 변수의 동일한 복사본을 공유합니다.

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

C++11부터 정적 지역 변수 초기화는 스레드로부터 안전이 보장됩니다. 이 기능을 *매직 정적*이 라고도 합니다. 그러나 다중 스레드 애플리케이션에서는 모든 후속 할당을 동기화해야 합니다. CRT에 대 한 종속성을 방지 하기 위해 [/zc: threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) 플래그를 사용 하 여 스레드로부터 안전한 정적 초기화 기능을 사용 하지 않도록 설정할 수 있습니다.

## <a name="extern"></a>시키거나

**Extern** 으로 선언 된 개체와 변수는 다른 변환 단위에 정의 되거나 바깥쪽 범위에서 외부 링크가 있는 개체를 선언 합니다. 자세한 내용은 [extern](extern-cpp.md) and [Translation unit and 링크](program-and-linkage-cpp.md)를 참조 하세요.

## <a name="thread_local"></a>thread_local (c + + 11)

**Thread_local** 지정자를 사용 하 여 선언 된 변수는 해당 변수가 만들어진 스레드에서만 액세스할 수 있습니다. 변수는 스레드를 만들 때 생성되고 스레드를 제거할 때 제거됩니다. 각 스레드에 변수의 자체 복사본이 있습니다. Windows에서 **thread_local** 은 Microsoft 전용 [__declspec (thread)](../cpp/thread.md) 특성과 기능적으로 동일 합니다.

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

**Thread_local** 지정자에 대 한 참고 사항:

- Dll의 동적으로 초기화 되는 스레드 지역 변수가 모든 호출 스레드에서 올바르게 초기화 되지 않을 수 있습니다. 자세한 내용은 [스레드](thread.md)를 참조하세요.

- **Thread_local** 지정자를 **static** 또는 **extern**과 함께 사용할 수 있습니다.

- 데이터 선언 및 정의에만 **thread_local** 을 적용할 수 있습니다. **thread_local** 는 함수 선언 또는 정의에 사용할 수 없습니다.

- 정적 저장 기간이 있는 데이터 항목에만 **thread_local** 지정할 수 있습니다. 여기에는 전역 데이터 개체 ( **정적** 및 **extern**), 지역 정적 개체 및 클래스의 정적 데이터 멤버가 포함 됩니다. 다른 저장소 클래스를 제공 하지 않는 경우 **thread_local** 선언 된 모든 지역 변수가 암시적으로 정적입니다. 즉, 블록 범위 **thread_local** 은 `thread_local static`와 동일 합니다.

- 선언과 정의가 동일한 파일이 나 별도의 파일에서 발생 하는지 여부에 상관 없이 스레드 로컬 개체의 선언과 정의 모두에 대해 **thread_local** 를 지정 해야 합니다.

Windows에서 **thread_local** 는 형식 정의에 **__declspec (스레드)** 를 적용할 수 있고 C 코드에서 유효 하다는 점을 제외 하 고는 [__declspec (thread)](../cpp/thread.md) 와 기능적으로 동일 합니다. 가능 하면 C++ 표준의 일부 이기 때문에 **thread_local** 를 사용 합니다. 따라서 이식성이 향상 됩니다.

##  <a name="register"></a>레지스터

**Visual Studio 2017 버전 15.3 이상** ( [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)과 함께 사용 가능): **register** 키워드는 더 이상 지원 되는 저장소 클래스가 아닙니다. 키워드는 나중에 사용 하기 위해 표준으로 예약 되어 있습니다.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>예: 자동 및 정적 초기화 비교

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

이 예에서는 `I1`, `I2`및 `I3` 개체가 초기화 되는 방법과 시기 및 제거 되는 경우를 보여 줍니다.

프로그램에 대해 몇 가지 주의할 점이 있습니다.

- 첫째, 제어 흐름이 정의된 블록을 종료할 때 `I1` 및 `I2`가 자동으로 제거됩니다.

- 둘째, C++에서는 블록의 시작 부분에서 개체나 변수를 선언할 필요가 없습니다. 또한 제어 흐름이 정의에 도달해야 이 개체가 초기화됩니다. (`I2` 및 `I3`는 이러한 정의의 예입니다.) 출력은 초기화 될 때 정확히 표시 됩니다.

- 마지막으로 `I3`과 같은 정적 지역 변수는 프로그램 지속 시간 동안 값을 보유하지만 프로그램이 종료되면 제거됩니다.

## <a name="see-also"></a>참고 항목

[선언 및 정의](../cpp/declarations-and-definitions-cpp.md)