---
title: 맞춤
description: 데이터 맞춤이 최신 C++에서 지정 되는 방식입니다.
ms.date: 12/11/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 45b22742394a0b1c159e8b8102a26802a2441929
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076121"
---
# <a name="alignment"></a>맞춤

C++의 하위 수준 기능 중 하나는 특정 하드웨어 아키텍처를 최대한 활용하기 위해 메모리 내 개체의 정확한 맞춤을 지정하는 기능입니다. 기본적으로 컴파일러는 크기 값에 대 한 클래스 및 구조체 멤버를 정렬 합니다. `bool` 및 `char` 1 바이트 경계, 2 바이트 경계에 `short` 2 바이트 경계, `int`, `long`, `float` 4 바이트 경계, `long long`, `double`, `long double` 8 바이트 경계에 합니다.

대부분의 시나리오에서는 기본 맞춤이 이미 최적 이므로 맞춤을 걱정 하지 않아도 됩니다. 그러나 경우에 따라 데이터 구조에 대 한 사용자 지정 맞춤을 지정 하 여 상당한 성능 향상 이나 메모리 절감 효과를 얻을 수 있습니다. Visual Studio 2015 이전에는 Microsoft 전용 키워드 `__alignof` 사용 하 고 `declspec(alignas)` 하 여 기본값 보다 큰 맞춤을 지정할 수 있습니다. Visual Studio 2015부터 최대 코드 이식성을 위해 c + + 11 표준 키워드인 **alignof** 및 **alignas** 를 사용 해야 합니다. 새 키워드는 Microsoft 전용 확장과 동일한 방식으로 동작 합니다. 이러한 확장에 대 한 설명서는 새 키워드에도 적용 됩니다. 자세한 내용은 [__Alignof 연산자](../cpp/alignof-operator.md) 및 [맞춤](../cpp/align-cpp.md)을 참조 하세요. 표준 C++ 에서는 대상 플랫폼에 대 한 컴파일러 기본값 보다 작은 경계에 맞춤에 대 한 압축 동작을 지정 하지 않으므로이 경우에도 Microsoft #pragma [pack](../preprocessor/pack.md) 을 사용 해야 합니다.

사용자 지정 맞춤을 사용 하 여 데이터 구조의 메모리 할당을 위해 [aligned_storage 클래스](../standard-library/aligned-storage-class.md) 를 사용 합니다. [Aligned_union 클래스](../standard-library/aligned-union-class.md) 는 trivial 생성자 또는 소멸자를 사용 하 여 공용 구조체에 대 한 맞춤을 지정 하기 위한 것입니다.

## <a name="alignment-and-memory-addresses"></a>맞춤 및 메모리 주소

맞춤은 숫자 주소 모듈로 2의 거듭제곱으로 표현된 메모리 주소의 속성입니다. 예를 들어 0X0001103 주소는 3입니다. 이 주소는 4n + 3에 맞춰져 있습니다. 여기서 4는 선택 된 2의 제곱을 나타냅니다. 주소 맞춤은 선택 된 2의 거듭제곱에 따라 다릅니다. 동일한 주소의 모듈로 8은 7입니다. 맞춤이 Xn+0인 경우 주소가 X에 맞춰집니다.

Cpu는 메모리에 저장 된 데이터에 대해 작동 하는 명령을 실행 합니다. 데이터는 메모리의 주소로 식별 됩니다. 단일 데이텀이 크기를 가집니다. 주소가 크기에 맞게 정렬 된 경우 *자연스럽 게 맞춰진* 데이텀을 호출 합니다. 그렇지 않으면 *잘못 정렬* 됩니다. 예를 들어 8 바이트의 부동 소수점 좌표는이를 식별 하는 데 사용 되는 주소에 8 바이트 맞춤이 있는 경우 자연스럽 게 맞춰집니다.

## <a name="compiler-handling-of-data-alignment"></a>데이터 정렬의 컴파일러 처리

컴파일러는 데이터의 맞춤을 방지 하는 방식으로 데이터를 할당 하려고 합니다.

단순 데이터 형식의 경우 컴파일러에서 데이터 형식 크기(바이트)의 배수인 주소를 할당합니다. 예를 들어, 컴파일러는 4의 배수가 되는 `long` 형식의 변수에 주소를 할당 하 고 주소의 하위 2 비트를 0으로 설정 합니다.

또한 컴파일러는 구조체의 각 요소를 자연스럽 게 맞추는 방식으로 구조를 채웁니다. 다음 코드 예제에서 `struct x_` 구조를 살펴보겠습니다.

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} bar[3];
```

컴파일러는 자연스럽게 맞춰지도록 이 구조를 채웁니다.

다음 코드 예제에서는 컴파일러가 채워진 구조를 메모리에 배치 하는 방법을 보여 줍니다.

```cpp
// Shows the actual memory layout
struct x_
{
   char a;            // 1 byte
   char _pad0[3];     // padding to put 'b' on 4-byte boundary
   int b;            // 4 bytes
   short c;          // 2 bytes
   char d;           // 1 byte
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4
} bar[3];
```

두 선언 모두 12 바이트로 `sizeof(struct x_)`을 반환 합니다.

두 번째 선언에는 다음 두 개의 패딩 요소가 포함되어 있습니다.

1. 4 바이트 경계에서 `int b` 멤버를 정렬 하려면 `char _pad0[3]` 합니다.

1. 구조체의 배열 요소 `struct _x bar[3];` 4 바이트 경계에 맞추려면 `char _pad1[1]` 합니다.

안쪽 여백은 자연 액세스를 허용 하는 방식으로 `bar[3]`의 요소를 정렬 합니다.

다음 코드 예제에서는 `bar[3]` 배열 레이아웃을 보여 줍니다.

```Output
adr offset   element
------   -------
0x0000   char a;         // bar[0]
0x0001   char pad0[3];
0x0004   int b;
0x0008   short c;
0x000a   char d;
0x000b   char _pad1[1];

0x000c   char a;         // bar[1]
0x000d   char _pad0[3];
0x0010   int b;
0x0014   short c;
0x0016   char d;
0x0017   char _pad1[1];

0x0018   char a;         // bar[2]
0x0019   char _pad0[3];
0x001c   int b;
0x0020   short c;
0x0022   char d;
0x0023   char _pad1[1];
```

## <a name="alignof-and-alignas"></a>alignof 및 alignas

**Alignas** 형식 지정자는 변수와 사용자 정의 형식 C++ 에 대 한 사용자 지정 맞춤을 지정 하는 이식 가능한 표준 방법입니다. **Alignof** 연산자는 지정 된 형식이 나 변수의 맞춤을 가져오는 표준 이식 가능한 방법입니다.

## <a name="example"></a>예제

클래스, 구조체 또는 공용 구조체 또는 개별 멤버에 대해 **alignas** 를 사용할 수 있습니다. 여러 **alignas** 지정 자가 발견 되 면 컴파일러는 가장 엄격한 one (가장 큰 값이 있는 항목)을 선택 합니다.

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>참고 항목

[데이터 구조 맞춤](https://en.wikipedia.org/wiki/Data_structure_alignment)
