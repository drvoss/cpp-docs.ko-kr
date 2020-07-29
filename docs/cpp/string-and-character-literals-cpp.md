---
title: 문자열 및 문자 리터럴 (c + +)
description: C + +에서 문자열 및 문자 리터럴을 선언 하 고 정의 하는 방법입니다.
ms.date: 02/18/2020
f1_keywords:
- R
- L
- u
- u8
- LR
- uR
- u8R
helpviewer_keywords:
- literal strings [C++]
- string literals [C++]
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
ms.openlocfilehash: 60389ecf01cf16b1cf2a86fc68da94bd558b6d83
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231132"
---
# <a name="string-and-character-literals-c"></a>문자열 및 문자 리터럴 (c + +)

C++를 사용하면 다양한 문자열 및 문자 형식이 지원되며 이러한 각 형식의 리터럴 값을 표현할 수 있습니다. 소스 코드에서는 문자 집합을 사용하여 문자 및 문자열 리터럴의 내용을 표현합니다. 유니버설 문자 이름 및 이스케이프 문자를 사용하면 기본 소스 문자 집합만 사용하여 모든 문자열을 표현할 수 있습니다. 원시 문자열 리터럴을 사용하면 이스케이프 문자를 사용하지 않아도 되며 원시 문자열 리터럴을 사용하여 모든 유형의 문자열 리터럴을 표현할 수 있습니다. 또한 `std::string` 추가 생성 이나 변환 단계를 수행 하지 않고도 리터럴을 만들 수 있습니다.

```cpp
#include <string>
using namespace std::string_literals; // enables s-suffix for std::string literals

int main()
{
    // Character literals
    auto c0 =   'A'; // char
    auto c1 = u8'A'; // char
    auto c2 =  L'A'; // wchar_t
    auto c3 =  u'A'; // char16_t
    auto c4 =  U'A'; // char32_t

    // Multicharacter literals
    auto m0 = 'abcd'; // int, value 0x61626364

    // String literals
    auto s0 =   "hello"; // const char*
    auto s1 = u8"hello"; // const char*, encoded as UTF-8
    auto s2 =  L"hello"; // const wchar_t*
    auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16
    auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32

    // Raw string literals containing unescaped \ and "
    auto R0 =   R"("Hello \ world")"; // const char*
    auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8
    auto R2 =  LR"("Hello \ world")"; // const wchar_t*
    auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16
    auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32

    // Combining string literals with standard s-suffix
    auto S0 =   "hello"s; // std::string
    auto S1 = u8"hello"s; // std::string
    auto S2 =  L"hello"s; // std::wstring
    auto S3 =  u"hello"s; // std::u16string
    auto S4 =  U"hello"s; // std::u32string

    // Combining raw string literals with standard s-suffix
    auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char*
    auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8
    auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t*
    auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16
    auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32
}
```

문자열 리터럴에는 접두사가 없거나, 각각 좁은 문자(싱글바이트 또는 멀티바이트), UTF-8, 와이드 문자(UCS-2 또는 UTF-16), UTF-16 및 UTF-32 인코딩을 나타내는 `u8`, `L`, `u`및  `U` 접두사가 있습니다. 원시 문자열 리터럴에는 `R` `u8R` `LR` `uR` `UR` 이러한 인코딩의 원시 버전에 해당 하는,,, 및 접두사가 있을 수 있습니다.  임시 또는 정적 `std::string` 값을 만들려면 접미사와 함께 문자열 리터럴이나 원시 문자열 리터럴을 사용할 수 있습니다 `s` . 자세한 내용은 아래의 [문자열 리터럴](#string-literals) 단원을 참조 하세요. 기본 소스 문자 집합, 유니버설 문자 이름 및 소스 코드에서 확장 된 코드 페이지의 문자 사용에 대 한 자세한 내용은 [문자 집합](../cpp/character-sets.md)을 참조 하세요.

## <a name="character-literals"></a>문자 리터럴

*문자 리터럴* 은 상수 문자로 구성됩니다. 작은따옴표로 묶은 문자로 표시 됩니다. 문자 리터럴의 5 가지 종류가 있습니다.

- 형식의 일반 문자 리터럴 **`char`** (예:)`'a'`

- 형식의 UTF-8 문자 리터럴 **`char`** ( **`char8_t`** c + + 20) (예:)`u8'a'`

- 형식의 와이드 문자 리터럴 **`wchar_t`** (예:)`L'a'`

- 형식의 UTF-16 문자 리터럴 **`char16_t`** (예:)`u'a'`

- 형식의 u t f-32 문자 리터럴 **`char32_t`** (예:)`U'a'`

문자 리터럴에 사용 되는 문자는 예약 된 문자 백슬래시 ( **`\`** ), 작은따옴표 ( **`'`** ) 또는 줄 바꿈 문자를 제외 하 고 모든 문자일 수 있습니다. 예약된 문자는 이스케이프 시퀀스를 사용하여 지정할 수 있습니다. 문자는 형식이 문자를 저장할 수 있을 만큼 큰 경우 유니버설 문자 이름을 사용하여 지정할 수 있습니다.

### <a name="encoding"></a>Encoding

문자 리터럴은 접두사에 따라 다르게 인코딩됩니다.

- 접두사가 없는 문자 리터럴은 일반적인 문자 리터럴입니다. 실행 문자 집합에서 표현할 수 있는 단일 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 일반 문자 리터럴의 값이 실행 문자 집합에 있는 해당 인코딩의 숫자 값과 같은 값을 갖습니다. 둘 이상의 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름이 포함 된 일반 문자 리터럴은 *여러 문자 리터럴입니다*. 실행 문자 집합에 표현할 수 없는 여러 문자 리터럴 또는 일반 문자 리터럴에는 형식이 있으며 **`int`** 해당 값은 구현에서 정의 됩니다. MSVC의 경우 아래의 **Microsoft** 전용 섹션을 참조 하십시오.

- 접두사로 시작 하는 문자 리터럴은 `L` 와이드 문자 리터럴입니다. 문자 리터럴이 실행 와이드 문자 집합에 표시 되지 않는 경우 단일 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 와이드 문자 리터럴의 값은 실행 와이드 문자 집합에 있는 해당 인코딩의 숫자 값과 동일 합니다 .이 경우 값은 구현에서 정의 됩니다. 여러 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 와이드 문자 리터럴의 값은 구현에서 정의 됩니다. MSVC의 경우 아래의 **Microsoft** 전용 섹션을 참조 하십시오.

- 접두사로 시작 하는 문자 리터럴은 `u8` utf-8 문자 리터럴입니다. 단일 UTF-8 코드 단위 (C0 컨트롤 및 기본 라틴어 유니코드 블록에 해당)로 표현할 수 있는 경우 단일 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 UTF-8 문자 리터럴의 값은 ISO 10646 코드 포인트 값과 동일 합니다. 단일 UTF-8 코드 단위로 값을 표현할 수 없는 경우 프로그램의 형식이 잘못 된 것입니다. 둘 이상의 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 UTF-8 문자 리터럴에 형식이 잘못 되었습니다.

- 접두사로 시작 하는 문자 리터럴은 `u` utf-16 문자 리터럴입니다. 단일 UTF-16 코드 단위 (기본 다국어 평면에 해당)로 표현할 수 있는 경우 단일 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 UTF-16 문자 리터럴의 값이 ISO 10646 코드 포인트 값과 같은 값을 갖습니다. 단일 UTF-16 코드 단위로 값을 표현할 수 없는 경우 프로그램의 형식이 잘못 된 것입니다. 둘 이상의 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 UTF-16 문자 리터럴은 형식이 잘못 되었습니다.

- 접두사로 시작 하는 문자 리터럴은 `U` u t f-32 문자 리터럴입니다. 단일 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 u t f-32 문자 리터럴의 값에는 ISO 10646 코드 포인트 값과 동일한 값이 있습니다. 둘 이상의 문자, 이스케이프 시퀀스 또는 유니버설 문자 이름을 포함 하는 u t f-32 문자 리터럴에 형식이 잘못 되었습니다.

### <a name="escape-sequences"></a><a name="bkmk_Escape"></a>이스케이프 시퀀스

이스케이프 시퀀스는 단순, 8진수 및 16진수의 세 종류가 있습니다. 이스케이프 시퀀스는 다음 값 중 하나일 수 있습니다.

|값|이스케이프 시퀀스|
|-----------|---------------------|
| 줄 바꿈 | \\n |
| 백슬래시 | \\\\ |
| 가로 탭 | \\t |
| 물음표 | ? 또는 \\? |
| 세로 탭 | \\hyper-v |
| 작은따옴표 | \\' |
| 백스페이스 | \\b |
| 큰따옴표 | \\" |
| 캐리지 리턴 | \\& |
| null 문자 | \\0 |
| 폼 피드 | \\350 |
| 8진수 | \\ooo |
| 경고(벨) | \\a |
| 16진수 | \\xhhh |

8 진수 이스케이프 시퀀스는 백슬래시와 그 뒤에 1 ~ 3 개의 8 진수 숫자 시퀀스가 있습니다. 8 진수 이스케이프 시퀀스는 8 진수가 아닌 첫 번째 문자에서 종료 됩니다. 세 번째 숫자 보다 빨리 발생 한 경우 가능한 가장 높은 8 진수 값은 `\377` 입니다.

16 진수 이스케이프 시퀀스는 백슬래시와 그 뒤에 `x` 하나 이상의 16 진수 숫자 시퀀스가 오는 백슬래시입니다. 앞에 오는 0은 무시됩니다. 일반 또는 u8 접두 문자 리터럴에서 가장 큰 16 진수 값은 0xFF입니다. L 접두사 또는 u 접두사가 있는 와이드 문자 리터럴에서 가장 큰 16진수 값은 0xFFFF입니다. U 접두사가 있는 와이드 문자 리터럴에서 가장 큰 16진수 값은 0xFFFFFFFF입니다.

이 샘플 코드에서는 일반 문자 리터럴을 사용 하 여 이스케이프 된 문자의 몇 가지 예를 보여 줍니다. 다른 문자 리터럴 형식에 대해 동일한 이스케이프 시퀀스 구문을 사용할 수 있습니다.

```cpp
#include <iostream>
using namespace std;

int main() {
    char newline = '\n';
    char tab = '\t';
    char backspace = '\b';
    char backslash = '\\';
    char nullChar = '\0';

    cout << "Newline character: " << newline << "ending" << endl;
    cout << "Tab character: " << tab << "ending" << endl;
    cout << "Backspace character: " << backspace << "ending" << endl;
    cout << "Backslash character: " << backslash << "ending" << endl;
    cout << "Null character: " << nullChar << "ending" << endl;
}
/* Output:
Newline character:
ending
Tab character:  ending
Backspace character:ending
Backslash character: \ending
Null character:  ending
*/
```

백슬래시 문자 ( **`\`** )는 줄의 끝에 배치 될 때 줄 연속 문자입니다. 백슬래시 문자를 문자 리터럴로 표시 하려면 한 행에 두 개의 백슬래시 ()를 입력 해야 합니다 **`\\`** . 줄 연속 문자에 대한 자세한 내용은 [Phases of Translation](../preprocessor/phases-of-translation.md)를 참조하세요.

#### <a name="microsoft-specific"></a>Microsoft 전용

좁은 여러 문자 리터럴에서 값을 만들기 위해 컴파일러는 단일 따옴표 사이에 있는 문자 또는 문자 시퀀스를 32 비트 정수 내의 8 비트 값으로 변환 합니다. 리터럴의 여러 문자는 필요에 따라 상위에서 하위로 해당 바이트를 채웁니다. 그런 다음 컴파일러는 일반적인 규칙에 따라 정수를 대상 형식으로 변환 합니다. 예를 들어 값을 만들기 위해 **`char`** 컴파일러는 하위 바이트를 사용 합니다. 또는 값을 만들기 위해 **`wchar_t`** **`char16_t`** 컴파일러는 하위 단어를 사용 합니다. 컴파일러는 비트가 할당된 바이트 또는 단어 이상으로 설정된 경우 결과가 잘린다고 경고합니다.

```cpp
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'
int i0     = 'abcd';    // 0x61626364
```

3 자리 이상의 숫자를 포함 하는 것 처럼 보이는 8 진수 이스케이프 시퀀스는 3 자리의 8 진수 시퀀스로 처리 되 고 그 다음에 후속 숫자를 여러 문자 리터럴에서 문자로 처리 하 여 놀라운 결과를 제공할 수 있습니다. 예를 들면 다음과 같습니다.

```cpp
char c1 = '\100';   // '@'
char c2 = '\1000';  // C4305, C4309, truncates to '0'
```

8 진수가 아닌 문자를 포함 하는 것 처럼 보이는 이스케이프 시퀀스는 마지막 8 진수 문자까지 8 진수 시퀀스로 평가 되 고 그 다음에 나머지 문자는 여러 문자 리터럴의 후속 문자로 계산 됩니다. 8 진수가 아닌 첫 번째 문자가 10 진수 이면 경고 C4125 생성 됩니다. 예를 들면 다음과 같습니다.

```cpp
char c3 = '\009';   // '9'
char c4 = '\089';   // C4305, C4309, truncates to '9'
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'
```

값이 더 높은 8 진수 이스케이프 시퀀스의 경우 `\377` 오류 C2022: ' i*value-in-decimal*n i t i o n ': 문자에 비해 너무 큽니다.

16 진수 및 16 진수가 아닌 문자를 포함 하는 것 처럼 보이는 이스케이프 시퀀스는 마지막 16 진수 문자까지 16 진수 이스케이프 시퀀스를 포함 하는 여러 문자 리터럴로 계산 된 후 16 진수가 아닌 문자로 평가 됩니다. 16 진수가 없는 16 진수 이스케이프 시퀀스의 경우 컴파일러 오류 C2153: "16 진 리터럴에 하나 이상의 16 진수가 있어야 합니다."

```cpp
char c6 = '\x0050'; // 'P'
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'
```

접두사가 있는 와이드 문자 리터럴에 `L` 여러 문자 시퀀스가 포함 된 경우 첫 번째 문자에서 값을 가져오고 컴파일러가 C4066 경고를 발생 시킵니다. 해당 하는 일반 여러 문자 리터럴의 동작과 달리 후속 문자는 무시 됩니다.

```cpp
wchar_t w1 = L'\100';   // L'@'
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored
wchar_t w6 = L'\x0050'; // L'P'
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored
```

**Microsoft 관련** 섹션은 여기에서 끝납니다.

### <a name="universal-character-names"></a><a name="bkmk_UCN"></a>유니버설 문자 이름

문자 리터럴 및 네이티브(비 원시) 문자열 리터럴에서는 유니버설 문자 이름으로 모든 문자를 나타낼 수 있습니다.  유니버설 문자 이름은 접두사 `\U` 뒤에 8 자리 유니코드 코드 포인트 또는 접두사, `\u` 네 자리 유니코드 코드 포인트 순으로 구성 됩니다. 올바른 형식의 유니버설 문자 이름을 만들려면 모든 8자리 또는 4자리 숫자가 각각 있어야 합니다.

```cpp
char u1 = 'A';          // 'A'
char u2 = '\101';       // octal, 'A'
char u3 = '\x41';       // hexadecimal, 'A'
char u4 = '\u0041';     // \u UCN 'A'
char u5 = '\U00000041'; // \U UCN 'A'
```

#### <a name="surrogate-pairs"></a>서로게이트 쌍

유니버설 문자 이름은 서로게이트 코드 포인트 범위 D 800-DFFF의 값을 인코딩할 수 없습니다. 유니코드 서로게이트 쌍에 대해 `\UNNNNNNNN`을 사용하여 유니버설 문자 이름을 지정합니다. 여기서 NNNNNNNN은 문자에 대한 8자리 코드 포인트입니다. 필요한 경우 컴파일러에서 서로게이트 쌍을 생성 합니다.

C++03에서는 해당 유니버설 문자 이름을 사용해서만 문자 하위 집합을 나타낼 수 있으며 실제로 유효한 유니코드 문자를 나타내지 않는 일부 유니버설 문자 이름이 허용됩니다. 이 실수는 c + + 11 표준에서 수정 되었습니다. C++11에서는 문자 및 문자열 리터럴과 식별자 모두 유니버설 문자 이름을 사용할 수 있습니다.  유니버설 문자 이름에 대한 자세한 내용은 [Character Sets](../cpp/character-sets.md)을 참조하세요. 유니코드에 대한 자세한 내용은 [유니코드](/windows/win32/intl/unicode)(영문)를 참조하세요. 서로게이트 쌍에 대한 자세한 내용은 [서로게이트 쌍 및 보조 문자](/windows/win32/Intl/surrogates-and-supplementary-characters)(영문)를 참조하세요.

## <a name="string-literals"></a><a name="string-literals"></a>문자열 리터럴

문자열 리터럴은 함께 사용되어 null로 끝나는 문자열을 형성하는 문자 시퀀스를 나타냅니다. 문자를 큰따옴표로 묶어야 합니다. 다음과 같은 종류의 문자열 리터럴이 있습니다.

### <a name="narrow-string-literals"></a>좁은 문자열 리터럴

좁은 문자열 리터럴은 접두사가 없는 큰따옴표를 구분 하 여 null로 끝나는 형식의 배열입니다 `const char[n]` . 여기서 n은 배열의 길이 (바이트)입니다. 좁은 문자열 리터럴에는 큰따옴표(`"`), 백슬래시(`\`) 또는 줄 바꿈 문자를 제외한 모든 그래픽 문자가 포함될 수 있습니다. 또한 좁은 문자열 리터럴에는 위에 나열된 이스케이프 시퀀스 및 바이트 크기에 맞는 유니버설 문자 이름이 포함될 수 있습니다.

```cpp
const char *narrow = "abcd";

// represents the string: yes\no
const char *escaped = "yes\\no";
```

#### <a name="utf-8-encoded-strings"></a>UTF-8로 인코딩된 문자열

U t f-8로 인코딩된 문자열은 형식의 u8 접두사가 있고 큰따옴표로 구분 된 null로 끝나는 배열입니다 `const char[n]` . 여기서 *n* 은 인코딩된 배열의 길이 (바이트)입니다. u8 접두사가 있는 문자열 리터럴에는 큰따옴표(`"`), 백슬래시(`\`) 또는 줄 바꿈 문자를 제외한 모든 그래픽 문자가 포함될 수 있습니다. 또한 u8 접두사가 있는 문자열 리터럴에는 위에 나열된 이스케이프 시퀀스 및 모든 유니버설 문자 이름이 포함될 수 있습니다.

```cpp
const char* str1 = u8"Hello World";
const char* str2 = u8"\U0001F607 is O:-)";
```

### <a name="wide-string-literals"></a>와이드 문자열 리터럴

와이드 문자열 리터럴은 ' '로 시작 하는 상수의 null로 끝나는 배열 이며 큰따옴표 **`wchar_t`** `L` ( **`"`** ), 백슬래시 ( **`\`** ) 또는 줄 바꿈 문자를 제외한 모든 그래픽 문자를 포함 합니다. 와이드 문자열 리터럴에는 위에 나열된 이스케이프 시퀀스 및 모든 유니버설 문자 이름이 포함될 수 있습니다.

```cpp
const wchar_t* wide = L"zyxw";
const wchar_t* newline = L"hello\ngoodbye";
```

#### <a name="char16_t-and-char32_t-c11"></a>char16_t 및 char32_t(C++11)

C + + 11에서는 이식 가능한 **`char16_t`** (16 비트 유니코드) 및 **`char32_t`** (32 비트 유니코드) 문자 형식이 도입 되었습니다.

```cpp
auto s3 = u"hello"; // const char16_t*
auto s4 = U"hello"; // const char32_t*
```

### <a name="raw-string-literals-c11"></a>원시 문자열 리터럴 (c + + 11)

원시 문자열 리터럴은 큰따옴표 ( **`"`** ), 백슬래시 ( **`\`** ) 또는 줄 바꿈 문자를 비롯 한 모든 그래픽 문자를 포함 하는 null로 끝나는 배열입니다. 원시 문자열 리터럴은 문자 클래스를 사용하는 정규식과 HTML 문자열 및 XML 문자열에 종종 사용됩니다. 예제를 보려면 [Bjarne Stroustrup의 C++11에 대한 FAQ](http://www.stroustrup.com/C++11FAQ.html)(영문) 문서를 참조하세요.

```cpp
// represents the string: An unescaped \ character
const char* raw_narrow = R"(An unescaped \ character)";
const wchar_t* raw_wide = LR"(An unescaped \ character)";
const char*       raw_utf8  = u8R"(An unescaped \ character)";
const char16_t* raw_utf16 = uR"(An unescaped \ character)";
const char32_t* raw_utf32 = UR"(An unescaped \ character)";
```

구분 기호는 원시 문자열 리터럴의 여는 괄호 바로 앞에 오는 최대 16 자의 사용자 정의 시퀀스로, 닫는 괄호 바로 뒤에 나옵니다.  예를 들어 `R"abc(Hello"\()abc"` 에서 구분 기호 시퀀스는 `abc` 이고 문자열 콘텐츠는 `Hello"\(`입니다. 구분 기호를 사용하여 큰따옴표와 괄호를 모두 포함하는 원시 문자열을 구분할 수 있습니다. 이 문자열 리터럴은 컴파일러 오류를 발생 시킵니다.

```cpp
// meant to represent the string: )"
const char* bad_parens = R"()")";  // error C2059
```

그러나 구분 기호를 사용하면 오류가 해결됩니다.

```cpp
const char* good_parens = R"xyz()")xyz";
```

원본에서 줄 바꿈 문자 (이스케이프 된 문자가 아님)가 포함 된 원시 문자열 리터럴을 생성할 수 있습니다.

```cpp
// represents the string: hello
//goodbye
const wchar_t* newline = LR"(hello
goodbye)";
```

### <a name="stdstring-literals-c14"></a>std:: string 리터럴 (c + + 14)

`std::string`리터럴은 (접미사 포함)로 표현 되는 사용자 정의 리터럴 (아래 참조)의 표준 라이브러리 구현입니다 `"xyz"s` `s` . 이러한 종류의 문자열 리터럴은 `std::string` `std::wstring` 지정 된 `std::u32string` 접두사에 따라,, 또는 형식의 임시 개체를 생성 `std::u16string` 합니다. 위와 같이 접두사를 사용 하지 않으면 `std::string` 이 생성 됩니다. `L"xyz"s`을 생성 `std::wstring` 합니다. `u"xyz"s`[std:: u16string](../standard-library/string-typedefs.md#u16string)을 생성 하 고 `U"xyz"s` [std:: u32string](../standard-library/string-typedefs.md#u32string)을 생성 합니다.

```cpp
//#include <string>
//using namespace std::string_literals;
string str{ "hello"s };
string str2{ u8"Hello World" };
wstring str3{ L"hello"s };
u16string str4{ u"hello"s };
u32string str5{ U"hello"s };
```

이 `s` 접미사는 원시 문자열 리터럴에도 사용할 수 있습니다.

```cpp
u32string str6{ UR"(She said "hello.")"s };
```

`std::string`리터럴은 `std::literals::string_literals` 헤더 파일의 네임 스페이스에 정의 됩니다 \<string> . `std::literals::string_literals`및가 `std::literals` 모두 [인라인 네임 스페이스로](../cpp/namespaces-cpp.md)선언 되기 때문에 `std::literals::string_literals` 는 네임 스페이스에 직접 속한 것 처럼 자동으로 처리 됩니다 `std` .

### <a name="size-of-string-literals"></a>문자열 리터럴의 크기

ANSI `char*` 문자열 및 기타 싱글바이트 인코딩 (utf-8 아님)의 경우 문자열 리터럴의 크기 (바이트)는 문자 수에 null 종결 문자에 대 한 1을 더한 값입니다. 다른 모든 문자열 형식의 경우 크기는 문자 수와 엄격히 관련 되지 않습니다. U t f-8에서는 최대 4 개의 요소를 사용 하 여 **`char`** 일부 *코드 단위*를 인코딩하고, **`char16_t`** **`wchar_t`** u t f-16으로 인코드된 경우 두 개의 요소 (총 4 바이트)를 사용 하 여 단일 *코드 단위*를 인코딩할 수 있습니다. 이 예제에서는 와이드 문자열 리터럴의 크기(바이트)를 보여 줍니다.

```cpp
const wchar_t* str = L"Hello!";
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);
```

및에는 문자열 형식의 요소 크기, 또는 문자열의 경우 `strlen()` `wcslen()` 1 바이트, 또는 문자열의 경우 `char*` `char8_t*` 2 바이트 `wchar_t*` `char16_t*` , 문자열의 경우 4 바이트와 `char32_t*` 같은 종료 null 문자의 크기가 포함 되지 않습니다.

문자열 리터럴의 최대 길이는 65535 바이트입니다. 이 제한은 좁은 문자열 리터럴과 와이드 문자열 리터럴 모두에 적용됩니다.

### <a name="modifying-string-literals"></a>문자열 리터럴 수정

문자열 리터럴 (리터럴 포함 안 함 `std::string` )은 상수 이므로이를 수정 하려고 하면 (예: `str[2] = 'A'` ) 컴파일러 오류가 발생 합니다.

#### <a name="microsoft-specific"></a>Microsoft 전용

Microsoft c + +에서는 문자열 리터럴을 사용 하 여 비상수 또는로 포인터를 초기화할 수 있습니다 **`char`** **`wchar_t`** . 이 비 const 초기화는 C99 코드에서 허용 되지만 c + + 98에서는 더 이상 사용 되지 않으며 c + + 11에서는 제거 되었습니다. 문자열을 수정하려고 하면 다음 예제와 같이 액세스 위반이 발생합니다.

```cpp
wchar_t* str = L"hello";
str[2] = L'a'; // run-time error: access violation
```

[ `/Zc:strictStrings` (문자열 리터럴 형식 변환 사용 안 함)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) 컴파일러 옵션을 설정할 때 문자열 리터럴이 비 const 문자 포인터로 변환 되 면 컴파일러에서 오류를 발생 시킬 수 있습니다. 표준 규격의 이식 가능한 코드에 권장됩니다. 또한 **`auto`** 올바른 (const) 형식으로 확인 되기 때문에 키워드를 사용 하 여 문자열 리터럴 초기화 포인터를 선언 하는 것이 좋습니다. 예를 들어 다음 코드 예제는 컴파일 시간에 문자열 리터럴에 쓰려는 시도를 catch합니다.

```cpp
auto str = L"hello";
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.
```

경우에 따라 실행 파일의 공간을 절약하기 위해 동일한 문자열 리터럴이 풀링될 수 있습니다. 문자열 리터럴 풀링에서 컴파일러는 각 참조가 문자열 리터럴의 별도 인스턴스를 가리키는 것이 아니라 특정 문자열 리터럴에 대한 모든 참조가 메모리의 같은 위치를 가리키게 합니다. 문자열 풀링을 사용 하려면 [`/GF`](../build/reference/gf-eliminate-duplicate-strings.md) 컴파일러 옵션을 사용 합니다.

**Microsoft 관련** 섹션은 여기에서 끝납니다.

### <a name="concatenating-adjacent-string-literals"></a>인접 문자열 리터럴 연결

인접하는 와이드 문자열 리터럴 또는 좁은 문자열 리터럴은 연결됩니다. 다음 선언은

```cpp
char str[] = "12" "34";
```

다음 선언과 동일합니다.

```cpp
char atr[] = "1234";
```

또한 다음 선언과 동일합니다.

```cpp
char atr[] =  "12\
34";
```

포함된 16진수 이스케이프 코드를 사용하여 문자열 리터럴을 지정하면 예기치 않은 결과가 발생할 수 있습니다. 다음 예제는 ASCII 5 문자와 f, i, v 및 e 문자가 포함된 문자열 리터럴을 만들려고 합니다.

```cpp
"\x05five"
```

실제 결과는 16진수 5F(ASCII 코드의 밑줄)와 i, v 및 e 문자입니다. 올바른 결과를 얻으려면 다음 이스케이프 시퀀스 중 하나를 사용할 수 있습니다.

```cpp
"\005five"     // Use octal literal.
"\x05" "five"  // Use string splicing.
```

`std::string`리터럴은 형식이 기 때문에 `std::string` **`+`** 형식에 대해 정의 된 연산자를 사용 하 여 연결할 수 있습니다 [`basic_string`](../standard-library/basic-string-class.md) . 또한 인접 문자열 리터럴과 동일한 방식으로 연결할 수도 있습니다. 두 경우 모두, 문자열 인코딩과 접미사가 다음과 일치해야 합니다.

```cpp
auto x1 = "hello" " " " world"; // OK
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes
```

### <a name="string-literals-with-universal-character-names"></a>유니버설 문자 이름을 가진 문자열 리터럴

네이티브(비 원시) 문자열 리터럴은 문자열 형식에서 하나 이상의 문자로 유니버설 문자 이름을 인코드할 수 있는 한 유니버설 문자 이름을 사용하여 모든 문자를 나타낼 수 있습니다.  예를 들어 확장 문자를 나타내는 유니버설 문자 이름은 ANSI 코드 페이지를 사용 하 여 좁은 문자열로 인코딩할 수 없지만, 일부 멀티 바이트 코드 페이지 또는 UTF-8 문자열 또는 와이드 문자열에서 좁은 문자열로 인코딩될 수 있습니다. C + + 11에서 유니코드 지원은 `char16_t*` 및 문자열 형식으로 확장 됩니다 `char32_t*` .

```cpp
// ASCII smiling face
const char*     s1 = ":-)";

// UTF-16 (on Windows) encoded WINKING FACE (U+1F609)
const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)";

// UTF-8  encoded SMILING FACE WITH HALO (U+1F607)
const char*     s3 = u8"😇 = \U0001F607 is O:-)";

// UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603)
const char16_t* s4 = u"😃 = \U0001F603 is :-D";

// UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E)
const char32_t* s5 = U"😎 = \U0001F60E is B-)";
```

## <a name="see-also"></a>참고 항목

[문자 집합](../cpp/character-sets.md)\
[숫자, 부울 및 포인터 리터럴](../cpp/numeric-boolean-and-pointer-literals-cpp.md)\
[사용자 정의 리터럴](../cpp/user-defined-literals-cpp.md)
