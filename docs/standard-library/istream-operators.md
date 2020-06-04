---
title: '&lt;istream&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 3b9521fde1b5a03389bfc1ad3e35fa407d9d6ac0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363033"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 연산자

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>연산자&gt;&gt;

스트림에서 문자 및 문자열을 추출합니다.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>매개 변수

*채널*\
단일 문자입니다.

*이스트르 (동안)*\
스트림입니다.

*Str*\
문자열입니다.

*발*\
형식입니다.

### <a name="return-value"></a>Return Value

스트림

### <a name="remarks"></a>설명

`basic_istream` 클래스도 여러 가지 추출 연산자를 정의합니다. 자세한 내용은 [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt)를 참조하세요.

함수 템플릿:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

요소까지 `N - 1` 추출하여 *str에서*시작하는 배열에 저장합니다. `Istr.` [너비가](../standard-library/ios-base-class.md#width) 0보다 크면 `Istr.width` *N은* ; 그렇지 않으면 선언할 수 있는 가장 `Elem` 큰 배열의 크기입니다. 함수는 항상 저장 `Elem()` 하는 추출 된 요소 후 값을 저장 합니다. 추출은 파일 의 끝에서 일찍, 값이 `Elem(0)` 있는 문자(추출되지 않은 문자) 또는 [ws에](../standard-library/istream-functions.md#ws)의해 삭제될 요소(추출되지 않은 요소)에서 중지됩니다. 함수가 요소를 추출하지 않으면 `Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`을 호출합니다. 어쨌든 *Istr을* `Istr.width(0)` 호출하고 반환합니다.

**보안 참고 사항** 입력 스트림에서 추출되는 null-terminateed 문자열은 대상 버퍼 *str의*크기를 초과해서는 안 됩니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

함수 템플릿:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

가능하면 요소를 추출하여 *Ch*. 그렇지 않으면 `is.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`을 호출합니다. 어쨌든 *Istr*.

함수 템플릿:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr >> ( char * ) str`를 반환합니다.

함수 템플릿:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr >> ( char& ) Ch`를 반환합니다.

함수 템플릿:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr >> ( char * ) str`를 반환합니다.

함수 템플릿:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr >> ( char& ) Ch`를 반환합니다.

함수 템플릿:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

rvalue `Istr >> val` 참조를 프로세스의 lvalue로 `Istr` 변환합니다.

### <a name="example"></a>예제

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>참고 항목

[\<아이스트림>](../standard-library/istream.md)
