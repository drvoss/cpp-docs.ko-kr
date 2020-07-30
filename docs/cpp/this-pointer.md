---
title: ':::no-loc(this)::: 포인터'
description: :::no-loc(this):::포인터는 비정적 멤버 함수에서 현재 개체에 대 한 컴파일러 생성 포인터입니다.
ms.date: 01/22/2020
f1_keywords:
- :::no-loc(this):::_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- 'pointers, to :::no-loc(class)::: instance'
- ':::no-loc(this)::: pointer'
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- ':::no-loc(this):::'
- ':::no-loc(class):::'
- ':::no-loc(struct):::'
- ':::no-loc(union):::'
- ':::no-loc(sizeof):::'
- ':::no-loc(const):::'
- ':::no-loc(volatile):::'
ms.openlocfilehash: c851beaba7fe1091ffd7827714f90307303058c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225828"
---
# <a name="no-locthis-pointer"></a>:::no-loc(this)::: 포인터

**`:::no-loc(this):::`** 포인터는 **`:::no-loc(class):::`** , **`:::no-loc(struct):::`** 또는 형식의 비정적 멤버 함수 내 에서만 액세스할 수 있는 포인터입니다 **`:::no-loc(union):::`** . 멤버 함수가 호출되는 개체를 가리킵니다. 정적 멤버 함수에는 **`:::no-loc(this):::`** 포인터가 없습니다.

## <a name="syntax"></a>구문

```cpp
:::no-loc(this):::
:::no-loc(this):::->member-identifier
```

## <a name="remarks"></a>설명

개체의 **`:::no-loc(this):::`** 포인터가 개체 자체의 일부가 아닙니다. 개체에 대 한 문의 결과에는 반영 되지 않습니다 **`:::no-loc(sizeof):::`** . 개체에 대해 비정적 멤버 함수를 호출 하면 컴파일러가 개체의 주소를 함수에 숨겨진 인수로 전달 합니다. 예를 들어, 다음 함수 호출은

```cpp
myDate.setMonth( 3 );
```

다음과 같이 해석 될 수 있습니다.

```cpp
setMonth( &myDate, 3 );
```

개체의 주소는 멤버 함수 내에서 포인터로 사용할 수 있습니다 **`:::no-loc(this):::`** . 대부분의 **`:::no-loc(this):::`** 포인터는 암시적입니다. 의 멤버를 참조할 때 명시적를 사용 하는 것은 불필요 하지만 필요 하지 **`:::no-loc(this):::`** :::no-loc(class)::: 않습니다. 예를 들면 다음과 같습니다.

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   :::no-loc(this):::->month = mn;      // are equivalent
   (*:::no-loc(this):::).month = mn;
}
```

식은 **`*:::no-loc(this):::`** 일반적으로 멤버 함수에서 현재 개체를 반환 하는 데 사용 됩니다.

```cpp
return *:::no-loc(this):::;
```

**`:::no-loc(this):::`** 포인터는 자체 참조를 방지 하는 데도 사용 됩니다.

```cpp
if (&Object != :::no-loc(this):::) {
// do not execute in cases of self-reference
```

> [!NOTE]
> 포인터는 **`:::no-loc(this):::`** 수정할 수 없으므로 포인터에 대 한 할당 **`:::no-loc(this):::`** 은 허용 되지 않습니다. 이전의 c + + 구현에서는에 대 한 할당을 사용할 수 **`:::no-loc(this):::`** 있습니다.

경우에 따라 **`:::no-loc(this):::`** 포인터가 직접 사용 됩니다. 예를 들어 :::no-loc(struct)::: 현재 개체의 주소가 필요한 자체 참조 데이터 ures를 조작 합니다.

## <a name="example"></a>예제

```cpp
// :::no-loc(this):::_pointer.cpp
// compile with: /EHsc

#include <iostream>
#include <string.h>

using namespace std;

:::no-loc(class)::: Buf
{
public:
    Buf( char* szBuffer, size_t sizeOfBuffer );
    Buf& operator=( :::no-loc(const)::: Buf & );
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

Buf& Buf::operator=( :::no-loc(const)::: Buf &otherbuf )
{
    if( &otherbuf != :::no-loc(this)::: )
    {
        if (buffer)
            delete [] buffer;

        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;
        buffer = new char[sizeOfBuffer];
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );
    }
    return *:::no-loc(this):::;
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

## <a name="type-of-the-no-locthis-pointer"></a>포인터의 형식입니다. :::no-loc(this):::

**`:::no-loc(this):::`** 포인터의 형식은 함수 선언에서 및 키워드로 수정할 수 있습니다 **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** . 이러한 특성 중 하나를 포함 하는 함수를 선언 하려면 함수 인수 목록 뒤에 키워드를 추가 합니다.

예를 들어 보겠습니다.

```cpp
// type_of_:::no-loc(this):::_pointer1.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

위의 코드는 `X` **`:::no-loc(this):::`** 포인터를 **`:::no-loc(const):::`** 개체에 대 한 포인터로 처리 하는 멤버 함수를 선언 합니다 **`:::no-loc(const):::`** . *Cv-mod 목록* 옵션의 조합을 사용할 수 있지만 항상 포인터가 아니라 포인터가 가리키는 개체를 수정 합니다 **`:::no-loc(this):::`** . 다음 선언은 함수를 선언 합니다 `X` . 여기서 **`:::no-loc(this):::`** 포인터는 **`:::no-loc(const):::`** 개체에 대 한 포인터입니다 **`:::no-loc(const):::`** .

```cpp
// type_of_:::no-loc(this):::_pointer2.cpp
:::no-loc(class)::: Point
{
    unsigned X() :::no-loc(const):::;
};
int main()
{
}
```

**`:::no-loc(this):::`** 멤버 함수에서의 형식은 다음 구문으로 설명 됩니다. *Cv 한정자 목록은* 멤버 함수의 선언 자에서 결정 됩니다. **`:::no-loc(const):::`** 또는 **`:::no-loc(volatile):::`** (또는 둘 다) 일 수 있습니다. * :::no-loc(class)::: -type* 은의 이름입니다 :::no-loc(class)::: .

[*cv-한정자-목록*] * :::no-loc(class)::: -형식* ** \* :::no-loc(const)::: :::no-loc(this)::: **

즉, **`:::no-loc(this):::`** 포인터는 항상 :::no-loc(const)::: 포인터입니다. 다시 할당할 수 없습니다.  **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** 멤버 함수 선언에 사용 되는 또는 한정자는 :::no-loc(class)::: **`:::no-loc(this):::`** 해당 함수의 범위에서 포인터가 가리키는 인스턴스에 적용 됩니다.

다음 표에서 이러한 한정자의 작동 방식에 대해 자세히 설명합니다.

### <a name="semantics-of-no-locthis-modifiers"></a>한정자의 의미 :::no-loc(this):::

|한정자|의미|
|--------------|-------------|
|**`:::no-loc(const):::`**|멤버 데이터를 변경할 수 없습니다. 가 아닌 멤버 함수를 호출할 수 없습니다 **`:::no-loc(const):::`** .|
|**`:::no-loc(volatile):::`**|멤버 데이터는 액세스할 때마다 메모리에서 로드 됩니다. 특정 최적화를 사용 하지 않습니다.|

개체를이 **`:::no-loc(const):::`** 아닌 멤버 함수에 전달 하는 것은 오류입니다 **`:::no-loc(const):::`** .

마찬가지로 개체를이 **`:::no-loc(volatile):::`** 아닌 멤버 함수에 전달 하는 것도 오류입니다 **`:::no-loc(volatile):::`** .

멤버로 선언 된 멤버 함수는 **`:::no-loc(const):::`** 멤버 데이터를 변경할 수 없습니다. 이러한 함수에서 **`:::no-loc(this):::`** 포인터는 개체에 대 한 포인터입니다 **`:::no-loc(const):::`** .

> [!NOTE]
> Con :::no-loc(struct)::: ors 및 de :::no-loc(struct)::: ors는 또는로 선언할 수 없습니다 **`:::no-loc(const):::`** **`:::no-loc(volatile):::`** . 그러나 또는 개체에 대해 호출 될 수 **`:::no-loc(const):::`** 있습니다 **`:::no-loc(volatile):::`** .

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)
