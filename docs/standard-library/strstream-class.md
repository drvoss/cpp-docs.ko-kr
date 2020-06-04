---
title: strstream 클래스
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 047b7e9d7fdece75137980b013d43abf1d5e3ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376627"
---
# <a name="strstream-class"></a>strstream 클래스

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>설명

이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.

> [!NOTE]
> 이 클래스는 사용되지 않습니다. 대신 [stringstream](../standard-library/sstream-typedefs.md#stringstream) 또는 [wstringstream](../standard-library/sstream-typedefs.md#wstringstream)을 사용하는 것이 좋습니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[strstream](#strstream)|`strstream` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[동결](#freeze)|스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.|
|[pcount](#pcount)|제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.|
|[rdbuf](#rdbuf)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|
|[Str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<strstream >

**네임스페이스:** std

## <a name="strstreamfreeze"></a><a name="freeze"></a>스트스트림::동결

스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>매개 변수

*_Freezeit*\
스트림을 고정할지 여부를 나타내는 **bool입니다.**

### <a name="remarks"></a>설명

멤버 함수는 [rdbuf](#rdbuf) -> [동결(_](../standard-library/strstreambuf-class.md#freeze) *Freezeit)을*호출합니다.

### <a name="example"></a>예제

[strstreambuf::동결을](../standard-library/strstreambuf-class.md#freeze) 사용하는 예제를 `freeze`참조하십시오.

## <a name="strstreampcount"></a><a name="pcount"></a>스트스트림::p 카운트

제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Return Value

제어되는 시퀀스에 기록되는 요소 수의 개수입니다.

### <a name="remarks"></a>설명

멤버 함수는 [rdbuf](#rdbuf) -> [pcount를](../standard-library/strstreambuf-class.md#pcount)반환합니다.

### <a name="example"></a>예제

pcount를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>스트스트림::rdbuf

스트림의 연결된 strstreambuf 개체에 대한 포인터를 반환합니다.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Return Value

스트림의 연결된 strstreambuf 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 형식의 `pointer` 저장된 스트림 버퍼의 주소를 [strstreambuf에](../standard-library/strstreambuf-class.md)반환합니다.

### <a name="example"></a>예제

`rdbuf`를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="strstreamstr"></a><a name="str"></a>스트스트림::str

[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.

```cpp
char *str();
```

### <a name="return-value"></a>Return Value

제어되는 시퀀스의 시작 부분에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 [rdbuf](#rdbuf) -> [str을 반환합니다.](../standard-library/strstreambuf-class.md#str)

### <a name="example"></a>예제

을 사용하는 `str`샘플은 [strstreambuf::str을](../standard-library/strstreambuf-class.md#str) 참조하십시오.

## <a name="strstreamstrstream"></a><a name="strstream"></a>스트스트림::스트스트림

`strstream` 형식의 개체를 생성합니다.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*횟수*\
버퍼의 크기입니다.

*_Mode*\
버퍼의 입력 및 출력 모드입니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.

*Ptr*\
버퍼입니다.

### <a name="remarks"></a>설명

두 생성자 모두 [streambuf](../standard-library/streambuf-typedefs.md#streambuf) **(sb)를**호출하여 `sb` 기본 클래스를 초기화합니다. [strstreambuf](../standard-library/strstreambuf-class.md) 첫 번째 생성자는 `sb` [strstreambuf를](../standard-library/strstreambuf-class.md#strstreambuf)호출하여 초기화합니다. 두 번째 생성자는 다음의 두 가지 방법 중 하나로 기본 클래스를 초기화합니다.

- `strstreambuf` `ptr` `count` `ptr` *ptr* `count` **ios_base::app**ios_base 경우 ::== 0, 다음 ptr 요소배열의 첫 번째 요소를 지정 해야 합니다., 그리고 생성자 호출 ( , `_Mode`  & 

- 그렇지 않으면 *ptr은* 첫 번째 요소가 *ptr에*의해 지정된 C 문자열을 포함하는 카운트 요소 배열의 `strstreambuf`첫 `ptr` `count`번째 `ptr`  +  `strlen` `ptr`요소를 지정해야 하며 생성자는 호출합니다.

## <a name="see-also"></a>참고 항목

[Iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
