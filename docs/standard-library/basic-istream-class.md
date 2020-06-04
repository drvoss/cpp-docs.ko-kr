---
title: basic_istream 클래스
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
ms.openlocfilehash: 03a6e3a65d6dc8c2fa896949855bd23a01578e5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376834"
---
# <a name="basic_istream-class"></a>basic_istream 클래스

이 템플릿 클래스는 문자 특성이 *Tr*([traits_type](../standard-library/basic-ios-class.md#traits_type)이라고도 함) 클래스에 의해 결정되는 `Char_T`([char_type](../standard-library/basic-ios-class.md#char_type)이라고도 함) 형식의 요소가 있는 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_istream : virtual public basic_ios<Char_T, Tr>
```

## <a name="remarks"></a>설명

[operator>>](#op_gt_gt)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 입력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

다른 많은 멤버 함수는 형식이 지정되지 않은 입력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

요소를 추출하는 동안 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(eofbit)` 파일의 끝이 발생하는 경우 두 함수 그룹 모두 호출합니다.

클래스 `basic_istream<Char_T, Tr>` 저장소의 개체:

- 클래스의 [`basic_ios`](../standard-library/basic-ios-class.md) `<Char_T, Tr>`가상 공용 기본 개체입니다.

- 포맷되지 않은 마지막 입력 작업에 대한 `count` 추출 수입니다(이전 코드에서 호출).

## <a name="example"></a>예제

입력 스트림에 대한 자세한 내용은 [basic_ifstream 클래스](../standard-library/basic-ifstream-class.md)에 대한 예제를 참조하세요.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_istream](#basic_istream)|`basic_istream` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[gcount](#gcount)|서식이 지정되지 않은 마지막 입력 동안 읽은 문자 수를 반환합니다.|
|[get](#get)|입력 스트림에서 하나 이상의 문자를 읽습니다.|
|[게라인](#getline)|입력 스트림에서 한 줄을 읽습니다.|
|[무시](#ignore)|현재 읽기 위치에서 많은 요소를 건너뜁니다.|
|[픽](#peek)|읽을 다음 문자를 반환합니다.|
|[putback](#putback)|지정된 문자를 스트림에 넣습니다.|
|[읽기](#read)|스트림에서 지정된 개수의 문자를 읽고 배열에 저장합니다.|
|[readsome](#readsome)|버퍼에서 읽기만 합니다.|
|[seekg](#seekg)|스트림에서 읽기 위치를 이동합니다.|
|[sentry](#sentry)|중첩된 클래스는 선언에서 형식이 지정된 입력 함수 및 형식이 지정되지 않은 입력 함수를 구성하는 개체를 설명합니다.|
|[스왑](#swap)|이 `basic_istream` 개체를 제공된 `basic_istream` 개체 매개 변수로 교환합니다.|
|[동기화](#sync)|스트림의 관련 입력 장치를 스트림의 버퍼와 동기화합니다.|
|[tellg](#tellg)|스트림에서 현재 읽기 위치를 보고합니다.|
|[unget](#unget)|가장 최근에 읽은 문자를 다시 스트림에 넣습니다.|

### <a name="operators"></a>연산자

|연산자|Description|
|-|-|
|[연산자>>](#op_gt_gt)|입력 스트림에 대해 함수를 호출하거나 입력 스트림에서 형식이 지정된 데이터를 읽습니다.|
|[연산자 =](#op_eq)|이 개체에 연산자의 오른쪽에 있는 `basic_istream`을 할당합니다. 복사본을 남기지 않는 `rvalue` 참조와 관련된 이동 할당입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<istream>

**네임스페이스:** std

## <a name="basic_istreambasic_istream"></a><a name="basic_istream"></a>basic_istream:basic_istream

`basic_istream` 형식의 개체를 생성합니다.

```cpp
explicit basic_istream(
    basic_streambuf<Char_T, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>매개 변수

*스트루프 (동부)는*\
[basic_streambuf](../standard-library/basic-streambuf-class.md) 형식의 개체입니다.

*_Isstd*\
표준 스트림인 경우 **true;** 그렇지 **않으면, 거짓**.

*오른쪽*\
복사할 `basic_istream` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 를 호출하여 [`init`](../standard-library/basic-ios-class.md#init) `(strbuf)`기본 클래스를 초기화합니다. 또한 추출 개수에 0을 저장합니다. 이 추출 수에 대한 자세한 내용은 [basic_istream 클래스](../standard-library/basic-istream-class.md) 개요의 설명 섹션을 참조하십시오.

두 번째 생성자는 `move(right)`를 호출하여 기본 개체를 초기화합니다. 또한 추출 `right.gcount()` 개수에 저장하고 *right**에 대한 추출 개수에 0을 저장합니다.

### <a name="example"></a>예제

입력 스트림에 대한 자세한 내용은 [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream)에 대한 예제를 참조하세요.

## <a name="basic_istreamgcount"></a><a name="gcount"></a>basic_istream::gcount

서식이 지정되지 않은 마지막 입력 동안 읽은 문자 수를 반환합니다.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Return Value

추출 개수입니다.

### <a name="remarks"></a>설명

형식이 지정되지 않은 문자를 읽으려면 [basic_istream::get](#get)을 사용하세요.

### <a name="example"></a>예제

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Input
a
```

```Output
Type the letter 'a': a
1
```

## <a name="basic_istreamget"></a><a name="get"></a>basic_istream::get

입력 스트림에서 하나 이상의 문자를 읽습니다.

```cpp
int_type get();

basic_istream<Char_T, Tr>& get(Char_T& Ch);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count, Char_T delimiter);

basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf);
basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf, Char_T delimiter);
```

### <a name="parameters"></a>매개 변수

*횟수*\
*strbuf*에서 읽을 문자 수입니다.

*구분 기호*\
*카운트*하기 전에 발생한 경우 읽기를 종료해야 하는 문자입니다.

*Str*\
쓸 수 있는 문자열입니다.

*채널*\
가져올 문자입니다.

*스트루프 (동부)는*\
쓸 수 있는 버퍼입니다.

### <a name="return-value"></a>Return Value

매개 변수 없는 형식의 get은 읽은 요소를 정수로서 또는 파일 끝으로서 반환합니다. 나머지 형식은 (* `this`) 스트림을 반환합니다.

### <a name="remarks"></a>설명

포맷되지 않은 첫 번째 입력 함수는 가능하면 요소를 `rdbuf->sbumpc`반환하여 추출합니다. 그렇지 않으면 `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)반환합니다. 함수가 요소를 추출하지 않으면 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`을 호출합니다.

두 번째 함수도 같은 방법으로 [int_type](../standard-library/basic-ios-class.md#int_type) 요소 `meta`를 추출합니다. 와 `meta` 같음이 `traits_type::eof`같으면 `setstate(failbit)`함수가 호출합니다. 그렇지 않으면 Ch . *Ch* `traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(meta)` 함수는 __*이 것을__반환합니다.

세 번째 `get(str, count, widen('\n'))`함수가 반환됩니다.

네 번째 함수는 `count - 1` 요소까지 추출하여 *str에서*시작하는 배열에 저장합니다. 함수는 항상 추출하여 저장한 요소 뒤에 `char_type`을 저장합니다. 테스트 순서에서 추출은 다음에서 중지됩니다.

- 파일의 끝.

- 함수가 추출된 후 *구분 기호와*동일한 요소를 추출합니다. 이 경우 요소는 제어된 시퀀스로 다시 배치됩니다.

- 함수 후 요소를 `count - 1` 추출합니다.

함수가 요소를 추출하지 않는 경우 `setstate(failbit)`. 어쨌든 __이쪽은 이것을__반환합니다.

다섯 번째 `get(strbuf, widen('\n'))`함수가 반환됩니다.

여섯 번째 함수는 요소를 추출하고 *strbuf*에 삽입합니다. 추출은 파일 끝 또는 추출되지 않은 *구분 기호와*동일한 요소에서 중지됩니다. 또한 삽입이 실패하거나 예외를 throw하면(catch했지만 다시 throw되지 않음) 문제의 요소를 추출하지 않고 중단합니다. 함수가 요소를 추출하지 않는 경우 `setstate(failbit)`. 어쨌든 함수는 __*this를__반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output
1111
```

## <a name="basic_istreamgetline"></a><a name="getline"></a>basic_istream::getline

입력 스트림에서 한 줄을 가져옵니다.

```cpp
basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type delimiter);
```

### <a name="parameters"></a>매개 변수

*횟수*\
*strbuf*에서 읽을 문자 수입니다.

*구분 기호*\
*카운트*하기 전에 발생한 경우 읽기를 종료해야 하는 문자입니다.

*Str*\
쓸 수 있는 문자열입니다.

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

이러한 포맷되지 않은 입력 함수 `getline(str, count, widen('\n'))`중 첫 번째 함수가 반환됩니다.

두 번째 함수는 `count - 1` 요소까지 추출하여 *str에서*시작하는 배열에 저장합니다. 함수는 항상 추출하여 저장한 요소 뒤에 문자열 종결 문자를 저장합니다. 테스트 순서에서 추출은 다음에서 중지됩니다.

- 파일의 끝.

- 함수가 추출된 후 *구분 기호와*동일한 요소를 추출합니다. 이 경우 요소는 다시 배치되지 않으며 제어된 시퀀스에 추가되지 않습니다.

- 함수 후 요소를 `count - 1` 추출합니다.

함수가 요소 나 `count - 1` 요소를 추출하지 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`않으면 을 호출합니다. 어쨌든 __이쪽은 이것을__반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output
121
```

## <a name="basic_istreamignore"></a><a name="ignore"></a>basic_istream::무시

현재 읽기 위치에서 많은 요소를 건너뜁니다.

```cpp
basic_istream<Char_T, Tr>& ignore(
    streamsize count = 1,
    int_type delimiter = traits_type::eof());
```

### <a name="parameters"></a>매개 변수

*횟수*\
현재 읽기 위치에서 건너뛸 요소의 수입니다.

*구분 기호*\
카운트 전에 발생한 요소는 `ignore` 반환되고 구분 *기호* 이후의 모든 요소를 읽을 수 있도록 합니다.

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

포맷되지 않은 입력 함수는 요소를 *카운트하기* 위해 최대 추출하고 삭제합니다. 그러나 *개수가* 같으면 `numeric_limits<int>::max`임의로 큰 것으로 간주됩니다. 추출은 파일 의 끝이나 *구분기호(추출된* 요소)와 동일한 요소에서 `Ch` `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(Ch)` 일찍 중지됩니다. 함수는 __*이 것을__반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="basic_istreamoperator"></a><a name="op_gt_gt"></a>기본\_istream::연산자>>

입력 스트림에 대해 함수를 호출하거나 입력 스트림에서 형식이 지정된 데이터를 읽습니다.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Char_T, Tr>& (* Pfn)(basic_ios<Char_T, Tr>&));
basic_istream& operator>>(basic_streambuf<Char_T, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>매개 변수

*Pfn*\
함수 포인터입니다.

*스트루프 (동부)는*\
`stream_buf` 형식의 개체입니다.

*발*\
스트림에서 읽은 값입니다.

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

istream> 헤더는 \<여러 전역 추출 연산자도 정의합니다. 자세한 내용은 [operator>> (\<istream>)](../standard-library/istream-operators.md#op_gt_gt)을 참조하세요.

첫 번째 멤버 함수는 `istr >> ws` 양식의 식이 [`ws`](../standard-library/istream-functions.md#ws) `(istr)`호출되도록 한 다음 __*this를__반환합니다. 두 번째 및 세 번째 함수는 "와 [`hex`](../standard-library/ios-functions.md#hex)같은 다른 조작자가 유사하게 작동하도록 합니다. 나머지 함수는 서식이 지정된 입력 함수입니다.

다음 함수는

```cpp
basic_istream& operator>>(
    basic_streambuf<Char_T, Tr>* strbuf);
```

*strbuf가* null 포인터가 아닌 경우 요소를 추출하고 *strbuf에*삽입합니다. 추출은 파일의 끝에서 중지됩니다. 또한 삽입이 실패하거나 예외를 throw하면(catch했지만 다시 throw되지 않음) 문제의 요소를 추출하지 않고 중단합니다. 함수가 요소를 추출하지 않으면 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`을 호출합니다. 어쨌든 함수는 __*this를__반환합니다.

다음 함수는

```cpp
basic_istream& operator>>(bool& val);
```

필드를 [`use_facet`](../standard-library/basic-filebuf-class.md#open) `< num_get<Char_T, InIt>(` [`getloc`](../standard-library/ios-base-class.md#getloc) `).` [`get`](../standard-library/ios-base-class.md#getloc) `( InIt(` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `), Init(0), *this, getloc, val)`추출하고 호출하여 부울 값으로 변환합니다. 여기서는 `InIt` 로 [`istreambuf_iterator`](../standard-library/istreambuf-iterator-class.md) `<Char_T, Tr>`정의됩니다. 함수는 __*이 것을__반환합니다.

각 함수:

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

필드를 추출하고 호출하여 `use_facet<num_get<Char_T, InIt>(getloc).` [`get`](#get) `(InIt(rdbuf), Init(0), *this, getloc, val)`숫자 값으로 변환합니다. `InIt` `istreambuf_iterator<Char_T, Tr>`여기서는 로 정의되며 *val에는* 긴 형식, **서명되지 않은 긴**또는 필요에 따라 **void가** <strong>\*</strong> 있습니다. **long**

변환된 값을 *val*의 유형으로 나타낼 수 없는 경우 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`함수는 을 호출합니다. 어쨌든 함수는 __*this를__반환합니다.

각 함수:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

필드를 추출하고 호출하여 `use_facet<num_get<Char_T, InIt>(getloc).get(InIt(rdbuf), Init(0), *this, getloc, val)`숫자 값으로 변환합니다. 여기서는 `InIt` `istreambuf_iterator<Char_T, Tr>`로 정의되며 *val에는* 필요에 따라 **유형이중** 또는 **긴 이중이** 있습니다.

변환된 값을 *val*의 유형으로 나타낼 수 없는 경우 `setstate(failbit)`함수는 을 호출합니다. 어쨌든 __이쪽은 이것을__반환합니다.

### <a name="example"></a>예제

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="basic_istreamoperator"></a><a name="op_eq"></a>basic_istream::연산자=

이 개체에 연산자의 오른쪽에 있는 `basic_istream`을 할당합니다. 복사본을 남기지 않는 `rvalue` 참조와 관련된 이동 할당입니다.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_ifstream` 개체에 대한 `rvalue` 참조입니다.

### <a name="return-value"></a>Return Value

반환 __*이__.

### <a name="remarks"></a>설명

멤버 연산자가 를 호출합니다. `swap(right)`

## <a name="basic_istreampeek"></a><a name="peek"></a>basic_istream::p

읽을 다음 문자를 반환합니다.

```cpp
int_type peek();
```

### <a name="return-value"></a>Return Value

읽을 다음 문자입니다.

### <a name="remarks"></a>설명

포맷되지 않은 입력 함수는 가능하면 요소를 반환하여 `rdbuf->` [`sgetc`](../standard-library/basic-streambuf-class.md#sgetc)추출합니다. 그렇지 않으면 `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
a abcde
```

## <a name="basic_istreamputback"></a><a name="putback"></a>basic_istream::p

지정된 문자를 스트림에 넣습니다.

```cpp
basic_istream<Char_T, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>매개 변수

*채널*\
스트림에 다시 배치할 문자입니다.

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

[포맷되지 않은 입력 함수는](../standard-library/basic-istream-class.md) 가능한 경우 를 [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`sputbackc`](../standard-library/basic-streambuf-class.md#sputbackc)호출하여 *Ch를*다시 넣습니다. `rdbuf` null 포인터이거나 `sputbackc` 반환 `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)호출이 있는 경우 함수가 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`호출합니다. 어쨌든 __이쪽은 이것을__반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output
qwq
```

## <a name="basic_istreamread"></a><a name="read"></a>basic_istream::읽기

스트림에서 지정된 개수의 문자를 읽고 배열에 저장합니다.

이 메서드는 전달된 값이 정확한지 확인하기 위해 호출자를 사용하므로 보안상 위험할 수 있습니다.

```cpp
basic_istream<Char_T, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*Str*\
문자를 읽을 배열입니다.

*횟수*\
읽을 문자 수입니다.

### <a name="return-value"></a>Return Value

스트림( `*this`)입니다.

### <a name="remarks"></a>설명

포맷되지 않은 입력 함수는 요소를 *카운트하기* 위해 최대 추출하여 *str에서*시작하는 배열에 저장합니다. 추출은 파일 의 끝에서 일찍 중지되며, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`이 경우 함수가 호출합니다. 어쨌든 __이쪽은 이것을__반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
abcde
```

## <a name="basic_istreamreadsome"></a><a name="readsome"></a>basic_istream::읽기

지정한 개수의 문자 값을 읽습니다.

이 메서드는 전달된 값이 정확한지 확인하기 위해 호출자를 사용하므로 보안상 위험할 수 있습니다.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*Str*\
`readsome`이 읽은 문자를 저장하는 배열입니다.

*횟수*\
읽을 문자 수입니다.

### <a name="return-value"></a>Return Value

실제로 읽은 문자 수입니다. [`gcount`](#gcount)

### <a name="remarks"></a>설명

이 포맷되지 않은 입력 함수는 입력 스트림에서 요소를 *카운트하기* 위해 최대 추출하여 배열 *str에*저장합니다.

이 함수는 입력을 기다리지 않고, 읽을 수 있는 데이터는 무엇이든 읽습니다.

### <a name="example"></a>예제

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="basic_istreamseekg"></a><a name="seekg"></a>basic_istream::추구

스트림에서 읽기 위치를 이동합니다.

```cpp
basic_istream<Char_T, Tr>& seekg(pos_type pos);

basic_istream<Char_T, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>매개 변수

*Pos*\
읽기 포인터를 이동할 절대 위치입니다.

*꺼져 있습니다.*\
웨이를 기준으로 읽기 *포인터를*이동하는 오프셋입니다.

*방법*\
[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) 열거형 중 하나입니다.

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 절대 검색을 수행하고 두 번째 멤버 함수는 상대 검색을 수행합니다.

> [!NOTE]
> 표준 C++는 텍스트 파일에서 상대 검색을 지원하지 않으므로 두 번째 멤버 함수를 텍스트 파일과 함께 사용하지 마세요.

[`fail`](../standard-library/basic-ios-class.md#fail) false이면 첫 번째 멤버 `newpos =` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) `(pos)`함수는 `pos_type` 일부 `newpos`임시 개체에 대해 을 호출합니다. false이면 `fail` 두 번째 `newpos = rdbuf->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `( off, way)`함수가 를 호출합니다. `(off_type)newpos == (off_type)(-1)` 두 경우 모두(위치 지정 작업이 실패) `istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`함수가 호출합니다. 두 함수 모두 __반환 *이 .__

true이면 [`fail`](../standard-library/basic-ios-class.md#fail) 멤버 함수는 아무 것도 수행하지 않습니다.

### <a name="example"></a>예제

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="basic_istreamsentry"></a><a name="sentry"></a>basic_istream::센트리

중첩된 클래스는 선언에서 형식이 지정된 입력 함수 및 형식이 지정되지 않은 입력 함수를 구성하는 개체를 설명합니다.

```cpp
class sentry {
   public:
   explicit sentry(
      basic_istream<Char_T, Tr>& _Istr,
      bool _Noskip = false);
   operator bool() const;
   };
```

### <a name="remarks"></a>설명

true이면 `_Istr.` [`good`](../standard-library/basic-ios-class.md#good) 생성자:

- null `_Istr.` [`tie`](../standard-library/basic-ios-class.md#tie) `->` [`flush`](../standard-library/basic-ostream-class.md#flush) `_Istr.tie` 포인터가 아닌 경우 호출합니다.

- 0이 [`ws`](../standard-library/istream-functions.md#ws) `(_Istr)` `_Istr.` [`flags`](../standard-library/ios-base-class.md#flags) `&` [`skipws`](../standard-library/ios-functions.md#skipws) 아닌 경우 효과적으로 호출합니다.

이러한 준비 후에 `_Istr.good` false인 경우 생성자는 `_Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`을 호출합니다. 어떤 경우에도 생성자는 `_Istr.good` 에서 `status`반환된 값을 저장합니다. 나중에 이 `operator bool` 저장된 값을 전달하기 위한 호출입니다.

## <a name="basic_istreamswap"></a><a name="swap"></a>basic_istream::스왑

두 `basic_istream` 개체의 내용을 교환합니다.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_istream` 개체에 대한 lvalue 참조입니다.

### <a name="remarks"></a>설명

멤버 함수는 [`basic_ios::swap`](../standard-library/basic-ios-class.md#swap) `(right)`을 호출합니다. 또한 추출 수를 추출 개수와 *올바른*추출 수를 교환합니다.

## <a name="basic_istreamsync"></a><a name="sync"></a>basic_istream::동기화

스트림의 관련 입력 장치를 스트림의 버퍼와 동기화합니다.

```cpp
int sync();
```

### <a name="return-value"></a>Return Value

null [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) 포인터인 경우 함수는 -1을 반환합니다. 그렇지 않으면 `rdbuf->` [`pubsync`](../standard-library/basic-streambuf-class.md#pubsync)을 호출합니다. 해당 호출이 -1을 반환하면 함수가 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` 호출되고 -1이 반환됩니다. 아닌 경우 함수는 0을 반환합니다.

## <a name="basic_istreamtellg"></a><a name="tellg"></a>basic_istream::텔

스트림에서 현재 읽기 위치를 보고합니다.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Return Value

스트림 내의 현재 위치입니다.

### <a name="remarks"></a>설명

false이면 [`fail`](../standard-library/basic-ios-class.md#fail) 멤버 함수가 [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `(0, cur, in)`반환됩니다. 그렇지 않으면 `pos_type(-1)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="basic_istreamunget"></a><a name="unget"></a>basic_istream::unget

가장 최근에 읽은 문자를 다시 스트림에 넣습니다.

```cpp
basic_istream<Char_T, Tr>& unget();
```

### <a name="return-value"></a>Return Value

스트림 __(*this).__

### <a name="remarks"></a>설명

[포맷되지 않은 입력 함수는](../standard-library/basic-istream-class.md) 가능한 경우 를 호출하여 `rdbuf->` [`sungetc`](../standard-library/basic-streambuf-class.md#sungetc)처럼 스트림의 이전 요소를 다시 넣습니다. [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) null 포인터이거나 `sungetc` 반환 `traits_type::` [`eof`](../standard-library/basic-ios-class.md#eof)호출이 있는 경우 함수가 [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`호출합니다. 어쨌든 __이쪽은 이것을__반환합니다.

실패하는 방법에 `unget` 대한 자세한 [`basic_streambuf::sungetc`](../standard-library/basic-streambuf-class.md#sungetc)내용은 를 참조하십시오.

### <a name="example"></a>예제

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Input
abc
```

```Output
Type 'abc': abc
abc
```

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
