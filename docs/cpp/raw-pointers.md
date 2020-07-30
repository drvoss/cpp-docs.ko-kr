---
title: 원시 포인터 (c + +)
description: C + +에서 원시 포인터를 사용 하는 방법
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- ':::no-loc(void):::'
- ':::no-loc(nullptr):::'
- ':::no-loc(const):::'
- ':::no-loc(char):::'
- ':::no-loc(new):::'
- ':::no-loc(delete):::'
ms.openlocfilehash: 53679559888191fe7f2aad7cb5a70d607974ae96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233654"
---
# <a name="raw-pointers-c"></a>원시 포인터 (c + +)

*포인터* 는 변수의 형식입니다. 개체의 주소를 메모리에 저장 하 고 해당 개체에 액세스 하는 데 사용 됩니다. *원시 포인터* 는 [스마트 포인터](smart-pointers-modern-cpp.md)와 같은 캡슐화 된 개체에 의해 수명이 제어 되지 않는 포인터입니다. 원시 포인터에는 포인터가 아닌 다른 변수의 주소를 할당 하거나 값을 할당할 수 있습니다 [:::no-loc(nullptr):::](:::no-loc(nullptr):::.md) . 값이 할당 되지 않은 포인터에는 임의 데이터가 포함 됩니다.

포인터가 가리키는 개체의 값을 검색 하기 위해 포인터를 *역참조* 할 수도 있습니다. *멤버 액세스 연산자* 는 개체의 멤버에 대 한 액세스를 제공 합니다.

```cpp
    int* p = :::no-loc(nullptr):::; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

포인터는 형식화 된 개체 또는를 가리킬 수 있습니다 **`:::no-loc(void):::`** . 프로그램은 메모리의 [힙에](https://wikipedia.org/wiki/Heap) 개체를 할당 하는 경우 해당 개체의 주소를 포인터 형식으로 받습니다. 이러한 포인터를 *소유 포인터*라고 합니다. 더 이상 필요 하지 않은 경우 힙 할당 개체를 명시적으로 해제 하려면 소유 하는 포인터 (또는 it의 복사본)를 사용 해야 합니다. 메모리를 해제 하지 못하면 *메모리 누수가*발생 하 고 컴퓨터의 다른 프로그램에서 해당 메모리 위치를 사용할 수 없게 됩니다. 을 사용 하 여 할당 된 메모리 **`:::no-loc(new):::`** 는 **`:::no-loc(delete):::`** (또는 ** :::no-loc(delete)::: \[ ]**)를 사용 하 여 해제 해야 합니다. 자세한 내용은 [ :::no-loc(new)::: 및 :::no-loc(delete)::: 연산자](:::no-loc(new):::-and-:::no-loc(delete):::-operators.md)를 참조 하세요.

```cpp
    MyClass* mc = :::no-loc(new)::: MyClass(); // allocate object on the heap
    mc->print(); // access class member
    :::no-loc(delete)::: mc; // :::no-loc(delete)::: object (please don't forget!)
```

포인터 (로 선언 되지 않은 경우 **`:::no-loc(const):::`** )는 메모리의 다른 위치를 가리키도록 증가 하거나 감소할 수 있습니다. 이 작업을 *포인터 산술 연산*이라고 합니다. 이 클래스는 C 스타일 프로그래밍에서 배열 또는 다른 데이터 구조의 요소를 반복 하는 데 사용 됩니다. **`:::no-loc(const):::`** 다른 메모리 위치를 가리키도록 포인터를 설정할 수 없으며,이는 [참조](references-cpp.md)와 비슷합니다. 자세한 내용은 [ :::no-loc(const)::: 및 휘발성 포인터](:::no-loc(const):::-and-volatile-pointers.md)를 참조 하십시오.

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    :::no-loc(const)::: :::no-loc(char):::* str = "Hello world";

    :::no-loc(const)::: int c = 1;
    :::no-loc(const)::: int* p:::no-loc(const)::: = &c; // declare a non-:::no-loc(const)::: pointer to :::no-loc(const)::: int
    :::no-loc(const)::: int c2 = 2;
    p:::no-loc(const)::: = &c2;  // OK p:::no-loc(const)::: itself isn't :::no-loc(const):::
    :::no-loc(const)::: int* :::no-loc(const)::: p:::no-loc(const):::2 = &c;
    // p:::no-loc(const):::2 = &c2; // Error! p:::no-loc(const):::2 is :::no-loc(const):::.
```

64 비트 운영 체제에서 포인터의 크기는 64 비트입니다. 시스템의 포인터 크기는 사용할 수 있는 주소 지정 가능한 메모리의 양을 결정 합니다. 포인터의 모든 복사본은 동일한 메모리 위치를 가리킵니다. 포인터 (참조와 함께)는 c + +에서 광범위 한 개체를 함수에 전달 하는 데 광범위 하 게 사용 됩니다. 개체의 주소를 복사 하 여 전체 개체를 복사 하는 것이 더 효율적인 경우가 많기 때문입니다. 함수를 정의 하는 경우 **`:::no-loc(const):::`** 함수에서 개체를 수정 하지 않으려는 경우 포인터 매개 변수를로 지정 합니다. 일반적으로 **`:::no-loc(const):::`** 참조는 개체의 값이 일 수 있는 경우를 제외 하 고 개체를 함수에 전달 하는 데 선호 되는 방법 **`:::no-loc(nullptr):::`** 입니다.

함수에 대 한 [포인터](#pointers_to_functions) 는 함수를 다른 함수에 전달 하 고 C 스타일 프로그래밍의 "콜백"에 사용 됩니다. 최신 c + +에서는이 용도로 [람다 식을](lambda-expressions-in-cpp.md) 사용 합니다.

## <a name="initialization-and-member-access"></a>초기화 및 멤버 액세스

다음 예제에서는 원시 포인터를 선언 하 고 초기화 하 고 사용 하는 방법을 보여 줍니다. **`:::no-loc(new):::`** 사용자가 명시적으로 지정 해야 하는 힙에 할당 된 개체를 가리키기 위해를 사용 하 여 초기화 **`:::no-loc(delete):::`** 됩니다. 또한이 예제에서는 원시 포인터와 관련 된 몇 가지 위험을 보여 줍니다. (이 예제는 C 스타일 프로그래밍 이며 최신 c + +가 아닌 C + +입니다.)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
:::no-loc(void)::: func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
:::no-loc(void)::: func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use :::no-loc(new)::: to allocate and initialize memory
    MyClass* pmc = :::no-loc(new)::: MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std:: cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    :::no-loc(delete):::(pmc); // don't forget to give memory back to operating system!
   // :::no-loc(delete):::(pmc2); //crash! memory location was already :::no-loc(delete):::d
}
```

## <a name="pointer-arithmetic-and-arrays"></a>포인터 산술 및 배열

포인터와 배열은 밀접 하 게 관련 되어 있습니다. 배열이 값으로 함수에 전달 되 면 첫 번째 요소에 대 한 포인터로 전달 됩니다. 다음 예제에서는 포인터와 배열의 다음과 같은 중요 한 속성을 보여 줍니다.

- **`sizeof`** 연산자는 배열의 전체 크기 (바이트)를 반환 합니다.
- 요소 수를 확인 하려면 전체 바이트를 한 요소의 크기로 나눕니다.
- 배열이 함수에 전달 되 면 포인터 형식으로 *decays* .
- **`sizeof`** 포인터에 적용 될 때 연산자는 포인터 크기, x 86의 경우 4 바이트 또는 x 64에서는 8 바이트를 반환 합니다.

```cpp
#include <iostream>

:::no-loc(void)::: func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

포인터를 사용 하지 않는 특정 산술 연산을 사용 :::no-loc(const)::: 하 여 다른 메모리 위치를 가리키도록 할 수 있습니다. **++**, **+=** **-=** 및 연산자를 사용 하 여 포인터를 증가 및 감소 시킵니다 **--** . 이 기술은 배열에서 사용할 수 있으며 형식화 되지 않은 데이터의 버퍼에서 특히 유용 합니다. 는 **:::no-loc(void):::\*** **`:::no-loc(char):::`** (1 바이트)의 크기로 증가 합니다. 형식화 된 포인터는 포인터가 가리키는 형식의 크기 만큼 증가 합니다.

다음 예제에서는 포인터 산술 연산을 사용 하 여 Windows에서 비트맵의 개별 픽셀에 액세스 하는 방법을 보여 줍니다. 및 및 역참조 연산자를 사용 합니다 **`:::no-loc(new):::`** **`:::no-loc(delete):::`** .

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    :::no-loc(const):::expr int bufferSize = 30000;
    unsigned :::no-loc(char):::* buffer = :::no-loc(new)::: unsigned :::no-loc(char):::[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned :::no-loc(char):::* begin = &buffer[0];
    unsigned :::no-loc(char):::* end = &buffer[0] + bufferSize;
    unsigned :::no-loc(char):::* p = begin;
    :::no-loc(const):::expr int pixelWidth = 3;
    :::no-loc(const):::expr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned :::no-loc(char):::).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<:::no-loc(char):::*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(&header), sizeof(header));
    wf.write(reinterpret_cast<:::no-loc(char):::*>(begin), bufferSize);

    :::no-loc(delete):::[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="no-locvoid-pointers"></a>:::no-loc(void):::* 포인터

에 대 한 포인터는 **`:::no-loc(void):::`** 단순히 원시 메모리 위치를 가리킵니다. **:::no-loc(void):::\*** C + + 코드와 c 함수를 전달 하는 경우와 같이 포인터를 사용 해야 하는 경우도 있습니다.

형식화 된 포인터를 포인터로 캐스팅 하면 :::no-loc(void)::: 메모리 위치의 내용이 변경 되지 않습니다. 그러나 증가 또는 감소 작업을 수행할 수 없도록 유형 정보가 손실 됩니다. 예를 들어에서로, 다시로 다시 이동 하는 등의 방법으로 메모리 위치를 캐스팅할 수 있습니다 `MyClass*` **`:::no-loc(void):::*`** `MyClass*` . 이러한 작업은 기본적으로 오류가 발생 하기 쉬우며 오류에 대 한 상당한 주의가 필요 :::no-loc(void)::: 합니다. 최신 c + +에서는 :::no-loc(void)::: 거의 모든 상황에서 포인터를 사용 하지 않습니다.

```cpp

//func.c
:::no-loc(void)::: func(:::no-loc(void):::* data, int length)
{
    :::no-loc(char):::* c = (:::no-loc(char):::*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    :::no-loc(void)::: func(:::no-loc(void):::* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    :::no-loc(void)::: print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = :::no-loc(new)::: MyClass{10, "Marian"};
    :::no-loc(void):::* p = static_cast<:::no-loc(void):::*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator :::no-loc(new)::: to allocate untyped memory block
    :::no-loc(void):::* p:::no-loc(void)::: = operator :::no-loc(new):::(1000);
    :::no-loc(char):::* p:::no-loc(char)::: = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::);
    for(:::no-loc(char):::* c = p:::no-loc(char):::; c < p:::no-loc(char)::: + 1000; ++c)
    {
        *c = 0x00;
    }
    func(p:::no-loc(void):::, 1000);
    :::no-loc(char)::: ch = static_cast<:::no-loc(char):::*>(p:::no-loc(void):::)[0];
    std::cout << ch << std::endl; // 'A'
    operator :::no-loc(delete):::(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>함수에 대 한 포인터

C 스타일 프로그래밍에서 함수 포인터는 주로 함수를 다른 함수에 전달 하는 데 사용 됩니다. 이 방법을 사용 하면 호출자가 함수를 수정 하지 않고 동작의 동작을 사용자 지정할 수 있습니다. 최신 c + +에서 [람다 식은](lambda-expressions-in-cpp.md) 형식 안전 성과 기타 이점을 포함 하는 동일한 기능을 제공 합니다.

함수 포인터 선언은 뾰족한 함수에 필요한 시그니처를 지정 합니다.

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
:::no-loc(void)::: (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

다음 예제에서는 `combine` 를 허용 하 고를 반환 하는 모든 함수를 매개 변수로 사용 하는 함수를 보여 줍니다 `std::string` `std::string` . 에 전달 되는 함수에 따라 `combine` 앞 이나 뒤에 문자열을 추가 합니다.

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>참고 항목

[스마트 포인터](smart-pointers-modern-cpp.md) 
 [간접 참조 연산자: *](indirection-operator-star.md)<br/>
[주소 연산자: &](address-of-operator-amp.md)</br>
[C + +를 다시 시작 합니다.](welcome-back-to-cpp-modern-cpp.md)
