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
ms.openlocfilehash: 459e46f6aa144c591173a159c282658b120b1af3
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150605"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; functions

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>  getline

입력 스트림에서 문자열을 한 줄씩 추출합니다.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>매개 변수

*is*\
문자열을 추출할 입력 스트림입니다.

*str*\
입력 스트림에서 문자를 읽어들일 문자열입니다.

*delim*\
줄 구분 기호입니다.

### <a name="return-value"></a>Return Value

입력 스트림이 *인*경우

### <a name="remarks"></a>설명

*에서 문자를 추출* `(1)` 표시 된 함수 시그니처 쌍은 *delim* 를 찾아 *str*에 저장 합니다.

`(2)` 표시 된 함수 시그니처 쌍은 줄 바꿈 문자를 기본 줄 구분 기호로 사용 하 고 **getline**(`is`, `str`, `is`로 동작 합니다. `widen`(' `\n`'))으로 동작합니다.

각 쌍의 두 번째 함수는 [value 참조](../cpp/lvalues-and-rvalues-visual-cpp.md)를 지원하기 위한 첫 번째 함수와 유사한 버전입니다.

다음 중 하나가 발생하면 추출이 중지됩니다.

- 파일의 끝에 있는 *경우의 내부 상태 플래그는 `ios_base::eofbit`* 로 설정 됩니다.

- 함수가 `delim`과 비교 시 같은 요소를 추출하는 경우, 해당 요소는 제어된 시퀀스로 다시 돌아가지도 않고 제어된 시퀀스에 추가되지도 않습니다.

- 함수는 `str.`[max_size](../standard-library/basic-string-class.md#max_size) 요소를 추출 하 고, *이* 경우의 내부 상태 플래그는 `ios_base::failbit`로 설정 됩니다.

- 이전에 나열 되지 않은 다른 오류가 발생 했습니다. *이* 경우의 내부 상태 플래그가로 설정 됩니다 `ios_base::badbit`

내부 상태 플래그에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#iostate)를 참조하세요.

함수가 요소를 추출 하지 않으면의 내부 상태 플래그가 `ios_base::failbit`로 *설정 됩니다.* 어떤 경우 든 `getline` *는*를 반환 합니다.

예외가 throw 되는 경우 *는이* 고 *str* 은 유효한 상태로 유지 됩니다.

### <a name="example"></a>예제

다음 코드에서는 `getline()`을 두 가지 모드에서 보여 줍니다. 첫 번째 모드에서는 기본 구분 기호(줄 바꿈 문자)를 사용하고 두 번째 모드에서는 공백을 구분 기호로 사용합니다. 파일의 끝 문자(키보드에서 CTRL+Z를 누름)를 사용하여 while 루프 종료를 제어합니다. 그러면 `cin`의 내부 상태 플래그가 `eofbit`로 설정되며, [basic_ios::clear()](../standard-library/basic-ios-class.md#clear)를 사용하여 이 상태를 해제해야 두 번째 while 루프가 정상적으로 작동합니다.

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

## <a name="stod"></a><a name="stod"></a>  stod

문자 시퀀스를 **double**로 변환 합니다.

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>Return Value

**Double** 값입니다.

### <a name="remarks"></a>설명

함수는 `strtod( str.c_str(), _Eptr)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **double** 형식의 `val` 값으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stof"></a><a name="stof"></a>  stof

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>Return Value

float 값입니다.

### <a name="remarks"></a>설명

함수는 `strtof( str.c_str(), _Eptr)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **float** 형식의 `val` 값으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stoi"></a><a name="stoi"></a>  stoi

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|반환 시 변환되지 않은 첫 번째 문자의 인덱스를 포함합니다.|
|*base*|사용할 기수입니다.|

### <a name="remarks"></a>설명

함수 `stoi` *str* 의 문자 시퀀스를 **int** 형식의 값으로 변환 하 고 값을 반환 합니다. 예를 들어 문자 시퀀스 "10" 전달 시 `stoi`에서 반환하는 값은 정수 10입니다.

`stoi`는 `strtol` 방식으로 호출하는 경우 싱글바이트 문자에 대해 `strtol( str.c_str(), _Eptr, idx)` 함수와 비슷하게 동작하고, `_Eptr` 방식으로 호출하는 경우에는 와이드 문자에 대해 `wcstol` 함수와 비슷하게 동작합니다. 여기서 `wcstol(Str.c_str(), _Eptr, idx)`은 함수 내부의 개체입니다. 자세한 내용은 [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)을 참조하세요.

`str.c_str() == *_Eptr`경우 `stoi` `invalid_argument`형식의 개체를 throw 합니다. 이러한 호출을 `errno`설정 하거나 반환 된 값을 **int**형식의 개체로 나타낼 수 없는 경우 `out_of_range`형식의 개체를 throw 합니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx`에 `*_Eptr - str.c_str()`을 저장 합니다.

## <a name="stol"></a><a name="stol"></a>  stol

문자 시퀀스를 **long**으로 변환 합니다.

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>Return Value

long 정수 값입니다.

### <a name="remarks"></a>설명

함수는 `strtol( str.c_str(), _Eptr, idx)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **long** 형식의 값 `val`으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stold"></a><a name="stold"></a>  stold

문자 시퀀스를 **long double**로 변환 합니다.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>Return Value

**Long double** 값입니다.

### <a name="remarks"></a>설명

함수는 `strtold( str.c_str(), _Eptr)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **long double** 형식의 값 `val`으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stoll"></a><a name="stoll"></a>  stoll

문자 시퀀스를 **long long**으로 변환 합니다.

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>Return Value

**Long long** 값입니다.

### <a name="remarks"></a>설명

함수는 `strtoll( str.c_str(), _Eptr, idx)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **long** 형식의 값 `val`으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stoul"></a><a name="stoul"></a>  stoul

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>Return Value

부호 없는 long 정수 값입니다.

### <a name="remarks"></a>설명

함수는 `strtoul( str.c_str(), _Eptr, idx)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **unsigned long** 형식의 값 `val`으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="stoull"></a><a name="stoull"></a>  stoull

문자 시퀀스를 **부호 없는 long long**으로 변환 합니다.

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

|매개 변수|Description|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>Return Value

**부호 없는 long long** 값입니다.

### <a name="remarks"></a>설명

함수는 `strtoull( str.c_str(), _Eptr, idx)`를 호출 하는 것 처럼 *str* 의 요소 시퀀스를 **부호 없는 long** 형식 `val` 값으로 변환 합니다. 여기서 `_Eptr`는 함수 내부의 개체입니다. `str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* 가 null 포인터가 아닌 경우 함수는 `*idx` `*_Eptr -  str.c_str()`를 저장 하 고 `val`반환 합니다.

## <a name="swap"></a><a name="swap"></a>  swap

두 문자열의 문자 배열을 교환합니다.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
요소를 다른 문자열의 요소와 교환할 단일 문자열입니다.

*오른쪽*\
요소가 첫 번째 문자열과 교환되는 다른 문자열입니다.

### <a name="remarks"></a>설명

템플릿 함수는 특수 멤버 함수를 *왼쪽*으로 실행 합니다. 문자열에 대해 [바꾸기](../standard-library/basic-string-class.md#swap)(*오른쪽*)-일관 된 복잡성을 보장 합니다.

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

## <a name="to_string"></a><a name="to_string"></a>  to_string

값을 `string`로 변환합니다.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*Val*|변환할 값입니다.|

### <a name="return-value"></a>Return Value

값을 나타내는 `string`입니다.

### <a name="remarks"></a>설명

함수는 `sprintf(Buf, Fmt, Val)`를 호출 하는 것 처럼 함수 내부 `Buf` 배열 개체에 저장 된 요소 *시퀀스로 변환 합니다* . 여기서 `Fmt`는입니다.

- `Val`에 **int** 형식이 `"%d"`

- `Val`에 **부호 없는 int** 형식이 `"%u"`

- `Val` **long** 형식 `"%ld"`

- `Val`의 **부호 없는 long** 형식 `"%lu"`

- `Val` **long long** 형식 `"%lld"`

- `Val`의 **부호 없는 long long** 형식 `"%llu"`

- `Val`에 **float** 또는 **double** 형식이 `"%f"`

- `Val` **길이가 long double** 형식 `"%Lf"`

함수에서 `string(Buf)`을 반환합니다.

## <a name="to_wstring"></a><a name="to_wstring"></a>  to_wstring

값을 와이드 문자열로 변환합니다.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|`Val`|변환할 값입니다.|

### <a name="return-value"></a>Return Value

값을 나타내는 와이드 문자열입니다.

### <a name="remarks"></a>설명

이 함수는 `Val`가 있는 위치에서 `Buf`를 호출하는 것과 같이 `swprintf(Buf, Len, Fmt, Val)`을 함수 내부의 배열 개체 `Fmt`에 저장된 요소 시퀀스로 변환합니다.

- `Val`에 **int** 형식이 `L"%d"`

- `Val`에 **부호 없는 int** 형식이 `L"%u"`

- `Val` **long** 형식 `L"%ld"`

- `Val`의 **부호 없는 long** 형식 `L"%lu"`

- `Val` **long long** 형식 `L"%lld"`

- `Val`의 **부호 없는 long long** 형식 `L"%llu"`

- `Val`에 **float** 또는 **double** 형식이 `L"%f"`

- `Val` **길이가 long double** 형식 `L"%Lf"`

함수에서 `wstring(Buf)`을 반환합니다.

## <a name="see-also"></a>참고 항목

[\<string>](../standard-library/string.md)
