---
title: '&lt;system_error&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 8631cae146a311f1890583900b564471d5a80958
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076255"
---
# <a name="ltsystem_errorgt-operators"></a>&lt;system_error&gt; 연산자

## <a name="operator"></a><a name="op_eq_eq"></a>연산자 = =

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
같은지 테스트할 개체입니다.

*오른쪽*\
같은지 테스트할 개체입니다.

### <a name="return-value"></a>반환 값

개체가 같으면 **true**이고, 개체가 같지 않으면 **false**입니다.

### <a name="remarks"></a>주의

함수는 `left.category() == right.category() && left.value() == right.value()`를 반환합니다.

## <a name="operator"></a><a name="op_neq"></a> operator!=

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
같지 않은지 테스트할 개체입니다.

*오른쪽*\
같지 않은지 테스트할 개체입니다.

### <a name="return-value"></a>반환 값

*왼쪽* 에 전달 된 개체가 *오른쪽*에 전달 된 개체와 같지 않으면 **true** 이 고, 그렇지 않으면입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>주의

함수는 `!(left == right)`를 반환합니다.

## <a name="operatorlt"></a><a name="op_lt"></a> 연산자&lt;

개체가 비교를 위해 전달된 개체보다 작은지 여부를 테스트합니다.

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
비교할 개체입니다.

*오른쪽*\
비교할 개체입니다.

### <a name="return-value"></a>반환 값

*왼쪽* 에 전달 된 개체가 *오른쪽*에 전달 된 개체 보다 작은 경우 **true** 입니다. 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>주의

이 함수는 오류 순서를 테스트합니다.

## <a name="operatorltlt"></a><a name="op_ostream"></a>연산자&lt;&lt;

```cpp
template <class charT, class traits>
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```
