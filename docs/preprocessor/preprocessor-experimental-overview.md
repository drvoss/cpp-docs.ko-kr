---
title: MSVC 실험적 전처리기 개요
description: MSVC 전처리기는 C/C++ 표준 준수를 위해 업데이트 됩니다.
ms.date: 02/09/2020
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: eb861b18a8d42c73429f6d00a3f47b35c9b198ca
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2020
ms.locfileid: "79090546"
---
# <a name="msvc-experimental-preprocessor-overview"></a>MSVC 실험적 전처리기 개요

::: moniker range="vs-2015"

Visual Studio 2015은 표준을 C++준수 하지 않는 기존의 전처리기를 사용 합니다. 실험적 전처리기는 [/o실험적: 전처리기](../build/reference/experimental-preprocessor.md) 컴파일러 스위치를 사용 하 여 visual studio 2017 및 visual studio 2019에서 사용할 수 있습니다. Visual Studio 2017 및 Visual Studio 2019에서 새로운 전처리기를 사용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다. 이를 확인 하려면 설명서 버전 선택기를 사용 하 여 해당 버전 중 하나를 선택 합니다.

::: moniker-end

::: moniker range=">=vs-2017"

표준 준수를 개선 하 C++ 고, 위해 노력해 왔으며 버그를 수정 하 고, 공식적으로 정의 되지 않은 몇 가지 동작을 변경 하기 위해 Microsoft 전처리기를 업데이트 하 고 있습니다. 매크로 정의의 오류에 대해 경고 하는 새 진단도 추가 했습니다.

이러한 변경 내용은 Visual Studio 2017 또는 Visual Studio 2019의 [/s실험적: 전처리기](../build/reference/experimental-preprocessor.md) 컴파일러 스위치를 사용 하 여 사용할 수 있습니다. 기본 전처리기 동작은 이전 버전과 동일 하 게 유지 됩니다.

Visual Studio 2019 버전 16.5부터 c + + 20 표준에 대 한 실험적 전처리기 지원은 기능 완료입니다.

## <a name="new-predefined-macro"></a>미리 정의 된 새 매크로

컴파일 시간에 사용 중인 전처리기를 검색할 수 있습니다. 미리 정의 된 매크로 [\_MSVC\_](predefined-macros.md) 의 값을 확인 하 여 기존의 전처리기가 사용 중인지 여부를 확인 합니다. 이 매크로는 전처리기가 호출 되는 것과 관계 없이 해당 매크로를 지 원하는 컴파일러 버전에 의해 무조건 설정 됩니다. 기존 전처리기에 대 한 값은 1입니다. 규격 전처리기의 경우 0입니다.

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>실험적 전처리기의 동작 변경 내용

실험적 전처리기에서 초기 작업은 모든 매크로 확장이 표준을 준수 하도록 하는 데 중점을 두었습니다. 이를 통해 현재 일반적인 동작에 의해 차단 되는 라이브러리에 MSVC 컴파일러를 사용할 수 있습니다. 업데이트 된 전처리기를 실제 프로젝트에서 테스트 했습니다. 다음은 몇 가지 일반적인 주요 변경 내용입니다.

### <a name="macro-comments"></a>매크로 주석

기존 전처리기는 전처리기 토큰이 아닌 문자 버퍼를 기반으로 합니다. 다음 전처리기 주석 트릭과 같은 비정상적인 동작을 허용 하며,이는 규격 전처리기에서 작동 하지 않습니다.

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

표준에 맞는 픽스는 적절 한 `#ifdef/#endif` 지시문 내에 `int myVal`을 선언 하는 것입니다.

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L # val

기존 전처리기는 문자열 접두사를 [문자열 화 operator (#)](stringizing-operator-hash.md) 연산자의 결과와 잘못 결합 합니다.

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

이 경우에는 인접 문자열 리터럴이 매크로 확장 후에 결합 되므로 `L` 접두사가 필요 하지 않습니다. 이전 버전과 호환 되는 수정은 정의를 변경 하는 것입니다.

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

와이드 문자열 리터럴에 대 한 인수를 "stringize" 하는 편리한 매크로 에서도 동일한 문제가 발생할 수 있습니다.

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

다음과 같은 다양 한 방법으로 문제를 해결할 수 있습니다.

- `L""` 및 `#str`의 문자열 연결을 사용 하 여 접두사를 추가 합니다. 매크로 확장 후 인접 문자열 리터럴이 결합 됩니다.

   ```cpp
   #define STRING1(str) L""#str
   ```

- 추가 매크로 확장을 사용 하 여 `#str` 뒤에 접두사 추가

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- 연결 연산자 `##`를 사용 하 여 토큰을 결합 합니다. `##` 및 `#`에 대 한 작업 순서는 지정 되지 않지만이 경우 모든 컴파일러는 `##` 하기 전에 `#` 연산자를 평가 하는 것으로 보입니다.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>잘못 된 \#\#에 대 한 경고

[토큰 붙여넣기 연산자 (# #)](token-pasting-operator-hash-hash.md) 가 유효한 단일 전처리 토큰을 생성 하지 않으면 동작이 정의 되지 않습니다. 기존 전처리기는 토큰을 자동으로 결합 하지 못합니다. 새 전처리기는 대부분의 다른 컴파일러의 동작과 일치 하 고 진단을 내보냅니다.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Variadic 매크로의 쉼표 생략

기존 MSVC 전처리기는 항상 빈 `__VA_ARGS__` 바꾸기 전에 쉼표를 제거 합니다. 실험적 전처리기는 널리 사용 되는 다른 플랫폼 간 컴파일러의 동작을 더욱 잘 따릅니다. 쉼표를 제거 하려면 variadic 인수가 비어 있지 않아야 하 고 `##` 연산자로 표시 되어야 합니다. 다음과 같은 예제를 참조하세요.

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

다음 `FUNC2(1)` 예제에서는 호출 하는 매크로에 variadic 인수가 없습니다. `FUNC2(1, )`에 대 한 호출에서 variadic 인수는 비어 있지만 누락 되지 않습니다 (인수 목록에서 쉼표를 확인).

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

예정 된 c + + 20 표준에서는 `__VA_OPT__`을 추가 하 여이 문제를 해결 했습니다. `__VA_OPT__`에 대 한 실험적 전처리기 지원은 Visual Studio 2019 버전 16.5부터 사용할 수 있습니다.

### <a name="c20-variadic-macro-extension"></a>C + + 20 variadic 매크로 확장

실험적 전처리기는 c + + 20 variadic 매크로 인수 생략을 지원 합니다.

```cpp
#define FUNC(a, ...) __VA_ARGS__ + a
int main()
  {
  int ret = FUNC(0);
  return ret;
  }
```

이 코드는 c + + 20 표준 보다는 일치 하지 않습니다. MSVC에서 실험적 전처리기는이 c + + 20 동작을 하위 언어 표준 모드 ( **`/std:c++14`** **`/std:c++17`** )로 확장 합니다. 이 확장은 다른 주요 플랫폼 C++ 간 컴파일러의 동작과 일치 합니다.

### <a name="macro-arguments-are-unpacked"></a>매크로 인수는 "압축 풀기" 됩니다.

일반적인 전처리기에서 매크로가 인수 중 하나를 다른 종속 매크로에 전달 하는 경우 인수는 삽입 될 때 "압축 풀기" 되지 않습니다. 일반적으로 이러한 최적화는 알지 못할 수 있지만 비정상적인 동작이 발생할 수 있습니다.

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

`A()`확장할 때 기존 전처리기는 `__VA_ARGS__`에 패키지 된 모든 인수를 TWO_STRINGS의 첫 번째 인수에 전달 합니다. 그러면이 인수는 `TWO_STRINGS` variadic 인수를 비워 둡니다. 이로 인해 `#first` 결과는 "1"이 아닌 "1, 2"가 됩니다. 자세히 살펴보면 일반적인 전처리기 확장의 `#__VA_ARGS__` 결과에 어떤 일이 발생 했는지 궁금할 수 있습니다. variadic 매개 변수가 비어 있는 경우 빈 문자열 리터럴이 `""`됩니다. 별도의 문제로 인해 빈 문자열 리터럴 토큰이 생성 되지 않습니다.

### <a name="rescanning-replacement-list-for-macros"></a>매크로에 대 한 대체 목록 다시 검사

매크로가 대체 된 후에는 대체 하는 추가 매크로 식별자에 대해 결과 토큰을 다시 검색 합니다. 검사를 수행 하기 위해 일반적인 전처리기에서 사용 하는 알고리즘은 실제 코드를 기반으로 하는이 예제와 같이 일치 하지 않습니다.

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

이 예제는 약간 거리가 보일 수도 있지만 실제 코드에서 살펴보았습니다. 진행 상황을 확인 하기 위해 `DO_THING`부터 확장을 나눌 수 있습니다.

1. `DO_THING(1, "World")` 확장 `CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)` 확장 되어 `IMPL ## 1`으로 확장 되 고 `IMPL1`
1. 이제 토큰은 다음 상태입니다. `IMPL1 ECHO(("Hello", "World"))`
1. 전처리기는 `IMPL1`함수 같은 매크로 식별자를 찾습니다. 그 다음에는 `(`되지 않으므로 함수 처럼 매크로 호출로 간주 되지 않습니다.
1. 전처리기는 다음 토큰으로 이동 합니다. 호출 되는 함수 형식 `ECHO` 매크로를 찾습니다. `ECHO(("Hello", "World"))`은로 확장 됩니다 `("Hello", "World")`
1. `IMPL1` 확장에 대해 다시 고려 되지 않으므로 확장의 전체 결과는 `IMPL1("Hello", "World");`

실험적 전처리기와 일반적인 전처리기에서 동일 하 게 동작 하도록 매크로를 수정 하려면 다른 간접 계층을 추가 합니다.

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

## <a name="incomplete-features"></a>불완전 한 기능

Visual Studio 2019 버전 16.5부터 실험적 전처리기는 c + + 20에 대 한 기능 전체입니다. 이전 버전의 Visual Studio에서는 대부분의 전처리기 지시문 논리가 일반적인 동작으로 대체 되기는 하지만 실험적 전처리기는 대부분 완전 합니다. 다음은 16.5 이전의 Visual Studio 버전에서 불완전 한 기능의 일부 목록입니다.

- `_Pragma`에 대한 지원
- C + + 20 기능
- 차단 버그 상승: 전처리기 상수 식의 논리 연산자는 버전 16.5 이전에는 새 전처리기에서 완전히 구현 되지 않습니다. 일부 `#if` 지시문에서 새 전처리기는 기존 전처리기로 대체 될 수 있습니다. 기존 전처리기와 호환 되지 않는 매크로가 확장 된 경우에만 효과가 있습니다. 전처리기 슬롯을 빌드하는 경우에 발생할 수 있습니다.

::: moniker-end
