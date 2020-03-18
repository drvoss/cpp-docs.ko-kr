---
title: '&lt;sstream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 707d35123797b84b2b7cef1d1cfd9005e4becb1c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425132"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 함수

||
|-|
|[swap](#sstream_swap)|

## <a name="sstream_swap"></a>  swap

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

|매개 변수|Description|
|---------------|-----------------|
|*left*|`sstream` 개체에 대한 참조입니다.|
|*right*|`sstream` 개체에 대한 참조입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`을 실행합니다.

## <a name="see-also"></a>참고 항목

[\<sstream>](../standard-library/sstream.md)
