---
title: extern(C++)
description: C++ Language extern 키워드에 대 한 지침입니다.
ms.date: 01/28/2020
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
no-loc:
- extern
- const
- constexpr
- permissive
ms.openlocfilehash: 422b6960802c59f1c45e0c22a4a85988c808a5b3
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821768"
---
# <a name="opno-locextern-c"></a>extern(C++)

**extern** 키워드는 전역 변수, 함수 또는 템플릿 선언에 적용할 수 있습니다. 기호가 *외부 링크*를 포함 하도록 지정 합니다. 링크 및 전역 변수 사용이 권장 되지 않는 이유에 대 한 배경 정보는 [변환 단위 및 링크](program-and-linkage-cpp.md)를 참조 하세요.

**extern** 키워드는 컨텍스트에 따라 네 가지 의미를 갖습니다.

- **const** 되지 않은 전역 변수 선언에서 **extern** 는 변수나 함수가 다른 변환 단위에 정의 되도록 지정 합니다. 변수가 정의 된 파일을 제외 하 고 모든 파일에 **extern** 를 적용 해야 합니다.

- **const** 변수 선언에서 변수는 외부 링크를 포함 하도록 지정 합니다. 모든 파일의 모든 선언에 **extern** 를 적용 해야 합니다. 전역 **const** 변수에는 기본적으로 내부 링크가 있습니다.

- **"C"extern** 함수가 다른 곳에서 정의 되 고 C 언어 호출 규칙을 사용 하도록 지정 합니다. extern "C" 한정자는 블록의 여러 함수 선언에 적용 될 수도 있습니다.

- 템플릿 선언에서 **extern** 템플릿이 다른 곳에서 이미 인스턴스화되어 있음을 지정 합니다. **extern** 는 현재 위치에서 새 인스턴스를 만들지 않고 다른 인스턴스화를 다시 사용할 수 있도록 컴파일러에 지시 합니다. 이러한 **extern** 사용에 대 한 자세한 내용은 [명시적 인스턴스화](explicit-instantiation.md)를 참조 하세요.

## <a name="opno-locextern-linkage-for-non-opno-locconst-globals"></a>const 되지 않은 globals의 extern 링크

링커는 전역 변수 선언 앞에 **extern** 를 볼 때 다른 변환 단위에서 정의를 찾습니다. 전역 범위에서 비 **const** 변수의 선언은 기본적으로 외부입니다. 정의를 제공 하지 않는 선언에만 **extern** 을 적용 합니다.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="opno-locextern-linkage-for-opno-locconst-globals"></a>const globals에 대 한 extern 링크

**const** 전역 변수에는 기본적으로 내부 링크가 있습니다. 변수에 외부 링크를 포함 하려면 **extern** 키워드를 정의에, 다른 파일의 다른 모든 선언에 적용 합니다.

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="opno-locextern-opno-locconstexpr-linkage"></a>링크 constexpr extern

Visual Studio 2017 버전 15.3 이전 버전에서는 변수가 **extern** 으로 표시 된 경우에도 컴파일러에서 항상 **constexpr** 변수 내부 링크를 제공 합니다. Visual Studio 2017 버전 15.5 이상에서 [/zc: externConstexpr](../build/reference/zc-externconstexpr.md) 컴파일러 스위치는 올바른 표준 준수 동작을 사용 하도록 설정 합니다. 결국 옵션이 기본값이 됩니다. [/permissive-](../build/reference/permissive-standards-conformance.md) 옵션은 **/zc: externConstexpr**를 사용 하지 않습니다.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

헤더 파일에 **constexpr** **extern** 선언 된 변수가 포함 된 경우 중복 선언이 결합 되도록 `__declspec(selectany)`으로 표시 되어야 합니다.

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="opno-locextern-c-and-opno-locextern-c-function-declarations"></a>"C" extern "C++" 함수 선언 extern

에서 C++문자열과 함께 사용 하는 경우 **extern** 는 다른 언어의 링크 규칙을 선언 자에 사용 하도록 지정 합니다. C 함수 및 데이터는 이전에 C 링크를 포함 하는 것으로 선언 된 경우에만 액세스할 수 있습니다. 단, 별도로 컴파일된 변환 단위로 정의되어야 합니다.

Microsoft C++ 는 *문자열 리터럴* 필드에 **"C"** 및 **C++""** 문자열을 지원 합니다. 모든 표준 포함 파일은 **extern "C"** 구문을 사용 하 여 프로그램에서 C++ 런타임 라이브러리 함수를 사용할 수 있도록 합니다.

## <a name="example"></a>예

다음 예제에서는 C 링크가 있는 이름을 선언 하는 방법을 보여 줍니다.

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

함수에 둘 이상의 링크 사양이 있는 경우 동의 해야 합니다. C와 C++ 링크를 모두 포함 하는 함수를 선언 하는 것은 오류입니다. 뿐만 아니라 함수에 대한 두 선언(링크 사양이 있는 선언과 없는 선언)이 프로그램에서 발생할 경우 링크 사양이 있는 선언이 첫 번째여야 합니다. 이미 링크 사양이 있는 함수의 모든 중복 선언에는 첫 번째 선언에서 지정된 링크가 제공됩니다. 예를 들면 다음과 같습니다.:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>참조

[키워드](../cpp/keywords-cpp.md)\
[변환 단위 및 링크](program-and-linkage-cpp.md)\
[C\의extern 저장소 클래스 지정자](../c-language/extern-storage-class-specifier.md)
[C\의 식별자 동작](../c-language/behavior-of-identifiers.md)
[C의 링크](../c-language/linkage.md)
