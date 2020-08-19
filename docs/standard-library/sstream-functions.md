---
title: '&lt;sstream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 722cba257b12bb753aaa61ac2f430df76c2ceb93
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560376"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 함수

||
|-|
|[스왑을](#sstream_swap)|

## <a name="swap"></a><a name="sstream_swap"></a> 스왑을

두 `sstream` 개체 간에 값을 교환합니다.

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
`sstream` 개체에 대한 참조입니다.

*오른쪽*\
`sstream` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`를 실행합니다.

## <a name="see-also"></a>참고 항목

[\<sstream>](../standard-library/sstream.md)
