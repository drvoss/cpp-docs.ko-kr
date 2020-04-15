---
title: 원시 포인터(C++)
description: C ++에서 원시 포인터를 사용하는 방법
ms.date: 11/19/2019
helpviewer_keywords:
- pointers [C++]
ms.openlocfilehash: 919447fcab123ce6b838391d3cc295fb8a8fe95e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374672"
---
# <a name="raw-pointers-c"></a>원시 포인터(C++)

포인터는 개체의 주소를 메모리에 저장하고 해당 개체에 액세스하는 데 사용되는 변수 유형입니다. *원시 포인터는* 스마트 포인터와 같은 캡슐화 개체에 의해 수명이 제어되지 않는 [포인터입니다.](smart-pointers-modern-cpp.md) 원시 포인터는 다른 비 포인터 변수의 주소를 할당하거나 [nullptr](nullptr.md)의 값을 할당 할 수 있습니다. 값이 할당되지 않은 포인터에는 임의의 데이터가 포함됩니다.

포인터를 *역참조하여* 가리키는 개체값을 검색할 수도 있습니다. *멤버 액세스 연산자는* 개체의 멤버에 대한 액세스를 제공합니다.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address

```

포인터는 입력된 개체를 가리키거나 **void를**가리킬 수 있습니다. 프로그램이 메모리의 [힙에](https://wikipedia.org/wiki/Heap) 새 개체를 할당하면 포인터 형태로 해당 개체의 주소를 받습니다. 이러한 포인터를 *소유 포인터라고 합니다.* 소유 포인터(또는 복사본)를 사용하여 더 이상 필요하지 않을 때 힙 할당된 개체를 명시적으로 삭제해야 합니다. 메모리를 삭제하지 않으면 *메모리가 누수되고* 해당 메모리 위치를 컴퓨터의 다른 프로그램에서 사용할 수 없게 됩니다. 자세한 내용은 [새 및 삭제 연산자](new-and-delete-operators.md)를 참조하십시오.

```cpp

    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

**포인터(const로**선언되지 않은 경우)는 메모리의 새 위치를 가리키도록 증분되거나 감소될 수 있습니다. 이를 *포인터 산술이라고* 하며 배열 또는 기타 데이터 구조의 요소를 반복하기 위해 C 스타일 프로그래밍에 사용됩니다. **const** 포인터는 다른 메모리 위치를 가리키도록 만들 수 없으며 이러한 의미에서 [참조와](references-cpp.md)매우 유사합니다. 자세한 내용은 [const 및 휘발성 포인터를](const-and-volatile-pointers.md)참조하십시오.

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    const char* str = "Hello world";

    const int c = 1;
    const int* pconst = &c; // declare a non-const pointer to const int
    const int c2 = 2;
    pconst = &c2;  // OK pconst itself isn't const
    const int* const pconst2 = &c;
    // pconst2 = &c2; // Error! pconst2 is const.
```

64비트 운영 체제에서 포인터의 크기는 64비트입니다. 시스템의 포인터 크기에 따라 주소 지정 가능한 메모리의 양을 결정합니다. 포인터의 모든 복사본은 동일한 메모리 위치를 가리킵니다. 참조와 함께 포인터는 C++에서 전체 개체를 복사하는 것보다 일반적으로 개체의 64비트 주소를 복사하는 것이 훨씬 효율적이기 때문에 함수와 함수를 오가서 전달하기 위해 광범위하게 사용됩니다. 함수를 정의할 때 함수가 개체를 수정하려는 경우가 아니면 포인터 매개 변수를 **const로** 지정합니다. 일반적으로 **const** 참조는 개체값이 **nullptr일**수 없는 경우 개체를 함수에 전달하는 기본 방법입니다.

[함수에 대한 포인터를](#pointers_to_functions) 사용하면 함수를 다른 함수로 전달할 수 있으며 C 스타일 프로그래밍의 "콜백"에 사용됩니다. 현대 C++는 이를 위해 [람다 식을](lambda-expressions-in-cpp.md) 사용합니다.

## <a name="initialization-and-member-access"></a>초기화 및 멤버 액세스

다음 예제에서는 원시 포인터를 선언하고 힙에 할당된 개체로 초기화한 다음 사용하는 방법을 보여 주며 이를 사용하는 방법을 보여 주습니다. 또한 원시 포인터와 관련된 몇 가지 위험을 보여줍니다. (기억, 이것은 C 스타일 프로그래밍이 아니라 현대 C ++!)

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
void func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
void func_B(MyClass mc)
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
    // Use new to allocate and initialize memory
    MyClass* pmc = new MyClass{ 108, "Nick" };

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
    func_A(mc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*mc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>포인터 산술 및 배열

포인터와 배열은 밀접하게 관련되어 있습니다. 배열이 함수에 값으로 전달되면 첫 번째 요소에 대한 포인터로 전달됩니다. 다음 예제에서는 포인터 및 배열의 다음과 같은 중요한 속성을 보여 줍니다.

- 연산자는 `sizeof` 배열의 바이트로 총 크기를 반환합니다.
- 요소 수를 결정하기 위해 총 바이트를 하나의 요소 크기로 나눕니다.
- 배열이 함수에 전달되면 포인터 유형으로 *디감전됩니다.*
- 포인터에 적용할 `sizeof` 연산자는 포인터 크기, x86에서 4 바이트 또는 x64에서 8 바이트를 반환합니다.

```cpp
#include <iostream>

void func(int arr[], int length)
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

특정 산술 연산은 const가 아닌 포인터에서 수행하여 새 메모리 위치를 가리킬 수 있습니다. 포인터는 **++**" **+=** **-=** 및 **--** 연산자를 사용하여 증분 및 감소될 수 있습니다. 이 기술은 배열에 사용할 수 있으며 형식이 없는 데이터의 버퍼에 특히 유용합니다. 문자(1바이트)의 크기에 따라 **char** **보이드\* ** 증분입니다. 가리키는 형식의 크기에 따라 형식이 입력된 포인터가 증가합니다.

다음 예제에서는 포인터 산술 연산을 사용하여 Windows의 비트맵에서 개별 픽셀에 액세스하는 방법을 보여 줍니다. **새** 및 **삭제**및 반참조 연산자의 사용을 기록합니다.

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

    constexpr int bufferSize = 30000;
    unsigned char* buffer = new unsigned char[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned char* begin = &buffer[0];
    unsigned char* end = &buffer[0] + bufferSize;
    unsigned char* p = begin;
    constexpr int pixelWidth = 3;
    constexpr int borderWidth = 2;

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
        p++; // Increment one byte sizeof(unsigned char).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<char*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<char*>(&header), sizeof(header));
    wf.write(reinterpret_cast<char*>(begin), bufferSize);

    delete[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="void-pointers"></a>void* 포인터

**보이드포인터는** 단순히 원시 메모리 위치를 가리킵니다. 경우에 따라 C++ 코드와 C 함수 간에 전달할 때와 같은 **void\* ** 포인터를 사용해야 합니다.

형식이 있는 포인터가 void 포인터로 캐스팅되면 메모리 위치의 내용은 변경되지 않지만 형식 정보가 손실되므로 증분 또는 감소 작업을 수행할 수 없습니다. 예를 들어 MyClass*에서 void*로 메모리 위치를 다시 마이클래스*로 다시 캐스팅할 수 있습니다. 이러한 작업은 본질적으로 오류가 발생하기 쉬우며 오류를 방지하기 위해 세심한 주의가 필요합니다. 현대 C ++는 절대적으로 필요한 경우가 아니면 void 포인터의 사용을 금지합니다.

```cpp

//func.c
void func(void* data, int length)
{
    char* c = (char*)(data);

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
    void func(void* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = new MyClass{10, "Marian"};
    void* p = static_cast<void*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator new to allocate untyped memory block
    void* pvoid = operator new(1000);
    char* pchar = static_cast<char*>(pvoid);
    for(char* c = pchar; c < pchar + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>함수에 대한 포인터

C 스타일 프로그래밍에서 함수 포인터는 주로 함수를 다른 함수에 전달하는 데 사용됩니다. 이 시나리오에서 호출자는 함수를 수정하지 않고 함수의 동작을 사용자 지정할 수 있습니다. 최신 C++에서 [람다 식은](lambda-expressions-in-cpp.md) 더 큰 형식 안전 성과 및 기타 이점을 가진 동일한 기능을 제공합니다.

함수 포인터 선언은 가리키는 함수에 있어야 하는 서명을 지정합니다.

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
void (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

다음 예제에서는 를 `combine` `std::string` 수락하고 `std::string`을 반환하는 모든 함수를 매개 변수로 받아들이는 함수를 보여 준다. 전달되는 `combine` 함수에 따라 문자열을 프리펜더하거나 부가합니다.

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
[간접 연산자 : *](indirection-operator-star.md)<br/>
[주소 연산자: &](address-of-operator-amp.md)</br>
[C++에 다시 오신 것을 환영합니다.](welcome-back-to-cpp-modern-cpp.md)
