---
title: /permissive-(표준 준수)
description: Microsoft C++ /허용-(표준 준수) 컴파일러 옵션에 대한 참조 가이드입니다.
ms.date: 04/14/2020
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 695f84e64f07128ac7744dc99e736f2a71ab3e79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337410"
---
# <a name="permissive--standards-conformance"></a>/permissive-(표준 준수)

컴파일러에 표준 준수 모드를 지정합니다. 이 옵션을 사용하면 코드에서 적합성 문제를 식별하고 수정하여 보다 정확하고 이식성이 뛰어난 문제를 식별할 수 있습니다.

## <a name="syntax"></a>구문

> **/허용-**

## <a name="remarks"></a>설명

이 옵션은 Visual Studio 2017 이상에서 지원됩니다.

**/허용 컴파일러** 옵션을 사용하여 표준 준수 컴파일러 동작을 지정할 수 있습니다. 이 옵션은 허용 동작을 사용하지 않도록 설정하고 엄격한 준수를 위해 [/Zc](zc-conformance.md) 컴파일러 옵션을 설정합니다. IDE에서 이 옵션은 IntelliSense 엔진이 부적합 코드에 밑줄을 긋게 합니다.

기본적으로 **/허용-** 옵션은 Visual Studio 2017 버전 15.5 및 이후 버전에서 만든 새 프로젝트에서 설정됩니다. 이전 버전에서는 기본적으로 설정되지 않았습니다. 옵션이 설정되면 컴파일러는 C++11 이전 코드의 몇 가지 일반적인 버그를 포함하여 비표준 언어 구문이 코드에서 검색될 때 진단 오류 또는 경고를 생성합니다.

**/허용-** 옵션은 Windows 가을 크리에이터 SDK(10.0.16299.0)에서 시작하는 소프트웨어 개발 키트(SDK) 또는 Windows 드라이버 키트(WDK)와 같은 최신 Windows 키트의 거의 모든 헤더 파일과 호환됩니다. 이전 버전의 SDK는 다양한 소스 코드 준수 이유로 **/permissive-에서** 컴파일하지 못할 수 있습니다. 컴파일러와 SDK는 서로 다른 릴리스 일정에 따라 제공되므로 몇 가지 문제가 남아 있습니다. 특정 헤더 파일 문제에 대 한, 아래 [의 Windows 헤더 문제를](#windows-header-issues) 참조 하십시오.

**/허용-옵션은** [/Zc:referenceBinding](zc-referencebinding-enforce-reference-binding-rules.md), [/Zc:strictStrings](zc-strictstrings-disable-string-literal-type-conversion.md)및 [/Zc:rvalueCast](zc-rvaluecast-enforce-type-conversion-rules.md) 옵션을 따라 동작에 맞게 설정합니다. 이러한 옵션은 기본적으로 비준수 동작으로 설정됩니다. 이 동작을 재정의하기 위해 명령줄에 **/permissive-** 후에 특정 **/Zc** 옵션을 전달할 수 있습니다.

Visual Studio 2017 버전 15.3에서 시작하는 컴파일러 버전에서 **/허용-옵션은** [/Zc:ternary](zc-ternary.md) 옵션을 설정합니다. 또한 컴파일러는 2단계 이름 조회에 대한 더 많은 요구 사항을 구현합니다. **/허용-** 옵션이 설정되면 컴파일러는 함수 및 클래스 템플릿 정의를 구문 분석하고 템플릿에 사용되는 종속 및 비종속 이름을 식별합니다. 이 릴리스에서는 이름 종속성 분석만 수행됩니다.

표준이 구현에 남기는 환경별 확장 및 언어 영역은 **/허용-의**영향을 받지 않습니다. 예를 들어 Microsoft 특정 `__declspec`호출 규칙 및 구조화 된 예외 처리 키워드 및 컴파일러 별 pragma 지시문 또는 **특성은 /permissive-mode에서** 컴파일러에 의해 플래그가 지정 되지 않습니다.

**/허용-** 옵션은 현재 컴파일러 버전의 적합성 지원을 사용하여 비준수언어 구문이 결정됩니다. 이 옵션은 코드가 C++ 표준의 특정 버전을 준수하는지 여부를 결정하지 않습니다. 최신 초안 표준에 대해 구현된 모든 컴파일러 지원을 사용하려면 [/std:latest](std-specify-language-standard-version.md) 옵션을 사용합니다. 컴파일러 지원을 현재 구현된 C++17 표준으로 제한하려면 [/std:c++17](std-specify-language-standard-version.md) 옵션을 사용합니다. 컴파일러 지원을 C++14 표준과 더 가깝게 일치하도록 제한하려면 [기본값인 /std:c++14](std-specify-language-standard-version.md) 옵션을 사용합니다.

모든 C++11, C++14 또는 C++17 표준 준수 코드가 모든 버전의 Visual Studio 2017에서 MSVC 컴파일러에서 지원되는 것은 아닙니다. Visual Studio 버전에 따라 **/permissive-option은** 2단계 이름 조회의 일부 측면과 관련된 문제를 감지하지 못하고, 비const 참조를 임시로 바인딩하고, 복사 초기화를 직접 초기화로 처리하며, 초기화에서 여러 사용자 정의 변환을 허용하거나 논리 연산자를 위한 대체 토큰 및 기타 지원되지 않는 준수 영역을 사용할 수 있습니다. Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요. **/허용-를**최대한 얻으려면 Visual Studio를 최신 버전으로 업데이트합니다.

### <a name="how-to-fix-your-code"></a>코드를 수정하는 방법

다음은 **/허용-를**사용할 때 비준수로 검색되는 코드의 몇 가지 예와 함께 문제를 해결하는 제안된 방법입니다.

#### <a name="use-default-as-an-identifier-in-native-code"></a>기본값을 네이티브 코드에서 식별자로 사용

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>종속 기반에서 멤버 찾기

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>멤버 선언에 정규화된 이름 사용

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>멤버 초기화에서 여러 조합원 초기화

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>숨겨진 친구 이름 조회 규칙

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(p); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>배열 경계에 범위 열거형 사용

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>네이티브 코드의 각 코드에 사용

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>ATL 속성 사용

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be
// used to automatically obtain a *.idl file for the interfaces with
// annotation. Second, add a midl step to your build system to make
// sure that the C++ interface definitions are outputted.
// Last, adjust your existing code to use ATL directly as shown in
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>모호한 조건부 연산자 인수

Visual Studio 2017 버전 15.3 이전의 컴파일러 버전에서 컴파일러는 표준에 의해 모호한 것으로 간주되는 `?:` 조건부 연산자(또는 삼차 연산자)에 대한 인수를 수락했습니다. **/허용 모드에서** 컴파일러는 이전 버전에서 진단 없이 컴파일된 경우 하나 이상의 진단을 발행합니다.

이 변경으로 인해 발생할 수 있는 일반적인 오류는 다음과 같습니다.

- 오류 C2593: '연산자?' 모호하다

- 오류 C2679: 바이너리 '?': 형식 'B'의 오른쪽 사용후연을 취하는 연산자가 없습니다 (또는 허용 가능한 변환이 없음)

- 오류 C2678: 바이너리 '?': 'A' 유형의 왼쪽 된 사용 심연을 사용 하는 연산자 (또는 허용 가능한 변환없음)

- 오류 C2446: ':': 'B'에서 'A'로 변환없음

이 문제를 일으킬 수 있는 일반적인 코드 패턴은 일부 클래스 C가 다른 형식 T의 비명시적 생성자와 T 형식에 대한 비명시적 변환 연산자 모두를 제공하는 경우입니다. 이 경우 두 번째 인수를 세 번째 인수의 유형으로 변환하고 세 번째 인수를 두 번째 인수의 유형으로 변환하는 것은 모두 유효한 변환입니다. 둘 다 유효하기 때문에 표준에 따라 모호합니다.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

T가 null-terminated 문자열 형식 중 하나를 나타내고 실제 `const char *` `const char16_t *`인수가 해당 형식의 문자열 `?:` 리터럴인 경우 이 일반적인 패턴에 중요한 예외가 있습니다. C++17이 의미체계를 C++14에서 변경했습니다. 결과적으로 예제 2의 코드는 **/std:c++14에서** 허용되고 **/zc:3.3ary** 또는 **/허용-가** 사용될 때 **/std:c++17에서** 거부됩니다.

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s;
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

오류가 발생할 수 있는 또 다른 경우는 형식의 `void`한 인수가 있는 조건부 연산자입니다. 이 경우 ASSERT와 같은 매크로에서 일반적일 수 있습니다.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

또한 조건부 연산자 결과 형식이 **/Zc:ternary** 및 **/허용-** 아래에서 변경될 수 있는 템플릿 메타프로그래밍에서 오류가 표시될 수 있습니다. 이 문제를 해결하는 한 가지 방법은 결과 형식에서 [std:remove_reference](../../standard-library/remove-reference-class.md) 사용하는 것입니다.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>2단계 이름 조회

**/permissive-** 옵션이 설정되면 컴파일러는 함수 및 클래스 템플릿 정의를 구문 분석하여 2단계 이름 조회에 필요한 대로 템플릿에 사용되는 종속 및 비종속 이름을 식별합니다. Visual Studio 2017 버전 15.3에서는 이름 종속성 분석이 수행됩니다. 특히 템플릿 정의의 컨텍스트에서 선언되지 않은 비종속 이름은 ISO C++ 표준에서 요구하는 진단 메시지를 발생시게 됩니다. Visual Studio 2017 버전 15.7에서는 정의 컨텍스트에서 인수 종속 조회가 필요한 비종속 이름의 바인딩도 수행됩니다.

```cpp
// dependent base
struct B {
    void g() {}
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

2단계 조회에 대한 레거시 동작을 원하지만 **/허용-동작을** 원한다면 **/Zc:twoPhase-** 옵션을 추가합니다.

### <a name="windows-header-issues"></a>윈도우 헤더 문제

**/허용-** 옵션은 Windows 가을 크리에이터 업데이트 SDK (10.0.16299.0) 또는 Windows 드라이버 키트 (WDK) 버전 1709 전에 윈도우 키트의 버전에 대 한 너무 엄격 하다. Windows 또는 장치 드라이버 코드에서 **/허용-를** 사용하려면 최신 버전의 Windows 키트로 업데이트하는 것이 좋습니다.

Windows 2018년 4월 업데이트 SDK(10.0.17134.0), Windows 가을 크리에이터 업데이트 SDK(10.0.16299.0) 또는 Windows 드라이버 키트(WDK) 1709의 특정 헤더 파일은 **여전히 /permissive-의**사용과 호환되지 않는 문제가 있습니다. 이러한 문제를 해결하려면 이러한 헤더를 필요로 하는 소스 코드 파일로만 헤더 사용을 제한하고 특정 소스 코드 파일을 컴파일할 때 **/permissive-** 옵션을 제거하는 것이 좋습니다.

Windows 2018년 4월 업데이트 SDK(10.0.17134.0)에서 릴리스된 이러한 WinRT WRL 헤더는 **/permissive-로**정리되지 않습니다. 이러한 문제를 해결하려면 **/허용-를**사용하지 않거나 **/Zc:twoPhase-를** 사용하여 다음 헤더를 사용하지 마십시오. **/permissive-**

- 윈트/wrl/async.h의 문제

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- winrt/wrl/implements에서 문제 발생합니다.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Windows 2018년 4월 업데이트 SDK(10.0.17134.0)에서 릴리스된 이러한 사용자 모드 헤더는 **/허용-로**정리되지 않습니다. 이러한 문제를 해결하려면 이러한 헤더로 작업할 때 **/허용-를** 사용하지 마십시오.

- 음/Tune.h의 문제

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- um/spddkhlp.h의 문제

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- 움/refptrco.h의 문제

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

이러한 문제는 Windows 가을 크리에이터 업데이트 SDK(10.0.16299.0)의 사용자 모드 헤더에만 해당됩니다.

- um/Query.h에서 의 문제

   **/허용 컴파일러** 스위치를 사용하는 경우 `tagRESTRICTION` 대/소문자(RTOr) 멤버 'or'로 인해 구조가 컴파일되지 않습니다.

   ```cpp
   struct tagRESTRICTION
   {
       ULONG rt;
       ULONG weight;
       /* [switch_is][switch_type] */ union _URes
       {
           /* [case()] */ NODERESTRICTION ar;
           /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
           /* [case()] */ NODERESTRICTION pxr;
           /* [case()] */ VECTORRESTRICTION vr;
           /* [case()] */ NOTRESTRICTION nr;
           /* [case()] */ CONTENTRESTRICTION cr;
           /* [case()] */ NATLANGUAGERESTRICTION nlr;
           /* [case()] */ PROPERTYRESTRICTION pr;
           /* [default] */  /* Empty union arm */
       } res;
   };
   ```

   이 문제를 해결하려면 **/허용 옵션** 없이 Query.h를 포함하는 파일을 컴파일합니다.

- um/cellularapi_oem.h에서 발행

   **/허용 컴파일러** 스위치를 사용하는 경우 정방향 `enum UICCDATASTOREACCESSMODE` 선언은 경고를 일으킵니다.

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   범위가 변경되지 않은 열거형의 전달 선언은 Microsoft 확장입니다. 이 문제를 해결하려면 **/허용 옵션** 없이 cellularapi_oem.h를 포함하는 파일을 컴파일하거나 [/wd](compiler-option-warning-level.md) 옵션을 사용하여 C4471을 무음으로 설정합니다.

- um/omscript.h에서 발행

   C++03에서는 문자열 리터럴에서 BSTR(형식 def에서 'wchar_t*'로 변환)은 더 이상 사용되지 않지만 허용됩니다. C++11에서는 변환이 더 이상 허용되지 않습니다.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   이 문제를 해결하려면 **/허용 옵션없이** omscript.h를 포함하는 파일을 컴파일하거나 **/Zc:strictStrings-를** 대신 사용합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

Visual Studio 2017 버전 15.5 이상 버전에서는 다음 절차를 사용합니다.

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다.

1. 구성 **속성** > **C/C++** > **언어** 속성 페이지를 선택합니다.

1. 적합성 **모드** 속성 값을 **예(/허용-)로**변경합니다. **확인을** 선택하거나 **적용을** 선택하여 변경 내용을 저장합니다.

Visual Studio 2017 버전 15.5 이전 버전에서는 다음 절차를 사용합니다.

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다.

1. 구성 **속성** > **C/C++** > 명령줄 속성 페이지를**선택합니다.**

1. **추가 옵션** 상자에 **/허용 컴파일러** 옵션을 입력합니다. **확인을** 선택하거나 **적용을** 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
