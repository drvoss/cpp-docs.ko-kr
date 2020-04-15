---
title: /Zc:ternary(조건 연산자 규칙 적용)
ms.date: 09/12/2019
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: 7c95f061e195ccf7fef8a6a21d193b257baa5f39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335672"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary(조건 연산자 규칙 적용)

조건부 연산자 식에서 두 번째 및 세 번째 심연의 유형 및 const 또는 휘발성(cv) 자격에 대한 C++ 표준 규칙을 적용합니다.

## <a name="syntax"></a>구문

> **/Zc:삼차**[]**-**

## <a name="remarks"></a>설명

Visual Studio 2017에서 시작하여 컴파일러는 C++ 표준 *조건부 연산자(?:* )**동작을**지원합니다. 삼차 *연산자로도*알려져 있습니다. C++ 표준은 세 가지 조건 중 하나를 충족해야 합니다: 진파는 동일한 유형및 **const** 또는 **휘발성** 자격(cv-qualification)이어야 하며, 한 개의 출원인만 동일한 유형으로 명확하게 변환할 수 있어야 하며, 다른 조건과 동일한 유형 및 이력서 자격으로 명확하게 전환할 수 있어야 합니다. 또는 하나 또는 둘 다 의 식은 throw 식이어야 합니다. Visual Studio 2017 버전 15.5 이전 버전에서는 컴파일러가 표준에 의해 모호한 것으로 간주되는 변환을 허용했습니다.

**/Zc:3차** 옵션을 지정하면 컴파일러가 표준을 준수합니다. 일치하는 형식과 두 번째 및 세 번째 심연의 이력서 자격에 대한 규칙을 충족하지 않는 코드를 거부합니다.

**/Zc:삼차** 옵션은 Visual Studio 2017에서 기본적으로 꺼져 있습니다. **/Zc:3.3ary를** 사용하여 준수 동작을 사용하도록 설정하거나 **/Zc:ternary-를** 사용하여 이전의 비준수 컴파일러 동작을 명시적으로 지정합니다. [/허용-](permissive-standards-conformance.md) 옵션은 암시적으로 이 옵션을 활성화하지만 **/Zc:ternary-를**사용하여 재정의할 수 있습니다.

### <a name="examples"></a>예

이 샘플에서는 형식에서 명시적이지 않은 초기화를 제공하는 클래스와 형식으로변환을 모두 제공하는 클래스가 모호한 변환으로 이어질 수 있는 방법을 보여 주어집니다. 이 코드는 기본적으로 컴파일러에서 허용되지만 **/Zc:3등** 또는 **/허용-가** 지정될 때 거부됩니다.

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

이 코드를 수정하려면 기본 공통 형식에 명시적으로 캐스팅하거나 형식 변환의 한 방향을 방지합니다. 변환을 명시적으로 만들어 컴파일러가 형식 변환과 일치하지 않도록 할 수 있습니다.

이 일반적인 패턴의 중요한 예외는 진산물의 형식이 null-terminated 문자열 형식(예: `const char*` `const char16_t*`.) 및 같은 경우입니다. 배열 형식 및 감소하는 포인터 형식을 사용하여 효과를 재현할 수도 있습니다. 실제 두 번째 또는 세 번째 `?:` 나산이 해당 형식의 문자열 리터럴인 경우의 동작은 사용되는 언어 표준에 따라 달라집니다. C++17이 이 경우의 의미 체계를 C++14에서 변경했습니다. 결과적으로 컴파일러는 기본 **/std:c ++14에서**다음 예제의 코드를 수락하지만 **/std:c++17을**지정할 때 코드를 거부합니다.

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

이 코드를 수정하려면 피연산자 중 하나를 명시적으로 캐스팅합니다.

**/Zc:ternary에서**컴파일러는 인수 중 하나가 void형식이고 다른 하나는 throw **void**식이 아닌 조건부 연산자를 거부합니다. 이 패턴의 일반적인 용도는 ASSERT와 같은 매크로입니다.

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

일반적인 해결책은 void가 아닌 인수를 `void()`로 대체하는 것입니다.

이 샘플에서는 **/Zc:3.3및** **/Zc:3ary-** 모두에서 오류를 생성하는 코드를 보여 주며,

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

이 코드는 이전에 이 오류를 주었습니다.

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

**/Zc:삼자,** 실패의 원인은 명확해진다. 여러 구현 정의 호출 규칙 중 하나라도 각 람다를 생성하는 데 사용할 수 있습니다. 그러나 컴파일러에는 가능한 람다 서명을 모호하게 하는 기본 설정 규칙이 없습니다. 새 출력은 다음과 같습니다.

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

**/Zc:ternary에서** 발견되는 문제의 일반적인 원인은 템플릿 메타 프로그래밍에 사용되는 조건부 연산자에서 비롯됩니다. 일부 결과 유형은 이 스위치에서 변경됩니다. 다음 예제에서는 **/Zc:3ary가** 비 메타 프로그래밍 컨텍스트에서 조건식의 결과 형식을 변경하는 두 가지 사례를 보여 줍니다.

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

일반적인 수정 사항은 이전 `std::remove_reference` 동작을 보존하는 데 필요한 경우 결과 유형에 특성을 적용하는 것입니다.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. 구성 **속성** > **C/C++** > 명령줄 속성 페이지를**선택합니다.**

1. **/Zc:3차** 또는 **/Zc:3등** 포함하도록 **추가 옵션** 속성을 수정한 다음 **확인을**선택합니다.

## <a name="see-also"></a>참고 항목

[/Zc(적합도)](zc-conformance.md)
