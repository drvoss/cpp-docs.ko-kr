---
title: any 클래스
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: 050276da665ab6ed3eb53d9e65bfea06b88bcbea
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268755"
---
# <a name="any-class"></a>any 클래스

any 개체 클래스의 상태라고 하는 생성자 요구 사항을 충족시키거나 값을 가지지 않는 any 형식의 인스턴스를 저장합니다.

저장된 인스턴스를 포함된 값이라고 합니다. 두 상태 모두 값이 없거나 값이 있고 포함된 값이 같은 경우 두 상태가 동일합니다.

## <a name="syntax"></a>구문

```cpp
class any
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[any](#any)|`any` 형식의 개체를 생성합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[emplace](#emplace)|any에 값을 설정합니다.|
|[has_value](#has_value)|any가 값이 있는 경우 **true**를 반환합니다.|
|[reset](#reset)|any를 다시 설정합니다.|
|[swap](#swap)|두 개의 any 개체를 교환합니다.|
|[type](#type)|any 형식을 반환합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_eq)|다른 any의 복사본을 사용하여 any를 바꿉니다.|

## <a name="any"></a> 모든

`any` 형식의 개체를 생성합니다. 소멸자가 포함 됩니다.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a> emplace

any에 값을 설정합니다.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a> has_value

any가 값이 있는 경우 **true**를 반환합니다.

```cpp
bool has_value() const noexcept;
```

## <a name="op_eq"></a> 연산자 =

다른 any의 복사본을 사용하여 any를 바꿉니다.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>매개 변수

*right*\
any로 복사되는 any입니다.

## <a name="reset"></a> 다시 설정

any를 다시 설정합니다.

```cpp
void reset() noexcept;
```

## <a name="swap"></a> 교환

두 개의 any 개체를 교환합니다.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a> 형식

any 형식을 반환합니다.

```cpp
const type_info& type() const noexcept;
```
