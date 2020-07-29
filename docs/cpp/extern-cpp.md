---
title: :::no-loc(extern):::(C++)
description: 'C + + 언어 키워드에 대 한 지침 :::no-loc(extern)::: 입니다.'
ms.date: 01/28/2020
f1_keywords:
- ':::no-loc(extern):::'
- :::no-loc(extern):::_CPP
helpviewer_keywords:
- ':::no-loc(extern)::: keyword [C++], linkage to non-C++ functions'
- declarations, :::no-loc(extern):::al
- ':::no-loc(extern):::al linkage, :::no-loc(extern)::: modifier'
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- ':::no-loc(extern):::'
- ':::no-loc(const):::'
- ':::no-loc(constexpr):::'
- ':::no-loc(permissive):::'
ms.openlocfilehash: 510352f9e99e513f4a426f6ef89be4474085d97c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227506"
---
# <a name="no-locextern-c"></a>:::no-loc(extern):::(C++)

**`:::no-loc(extern):::`** 키워드는 전역 변수, 함수 또는 템플릿 선언에 적용할 수 있습니다. 기호가 * :::no-loc(extern)::: al 링크*를 포함 하도록 지정 합니다. 링크 및 전역 변수 사용이 권장 되지 않는 이유에 대 한 배경 정보는 [변환 단위 및 링크](program-and-linkage-cpp.md)를 참조 하세요.

**`:::no-loc(extern):::`** 키워드는 컨텍스트에 따라 네 가지 의미를 갖습니다.

- **`:::no-loc(const):::`** 비전역 변수 선언에서 **`:::no-loc(extern):::`** 변수나 함수를 다른 변환 단위에 정의 하도록 지정 합니다. 는 **`:::no-loc(extern):::`** 변수가 정의 된 파일을 제외한 모든 파일에 적용 되어야 합니다.

- **`:::no-loc(const):::`** 변수 선언에서 변수는 al 링크를 포함 하도록 지정 합니다 :::no-loc(extern)::: . **`:::no-loc(extern):::`** 모든 파일의 모든 선언에를 적용 해야 합니다. 전역 **`:::no-loc(const):::`** 변수에는 기본적으로 내부 링크가 있습니다.

- ** :::no-loc(extern)::: "C"** 는 함수가 다른 곳에서 정의 되 고 C 언어 호출 규칙을 사용 하도록 지정 합니다. :::no-loc(extern):::"C" 한정자는 블록의 여러 함수 선언에도 적용 될 수 있습니다.

- 템플릿 선언에서 **`:::no-loc(extern):::`** 템플릿이 이미 다른 곳에서 인스턴스화되어 있음을 지정 합니다. **`:::no-loc(extern):::`** 현재 위치에서 새 인스턴스를 만들지 않고 다른 인스턴스를 다시 사용할 수 있도록 컴파일러에 지시 합니다. 이 사용에 대 한 자세한 내용은 **`:::no-loc(extern):::`** [명시적 인스턴스화](explicit-instantiation.md)를 참조 하세요.

## <a name="no-locextern-linkage-for-non-no-locconst-globals"></a>:::no-loc(extern):::비 :::no-loc(const)::: globals 링크

링커는 **`:::no-loc(extern):::`** 전역 변수 선언 앞에서 볼 때 다른 변환 단위에서 정의를 찾습니다. **`:::no-loc(const):::`** 전역 범위에서 변수가 아닌 선언에는 :::no-loc(extern)::: 기본적으로 al이 있습니다. 정의를 **`:::no-loc(extern):::`** 제공 하지 않는 선언에만 적용 됩니다.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileC.cpp
:::no-loc(extern)::: int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
:::no-loc(extern)::: int i = 43; // same error (:::no-loc(extern)::: is ignored on definitions)
```

## <a name="no-locextern-linkage-for-no-locconst-globals"></a>:::no-loc(extern):::globals 링크 :::no-loc(const):::

**`:::no-loc(const):::`** 전역 변수에는 기본적으로 내부 링크가 있습니다. 변수에 al 링크를 포함 하려면 :::no-loc(extern)::: 키워드를 정의에 **`:::no-loc(extern):::`** , 다른 파일의 다른 모든 선언에 적용 합니다.

```cpp
//fileA.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i = 42; // :::no-loc(extern)::: :::no-loc(const)::: definition

//fileB.cpp
:::no-loc(extern)::: :::no-loc(const)::: int i;  // declaration only. same as i in FileA
```

## <a name="no-locextern-no-locconstexpr-linkage"></a>:::no-loc(extern)::::::no-loc(constexpr):::링크

Visual Studio 2017 버전 15.3 이전 버전에서는 **`:::no-loc(constexpr):::`** 변수가로 표시 된 경우에도 컴파일러에서 항상 변수 내부 링크를 제공 **`:::no-loc(extern):::`** 합니다. Visual Studio 2017 버전 15.5 이상에서 [/zc: :::no-loc(extern)::: Constexpr](../build/reference/zc-:::no-loc(extern)::::::no-loc(constexpr):::.md) 컴파일러 스위치는 올바른 표준 준수 동작을 사용 하도록 설정 합니다. 결국 옵션이 기본값이 됩니다. 이 [/:::no-loc(permissive):::-](../build/reference/:::no-loc(permissive):::-standards-conformance.md) 옵션은 **/Zc: :::no-loc(extern)::: Constexpr**을 사용 하지 않습니다.

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: int x = 10; //error LNK2005: "int :::no-loc(const)::: x" already defined
```

선언 된 변수가 헤더 파일에 포함 되어 있는 경우 **`:::no-loc(extern):::`** **`:::no-loc(constexpr):::`** `__declspec(selectany)` 에는 중복 선언이 결합 되도록 올바르게 표시 되어야 합니다.

```cpp
:::no-loc(extern)::: :::no-loc(constexpr)::: __declspec(selectany) int x = 10;
```

## <a name="no-locextern-c-and-no-locextern-c-function-declarations"></a>:::no-loc(extern):::"C" 및 :::no-loc(extern)::: "c + +" 함수 선언

C + +에서 문자열과 함께 사용 되는 경우 **`:::no-loc(extern):::`** 다른 언어의 링크 규칙을 선언 자에 사용 하도록 지정 합니다. C 함수 및 데이터는 이전에 C 링크를 포함 하는 것으로 선언 된 경우에만 액세스할 수 있습니다. 단, 별도로 컴파일된 변환 단위로 정의되어야 합니다.

Microsoft c + +는 *문자열 리터럴* 필드에서 문자열 **"c"** 및 **"c + +"** 를 지원 합니다. 모든 표준 포함 파일은 ** :::no-loc(extern)::: "c"** 구문을 사용 하 여 c + + 프로그램에서 런타임 라이브러리 함수를 사용할 수 있도록 합니다.

## <a name="example"></a>예제

다음 예제에서는 C 링크가 있는 이름을 선언 하는 방법을 보여 줍니다.

```cpp
// Declare printf with C linkage.
:::no-loc(extern)::: "C" int printf(:::no-loc(const)::: char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
:::no-loc(extern)::: "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
:::no-loc(extern)::: "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
:::no-loc(extern)::: "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

:::no-loc(extern)::: "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
:::no-loc(extern)::: "C" int errno;
```

함수에 둘 이상의 링크 사양이 있는 경우 동의 해야 합니다. C 및 c + + 링크를 모두 포함 하는 함수를 선언 하는 것은 오류입니다. 뿐만 아니라 함수에 대한 두 선언(링크 사양이 있는 선언과 없는 선언)이 프로그램에서 발생할 경우 링크 사양이 있는 선언이 첫 번째여야 합니다. 이미 링크 사양이 있는 함수의 모든 중복 선언에는 첫 번째 선언에서 지정된 링크가 제공됩니다. 예를 들면 다음과 같습니다.

```cpp
:::no-loc(extern)::: "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
:::no-loc(extern)::: "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>참고 항목

[어](../cpp/keywords-cpp.md)\
[변환 단위 및 링크](program-and-linkage-cpp.md)\
[:::no-loc(extern):::C의 저장소 클래스 지정자](../c-language/:::no-loc(extern):::-storage-class-specifier.md)\
[C의 식별자 동작](../c-language/behavior-of-identifiers.md)\
[C의 링크](../c-language/linkage.md)
