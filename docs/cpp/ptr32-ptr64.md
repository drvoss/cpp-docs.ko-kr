---
title: __ptr32, __ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: c3ebe642284c6ee269dbfc39985630b7d949435f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179213"
---
# <a name="__ptr32-__ptr64"></a>__ptr32, __ptr64

**Microsoft 전용**

**__ptr32** 는 32 비트 시스템의 네이티브 포인터를 나타내며 **__ptr64** 는 64 비트 시스템의 네이티브 포인터를 나타냅니다.

다음 예제에서는 이러한 포인터 형식 각각을 선언하는 방법을 보여 줍니다.

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32 비트 시스템에서 **__ptr64** 로 선언 된 포인터는 32 비트 포인터로 잘립니다. 64 비트 시스템에서 **__ptr32** 로 선언 된 포인터는 64 비트 포인터로 강제 변환 됩니다.

> [!NOTE]
> **/Clr: pure**를 사용 하 여 컴파일하는 경우 **__ptr32** 또는 **__ptr64** 를 사용할 수 없습니다. 사용시 C2472 컴파일러 오류가 발생합니다. **/Clr: pure** 및 **/clr: safe** 컴파일러 옵션은 visual studio 2015에서 더 이상 사용 되지 않으며 visual studio 2017에서는 지원 되지 않습니다.

이전 버전과의 호환성을 위해 **_ptr32** 및 **_ptr64** 는 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 이 지정 된 경우를 제외 하 고 **__ptr32** 및 **__ptr64** 의 동의어입니다.

## <a name="example"></a>예제

다음 예제에서는 **__ptr32** 및 **__ptr64** 키워드를 사용 하 여 포인터를 선언 하 고 할당 하는 방법을 보여 줍니다.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[기본 제공 형식](../cpp/fundamental-types-cpp.md)
