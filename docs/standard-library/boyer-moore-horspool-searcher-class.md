---
title: boyer_moore_horspool_searcher 클래스
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_horspool_searcher
helpviewer_keywords:
- std::boyer_moore_horspool_searcher [C++]
ms.openlocfilehash: 4d404b414ad632e02be5f4e9fad0e22cefb86ce2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366785"
---
# <a name="boyer_moore_horspool_searcher-class"></a>boyer_moore_horspool_searcher 클래스

클래스는 `boyer_moore_horspool_searcher` Boyer-Moore-Horspool 알고리즘을 사용하여 개체의 생성자에 지정된 시퀀스를 검색하는 함수 개체 유형입니다. 검색은 개체의 함수 호출 연산자에게 제공된 다른 시퀀스 내에서 수행됩니다. 이 클래스는 [std::search의](algorithm-functions.md#search)오버로드 중 하나에 매개 변수로 전달됩니다.

## <a name="syntax"></a>구문

```cpp
template <
    class RandomAccessIterator,
    class Hash = hash<typename iterator_traits<RandomAccessIterator>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_horspool_searcher
{
    boyer_moore_horspool_searcher(
        RandomAccessIterator pat_first,
        RandomAccessIterator pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>멤버

| | |
| - | - |
| **생성자** | |
| [boyer_moore_horspool_searcher](#boyer-moore-horspool-searcher-constructor) | |
| **연산자** | |
| [연산자()](#operator-call) | |

## <a name="boyer_moore_horspool_searcher-constructor"></a><a name="boyer-moore-horspool-searcher-constructor"></a>boyer_moore_horspool_searcher 생성자

시퀀스, `boyer_moore_horspool_searcher` 해시 함수 개체 및 같음 조건자 검색을 사용 하 여 함수 개체를 생성 합니다.

```cpp
boyer_moore_horspool_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>매개 변수

*pat_first*\
검색할 시퀀스의 초기 요소입니다.

*pat_last*\
검색할 시퀀스의 끝입니다.

*Hf*\
시퀀스 요소를 해시하는 데 사용되는 호출 가능한 개체입니다.

*Pred*\
시퀀스 요소에 대한 선택적 같음 비교 조건자입니다. 같음 비교 유형이 지정되지 않은 `std::equal_to`경우 기본값은 입니다.

### <a name="remarks"></a>설명

*BinaryPredicate,* *해시*또는 *RandomAccessIterator* 형식의 복사 생성자 또는 *BinaryPredicate* 또는 *해시의*호출 연산자가 throw하는 예외를 throw합니다.

이 클래스는 C++17의 새로운 클래스입니다.

## <a name="operator"></a><a name="operator-call"></a>연산자()

함수 개체의 호출 연산자입니다. 생성자에 지정된 `[first, last)` 시퀀스에 대한 인수 시퀀스 내에서 검색합니다.

```cpp
template <class ForwardIterator2>   // C++17
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>매개 변수

*첫 번째*\
내에서 검색할 시퀀스의 초기 요소입니다.

*마지막*\
내에서 검색할 시퀀스의 끝입니다.

### <a name="remarks"></a>설명

검색 패턴이 `[pat_first, pat_last)` 비어 있으면 `make_pair(first, first)`을 반환합니다. 검색 패턴을 찾을 수 없는 `make_pair(last, last)`경우 을 반환합니다. 그렇지 않으면 조건자 *pred에* `[pat_first, pat_last)` 따라 동일한 시퀀스의 `[first, last)` 시작과 끝에 한 쌍의 이터레이터를 반환합니다.

이 클래스는 C++17의 새로운 클래스입니다.

## <a name="see-also"></a>참고 항목

[\<기능>](functional.md)\
[알고리즘 기능](algorithm-functions.md)\
[boyer_moore_searcher 클래스](boyer-moore-searcher-class.md)\
[std::검색](algorithm-functions.md#search)
