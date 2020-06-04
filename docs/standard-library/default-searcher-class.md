---
title: default_searcher 클래스
ms.date: 08/03/2019
f1_keywords:
- functional/std::default_searcher
helpviewer_keywords:
- std::default_searcher [C++]
ms.openlocfilehash: 2c8b93b83b271f787c993f789e1a68f84a60f016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368920"
---
# <a name="default_searcher-class"></a>default_searcher 클래스

A는 `default_searcher` 개체의 생성자에서 지정된 시퀀스를 검색하는 작업에 대한 함수 개체 유형입니다. 검색은 개체의 함수 호출 연산자에게 제공된 다른 시퀀스 내에서 수행됩니다. `default_searcher` [호출st::검색](algorithm-functions.md#search) 검색을 수행 합니다.

## <a name="syntax"></a>구문

```cpp
template <class ForwardIterator, class BinaryPredicate = equal_to<>>
class default_searcher
{
    default_searcher(
        ForwardIterator pat_first,
        ForwardIterator pat_last,
        BinaryPredicate pred = BinaryPredicate());

    template <class ForwardIterator2>
    pair<ForwardIterator2, ForwardIterator2> operator()(
        ForwardIterator2 first,
        ForwardIterator2 last) const;
};
```

## <a name="members"></a>멤버

| | |
| - | - |
| **생성자** | |
| [default_searcher](#default-searcher-constructor) | |
| **연산자** | |
| [연산자()](#operator-call) | |

## <a name="default_searcher-constructor"></a><a name="default-searcher-constructor"></a>default_searcher 생성자

시퀀스를 `default_searcher` 사용하여 함수 객체를 검색하고 같음 조건자로 구성합니다.

```cpp
default_searcher(                   // C++17
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());

constexpr default_searcher(         // C++20
    ForwardIterator pat_first,
    ForwardIterator pat_last,
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>매개 변수

*pat_first*\
검색할 시퀀스의 초기 요소입니다.

*pat_last*\
검색할 시퀀스의 끝입니다.

*Pred*\
시퀀스 요소에 대한 선택적 같음 비교 조건자입니다. 같음 비교 유형이 지정되지 않은 `std::equal_to`경우 기본값은 입니다.

### <a name="remarks"></a>설명

*BinaryPredicate* 또는 *ForwardIterator* 형식의 복사 생성자가 throw하는 예외를 throw합니다.

이 클래스는 C++17의 새로운 클래스입니다. C ++20은 생성자.를 `constexpr`만들었습니다.

## <a name="operator"></a><a name="operator-call"></a>연산자()

함수 연산자의 호출 연산자입니다. 생성자에 지정된 `[first, last)` 시퀀스에 대한 인수 시퀀스 내에서 검색합니다.

```cpp
template <class ForwardIterator2>   // C++17
pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;

template <class ForwardIterator2>   // C++20
constexpr pair<ForwardIterator2, ForwardIterator2> operator()(
    ForwardIterator2 first,
    ForwardIterator2 last) const;
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
내에서 검색할 시퀀스의 초기 요소입니다.

*마지막*\
내에서 검색할 시퀀스의 끝입니다.

### <a name="remarks"></a>설명

반복기 쌍을 반환합니다. 초기 이터레이터 *i는* 다음의 효과적인 결과입니다.

`std::search( first, last, pat_first, pat_last, pred )`.

쌍의 두 번째 이터레이터는 *i** 마지막인 경우 *마지막입니다.* *last* 그렇지 않으면 다음의 효과적인 결과입니다.

`std::next( i, std::distance( pat_first, pat_last ))`.

이 클래스는 C++17의 새로운 클래스입니다. C ++20은 통화 `constexpr`연산자로 만들었습니다.

## <a name="see-also"></a>참고 항목

[\<기능>](functional.md)\
[알고리즘 기능](algorithm-functions.md)\
[std::검색](algorithm-functions.md#search)
