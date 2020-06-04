---
title: '&lt;string&gt; functions'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 3f1dca71a6bb9d5461150378191b9373f907ecd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376654"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; functions

||||
|-|-|-|
|[게라인](#getline)|[스토드 ()에 스토드 (것)](#stod)|[스모그 (것)스모](#stof)|
|[스토이 ()의](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[스툴 (것)들](#stoul)|[스토울 (stoull)](#stoull)|
|[스왑](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>게라인

입력 스트림에서 문자열을 한 줄씩 추출합니다.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>매개 변수

*in_stream*\
문자열을 추출할 입력 스트림입니다.

*Str*\
입력 스트림에서 문자를 읽어들일 문자열입니다.

*구분 기호*\
줄 구분 기호입니다.

### <a name="return-value"></a>Return Value

입력 스트림이 *in_stream.*

### <a name="remarks"></a>설명

함수 시그니처 쌍은 `(1)` in_stream 추출 문자를 표시하여 *구분 기호가* 발견될 *때까지* *str에*저장합니다.

표시된 `(2)` 함수 시그니처 쌍은 줄 바선을 기본 줄 구분 기호로 사용하고 로 `getline(in_stream, str, in_stream. widen('\n'))`작동합니다.

각 쌍의 두 번째 함수는 [value 참조](../cpp/lvalues-and-rvalues-visual-cpp.md)를 지원하기 위한 첫 번째 함수와 유사한 버전입니다.

다음 중 하나가 발생하면 추출이 중지됩니다.

- 파일의 끝에서 *in_stream* 내부 상태 플래그가 `ios_base::eofbit`로 설정됩니다.

- 함수가 추출된 후 *구분 기호와*동일한 요소를 추출합니다. 요소는 다시 배치되거나 제어된 시퀀스에 추가되지 않습니다.

- 함수 후 `str.` [max_size](../standard-library/basic-string-class.md#max_size) 요소를 추출합니다. *in_stream* 내부 상태 플래그가 `ios_base::failbit`로 설정됩니다.

- 이전에 나열된 오류 이외의 다른 오류; *in_stream* 내부 상태 플래그가 `ios_base::badbit`로 설정됩니다.

내부 상태 플래그에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#iostate)를 참조하세요.

함수가 요소를 추출하지 않으면 *in_stream* 내부 상태 플래그가 로 `ios_base::failbit`설정됩니다. 어쨌든 *in_stream* `getline` 반환합니다.

예외가 throw되면 *in_stream* *str은* 유효한 상태로 남아 있습니다.

### <a name="example"></a>예제

다음 코드에서는 `getline()`을 두 가지 모드에서 보여 줍니다. 첫 번째 모드에서는 기본 구분 기호(줄 바꿈 문자)를 사용하고 두 번째 모드에서는 공백을 구분 기호로 사용합니다. 파일의 끝 문자(키보드에서 CTRL+Z를 누름)를 사용하여 while 루프 종료를 제어합니다. 이 값은 두 번째 `cin` `eofbit`while 루프가 제대로 작동하기 전에 [basic_ios::clear()로](../standard-library/basic-ios-class.md#clear) 지워야 하는 의 내부 상태 플래그를 설정합니다.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a><a name="stod"></a>스토드 ()에 스토드 (것)

문자 시퀀스를 **`double`** 로 변환합니다.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

### <a name="return-value"></a>Return Value

값입니다. **`double`**

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`double`** `strtod( str.c_str(), _Eptr)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stof"></a><a name="stof"></a>스모그 (것)스모

문자 시퀀스를 float로 변환합니다.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

### <a name="return-value"></a>Return Value

값입니다. **`float`**

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`float`** `strtof( str.c_str(), _Eptr)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stoi"></a><a name="stoi"></a>스토이 ()의

문자 시퀀스를 정수로 변환합니다.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Return Value

정수 값입니다.

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

*기본*\
사용할 기수입니다.

### <a name="remarks"></a>설명

함수는 `stoi` *str의* 문자 시퀀스를 형식 **`int`** 값으로 변환하고 값을 반환합니다. 예를 들어 문자 시퀀스 "10" 전달 시 `stoi`에서 반환하는 값은 정수 10입니다.

`stoi`함수 내부의 개체가 `strtol` 호출되는 방식으로 `strtol( str.c_str(), _Eptr, idx)` `_Eptr` 호출될 때 단일 바이트 문자에 대한 함수와 유사하게 작동합니다. 또는 `wcstol` 와이드 문자의 경우 비슷한 방식으로 호출될 때 `wcstol(Str.c_str(), _Eptr, idx)`. 자세한 내용은 [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)을 참조하세요.

이 `str.c_str() == *_Eptr` `stoi` 경우 형식의 `invalid_argument`개체를 throw합니다. 이러한 호출이 설정되거나 `errno`반환된 값을 형식의 **`int`** 개체로 나타낼 수 없는 경우 형식의 `out_of_range`개체를 throw합니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr - str.c_str()` 경우 `*idx`함수는 에 저장됩니다.

## <a name="stol"></a><a name="stol"></a>스톨 (것)들을

문자 시퀀스를 **`long`** 로 변환합니다.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

*기본*\
사용할 기수입니다.

### <a name="return-value"></a>Return Value

long 정수 값입니다.

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`long`** `strtol( str.c_str(), _Eptr, idx)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stold"></a><a name="stold"></a>스말드

문자 시퀀스를 **`long double`** 로 변환합니다.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

### <a name="return-value"></a>Return Value

값입니다. **`long double`**

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`long double`** `strtold( str.c_str(), _Eptr)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stoll"></a><a name="stoll"></a>스 톨

문자 시퀀스를 **`long long`** 로 변환합니다.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

*기본*\
사용할 기수입니다.

### <a name="return-value"></a>Return Value

값입니다. **`long long`**

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`long long`** `strtoll( str.c_str(), _Eptr, idx)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stoul"></a><a name="stoul"></a>스툴 (것)들

문자 시퀀스를 부호 없는 long으로 변환합니다.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

*기본*\
사용할 기수입니다.

### <a name="return-value"></a>Return Value

부호 없는 long 정수 값입니다.

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`unsigned long`** `strtoul( str.c_str(), _Eptr, idx)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="stoull"></a><a name="stoull"></a>스토울 (stoull)

문자 시퀀스를 **`unsigned long long`** 로 변환합니다.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

*Str*\
변환할 문자 시퀀스입니다.

*Idx*\
변환되지 않은 첫 번째 문자의 인덱스 값입니다.

*기본*\
사용할 기수입니다.

### <a name="return-value"></a>Return Value

값입니다. **`unsigned long long`**

### <a name="remarks"></a>설명

함수는 *str의* 요소 시퀀스를 함수 내부개체를 호출하는 **`unsigned long long`** `strtoull( str.c_str(), _Eptr, idx)` `_Eptr` 것처럼 형식 값으로 변환합니다. 이 `str.c_str() == *_Eptr`형식의 `invalid_argument`개체를 throw하는 경우 . 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않으면 *idx가* null 포인터가 아닌 `*_Eptr -  str.c_str()` 경우 `*idx` 함수는 값을 저장하고 반환합니다.

## <a name="swap"></a><a name="swap"></a>스왑

두 문자열의 문자 배열을 교환합니다.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
요소를 다른 문자열의 요소로 교환해야 하는 하나의 문자열입니다.

*오른쪽*\
요소가 첫 번째 문자열과 교환되는 다른 문자열입니다.

### <a name="remarks"></a>설명

템플릿 함수는 *왼쪽에*있는 특수 멤버 함수를 실행합니다. [일정한](../standard-library/basic-string-class.md#swap)복잡성을 보장하는 문자열의 스왑(오른쪽)입니다.*right*

### <a name="example"></a>예제

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a><a name="to_string"></a>to_string

값을 `string`로 변환합니다.

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>매개 변수

*값*\
변환할 값입니다.

### <a name="return-value"></a>Return Value

값을 나타내는 `string`입니다.

### <a name="remarks"></a>설명

함수는 *값을* 배열 개체 `Buf` 내부에 저장된 요소 시퀀스로 변환하여 `sprintf(Buf, Fmt, value)`함수를 `Fmt` 호출하는 것처럼

- `"%d"`*값이* 형식인 경우**`int`**

- `"%u"`*값이* 형식인 경우**`unsigned int`**

- `"%ld"`*값이* 형식인 경우**`long`**

- `"%lu"`*값이* 형식인 경우**`unsigned long`**

- `"%lld"`*값이* 형식인 경우**`long long`**

- `"%llu"`*값이* 형식인 경우**`unsigned long long`**

- `"%f"`*값이* 형식이거나 **`float`****`double`**

- `"%Lf"`*값이* 형식인 경우**`long double`**

함수에서 `string(Buf)`을 반환합니다.

## <a name="to_wstring"></a><a name="to_wstring"></a>to_wstring

값을 와이드 문자열로 변환합니다.

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>매개 변수

*값*\
변환할 값입니다.

### <a name="return-value"></a>Return Value

값을 나타내는 와이드 문자열입니다.

### <a name="remarks"></a>설명

함수는 *값을* 배열 개체 `Buf` 내부에 저장된 요소 시퀀스로 변환하여 `swprintf(Buf, Len, Fmt, value)`함수를 `Fmt` 호출하는 것처럼

- `L"%d"`*값이* 형식인 경우**`int`**

- `L"%u"`*값이* 형식인 경우**`unsigned int`**

- `L"%ld"`*값이* 형식인 경우**`long`**

- `L"%lu"`*값이* 형식인 경우**`unsigned long`**

- `L"%lld"`*값이* 형식인 경우**`long long`**

- `L"%llu"`*값이* 형식인 경우**`unsigned long long`**

- `L"%f"`*값이* 형식이거나 **`float`****`double`**

- `L"%Lf"`*값이* 형식인 경우**`long double`**

함수에서 `wstring(Buf)`을 반환합니다.

## <a name="see-also"></a>참고 항목

[\<문자열>](../standard-library/string.md)
