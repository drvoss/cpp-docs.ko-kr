---
title: basic_ostringstream 클래스
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: 9e10474d3e4fb2a37e8ab52f77495758c37e8a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376776"
---
# <a name="basic_ostringstream-class"></a>basic_ostringstream 클래스

< **Elem,** **Tr**, `Alloc`> [클래스](../standard-library/basic-stringbuf-class.md)basic_stringbuf 스트림 버퍼에 요소 및 인코딩된 개체의 삽입을 제어하는 개체에 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*Alloc*\
할당자 클래스입니다.

*Elem*\
문자열 기본 요소의 형식입니다.

*Tr*\
문자열의 기본 요소에서 특수화된 문자 특성입니다.

## <a name="remarks"></a>설명

클래스는 요소 및 인코딩된 개체의 삽입을 스트림 버퍼에 제어하는 개체에 `Elem`대해 설명하며, 형식의 `Tr`요소, 클래스에 의해 문자 특성이 결정되고 `Alloc`클래스의 할당자가 해당 요소를 할당하는 개체를 설명합니다. 이 개체는 basic_stringbuf< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 저장합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|`basic_ostringstream` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[allocator_type](#allocator_type)|형식은 템플릿 매개 변수 *Alloc의*동의어입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[rdbuf](#rdbuf)|`pointer` 형식의 저장된 스트림 버퍼의 주소를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem` `Alloc` , `Tr`> 반환합니다.|
|[Str](#str)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<sstream>

**네임스페이스:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a>basic_ostringstream:allocator_type

형식은 템플릿 매개 변수 *Alloc의*동의어입니다.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a>basic_ostringstream:basic_ostringstream

Basic_ostringstream 형식의 개체를 생성합니다.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.

*Str*\
`basic_string` 형식의 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 [basic_ostream](../standard-library/basic-ostream-class.md) **(sb)를**호출하여 `sb` 기본 클래스를 초기화하며, 여기서 `Alloc` 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**,> 저장된 개체입니다. 또한 basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`)을 호출하여 **sb**를 초기화합니다.

두 번째 생성자는 basic_ostream( **sb**)를 호출하여 기본 개체를 초기화합니다. 또한 **< 엘렘,** **Tr**, `Alloc`> (_ *Str,* `_Mode` `ios_base::out`&#124;)basic_stringbuf `sb` 호출하여 초기화합니다.

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a>basic_ostringstream::rdbuf

형식의 `pointer` 저장된 스트림 버퍼의 주소를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**, `Alloc`> 반환합니다.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Return Value

저장된 스트림 버퍼의 주소, `pointer` **< Elem,** **Tr,** `Alloc`> basic_stringbuf 형식입니다.

### <a name="remarks"></a>설명

멤버 함수는 저장된 `pointer` 스트림 버퍼의 주소를 반환하여 **elem,** `Alloc` **Tr,**> basic_stringbuf<.

### <a name="example"></a>예제

`rdbuf`의 사용 예제는 [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)를 참조하세요.

## <a name="basic_ostringstreamstr"></a><a name="str"></a>basic_ostringstream::str

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

클래스 [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr** `Alloc` ,> 의 개체를 반환하며, 제어시퀀스는 ** \*이에**의해 제어되는 시퀀스의 복사본입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 [rdbuf](#rdbuf) -> [str을 반환합니다.](../standard-library/basic-stringbuf-class.md#str) 두 번째 멤버 `rdbuf`  -> 함수는 **str**()를 `_Newstr`호출합니다.

### <a name="example"></a>예제

[basic_stringbuf::str을](../standard-library/basic-stringbuf-class.md#str) 사용하는 예제는 `str`을 참조하십시오.

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
