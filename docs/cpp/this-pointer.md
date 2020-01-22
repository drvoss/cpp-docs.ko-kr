---
title: this 포인터
description: this 포인터는 비정적 멤버 함수에서 현재 개체에 대 한 컴파일러 생성 포인터입니다.
ms.date: 01/22/2020
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- this
- class
- struct
- union
- sizeof
- const
- volatile
ms.openlocfilehash: 58bba2edd7a457c624b747b5a65d209995852848
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518337"
---
# <a name="opno-locthis-pointer"></a>this 포인터

**this** 포인터는 **class** , **struct** 또는 **union** 형식의 비정적 멤버 함수 내 에서만 액세스할 수 있는 포인터입니다. 멤버 함수가 호출되는 개체를 가리킵니다. 정적 멤버 함수는 **this** 포인터를 포함 하지 않습니다.

## <a name="syntax"></a>구문

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>주의

개체의 **this** 포인터가 개체 자체의 일부가 아닙니다. 개체에 대 한 **sizeof** 문의 결과에는 반영 되지 않습니다. 개체에 대해 비정적 멤버 함수를 호출 하면 컴파일러가 개체의 주소를 함수에 숨겨진 인수로 전달 합니다. 예를 들어, 다음 함수 호출은

```cpp
myDate.setMonth( 3 );
```

다음과 같이 해석 될 수 있습니다.

```cpp
setMonth( &myDate, 3 );
```

개체의 주소는 멤버 함수에서 **this** 포인터로 사용할 수 있습니다. 대부분의 **this** 포인터는 암시적입니다. class멤버를 참조할 때 명시적 **this** 를 사용 하는 것은 필요 하지 않습니다. 예를 들면 다음과 같습니다.:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are equivalent
   (*this).month = mn;
}
```

멤버 함수에서 현재 개체를 반환하기 위해 `*this` 식이 주로 사용됩니다.

```cpp
return *this;
```

**this** 포인터는 자체 참조를 방지 하는 데도 사용 됩니다.

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
> **this** 포인터는 수정할 수 없으므로 **this** 포인터에 대 한 할당은 허용 되지 않습니다. this에 대해 C++ 허용 되는할당의 이전 구현입니다.

경우에 따라 **this** 포인터를 직접 사용 하 여 현재 개체의 주소가 필요한 자기 참조 데이터 구조를 조작 합니다.

## <a name="example"></a>예

```cpp
// this_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

class Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( const Buf & );
    void Display() { cout << buffer << endl; }

private:
    char*   buffer;
    size_t  sizeOfBuffer;
};

Buf::Buf( char* szBuffer, size_t sizeOfBuffer )
{
    sizeOfBuffer++; // account for a NULL terminator

    buffer = new char[ sizeOfBuffer ];
    if (buffer)
    {
        strcpy_s( buffer, sizeOfBuffer, szBuffer );
        sizeOfBuffer = sizeOfBuffer;
    }
}

Buf& Buf::operator=( const Buf &otherbuf )
{
    if( &otherbuf != this )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *this;
}

int main()
{
    Buf myBuf( "my buffer", 10 );
    Buf yourBuf( "your buffer", 12 );

    // Display 'my buffer'
    myBuf.Display();

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-opno-locthis-pointer"></a>this 포인터의 형식입니다.

**const** 및 **volatile** 키워드를 통해 함수 선언에서 **this** 포인터의 형식을 수정할 수 있습니다. 이러한 특성 중 하나를 포함 하는 함수를 선언 하려면 함수 인수 목록 뒤에 키워드를 추가 합니다.

예를 들어 보겠습니다.

```cpp
// type_of_this_pointer1.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

위의 코드는 **this** 포인터가 **const** 개체에 대 한 **const** 포인터로 처리 되는 `X`멤버 함수를 선언 합니다. *Cv-mod 목록* 옵션의 조합을 사용할 수 있지만 항상 포인터 자체가 아닌 **this** 포인터가 가리키는 개체를 수정 합니다. 다음 선언에서는 함수 `X`를 선언 합니다. 여기서 **this** 포인터는 **const** 개체에 대 한 **const** 포인터입니다.

```cpp
// type_of_this_pointer2.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

멤버 함수의 **this** 형식은 다음 구문으로 설명 됩니다. *Cv 한정자 목록은* 멤버 함수의 선언 자에서 결정 됩니다. **const** 또는 **volatile** 수 있습니다 (또는 둘 다). *class* 은 class의 이름입니다.

[*cv-한정자-목록*] *class형식* **\* const this**

즉, **this** 포인터는 항상 const 포인터입니다. 다시 할당할 수 없습니다.  멤버 함수 선언에 사용 되는 **const** 또는 **volatile** 한정자는 해당 함수의 범위에서 **this** 포인터가 가리키는 class 인스턴스에 적용 됩니다.

다음 표에서 이러한 한정자의 작동 방식에 대해 자세히 설명합니다.

### <a name="semantics-of-opno-locthis-modifiers"></a>this 한정자의 의미 체계

|Modifier|의미|
|--------------|-------------|
|**const**|멤버 데이터를 변경할 수 없습니다. **const** 되지 않은 멤버 함수를 호출할 수 없습니다.|
|**volatile**|멤버 데이터는 액세스할 때마다 메모리에서 로드 됩니다. 특정 최적화를 사용 하지 않습니다.|

**const** 개체를 **const** 되지 않은 멤버 함수에 전달 하는 것은 오류입니다.

마찬가지로 **volatile** 개체를 **volatile** 되지 않은 멤버 함수에 전달 하는 것도 오류입니다.

**const** 로 선언 된 멤버 함수는 멤버 데이터를 변경할 수 없습니다. 이러한 함수에서 **this** 포인터는 **const** 개체에 대 한 포인터입니다.

> [!NOTE]
> 생성자 및 소멸자는 **const** 또는 **volatile** 로 선언할 수 없습니다. 그러나 **const** 또는 **volatile** 개체에 대해 호출 될 수 있습니다.

## <a name="see-also"></a>참조

[C++ 키워드](../cpp/keywords-cpp.md)
