---
title: MSVC 실험 전처리기 개요
description: MSVC 전처리기는 C/C++ 표준을 준수하도록 업데이트됩니다.
ms.date: 02/09/2020
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 00c34ef75270e505d3781cf7eedf4d8aba95ee6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337478"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC 실험 전처리기 개요

::: moniker range="vs-2015"

Visual Studio 2015는 표준 C++를 준수하지 않는 기존 전처리업체를 사용합니다. 실험전형 프로세서는 [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) 컴파일러 스위치를 사용하여 Visual Studio 2017 및 Visual Studio 2019에서 사용할 수 있습니다. Visual Studio 2017 및 Visual Studio 2019의 새로운 전처리기 사용에 대한 자세한 내용을 확인할 수 있습니다. 선호하는 버전의 Visual Studio에 대한 설명서를 보려면 **버전** 선택기 컨트롤을 사용합니다. 이 페이지의 목조 테이블 맨 위에 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

Microsoft C++ 전처리기를 업데이트하여 표준 준수를 개선하고, 오랜 버그를 수정하고, 공식적으로 정의되지 않은 일부 동작을 변경합니다. 또한 매크로 정의의 오류에 대해 경고하는 새로운 진단 유틸리티도 추가되었습니다.

이러한 변경 내용은 Visual Studio 2017 또는 Visual Studio 2019에서 [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) 컴파일러 스위치를 사용하여 사용할 수 있습니다. 기본 전처리기 동작은 이전 버전과 동일하게 유지됩니다.

Visual Studio 2019 버전 16.5부터 C++20 표준에 대한 실험적인 전처리기 지원이 기능 완료되었습니다.

## <a name="new-predefined-macro"></a>미리 정의된 새 매크로

컴파일 타임에 사용 중인 전처리업체를 검색할 수 있습니다. 미리 정의된 [ \_매크로\_MSVC TRADITIONAL의](predefined-macros.md) 값을 확인하여 기존 전처리업체가 사용 중인지 확인합니다. 이 매크로는 사전 처리자가 호출되는 컴파일러와 는 별개로 이를 지원하는 컴파일러 버전에 의해 무조건 설정됩니다. 해당 값은 기존 전처리기의 경우 1입니다. 준수 전처리기의 경우 0입니다.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>실험 전처리기의 동작 변경

실험 전처리기의 초기 작업은 모든 매크로 확장이 표준을 준수하도록 하는 데 중점을 두어 왔습니다. 기존 동작에 의해 현재 차단된 라이브러리와 함께 MSVC 컴파일러를 사용할 수 있습니다. 실제 프로젝트에서 업데이트된 전처리기 테스트를 거쳤습니다. 다음은 우리가 찾은 몇 가지 일반적인 주요 변경 사항입니다.

### <a name="macro-comments"></a>매크로 댓글

기존 전처리기는 프로세서 전토큰이 아닌 문자 버퍼를 기반으로 합니다. 다음 전처리기 주석 트릭과 같은 비정상적인 동작을 허용하며, 이는 준수 전처리기에서 작동하지 않습니다.

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

표준을 준수하는 수정 프로그램은 적절한 `int myVal` `#ifdef/#endif` 지침 내에서 선언하는 것입니다.

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L#val

기존 전처리기는 문자열 지정 [연산자(#)](stringizing-operator-hash.md) 연산자의 결과에 문자열 접두사를 잘못 결합합니다.

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

이 경우 인접한 `L` 문자열 리터럴이 매크로 확장 후 결합되므로 접두사는 필요하지 않습니다. 이전 버전과 호환되는 수정 프로그램은 정의를 변경하는 것입니다.

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

동일한 문제는 인수를 넓은 문자열 리터럴로 "문자열화"하는 편리한 매크로에서도 발견됩니다.

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

다양한 방법으로 문제를 해결할 수 있습니다.

- 문자열 연결 `L""` 및 `#str` 접두사를 추가합니다. 인접한 문자열 리터럴은 매크로 확장 후에 결합됩니다.

   ```cpp
   #define STRING1(str) L""#str
   ```

- 추가 매크로 확장으로 문자열화 된 후 `#str` 접두사 추가

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- 연결 연산자에서 `##` 토큰을 결합합니다. `##` 모든 `#` 컴파일러가 이 경우 이전에 `#` `##` 연산자를 평가하는 것처럼 보이지만 작업 순서는 지정되지 않습니다.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>유효하지 않은 경고\#\#

토큰 [붙여넣기 연산자(##)가](token-pasting-operator-hash-hash.md) 유효한 단일 전처리 토큰을 생성하지 않으면 동작이 정의되지 않습니다. 기존의 전처리기는 자동으로 토큰을 결합하지 못합니다. 새 전처리기는 대부분의 다른 컴파일러의 동작과 일치하고 진단을 내보릅니다.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>다양한 매크로의 쉼표 엘리션

기존의 MSVC 전처리기는 빈 `__VA_ARGS__` 교체 전에 쉼표를 항상 제거합니다. 실험 전처리기는 다른 인기 있는 플랫폼 간 컴파일러의 동작을 보다 밀접하게 따릅니다. 쉼표를 제거하려면 variadic 인수가 없어야 하며(비어 있는 것뿐만 아니라) `##` 연산자로 표시해야 합니다. 다음과 같은 예제를 참조하세요.

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the
    // following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the
    // following macro with: func(1, ), which
    // results in a syntax error.
    FUNC(1, );
}
```

다음 예제에서는 variadic `FUNC2(1)` 인수 호출에서 호출되는 매크로에 없습니다. variadic `FUNC2(1, )` 인수에 대한 호출에서 비어 있지만 누락되지 않았습니다 (인수 목록에서 쉼표를 알 수 있음).

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
   // Expands to func(1)
   FUNC2(1);

   // Expands to func(1, )
   FUNC2(1, );
}
```

다가오는 C ++20 표준에서 이 문제는 을 `__VA_OPT__`추가하여 해결되었습니다. 실험적인 전처리기 `__VA_OPT__` 지원은 Visual Studio 2019 버전 16.5부터 사용할 수 있습니다.

### <a name="c20-variadic-macro-extension"></a>C++20 다양한 매크로 확장

실험 전처리기는 C++20 의 다양한 매크로 인수 엘리션을 지원합니다.

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

이 코드는 C++20 표준 보다 앞에 적합하지 않습니다. MSVC에서 실험 전처리기는 이 C++20 동작을 낮은**`/std:c++14`** 언어 **`/std:c++17`** 표준 모드(, )로 확장합니다. 이 확장은 다른 주요 플랫폼 간 C++ 컴파일러의 동작과 일치합니다.

### <a name="macro-arguments-are-unpacked"></a>매크로 인수는 "압축 해제"

기존 전처리기에서 매크로가 인수 중 하나를 다른 종속 매크로로 전달하면 인수가 삽입될 때 "압축 해제"되지 않습니다. 일반적으로 이 최적화는 눈에 띄지 않지만 비정상적인 동작으로 이어질 수 있습니다.

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conforming preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

확장할 `A()`때 기존 전처리기는 TWO_STRINGS 첫 번째 `__VA_ARGS__` 인수로 패키지된 모든 인수를 전달하여 `TWO_STRINGS` 빈 변수 인수를 남깁니다. 이렇게 하면 결과가 `#first` "1"이 아니라 "1, 2"가 됩니다. 당신이 밀접하게 따라하는 경우, 당신은 기존의 전처리기 확장의 `#__VA_ARGS__` 결과에 무슨 일이 있었는지 궁금 할 수 있습니다 : variadic `""`매개 변수가 비어있는 경우 빈 문자열 리터럴이 발생해야합니다 . 별도의 문제로 인해 빈 문자열 리터럴 토큰이 생성되지 않도록 했습니다.

### <a name="rescanning-replacement-list-for-macros"></a>매크로에 대한 대체 목록 다시 검색

매크로를 대체한 후 결과 토큰을 다시 스캔하여 대체할 추가 매크로 식별자를 가져옵니다. 실제 코드를 기반으로 하는 이 예제에서 와 같이 기존 전처리기에서 재검사를 수행하는 데 사용되는 알고리즘이 일치하지 않습니다.

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))
DO_THING(1, "World");

// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conforming preprocessor:
// IMPL1 ( "Hello","World");
```

이 예제는 약간 모순된 것처럼 보일 수 있지만 실제 코드에서 보았습니다. 진행 중 이 와 같은 확장을 확인하려면 다음을 시작으로 확장팩을 세분화할 `DO_THING`수 있습니다.

1. `DO_THING(1, "World")`로 확장됩니다.`CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)``IMPL ## 1`로 확장됩니다.`IMPL1`
1. 이제 토큰이 이 상태에 있습니다.`IMPL1 ECHO(("Hello", "World"))`
1. 전처리기는 함수와 같은 매크로 `IMPL1`식별자를 찾습니다. 다음에 는 `(`기능과 같은 매크로 호출로 간주되지 않습니다.
1. 전처리기는 다음 토큰으로 이동합니다. 함수와 같은 매크로가 `ECHO` 호출되는 `ECHO(("Hello", "World"))`것을 찾습니다.`("Hello", "World")`
1. `IMPL1`확장에 대해 다시 고려되지 않으므로 확장의 전체 결과는 다음과 됩니다.`IMPL1("Hello", "World");`

실험 전처리기와 기존 전처리기 모두에서 동일한 방식으로 작업하도록 매크로를 수정하려면 다른 간접 레이어를 추가합니다.

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))
DO_THING_FIXED(1, "World");

// macro expands to:
// do_thing_one( "Hello", "World");
```

## <a name="incomplete-features"></a>불완전한 기능

Visual Studio 2019 버전 16.5부터 는 C++20에 대한 실험전처리기의 기능이 완성되었습니다. 이전 버전의 Visual Studio에서는 일부 전처리기 지시문 논리가 여전히 기존 동작으로 돌아가지만 실험 전처리기는 대부분 완료되었습니다. 다음은 16.5 이전 Visual Studio 버전의 불완전한 기능의 일부 목록입니다.

- `_Pragma`에 대한 지원
- C ++ 20 기능
- 부스트 차단 버그: 버전 16.5 이전의 새 전처리기에서 프로세서 상수 식의 논리 연산자가 완전히 구현되지 않았습니다. 일부 `#if` 지시문에서는 새 전처리기는 기존 전처리기로 대체될 수 있습니다. 이 효과는 기존 전처리기와 호환되지 않는 매크로가 확장될 때만 두드러지며 이 효과는 두드러지않습니다. 부스트 전처리기 슬롯을 구축할 때 발생할 수 있습니다.

::: moniker-end
