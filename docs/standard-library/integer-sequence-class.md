---
title: integer_sequence 클래스
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
helpviewer_keywords:
- std::index_sequence
- std::make_index_sequence
- std::integer_sequence
- std::make_integer_sequence
- std::index_sequence_for
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
ms.openlocfilehash: d0de2e56e1f6b8e68e5989f21ecd89b9646caa1b
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076468"
---
# <a name="integer_sequence-class"></a>integer_sequence 클래스

정수 시퀀스를 나타냅니다. std::tuple\<T...>과 같이 인수로 함수에 전달되는 variadic 형식의 매개 변수 팩을 추론하고 확장하는 데 사용할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>매개 변수

*T*\
값의 형식입니다. bool, char, char16_t, char32_t, wchar_t, 부호 있는 정수 또는 부호 없는 정수 등 정수 계열 형식이어야 합니다.

*Vals*\
정수 계열 형식 T 값의 시퀀스를 나타내는 비형식 매개 변수 팩입니다.

## <a name="members"></a>멤버

|||
|-|-|
|`static size_t size() noexcept`|시퀀스의 요소 수입니다.|
|`typedef T value_type`|시퀀스에 있는 각 요소의 형식입니다. 정수 계열 형식이어야 합니다.|

## <a name="remarks"></a>주의

함수로 직접 전달되는 매개 변수 팩은 특별한 라이브러리 도우미 없이 압축을 풀 수 있습니다. 매개 변수 팩이 함수로 전달되는 형식의 일부이고 요소에 액세스하는 데 인덱스가 필요한 경우 `integer_sequence`와 관련 형식 별칭 `make_integer_sequence`, `index_sequence`, `make_index_sequence` 및 `index_sequence_for`를 사용하면 가장 쉽게 압축을 풀 수 있습니다.

## <a name="example"></a>예제

다음 예제는 최초 제안 [N3658](https://wg21.link/n3658)을 기반으로 합니다. 이 예제에서는 `integer_sequence`를 사용하여 `std::tuple`에서 `std::array<T,N>`을 만드는 방법 및 `integer_sequence`를 사용하여 튜플 멤버를 얻는 방법을 보여 줍니다.

`a2t` 함수에서 `index_sequence`는 `integer_sequence` 정수 계열 형식을 기반으로 하는 `size_t`의 별칭입니다. `make_index_sequence`는 컴파일 시간에 호출자에 의해 전달되는 배열과 동일한 수의 요소로 0부터 시작하는 `index_sequence`를 만드는 별칭입니다. `a2t`는 값별로 `index_sequence`를 `a2t_`에 전달합니다. 여기서 `a[I]...` 식은 `I`의 압축을 풉니다. 그러면 요소는 개별 인수로 사용되는 `make_tuple`에 공급됩니다. 예를 들어 시퀀스에 세 개의 요소가 포함되어 있으면 `make_tuple`이 make_tuple(a[0], a[1], a[2])로 호출됩니다. 물론 배열 요소 자체는 임의 형식일 수 있습니다.

Apply 함수는 [std:: tuple](../standard-library/tuple-class.md)을 허용 하 고 `tuple_size` 도우미 클래스를 사용 하 여 `integer_sequence`를 생성 합니다. [Tuple_size](../standard-library/tuple-size-class-tuple.md) 참조 형식에서 작동 하지 않기 때문에 [std::d ecay_t](../standard-library/decay-class.md) 가 필요 합니다. `apply_` 함수는 튜플 멤버의 압축을 풀고 별도의 인수로 함수 호출에 전달합니다. 이 예제에서 함수는 값을 출력하는 간단한 람다 식입니다.

```cpp
#include <stddef.h>
#include <iostream>
#include <tuple>
#include <utility>
#include <array>
#include <string>

using namespace std;

// Create a tuple from the array and the index_sequence
template<typename Array, size_t... I>
auto a2t_(const Array& a, index_sequence<I...>)
{
    return make_tuple(a[I]...);
}

// Create an index sequence for the array, and pass it to the
// implementation function a2t_
template<typename T, size_t N>
auto a2t(const array<T, N>& a)
{
    return a2t_(a, make_index_sequence<N>());
}

// Call function F with the tuple members as separate arguments.
template<typename F, typename Tuple = tuple<T...>, size_t... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return forward<F>(f)(get<I>(forward<Tuple>(args))...);
}

// Create an index_sequence for the tuple, and pass it with the
// function object and the tuple to the implementation function apply_
template<typename F, typename Tuple = tuple<T...>>
decltype(auto) apply(F&& f, Tuple&& args)
{
    using Indices = make_index_sequence<tuple_size<decay_t<Tuple>>::value >;
    return apply_(forward<F>(f), forward<Tuple>(args), Indices());
}

int main()
{
    const array<string, 3> arr { "Hello", "from", "C++14" };

    //Create a tuple given a array
    auto tup = a2t(arr);

    // Extract the tuple elements
    apply([](const string& a, const string& b, const string& c) {cout << a << " " << b << " " << c << endl; }, tup);

    char c;
    cin >> c;
}
```

매개 변수 팩에 대한 `index_sequence`를 만들려면 `index_sequence_for`\<sizeof...(T)>의 별칭인 `make_index_sequence`\<T...>를 사용합니다.

## <a name="requirements"></a>요구 사항

헤더: \<type_traits\>

네임스페이스: std

## <a name="see-also"></a>참고 항목

[Ellipses 및 Variadic 템플릿](../cpp/ellipses-and-variadic-templates.md)
