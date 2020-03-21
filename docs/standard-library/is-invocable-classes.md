---
title: is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r 클래스
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: 53394a10464e2688953cd1b5703530e2719b7593
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076449"
---
# <a name="is_invocable-is_invocable_r-is_nothrow_invocable-is_nothrow_invocable_r-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable, is_nothrow_invocable_r 클래스

이러한 템플릿은 지정 된 인수 형식을 사용 하 여 형식을 호출할 수 있는지 여부를 결정 합니다. `is_invocable_r` 및 `is_nothrow_invocable_r`는 호출 결과를 특정 형식으로 변환할 수 있는지도 결정 합니다. `is_nothrow_invocable` 및 `is_nothrow_invocable_r`는 호출에서 예외를 throw 하지 않는 것으로 알려진 있는지도 결정 합니다. C + + 17에 추가 되었습니다.

## <a name="syntax"></a>구문

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>매개 변수

*호출 가능*\
쿼리할 호출 가능 형식입니다.

*Args*\
쿼리할 인수 형식입니다.

*변환할* 수 있는\
*호출 가능* 결과의 형식은로 변환할 수 있어야 합니다.

## <a name="remarks"></a>주의

`is_invocable` 형식 조건자는 확인 되지 않은 *컨텍스트에서 인수 인수를 사용* 하 여 호출할 *수 있는 호출 가능 형식을 호출할* 수 있는 경우 true입니다.

`is_invocable_r` 형식 조건자는 확인 되지 않은 *컨텍스트에서 인수 인수* 를 사용 하 여 호출할 *수 있는 호출 가능 형식을 호출할* 수 있는 경우 true 이며, *변환할*수 있는 결과 형식을 생성 합니다.

`is_nothrow_invocable` 형식 조건자는 확인 되지 않은 *컨텍스트에서 인수 인수* 를 사용 하 여 호출할 수 있는 호출 가능 형식이 호출 될 수 있는 경우 true이 고, 이러한 호출은 예외를 throw 하지 않는 것으로 *알려져 있습니다.*

`is_nothrow_invocable_r` 형식 조건자는 확인 되지 않은 *컨텍스트에서 인수 인수* 를 사용 하 *여 호출 가능 형식으로* *변환할 수*있는 결과 형식을 생성 하 고 이러한 호출을 예외를 throw 하지 않는 것으로 알려진 경우 true입니다.

매개 변수 pack *Args* 의 *변환*가능 하 고, *호출 가능*하 고, 형식에 대 한 각 형식은 완전 한 형식, 알 수 없는 범위 배열 또는 cv 정규화 된 **void**여야 합니다. 그렇지 않으면 조건자의 동작이 정의 되지 않습니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits >

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
