---
title: 선택적&gt; 연산자 &lt;
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: c5d0de435180054b186400384fc0583df5b03246
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425288"
---
# <a name="ltoptionalgt-operators"></a>선택적&gt; 연산자 &lt;

## <a name="op_eq_eq"></a>연산자 = =

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체와 같은지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

## <a name="op_neq"></a> operator!=

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체와 같지 않은지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `!(left == right)`를 반환합니다.

## <a name="op_lt"></a> 연산자&lt;

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 작은지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌변의 목록이 연산자 우변의 목록보다 작지만 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.

## <a name="op_lt_eq"></a>  operator&lt;=

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 작거나 같은지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌변의 목록이 연산자 우변의 목록보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `!(right < left)`를 반환합니다.

## <a name="op_gt"></a> 연산자&gt;

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 큰지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌변의 목록이 연산자 우변의 목록보다 크면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `right < left`를 반환합니다.

## <a name="op_gt_eq"></a>연산자&gt;=

연산자의 좌변에 있는 `optional` 개체가 우변에 있는 `optional` 개체보다 크거나 같은지 테스트합니다.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

*오른쪽*\
`optional`, `nullopt_t`또는 `T`형식의 개체입니다.

### <a name="return-value"></a>Return Value

연산자 좌변의 **가 연산자 우변의** 보다 크거나 같으면 `optional`true`optional`이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left < right)`를 반환합니다.
