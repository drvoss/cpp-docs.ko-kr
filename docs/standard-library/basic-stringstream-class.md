---
title: basic_stringstream 클래스
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: f08689b1080837f042abfb3c4c52bb0ad558a448
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364864"
---
# <a name="basic_stringstream-class"></a>basic_stringstream 클래스

**Elem,** **Tr,** `Alloc`> 클래스의 스트림 버퍼를 사용하여 요소 및 인코딩된 개체의 삽입 및 추출을 제어하는 개체에 [basic_stringbuf 대해](../standard-library/basic-stringbuf-class.md)< 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*Alloc*\
할당자 클래스입니다.

*Elem*\
문자열 기본 요소의 형식입니다.

*Tr*\
문자열의 기본 요소에서 특수화된 문자 특성입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> 스트림 버퍼를 사용하여 요소 및 인코딩 된 개체의 `Elem`삽입 및 추출을 제어하는 `Tr`개체를 설명하고 문자 특성은 클래스에 의해 `Alloc`결정되고 그 요소는 클래스의 할당자가 할당합니다. 이 개체는 basic_stringbuf< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 저장합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[basic_stringstream](#basic_stringstream)|`basic_stringstream` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[allocator_type](#allocator_type)|이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[rdbuf](#rdbuf)|`pointer` 형식의 저장된 스트림 버퍼의 주소를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem` `Alloc` , `Tr`> 반환합니다.|
|[Str](#str)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<sstream>

**네임스페이스:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a>basic_stringstream:allocator_type

이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a>basic_stringstream:basic_stringstream

`basic_stringstream` 형식의 개체를 생성합니다.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.

*Str*\
`basic_string` 형식의 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 [basic_iostream](../standard-library/basic-iostream-class.md) **(sb)를**호출하여 `sb` 기본 클래스를 초기화하며, [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< 여기서 `Alloc` basic_stringbuf**Elem,** **Tr**,> 클래스의 저장된 개체입니다. 또한 **< 엘렘,** **tr,** `Alloc`> ()basic_stringbuf `_Mode` `sb` 호출하여 초기화합니다.

두 번째 생성자는 basic_iostream( **sb**)를 호출하여 기본 개체를 초기화합니다. 또한 **< 엘렘,** **Tr** `Alloc` ,> (_ Str, `_Mode`)basic_stringbuf `sb` 호출하여 초기화합니다. *Str*

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a>basic_stringstream:rdbuf

**pointer** 형식의 저장된 스트림 버퍼 주소를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>로 반환합니다.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Return Value

**elem,** **Tr,** `Alloc`> `pointer`< basic_stringbuf 형식의 저장된 스트림 버퍼의 주소입니다.

### <a name="example"></a>예제

`rdbuf`의 사용 예제는 [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)를 참조하세요.

## <a name="basic_stringstreamstr"></a><a name="str"></a>basic_stringstream::str

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
