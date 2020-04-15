---
title: '&lt;sstream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: bdf7cd26b25680eb7e5270fdc8ae7dac0d10f70f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336648"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 함수

||
|-|
|[스왑](#sstream_swap)|

## <a name="swap"></a><a name="sstream_swap"></a>스왑

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

|매개 변수|설명|
|---------------|-----------------|
|*왼쪽*|`sstream` 개체에 대한 참조입니다.|
|*오른쪽*|`sstream` 개체에 대한 참조입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`를 실행합니다.

## <a name="see-also"></a>참고 항목

[\<>](../standard-library/sstream.md)
