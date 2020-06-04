---
title: /Zc:alignedNew(C++17 과다 정렬된 할당)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: 041f62bbbf5f7a2750960d21d1534cf6daf4b874
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335694"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew(C++17 과다 정렬된 할당)

C++ 17 과다 정렬된 **새로 만들기**, 최대 크기의 표준 정렬 형식인 **max\_align\_t**에 대한 기본값보다 큰 경계에 정렬된 동적 메모리 할당에 대한 지원을 사용하도록 설정합니다.

## <a name="syntax"></a>구문

> **/Zc:정렬새**\[-]

## <a name="remarks"></a>설명

MSVC 컴파일러 및 라이브러리는 C++ 17 표준 과다 정렬된 동적 메모리 할당을 지원합니다. **/Zc:alignedNew** 옵션을 지정하면 기본 형식에 `new Example;` 필요한 가장 큰 정렬보다 `max_align_t`큰 경우에도 *예제의* 정렬을 준수하는 동적 할당이 지정됩니다. 할당된 형식의 정렬이 원래 연산자가 보장하는 정렬보다 **new**더 이상 없는 경우, 미리 정의된 ** \_ \_매크로\_\_STDCPP\_DEFAULT NEW ALIGNMENT의\_** 값으로 사용할 수 있으며, 문은 `new Example;` C++14에서와 `::operator new(size_t)` 마찬가지로 호출을 초래합니다. 정렬이 ** \_ \_STDCPP\_기본 새\_\_정렬보다\_** 크면 구현대신 을 `::operator new(size_t, align_val_t)`사용하여 메모리를 가져옵니다. 마찬가지로, 과다 정렬된 형식을 삭제하면 `::operator delete(void*, align_val_t)` 또는 크기가 지정된 삭제 서명 `::operator delete(void*, size_t, align_val_t)`가 호출됩니다.

**/Zc:alignedNew** 옵션은 [/std:c++17](std-specify-language-standard-version.md) 또는 [/std:c++latest](std-specify-language-standard-version.md)가 활성화된 경우에만 사용할 수 있습니다. **/std:c++17** 또는 **/std:c++latest**에서 **/Zc:alignedNew**는 기본적으로 ISO C++17 표준을 준수하도록 활성화되어 있습니다. 연산자 **새로 만들기** 및 **삭제**를 구현하는 유일한 이유가 과다 정렬된 할당을 지원하기 위한 것이라면 C++17 모드에서 이 코드가 더 이상 필요하지 않을 수 있습니다. **/std::c++17** 또는 **/std:c++latest**를 사용할 때 이 옵션을 해제하고 **새로 만들기** 및 **삭제**의 C++14 동작으로 되돌리려면 **/Zc:alignedNew-** 를 지정합니다. 연산자 **새로 만들기** 및 **삭제**를 구현했지만 `align_val_t` 매개 변수를 가진 과다 정렬된 연산자 **새로 만들기** 및 **삭제** 오버로드를 구현할 준비가 되지 않은 경우, **/Zc:alignedNew-** 옵션을 사용하여 컴파일러 및 표준 라이브러리에서 과다 정렬된 오버로드에 대한 호출을 생성하지 못하도록 합니다. [/permissive-](permissive-standards-conformance.md) 옵션은 **/Zc:alignedNew**의 기본 설정을 변경하지 않습니다.

**/Zc:alignedNew**에 대한 지원은 Visual Studio 2017 버전 15.5부터 제공됩니다.

## <a name="example"></a>예제

이 샘플은 **/Zc:alignedNew** 옵션이 설정된 경우 연산자 **새로 만들기** 및 연산자 **삭제** 동작 방식을 보여줍니다.

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

이 출력은 32비트 빌드에서 일반적입니다. 포인터 값은 애플리케이션이 메모리에서 실행되는 위치에 따라 다릅니다.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Visual C++의 규칙과 관련된 문제에 대한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)를 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **C/C++** > 명령줄 속성 페이지를**선택합니다.**

1. **/Zc:alignedNew** 또는 **/Zc:alignedNew-** 를 포함하도록 **추가 옵션** 속성을 수정한 다음, **확인**을 선택합니다.

## <a name="see-also"></a>참고 항목

[/Zc(적합도)](zc-conformance.md)
