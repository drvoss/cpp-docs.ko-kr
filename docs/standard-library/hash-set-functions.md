---
title: '&lt;hash_set&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: d7df6b3c5dc0d0d493d17b3e9995bc4758ffd6d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370592"
---
# <a name="lthash_setgt-functions"></a>&lt;hash_set&gt; 함수

|||
|-|-|
|[스왑](#swap)|[swap(hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a><a name="swap"></a>스왑

> [!NOTE]
> 이 API는 더 이상 사용되지 않습니다. [unordered_set 클래스](../standard-library/unordered-set-class.md)를 대신 사용하는 것이 좋습니다.

두 hash_set의 요소를 교환합니다.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
hash_set 교환할 요소를 제공하거나 hash_set 요소는 *왼쪽*hash_set 요소와 교환되어야 합니다.

*왼쪽*\
hash_set 그 요소는 hash_set 권리의 것과 교환될 수 *있습니다.*

### <a name="remarks"></a>설명

템플릿 `swap` 함수는 멤버 함수 `left.` [스왑()을](../standard-library/hash-set-class.md#swap)`right`실행하기 위해 hash_set 컨테이너 클래스에 특화된 알고리즘이다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전

**template \<class T> void swap(T&, T&),**

는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예제

`swap`의 템플릿 버전 사용 예제를 보려면 멤버 클래스 [hash_set::swap](../standard-library/hash-set-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a>스왑 (hash_multiset)

> [!NOTE]
> 이 API는 더 이상 사용되지 않습니다. [unordered_set 클래스](../standard-library/unordered-set-class.md)를 대신 사용하는 것이 좋습니다.

두 hash_multiset의 요소를 교환합니다.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
교환할 요소를 제공하는 hash_multiset 또는 hash_multiset *hash_multiset*교환할 수 있습니다.

*왼쪽*\
hash_multiset 그 요소는 hash_multiset *권리의*것과 교환되어야한다 .

### <a name="remarks"></a>설명

템플릿 `swap` 함수는 멤버 함수 `left.` [스왑()을](../standard-library/hash-multiset-class.md#swap)`right`실행하기 hash_multiset 컨테이너 클래스에 특화된 알고리즘입니다. 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전

**template \<class T> void swap(T&, T&),**

는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예제

`swap`의 템플릿 버전 사용 예제를 보려면 멤버 클래스 [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[<hash_set>](../standard-library/hash-set.md)
