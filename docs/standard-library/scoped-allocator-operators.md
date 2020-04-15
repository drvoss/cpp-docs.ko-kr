---
title: '&lt;scoped_allocator&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 45da89793c3f4ea131404fc3392413e7aea9ef3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373390"
---
# <a name="ltscoped_allocatorgt-operators"></a>&lt;scoped_allocator&gt; 연산자

|||
|-|-|
|[연산자!=](#op_neq)|[연산자==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>연산자!=

두 `scoped_allocator_adaptor` 개체가 다른지 비교합니다.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*오른쪽*\
오른쪽 `scoped_allocator_adaptor` 개체입니다.

### <a name="return-value"></a>Return Value

`!(left == right)`

## <a name="operator"></a><a name="op_eq_eq"></a>연산자==

두 `scoped_allocator_adaptor` 개체가 같은지 테스트합니다.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*오른쪽*\
오른쪽 `scoped_allocator_adaptor` 개체입니다.

### <a name="return-value"></a>Return Value

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>참고 항목

[<scoped_allocator>](../standard-library/scoped-allocator.md)
