---
title: 모든 클래스
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
ms.openlocfilehash: 66e74a7fa7f35aae9ac9e1f3ba7520e8d3f9b3f2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203964"
---
# <a name="any-class"></a>모든 클래스

생성자 요구 사항을 충족 하는 모든 형식의 인스턴스를 저장 하거나 클래스의 상태 라고 하는 값을 포함 하지 않습니다.

저장 된 인스턴스를 포함 된 값 이라고 합니다. 두 상태 중 하나에 값이 없거나 둘 다에 값이 있고 포함 된 값이 같으면 두 상태는 동일 합니다.

## <a name="syntax"></a>구문

```cpp
class any
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[일부](#any)|`any` 형식의 개체를 생성합니다.|

### <a name="functions"></a>Functions

|||
|-|-|
|[emplace](#emplace)|모든 값을 설정 합니다.|
|[has_value](#has_value)|**`true`** 에 값이 있으면를 반환 합니다.|
|[reset](#reset)|Any를 다시 설정 합니다.|
|[스왑을](#swap)|두 개체를 바꿉니다.|
|[type](#type)|모든 형식을 반환 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#op_eq)|Any를 다른의 복사본으로 바꿉니다.|

## <a name="any"></a><a name="any"></a>일부

`any` 형식의 개체를 생성합니다. 소멸자도 포함 합니다.

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

## <a name="emplace"></a><a name="emplace"></a>emplace

모든 값을 설정 합니다.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a><a name="has_value"></a>has_value

**`true`** 에 값이 있으면를 반환 합니다.

```cpp
bool has_value() const noexcept;
```

## <a name="operator"></a><a name="op_eq"></a>연산자 =

Any를 다른의 복사본으로 바꿉니다.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
Any로 복사 되는 모든입니다.

## <a name="reset"></a><a name="reset"></a>다시 설정

Any를 다시 설정 합니다.

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a>스왑을

두 개체를 바꿉니다.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a><a name="type"></a> 형식

모든 형식을 반환 합니다.

```cpp
const type_info& type() const noexcept;
```
