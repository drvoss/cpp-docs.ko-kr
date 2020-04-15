---
title: pointers_to_members
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
ms.openlocfilehash: adffacc3ddc08679d7db4e17e027d8a7dbe8a92b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320324"
---
# <a name="pointers-to-members"></a>pointers_to_members

멤버에 대한 포인터 선언은 포인터 선언의 특별한 경우입니다.  다음 시퀀스를 사용하여 선언됩니다.

> *스토리지 클래스 지정기*<sub>옵트</sub> *CV-한정자*<sub>옵트</sub> *타입-지정기* *ms-수정자*<sub>옵트인</sub> *자격-이름* **`::*`** *cv-한정자* *옵트인피어* *pm-initializer*<sub>옵트</sub> <sub>opt</sub>**`;`**

1. 선언 지정자:

   - 선택적 스토리지 클래스 지정자.

   - 선택적 **구성선** 및 **휘발성** 지정기.

   - 형식 지정자: 형식의 이름 클래스가 아니라 가리키는 멤버의 유형입니다.

1. 선언자:

   - 선택적 Microsoft 전용 한정자. 자세한 내용은 [Microsoft 관련 수정을](../cpp/microsoft-specific-modifiers.md)참조하십시오.

   - 가리킬 멤버가 포함된 클래스의 정규화된 이름입니다.

   - 연산자입니다. __`::`__

   - 연산자입니다. __`*`__

   - 선택적 **구성선** 및 **휘발성** 지정기.

   - 멤버에 대한 포인터의 이름을 지정하는 식별자

1. 선택적 포인터-멤버 초기화:

   - 연산자입니다. **`=`**

   - 연산자입니다. **`&`**

   - 클래스의 정규화된 이름

   - 연산자입니다. __`::`__

   - 적절한 형식의 클래스의 비정적 멤버의 이름입니다.

항상 그렇듯이 여러 선언자(및 모든 관련 이니셜라이저)가 단일 선언에서 허용됩니다. 멤버에 대한 포인터는 클래스의 정적 멤버, 참조 형식의 멤버 **`void`** 또는 을 가리킬 수 없습니다.

클래스의 멤버에 대한 포인터는 일반 포인터와 다릅니다. 일반 포인터는 메모리에 있는 단일 개체만 식별합니다(해당 개체의 주소를 포함함). 클래스의 멤버에 대한 포인터는 클래스의 모든 인스턴스에서 해당 멤버를 식별합니다. 다음 예제에서는 `Window` 클래스와 멤버 데이터에 대한 몇 가지 포인터를 선언합니다.

```cpp
// pointers_to_members1.cpp
class Window
{
public:
   Window();                               // Default constructor.
   Window( int x1, int y1,                 // Constructor specifying
   int x2, int y2 );                       //  window size.
bool SetCaption( const char *szTitle ); // Set window caption.
   const char *GetCaption();               // Get window caption.
   char *szWinCaption;                     // Window caption.
};

// Declare a pointer to the data member szWinCaption.
char * Window::* pwCaption = &Window::szWinCaption;
int main()
{
}
```

앞의 `pwCaption` 예제에서는 type. `Window` `char*`클래스의 모든 멤버에 대한 포인터입니다. `pwCaption`의 형식은 `char * Window::*`입니다. 다음 코드에서는 `SetCaption` 및 `GetCaption` 멤버 함수에 대한 포인터를 선언합니다.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

`pfnwGC` 및 `pfnwSC` 포인터는 `GetCaption` 클래스의 `SetCaption` 및 `Window`을 각각 가리킵니다. 이 코드에서는 멤버에 대한 포인터 `pwCaption`을 직접 사용하여 창 캡션에 정보를 복사합니다.

```cpp
Window wMainWindow;
Window *pwChildWindow = new Window;
char   *szUntitled    = "Untitled -  ";
int    cUntitledLen   = strlen( szUntitled );

strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';
```

**`.*`** **`->*`** 연산자와 연산자(포인터-멤버 연산자)의 차이점은 **`.*`** 연산자가 개체 또는 개체 참조를 **`->*`** 지정한 멤버를 선택하고 연산자는 포인터를 통해 멤버를 선택한다는 것입니다. 이러한 연산자에 대한 자세한 내용은 [포인터-멤버 연산자가 있는 식을](../cpp/pointer-to-member-operators-dot-star-and-star.md)참조하십시오.

포인터-멤버 연산자의 결과는 멤버의 유형입니다. 이 예제의 경우 `char *`입니다.

다음 코드에서는 멤버에 대한 포인터를 사용하여 `GetCaption` 및 `SetCaption` 멤버 함수를 호출합니다.

```cpp
// Allocate a buffer.
enum {
    sizeOfBuffer = 100
};
char szCaptionBase[sizeOfBuffer];

// Copy the main window caption into the buffer
//  and append " [View 1]".
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );
// Set the child window's caption.
(pwChildWindow->*pfnwSC)( szCaptionBase );
```

## <a name="restrictions-on-pointers-to-members"></a>멤버에 대한 포인터 제한

정적 멤버의 주소는 멤버에 대한 포인터가 아닙니다. 정적 멤버의 한 인스턴스에 대한 일반 포인터입니다. 지정된 클래스의 모든 개체에 대해 정적 멤버의 인스턴스가 하나만 있습니다. 즉, 일반 주소()**&** 및 디레퍼런스()<strong>\*</strong>연산자()를 사용할 수 있습니다.

## <a name="pointers-to-members-and-virtual-functions"></a>멤버 및 가상 함수에 대한 포인터

포인터-멤버 함수를 통해 가상 함수를 호출하는 것은 함수가 직접 호출된 것처럼 작동합니다. 올바른 함수는 v-table에서 조회되고 호출됩니다.

가상 함수 작업은 항상 기본 클래스 포인터를 통해 호출합니다. (가상 기능에 대한 자세한 내용은 [가상 함수를](../cpp/virtual-functions.md)참조하십시오.)

다음 코드에서는 멤버 포인터 함수를 통해 가상 함수를 호출하는 방법을 보여 줍니다.

```cpp
// virtual_functions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base
{
    public:
    virtual void Print();
};
void (Base ::* bfnPrint)() = &Base :: Print;
void Base :: Print()
{
    cout << "Print function for class Base\n";
}

class Derived : public Base
{
    public:
    void Print();  // Print is still a virtual function.
};

void Derived :: Print()
{
    cout << "Print function for class Derived\n";
}

int main()
{
    Base   *bPtr;
    Base    bObject;
    Derived dObject;
    bPtr = &bObject;    // Set pointer to address of bObject.
    (bPtr->*bfnPrint)();
    bPtr = &dObject;    // Set pointer to address of dObject.
    (bPtr->*bfnPrint)();
}

//Output: Print function for class Base
Print function for class Derived
```
