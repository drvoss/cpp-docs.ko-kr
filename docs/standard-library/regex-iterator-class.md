---
title: regex_iterator 클래스
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
ms.openlocfilehash: 6bc57d6815fa6f30e26b22e9b7ab758a1ac20e16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374550"
---
# <a name="regex_iterator-class"></a>regex_iterator 클래스

일치 항목에 대한 반복기 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>매개 변수

*입찰가*\
부분 일치에 대한 반복기 형식입니다.

*Elem*\
일치 항목을 찾을 요소의 형식입니다.

*RXtraits*\
요소에 대한 특성 클래스입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 상수 전달 이터레이터 개체를 설명합니다. 반복기 범위 `match_results<BidIt>` 에 정의된 문자 시퀀스에 정규식 개체 `*pregex` 를 반복적으로 적용하여 `[begin, end)`형식의 개체를 추출합니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[regex_iterator](#regex_iterator)|반복기를 생성합니다.|

### <a name="typedefs"></a>Typedefs

|형식 이름|Description|
|-|-|
|[difference_type](#difference_type)|반복기 차이의 형식입니다.|
|[iterator_category](#iterator_category)|반복기 범주의 형식입니다.|
|[포인터(pointer)](#pointer)|일치 항목에 대한 포인터의 형식입니다.|
|[참조](#reference)|일치 항목에 대한 참조의 형식입니다.|
|[regex_type](#regex_type)|일치 항목을 찾을 정규식의 형식입니다.|
|[Value_type](#value_type)|일치 항목의 형식입니다.|

### <a name="operators"></a>연산자

|연산자|Description|
|-|-|
|[연산자!=](#op_neq)|반복기가 같지 않은지 비교합니다.|
|[연산자*](#op_star)|지정된 일치 항목에 액세스합니다.|
|[연산자++](#op_add_add)|반복기를 증가시킵니다.|
|[연산자 =](#op_eq)|반복기가 같은지 비교합니다.|
|[연산자 >](#op_arrow)|지정된 일치 항목에 액세스합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<regex>

**네임스페이스:** std

## <a name="examples"></a>예

정규식에 대한 예제는 다음 항목을 참조하세요.

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [스왑](../standard-library/regex-functions.md#swap)

```cpp
// std__regex__regex_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="regex_iteratordifference_type"></a><a name="difference_type"></a>regex_iterator::d이퍼런스_타입

반복기 차이의 형식입니다.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>설명

이 형식은 `std::ptrdiff_t`의 동의어입니다.

## <a name="regex_iteratoriterator_category"></a><a name="iterator_category"></a>regex_iterator:iterator_category

반복기 범주의 형식입니다.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>설명

이 형식은 `std::forward_iterator_tag`의 동의어입니다.

## <a name="regex_iteratoroperator"></a><a name="op_neq"></a>regex_iterator::연산자!=

반복기가 같지 않은지 비교합니다.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
비교할 반복기입니다.

### <a name="remarks"></a>설명

멤버 함수는 `!(*this == right)`를 반환합니다.

## <a name="regex_iteratoroperator"></a><a name="op_star"></a>regex_iterator::연산자*

지정된 일치 항목에 액세스합니다.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `match`를 반환합니다.

## <a name="regex_iteratoroperator"></a><a name="op_add_add"></a>regex_iterator::연산자++

반복기를 증가시킵니다.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>설명

현재 일치 항목에 문자가 없으면 첫 번째 연산자가 `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`를 호출하고, 그렇지 않으면 저장된 값 `begin` 으로 이동하여 현재 일치 항목 다음의 첫 번째 문자를 가리킨 다음 `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`을 호출합니다. 두 경우 모두 검색에 실패하면 연산자가 개체를 시퀀스의 끝 반복기로 설정합니다. 연산자가 개체를 반환합니다.

두 번째 연산자는 개체의 복사본을 만들고 개체를 증가시킨 다음 복사본을 반환합니다.

## <a name="regex_iteratoroperator"></a><a name="op_eq"></a>regex_iterator::연산자=

반복기가 같은지 비교합니다.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
비교할 반복기입니다.

### <a name="remarks"></a>설명

멤버 함수는 `*this` 시퀀스 끝 이터레이터이거나 시퀀스 끝 이터레이터 *right* 및 `begin == right.begin`. `end == right.end` `pregex == right.pregex` `flags == right.flags` 그렇지 않으면 false를 반환합니다.

## <a name="regex_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_iterator::연산자-&gt;

지정된 일치 항목에 액세스합니다.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>설명

멤버 함수는 저장된 값 `match`의 주소를 반환합니다.

## <a name="regex_iteratorpointer"></a><a name="pointer"></a>regex_iterator::p

일치 항목에 대한 포인터의 형식입니다.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>*`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

## <a name="regex_iteratorreference"></a><a name="reference"></a>regex_iterator:::참조

일치 항목에 대한 참조의 형식입니다.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>&`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

## <a name="regex_iteratorregex_iterator"></a><a name="regex_iterator"></a>regex_iterator:regex_iterator

반복기를 생성합니다.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
일치하는 시퀀스의 시작입니다.

*마지막*\
일치하는 시퀀스의 끝입니다.

*다시*\
일치 항목에 대한 정규식입니다.

*F*\
일치에 대한 플래그입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 시퀀스의 끝 반복기를 생성합니다. 두 번째 생성자는 저장된 값을 `begin` *첫째로*초기화하고, 저장된 `end` 값은 *마지막으로,* 저장된 값은 에서 를, `pregex` `&re` *f를*가진 저장된 값은 `flags` . 그런 다음 `regex_search(begin, end, match, *pregex, flags)`를 호출합니다. 검색에 실패하면 생성자는 개체를 시퀀스의 끝 반복기로 설정합니다.

## <a name="regex_iteratorregex_type"></a><a name="regex_type"></a>regex_iterator:regex_type

일치 항목을 찾을 정규식의 형식입니다.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>설명

typedef는 `basic_regex<Elem, RXtraits>`의 동의어입니다.

## <a name="regex_iteratorvalue_type"></a><a name="value_type"></a>regex_iterator:value_type

일치 항목의 형식입니다.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>설명

이 형식은 `match_results<BidIt>`의 동의어로, 여기서 `BidIt` 는 템플릿 매개 변수입니다.

## <a name="see-also"></a>참고 항목

[\<정규식>](../standard-library/regex.md)\
[regex_constants 클래스](../standard-library/regex-constants-class.md)\
[regex_error 클래스](../standard-library/regex-error-class.md)\
[\<정규식> 함수](../standard-library/regex-functions.md)\
[regex_iterator 클래스](../standard-library/regex-iterator-class.md)\
[\<정규식> 연산자](../standard-library/regex-operators.md)\
[regex_token_iterator 클래스](../standard-library/regex-token-iterator-class.md)\
[regex_traits 클래스](../standard-library/regex-traits-class.md)\
[\<정규식> 타입defs](../standard-library/regex-typedefs.md)
