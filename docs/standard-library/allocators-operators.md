---
title: '&lt;allocators&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 7bc37e98ed85582cac8fc7ae21e54a6d5da9e06f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364958"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 연산자

다음은 &lt;할당자에&gt;정의된 전역 템플릿 연산자 함수입니다. 클래스 멤버 연산자 함수는 클래스 설명서를 참조하십시오.

|||
|-|-|
|[연산자!=](#op_neq)|[연산자==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>연산자!=

지정된 클래스의 할당자 개체가 다른지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*왼쪽*|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|
|*오른쪽*|같지 않은지를 테스트할 할당자 개체 중 하나입니다.|

### <a name="return-value"></a>Return Value

할당자 개체가 같지 않으면 **true**이고 할당자 개체가 같으면 **false**입니다.

### <a name="remarks"></a>설명

템플릿 연산자는 `!(left == right)`을 반환합니다.

## <a name="operator"></a><a name="op_eq_eq"></a>연산자==

지정된 클래스의 할당자 개체가 같은지 테스트합니다.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*왼쪽*|같은지를 테스트할 할당자 개체 중 하나입니다.|
|*오른쪽*|같은지를 테스트할 할당자 개체 중 하나입니다.|

### <a name="return-value"></a>Return Value

할당자 개체가 같으면 **true**이고 할당자 개체가 같지 않으면 **false**입니다.

### <a name="remarks"></a>설명

템플릿 연산자가 `left.equals(right)`를 반환합니다.

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
