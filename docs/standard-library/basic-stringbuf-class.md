---
title: basic_stringbuf 클래스
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
ms.openlocfilehash: 578d0e31e08f3e077a908c4344f77da5495df40d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364882"
---
# <a name="basic_stringbuf-class"></a>basic_stringbuf 클래스

배열 개체에 저장된 요소의 시퀀스에서 문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식 요소의 전송을 제어하는 스트림 버퍼에 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*Alloc*\
할당자 클래스입니다.

*Elem*\
문자열 기본 요소의 형식입니다.

*Tr*\
문자열의 기본 요소에서 특수화된 문자 특성입니다.

## <a name="remarks"></a>설명

시퀀스의 변경 내용을 수용하도록 필요에 따라 개체가 할당, 확장 및 해제됩니다.

basic_stringbuf< `Elem`, `Tr`, `Alloc`> 클래스의 개체는 해당 생성자에서 `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) 인수의 복사본을 해당 `stringbuf` 모드 **mode**로 저장합니다.

- `mode & ios_base::in`이 0이 아닌 경우 입력 버퍼에 액세스할 수 있습니다. 자세한 내용은 [basic_streambuf 클래스](../standard-library/basic-streambuf-class.md)를 참조하세요.

- `mode & ios_base::out`이 0이 아닌 경우 출력 버퍼에 액세스할 수 있습니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|`basic_stringbuf` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[allocator_type](#allocator_type)|형식은 템플릿 매개 변수 *Alloc의*동의어입니다.|
|[char_type](#char_type)|형식 이름을 *Elem* 템플릿 매개 변수와 연결합니다.|
|[int_type](#int_type)|이 형식을 `basic_filebuf`범위 내에서 *Tr* 범위에서 동일한 이름의 형식과 동일합니다.|
|[off_type](#off_type)|이 형식을 `basic_filebuf`범위 내에서 *Tr* 범위에서 동일한 이름의 형식과 동일합니다.|
|[pos_type](#pos_type)|이 형식을 `basic_filebuf`범위 내에서 *Tr* 범위에서 동일한 이름의 형식과 동일합니다.|
|[traits_type](#traits_type)|형식 이름을 *Tr* 템플릿 매개 변수와 연결합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[오버플로](#overflow)|가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.|
|[pbackfail](#pbackfail)|보호된 가상 멤버 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.|
|[seekoff](#seekoff)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[seekpos](#seekpos)|보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.|
|[Str](#str)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|
|swap||
|[언더플로](#underflow)|입력 스트림에서 현재 요소를 추출하는 보호된 가상 멤버 함수입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<sstream>

**네임스페이스:** std

## <a name="basic_stringbufallocator_type"></a><a name="allocator_type"></a>basic_stringbuf:allocator_type

형식은 템플릿 매개 변수 *Alloc의*동의어입니다.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringbufbasic_stringbuf"></a><a name="basic_stringbuf"></a>basic_stringbuf:basic_stringbuf

`basic_stringbuf` 형식의 개체를 생성합니다.

```cpp
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.

*Str*\
[basic_string](../standard-library/basic-string-class.md) 형식의 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 입력 버퍼와 출력 버퍼를 제어하는 모든 포인터에 null 포인터를 저장합니다. 자세한 내용은 [basic_streambuf 클래스](../standard-library/basic-streambuf-class.md)의 설명 섹션을 참조하세요. 또한 *_Mode* stringbuf 모드로 저장합니다. 자세한 내용은 [basic_stringbuf 클래스](../standard-library/basic-stringbuf-class.md)의 설명 섹션을 참조하세요.

두 번째 생성자는 문자열 개체 *str에*의해 제어되는 시퀀스의 복사본을 할당합니다. `_Mode & ios_base::in`이 0이 아닌 경우 시퀀스 시작 시 읽기를 시작하도록 입력 버퍼를 설정합니다. `_Mode & ios_base::out`이 0이 아닌 경우 시퀀스 시작 시 쓰기를 시작하도록 출력 버퍼를 설정합니다. 또한 *_Mode* stringbuf 모드로 저장합니다. 자세한 내용은 [basic_stringbuf 클래스](../standard-library/basic-stringbuf-class.md)의 설명 섹션을 참조하세요.

## <a name="basic_stringbufchar_type"></a><a name="char_type"></a>basic_stringbuf:char_type

형식 이름을 *Elem* 템플릿 매개 변수와 연결합니다.

```cpp
typedef Elem char_type;
```

## <a name="basic_stringbufint_type"></a><a name="int_type"></a>basic_stringbuf:int_type

basic_filebuf 범위 내에서 이 형식을 범위의 동일한 이름의 형식과 동일하게 `Tr` 만듭니다.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_stringbufoff_type"></a><a name="off_type"></a>basic_stringbuf:off_type

basic_filebuf 범위 내에서 이 형식을 범위의 동일한 이름의 형식과 동일하게 `Tr` 만듭니다.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_stringbufoverflow"></a><a name="overflow"></a>basic_stringbuf::오버플로우

가득 찬 버퍼에 새 문자를 삽입할 때 호출할 수 있는 보호된 가상 함수입니다.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼에 삽입할 문자 또는 `traits_type::eof`입니다.

### <a name="return-value"></a>Return Value

함수는 정상적으로 실행되지 않으면 `traits_type::eof`를 반환합니다. 아닌 경우 **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*)를 반환합니다.

### <a name="remarks"></a>설명

* \_메타가* **traits_type::**[eof와](../standard-library/char-traits-struct.md#eof)동일하게 비교하지 않으면 보호된 가상 멤버 함수는 **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)*\_(메타)* 요소를 출력 버퍼에 삽입하려고 시도합니다. 수행할 수 있는 방법은 다양합니다.

- 쓰기 위치를 사용할 수 있는 경우 요소를 쓰기 위칭에 저장하고 출력 버퍼에 대해 다음 포인터를 증분할 수 있습니다.

- 출력 버퍼에 대해 새 스토리지 또는 추가 스토리지를 할당하여 쓰기 위치를 사용 가능하게 만들 수 있습니다. 이러한 방식으로 출력 버퍼를 확장하면 연결된 입력 버퍼도 확장됩니다.

## <a name="basic_stringbufpbackfail"></a><a name="pbackfail"></a>basic_stringbuf::p백 실패

보호된 가상 구성원 함수는 요소를 입력 버퍼에 다시 넣은 후 다음 포인터에서 가리키는 현재 요소로 설정하려고 합니다.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>매개 변수

*_Meta*\
버퍼에 삽입할 문자 또는 `traits_type::eof`입니다.

### <a name="return-value"></a>Return Value

함수는 정상적으로 실행되지 않으면 `traits_type::eof`를 반환합니다. 아닌 경우 **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*)를 반환합니다.

### <a name="remarks"></a>설명

*_Meta* **traits_type::**[eof와](../standard-library/char-traits-struct.md#eof)동일하게 비교하는 경우, 밀어낼 요소는 현재 요소 앞에 스트림에 이미 있는 요소입니다. 그렇지 않으면 해당 요소는 **바이트** = **traits_type:to_char_type(_**[to_char_type](../standard-library/char-traits-struct.md#to_char_type) *메타)로*대체됩니다. 함수는 여러 가지 방법으로 요소를 다시 넣을 수 있습니다.

- putback 위치를 사용할 수 있고 여기에 저장된 요소가 byte와 비교 시 같으면 입력 버퍼에 대한 다음 포인터를 감소시킬 수 있습니다.

- putback 위치를 사용할 수 있고 stringbuf 모드에서 시퀀스를 변경하도록 허용하면 (**mode & ios_base::out**이 0이 아님) 함수는 byte를 putback 위치에 저장하고 입력 버퍼에 대한 다음 포인터를 감소시킬 수 있습니다.

## <a name="basic_stringbufpos_type"></a><a name="pos_type"></a>basic_stringbuf::pos_type

basic_filebuf 범위 내에서 이 형식을 범위의 동일한 이름의 형식과 동일하게 `Tr` 만듭니다.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_stringbufseekoff"></a><a name="seekoff"></a>basic_stringbuf::검색오프

보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Off*\
*_Way*상대적으로 추구하는 위치. 자세한 내용은 [basic_stringbuf::off_type](#off_type)을 참조하세요.

*_Way*\
오프셋 작업의 시작 지점입니다. 가능한 값은 [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir)을 참조하세요.

*_Mode*\
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.

### <a name="return-value"></a>Return Value

새 위치 또는 잘못된 스트림 위치를 반환합니다.

### <a name="remarks"></a>설명

`basic_stringbuf<Elem, Tr, Alloc>` 클래스 개체의 경우 스트림 위치는 스트림 오프셋으로만 구성됩니다. 오프셋 0은 제어되는 시퀀스의 첫 번째 요소를 지정합니다.

새 위치는 다음과 같이 결정됩니다.

-  ==  `ios_base::beg` *_Off*. `_Way`

- 새 위치가 현재 스트림 위치와 *_Off.* `_Way`  ==  `ios_base::cur`

- 새 위치가 스트림의 끝과 *_Off.* `_Way`  ==  `ios_base::end`

`_Mode & ios_base::in`이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. `_Mode & ios_base::out`이 0이 아닌 경우 함수는 출력 버퍼에서 읽을 다음 위치를 변경합니다. 스트림이 영향을 받으려면 버퍼가 존재해야 합니다. 위치 지정 작업을 정상적으로 수행하려면 결과 스트림 위치가 제어되는 시퀀스 내에 있어야 합니다. 함수가 두 스트림 위치에 모두 `ios_base::beg` 영향을 `ios_base::end` 미치는 경우 *_Way* 있어야 하며 두 스트림이 모두 동일한 요소에 배치되어야 합니다. 아닌 경우(또는 두 위치 모두 영향을 받지 않는 경우) 배치 작업이 실패합니다.

두 스트림 위치 중 하나 또는 모두를 정상적으로 변경하는 경우 함수는 결과 스트림 위치를 반환합니다. 그렇지 않으면 함수는 실패하며 잘못된 스트림 위치가 반환됩니다.

## <a name="basic_stringbufseekpos"></a><a name="seekpos"></a>basic_stringbuf::seekpos

보호된 가상 멤버 함수는 제어된 스트림의 현재 위치를 변경하려고 합니다.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Sp*\
찾을 위치입니다.

*_Mode*\
포인터 위치에 대한 모드를 지정합니다. 기본적으로는 읽기 및 쓰기 위치를 수정할 수 있습니다.

### <a name="return-value"></a>Return Value

두 스트림 위치 중 하나 또는 모두를 정상적으로 변경하는 경우 함수는 결과 스트림 위치를 반환합니다. 그렇지 않으면 함수는 실패하며 잘못된 스트림 위치가 반환됩니다. 스트림 위치가 잘못되었는지를 확인하려면 반환 값을 `pos_type(off_type(-1))`과 비교합니다.

### <a name="remarks"></a>설명

basic_stringbuf< **Elem**, **Tr**, `Alloc`> 클래스 개체의 경우 스트림 위치는 스트림 오프셋으로만 구성됩니다. 오프셋 0은 제어되는 시퀀스의 첫 번째 요소를 지정합니다. 새 위치는 _ *Sp*에 의해 결정됩니다.

**mode & ios_base::in**이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. **mode & ios_base::out**이 0이 아닌 경우 함수는 입력 버퍼에서 읽을 다음 위치를 변경합니다. 스트림이 영향을 받으려면 버퍼가 존재해야 합니다. 위치 지정 작업을 정상적으로 수행하려면 결과 스트림 위치가 제어되는 시퀀스 내에 있어야 합니다. 아닌 경우(또는 두 위치 모두 영향을 받지 않는 경우) 배치 작업이 실패합니다.

## <a name="basic_stringbufstr"></a><a name="str"></a>basic_stringbuf::str

쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>매개 변수

*_Newstr*\
새 문자열입니다.

### <a name="return-value"></a>Return Value

[basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** 클래스의 개체를 반환합니다. 이 개체의 제어된 시퀀스는 **\*this**에 의해 제어된 시퀀스의 복사본입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 basic_string< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 반환합니다. 이 개체의 제어된 시퀀스는 **\*this**에 의해 제어된 시퀀스의 복사본입니다. 복사되는 시퀀스는 저장된 stringbuf 모드에 따라 달라집니다.

- **mode & ios_base::out**이 0이고 출력 버퍼가 존재하는 경우 시퀀스는 전체 출력 버퍼입니다(`pbase`로 시작되는 [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) 요소).

- **mode & ios_base::in**이 0이 아니고 입력 버퍼가 존재하는 경우 시퀀스는 전체 입력 버퍼입니다(`eback`으로 시작되는 [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) 요소).

- 아닌 경우 복사된 시퀀스는 비어 있습니다.

두 번째 멤버 함수는 현재 ** \*이에**의해 제어되는 모든 시퀀스를 할당 합니다. 그런 다음 *_Newstr*의해 제어되는 시퀀스의 복사본을 할당합니다. **mode & ios_base::in**이 0이 아닌 경우 시퀀스 시작 시 읽기를 시작하도록 입력 버퍼를 설정합니다. **mode & ios_base::out**이 0이 아닌 경우 시퀀스 시작 시 쓰기를 시작하도록 출력 버퍼를 설정합니다.

### <a name="example"></a>예제

```cpp
// basic_stringbuf_str.cpp
// compile with: /EHsc
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   basic_string<char> i( "test" );
   stringstream ss;

   ss.rdbuf( )->str( i );
   cout << ss.str( ) << endl;

   ss << "z";
   cout << ss.str( ) << endl;

   ss.rdbuf( )->str( "be" );
   cout << ss.str( ) << endl;
}
```

```Output
test
zest
be
```

## <a name="basic_stringbuftraits_type"></a><a name="traits_type"></a>basic_stringbuf:traits_type

형식 이름을 *Tr* 템플릿 매개 변수와 연결합니다.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 *Tr*의 동의어입니다.

## <a name="basic_stringbufunderflow"></a><a name="underflow"></a>basic_stringbuf::언더플로우

입력 스트림에서 현재 요소를 추출하는 보호된 가상 함수입니다.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Return Value

함수가 성공할 수 없는 경우 **traits_type 반환합니다.**[eof](../standard-library/char-traits-struct.md#eof) 성공할 경우, 변환된 입력 스트림의 현재 요소를 반환합니다.

### <a name="remarks"></a>설명

보호된 가상 멤버 함수는 입력 `byte` 버퍼에서 현재 요소를 추출하고, 현재 스트림 위치를 진행하고, **traits_type::** **to_int_type(바이트)로**요소를 반환하려고 합니다.[to_int_type](../standard-library/char-traits-struct.md#to_int_type) 읽기 위치를 사용할 수 있는 경우 읽기 위치에 저장된 `byte` 요소로 이동하여 입력 버퍼에 대한 다음 포인터를 진행합니다.

## <a name="basic_streambufswap"></a><a name="swap"></a>basic_streambuf::스왑

이 문자열 버퍼의 내용을 다른 문자열 버퍼로 바꿉니다.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>매개 변수

*다른*\
해당 내용이 이 basic_stringbuf로 바뀌는 basic_stringbuf입니다.

### <a name="remarks"></a>설명

## <a name="basic_stringbufoperator"></a><a name="op_eq"></a>basic_stringbuf::연산자=

연산자 우변의 basic_stringbuf 내용을 좌변의 basic_stringbuf에 할당합니다.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>매개 변수

*다른*\
로캘 특성을 포함하여 해당 내용이 연산자 좌변의 stringbuf에 할당되는 basic_stringbuf입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
