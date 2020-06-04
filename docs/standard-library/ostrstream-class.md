---
title: ostrstream 클래스
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: b52ba70607a5214a6aa28f04cdded0b19a56b2f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373539"
---
# <a name="ostrstream-class"></a>ostrstream 클래스

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>설명

이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.

> [!NOTE]
> 이 클래스는 사용되지 않습니다. 대신 [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) 또는 [wostringstream](../standard-library/sstream-typedefs.md#wostringstream)을 사용하는 것이 좋습니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[ostrstream](#ostrstream)|`ostrstream` 형식의 개체를 생성합니다.|

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

## <a name="ostrstreamfreeze"></a><a name="freeze"></a>ostrstream::동결

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

[strstream::동결을](../standard-library/strstreambuf-class.md#freeze) 사용하는 예제를 `freeze`참조하십시오.

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a>오스트스트림::오스트스트림

`ostrstream` 형식의 개체를 생성합니다.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>매개 변수

*Ptr*\
버퍼입니다.

*횟수*\
버퍼 크기(바이트)입니다.

*_Mode*\
버퍼의 입력 및 출력 모드입니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.

### <a name="remarks"></a>설명

두 생성자 모두 클래스 [strstreambuf의](../standard-library/strstreambuf-class.md)저장된 `sb` 개체인 ostream(sb)을 호출하여 기본 클래스를 초기화합니다. [ostream](../standard-library/ostream-typedefs.md#ostream)**sb** 첫 번째 생성자는 `sb` `strstreambuf`호출하여 초기화합니다. 두 번째 생성자는 다음의 두 가지 방법 중 하나로 기본 클래스를 초기화합니다.

- `_Mode`  &  **ios_base ::==** 0인 `ptr` 경우 요소 `count` 배열의 첫 번째 요소를 지정해야 하며 `strstreambuf`생성자가 호출합니다.`ptr` `count` `ptr`

- `ptr` `ptr`그렇지 않으면 첫 번째 요소가 "? `strstreambuf``ptr` `count` `ptr`  +  `strlen` `ptr`

## <a name="ostrstreampcount"></a><a name="pcount"></a>오스트스트림::p 카운트

제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Return Value

제어되는 시퀀스에 기록되는 요소 수의 개수입니다.

### <a name="remarks"></a>설명

멤버 함수는 [rdbuf](#rdbuf) -> [pcount를](../standard-library/strstreambuf-class.md#pcount)반환합니다.

### <a name="example"></a>예제

`pcount`를 사용하는 샘플은 [strstream::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a>오스트스트림::rdbuf

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

## <a name="ostrstreamstr"></a><a name="str"></a>오스트스트림::str

[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.

```cpp
char *str();
```

### <a name="return-value"></a>Return Value

제어되는 시퀀스의 시작 부분에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 [rdbuf](#rdbuf) -> [str을 반환합니다.](../standard-library/strstreambuf-class.md#str)

### <a name="example"></a>예제

을 사용하는 `str`샘플은 [strstream::str을](../standard-library/strstreambuf-class.md#str) 참조하십시오.

## <a name="see-also"></a>참고 항목

[오스트림 (오스트림)](../standard-library/ostream-typedefs.md#ostream)\
[C++ 표준 라이브러리의 나사 안전](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
