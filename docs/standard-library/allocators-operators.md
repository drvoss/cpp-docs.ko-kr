---
title: '&lt;allocators&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 2d2f928ab3773ed8e0b0afdc0113db2ef5b2a3dd
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561220"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 연산자

이러한 함수는 할당자에 정의 된 전역 템플릿 연산자 함수 &lt; &gt; 입니다. 클래스 멤버 연산자 함수는 클래스 설명서를 참조 하세요.

|||
|-|-|
|[연산자! =](#op_neq)|[연산자 = =](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a> 연산자! =

지정된 클래스의 할당자 개체가 다른지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
같지 않은지를 테스트할 할당자 개체 중 하나입니다.

*오른쪽*\
같지 않은지를 테스트할 할당자 개체 중 하나입니다.

### <a name="return-value"></a>Return Value

**`true`** 할당자 개체가 같지 않으면이 고, 그렇지 않으면입니다. **`false`** 할당자 개체가 같으면입니다.

### <a name="remarks"></a>설명

템플릿 연산자는 `!(left == right)`을 반환합니다.

## <a name="operator"></a><a name="op_eq_eq"></a> 연산자 = =

지정된 클래스의 할당자 개체가 같은지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

*비어*\
같은지를 테스트할 할당자 개체 중 하나입니다.

*오른쪽*\
같은지를 테스트할 할당자 개체 중 하나입니다.

### <a name="return-value"></a>Return Value

**`true`** 할당자 개체가 같으면이 고, 그렇지 않으면입니다. **`false`** 할당자 개체가 같지 않으면입니다.

### <a name="remarks"></a>설명

템플릿 연산자가 `left.equals(right)`를 반환합니다.

## <a name="see-also"></a>참고 항목

[\<allocators>](allocators-header.md)
