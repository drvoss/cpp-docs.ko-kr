---
title: 원시 포인터 (C++)
description: 에서 원시 포인터를 사용 하는 방법C++
ms.date: 11/19/2019
helpviewer_keywords:
- pointers [C++]
ms.openlocfilehash: 2dbb4f11fc0c08578e82371e8df77e9643313879
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077140"
---
# <a name="raw-pointers-c"></a>원시 포인터 (C++)

포인터는 개체의 주소를 메모리에 저장 하 고 해당 개체에 액세스 하는 데 사용 되는 변수의 형식입니다. *원시 포인터* 는 수명이 [스마트 포인터](smart-pointers-modern-cpp.md)와 같은 캡슐화 된 개체에 의해 제어 되지 않는 포인터입니다. 원시 포인터에는 다른 비 포인터 변수의 주소를 할당할 수 있습니다. 그렇지 않으면 [nullptr](nullptr.md)값을 할당할 수 있습니다. 값이 할당 되지 않은 포인터에 임의의 데이터가 포함 되어 있습니다.

포인터가 가리키는 개체의 값을 검색 하기 위해 포인터를 *역참조* 할 수도 있습니다. *멤버 액세스 연산자* 는 개체의 멤버에 대 한 액세스를 제공 합니다.

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address

```

포인터는 형식화 된 개체 또는 **void**를 가리킬 수 있습니다. 프로그램은 메모리의 [힙에](https://wikipedia.org/wiki/Heap) 새 개체를 할당 하는 경우 해당 개체의 주소를 포인터 형식으로 받습니다. 이러한 포인터는 *소유 포인터*라고 합니다. 더 이상 필요 하지 않은 힙 할당 개체를 명시적으로 삭제 하려면 소유 하는 포인터 (또는 it의 복사본)를 사용 해야 합니다. 메모리를 삭제 하지 못하면 *메모리 누수가* 발생 하 고 컴퓨터의 다른 프로그램에서 해당 메모리 위치를 사용할 수 없게 됩니다. 자세한 내용은 [new 및 delete 연산자](new-and-delete-operators.md)를 참조 하세요.

```cpp

    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

포인터 ( **const**로 선언 되지 않은 경우)는 메모리의 새 위치를 가리키도록 증가 하거나 감소할 수 있습니다. 이를 *포인터 산술 연산* 이라고 하 고 C 스타일 프로그래밍에서 배열 또는 다른 데이터 구조의 요소를 반복 하는 데 사용 됩니다. **Const** 포인터는 다른 메모리 위치를 가리키도록 만들 수 없으며,이는 [참조](references-cpp.md)와 매우 비슷합니다. 자세한 내용은 [const 및 volatile 포인터](const-and-volatile-pointers.md)를 참조 하세요.

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

64 비트 운영 체제에서 포인터의 크기는 64 비트입니다. 시스템의 포인터 크기는 사용할 수 있는 주소 지정 가능한 메모리의 양을 결정 합니다. 포인터의 모든 복사본은 동일한 메모리 위치를 가리킵니다. 포인터 (참조와 함께)는 개체의 64 C++ 비트 주소를 복사 하는 것이 전체 개체를 복사 하는 것 보다 일반적으로 훨씬 효율적 이기 때문에 더 큰 개체를 함수에 전달 하는 데 광범위 하 게 사용 됩니다. 함수를 정의 하는 경우 함수에서 개체를 수정 하지 않으려는 경우 포인터 매개 변수를 **const** 로 지정 합니다. 일반적으로 개체의 값이 **nullptr**일 수 있는 경우를 제외 하 고 개체를 함수에 전달 하는 데는 **const** 참조가 기본 설정 되어 있습니다.

함수에 대 한 [포인터](#pointers_to_functions) 는 함수를 다른 함수에 전달 하 고 C 스타일 프로그래밍의 "콜백"에 사용 됩니다. 최신 C++ 에서는 이러한 용도로 [람다 식을](lambda-expressions-in-cpp.md) 사용 합니다.

## <a name="initialization-and-member-access"></a>초기화 및 멤버 액세스

다음 예제에서는 원시 포인터를 선언 하 고 힙에 할당 된 개체를 사용 하 여 초기화 한 다음 사용 하는 방법을 보여 줍니다. 또한 원시 포인터와 관련 된 몇 가지 위험을 보여 줍니다. (이는 C 스타일 프로그래밍 이며 최신 C++이 아님)

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

포인터와 배열은 밀접 하 게 관련 되어 있습니다. 배열이 값으로 함수에 전달 되 면 첫 번째 요소에 대 한 포인터로 전달 됩니다. 다음 예제에서는 포인터와 배열의 다음과 같은 중요 한 속성을 보여 줍니다.

- `sizeof` 연산자는 배열의 전체 크기 (바이트)를 반환 합니다.
- 요소 수를 확인 하려면 전체 바이트를 한 요소의 크기로 나눕니다.
- 배열이 함수에 전달 되 면 포인터 형식으로 *decays* .
- 포인터에 적용 될 때 `sizeof` 연산자는 포인터 크기, x 86의 경우 4 바이트, x 64에서는 8 바이트를 반환 합니다.

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

Const가 아닌 포인터에 대해 특정 산술 연산을 수행 하 여 새 메모리 위치를 가리키도록 할 수 있습니다. **++** , **+=** , **-=** 및 **--** 연산자를 사용 하 여 포인터를 증가 및 감소 시킬 수 있습니다. 이 기술은 배열에서 사용할 수 있으며 형식화 되지 않은 데이터의 버퍼에서 특히 유용 합니다. **Void\*** **char** 크기 (1 바이트) 만큼 증가 합니다. 형식화 된 포인터는 포인터가 가리키는 형식의 크기 만큼 증가 합니다.

다음 예제에서는 포인터 산술 연산을 사용 하 여 Windows에서 비트맵의 개별 픽셀에 액세스 하는 방법을 보여 줍니다. **New** 및 **delete**를 사용 하 고 역참조 연산자를 사용 합니다.

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

## <a name="void-pointers"></a>void * 포인터

**Void** 에 대 한 포인터는 단순히 원시 메모리 위치를 가리킵니다. 코드와 C 함수를 전달 하는 경우와 같이 **void\*** 포인터를 사용 해야 하는 경우도 있습니다. C++

형식화 된 포인터가 void 포인터로 캐스팅 되 면 메모리 위치의 내용이 변경 되지 않지만, 증가 또는 감소 작업을 수행할 수 없도록 형식 정보가 손실 됩니다. 예를 들어 MyClass *에서 void *로, 다시 MyClass *로 다시 변환 하는 등의 방법으로 메모리 위치를 캐스팅할 수 있습니다. 이러한 작업은 기본적으로 오류가 발생 하기 쉬우며 오류가 발생 하지 않도록 주의 해야 합니다. 현재 C++ 는 반드시 필요한 경우를 제외 하 고는 void 포인터 사용을 사용 하지 않습니다.

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
    for(char* c = static_cast<char*>(pvoid); pvoid < &pvoid + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>함수에 대 한 포인터

C 스타일 프로그래밍에서 함수 포인터는 주로 함수를 다른 함수에 전달 하는 데 사용 됩니다. 이 시나리오에서 호출자는 함수를 수정 하지 않고 동작의 동작을 사용자 지정할 수 있습니다. 현대 C++에서 [람다 식은](lambda-expressions-in-cpp.md) 형식 안전 성과 기타 이점을 가진 동일한 기능을 제공 합니다.

함수 포인터 선언은 뾰족한 함수에 필요한 시그니처를 지정 합니다.

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

다음 예제에서는 `std::string`를 수락 하 고 `std::string`를 반환 하는 함수를 매개 변수로 사용 하는 `combine` 함수를 보여 줍니다. `combine` 전달 되는 함수에 따라 문자열 앞에 추가 하거나 추가 합니다.

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
[다시 시작C++](welcome-back-to-cpp-modern-cpp.md)
