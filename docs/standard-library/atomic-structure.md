---
title: atomic 구조체
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 1b3b60d71fcdf68fdf215820535c3bfb3d4dfb2b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456741"
---
# <a name="atomic-structure"></a>atomic 구조체

*Ty* 형식으로 저장된 값에 대하여 원자 연산을 수행하는 개체에 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>멤버

|멤버|설명|
|----------|-----------------|
|**생성자**||
|[atomic](#atomic)|atomic 개체를 생성합니다.|
|**연산자**||
|[atomic:: operator Ty](#op_ty)|저장된 값을 읽고 반환합니다. ([atomic::load](#load))|
|[atomic::operator=](#op_eq)|지정된 값을 사용하여 저장된 값을 바꿉니다. ([atomic::store](#store))|
|[atomic::operator++](#op_inc)|저장된 값을 증가시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic::operator+=](#op_add_eq)|지정된 값을 저장된 값에 더합니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic::operator--](#op_dec)|저장된 값을 감소시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic::operator-=](#op_sub_eq)|지정된 값을 저장된 값에서 뺍니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.|
|[atomic::operator&=](#op_and_eq)|지정된 값과 저장된 값에 대해 비트 and를 수행합니다. 정수 계열 특수화에서만 사용됩니다.|
|[atomic::operator&#124;=](#op_or_eq)|지정된 값과 저장된 값에 대해 비트 or를 수행합니다. 정수 계열 특수화에서만 사용됩니다.|
|[atomic::operator^=](#op_xor_eq)|지정된 값과 저장된 값에 배타적 비트 or 연산을 수행합니다. 정수 계열 특수화에서만 사용됩니다.|
|**함수**||
|[compare_exchange_strong](#compare_exchange_strong)|**this** 에 대해 *atomic_compare_and_exchange* 작업을 수행 하 고 결과를 반환 합니다.|
|[compare_exchange_weak](#compare_exchange_weak)|**this** 에 대해 *weak_atomic_compare_and_exchange* 작업을 수행 하 고 결과를 반환 합니다.|
|[fetch_add](#fetch_add)|지정된 값을 저장된 값에 더합니다.|
|[fetch_and](#fetch_and)|지정된 값과 저장된 값에 대해 비트 and를 수행합니다.|
|[fetch_or](#fetch_or)|지정된 값과 저장된 값에 대해 비트 or를 수행합니다.|
|[fetch_sub](#fetch_sub)|지정된 값을 저장된 값에서 뺍니다.|
|[fetch_xor](#fetch_xor)|지정된 값과 저장된 값에 배타적 비트 or 연산을 수행합니다.|
|[is_lock_free](#is_lock_free)|**this**에 대한 원자성 작업이 *잠금 해제*인지 여부를 지정합니다. 원자 형식의 어떤 원자 연산도 잠금을 사용하지 않는 경우 해당 원자 형식을 *잠금 해제*라고 합니다.|
|[load](#load)|저장된 값을 읽고 반환합니다.|
|[store](#store)|지정된 값을 사용하여 저장된 값을 바꿉니다.|

## <a name="remarks"></a>설명

*Ty* 형식은 *사소하게 복사할 수* 있어야 합니다. 즉, [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)를 사용하여 바이트를 복사하면 원래 개체와 비교하여 동일한 유효한 *Ty* 개체가 생성되어야 합니다. [compare_exchange_weak](#compare_exchange_weak) 및 [compare_exchange_strong](#compare_exchange_strong) 멤버 함수는 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)를 사용하여 두 개의 *Ty* 값이 같은지 여부를 확인합니다. 이러한 함수는 *Ty* 정의 `operator==`를 사용하지 않습니다. `atomic` 멤버 함수는 `memcpy`를 사용하여 *Ty* 형식의 값을 복사합니다.

모든 포인터 형식에 대한 부분 특수화인 **atomic\<Ty \* >** 가 있습니다. 특수화를 사용하면 관리되는 포인터 값에 오프셋을 더하거나 값에서 오프셋을 뺄 수 있습니다. 산술 연산은 `ptrdiff_t` 형식의 인수를 사용하고, 일반 주소 산술과 일관되도록 *Ty*의 크기에 따라 해당 인수를 조정합니다.

**bool**을 제외한 모든 정수 계열 형식에 대한 특수화가 있습니다. 각 특수화에서는 원자 산술 및 논리 연산을 위한 다양한 방법을 제공합니다.

||||
|-|-|-|
|**atomic\<char>**|**atomic\<signed char>**|**atomic\<unsigned char>**|
|**atomic\<char16_t>**|**atomic\<char32_t>**|**atomic\<wchar_t>**|
|**atomic\<short>**|**atomic\<unsigned short>**|**atomic\<int>**|
|**atomic\<unsigned int>**|**atomic\<long>**|**atomic\<unsigned long>**|
|**원자\<long long >**|**원자성\<부호 없는 long long >**|

정수 특수화는 해당 `atomic_integral` 형식에서 파생됩니다. 예를 들어 **atomic\<unsigned int >** 은 `atomic_uint`에서 파생 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<atomic>

**네임스페이스:** std

## <a name="atomic"></a>atomic::atomic

atomic 개체를 생성합니다.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
초기화 값입니다.

### <a name="remarks"></a>설명

원자성 개체를 복사 하거나 이동할 수 없습니다.

atomic\<*Ty*>의 인스턴스화된 개체는 집합체 초기화를 사용하는 것이 아니라 *Ty* 형식의 인수를 사용하는 생성자에 의해서만 초기화될 수 있습니다. 그러나 atomic_integral 개체는 집합체 초기화를 사용해야만 초기화할 수 있습니다.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a>atomic:: operator *Ty*

템플릿에 지정된 형식에 대한 연산자 atomic\<*Ty*>입니다. **\*this**에 저장된 값을 검색합니다.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>설명

이 연산자는 `memory_order_seq_cst` [memory_order](atomic-enums.md)을 적용 합니다.

## <a name="op_eq"></a> atomic::operator=

지정된 값을 저장합니다.

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty* 개체입니다.

### <a name="return-value"></a>반환 값

*Value*을 반환 합니다.

## <a name="op_inc"></a>atomic::operator++

저장된 값을 증가시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>반환 값

처음 두 연산자는 증가 된 값을 반환 합니다. 마지막 두 연산자는 증가값 앞의 값을 반환 합니다. 연산자는 [memory_order](atomic-enums.md)을 `memory_order_seq_cst` 사용 합니다.

## <a name="op_add_eq"></a>atomic::operator +=

지정된 값을 저장된 값에 더합니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
정수 계열 또는 포인터 값입니다.

### <a name="return-value"></a>반환 값

더하기의 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

이 연산자는 `memory_order_seq_cst` [memory_order](atomic-enums.md)을 사용 합니다.

## <a name="op_dec"></a> atomic::operator--

저장된 값을 감소시킵니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>반환 값

처음 두 연산자는 감소된 값을 반환합니다. 마지막 두 연산자는 감소 전의 값을 반환합니다. 연산자는 `memory_order_seq_cst` [memory_order](atomic-enums.md)를 사용합니다.

## <a name="op_sub_eq"></a> atomic::operator-=

지정된 값을 저장된 값에서 뺍니다. 정수 계열 및 포인터 특수화에서만 사용됩니다.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
정수 계열 또는 포인터 값입니다.

### <a name="return-value"></a>반환 값

뺄셈 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

이 연산자는 `memory_order_seq_cst` [memory_order](atomic-enums.md)을 사용 합니다.

## <a name="op_and_eq"></a>atomic::operator&=

지정된 값과 **\*this**에 저장된 값에 대하여 비트 and를 수행합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

### <a name="return-value"></a>반환 값

비트 and의 결과입니다.

### <a name="remarks"></a>설명

이 연산자는 읽기-수정-쓰기 작업을 수행하여 **\*this**의 저장된 값을 *Value*와 **\*this**에 저장된 현재 값의 비트 and로, `memory_order_seq_cst` [memory_order](atomic-enums.md)의 제약 내에서 바꿉니다.

## <a name="op_or_eq"></a>atomic:: operator&#124;=

지정된 값과 **\*this**의 저장된 값에 대해 비트 or를 수행합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

### <a name="return-value"></a>반환 값

비트 or의 결과입니다.

### <a name="remarks"></a>설명

이 연산자는 읽기-수정-쓰기 작업을 수행하여 **\*this**에 저장된 값을 *Value* 및 **\*this**에 저장된 현재 값의 비트 or로, `memory_order_seq_cst` [memory_order](atomic-enums.md) 제약 조건 내에서 바꿉니다.

## <a name="op_xor_eq"></a> atomic::operator^=

지정된 값과 **\*this**의 저장된 값에 대해 비트 배타적 or를 수행합니다. 정수 계열 특수화에서만 사용됩니다.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

### <a name="return-value"></a>반환 값

배타적 비트 or의 결과입니다.

### <a name="remarks"></a>설명

이 연산자는 읽기-수정-쓰기 작업을 수행하여 **\*this**에 저장된 값을 *Value* 및 **\*this**에 저장된 현재 값의 비트 배타적 or로, `memory_order_seq_cst` [memory_order](atomic-enums.md) 제약 조건 내에서 바꿉니다.

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

**\*this**에 대해 원자성 비교 및 교환 작업을 수행 합니다.

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*.Exp*\
*Ty*형식의 값입니다.

*Value*\
*Ty*형식의 값입니다.

*Order1*\
첫 `memory_order` 번째 인수입니다.

*Order2*\
두 번째 `memory_order` 인수입니다.

### <a name="return-value"></a>반환 값

값 비교 결과를 나타내는 **bool** 입니다.

### <a name="remarks"></a>설명

원자 비교 및 교환 작업은 **\*this**에 저장된 값을 *Exp*와 비교합니다. 값이 같으면 작업은 읽기-수정-쓰기 작업을 사용하고 *Order1*로 지정된 메모리 순서 제약 조건을 적용하여 **\*this**에 저장된 값을 *Value*로 바꿉니다. 값이 같지 않으면 작업에서 **\*this**에 저장된 값을 사용하여 *Exp*를 대체하고 *Order2*로 지정된 메모리 순서 제약 조건을 적용합니다.

두 번째 `memory_order`를 포함하지 않는 오버로드는 *Order1*의 값을 기반으로 하는 암시적 *Order2*를 사용합니다. *Order1*이 `memory_order_acq_rel`이면 *Order2*는 `memory_order_acquire`입니다. *Order1*이 `memory_order_release`이면 *Order2*는 `memory_order_relaxed`입니다. 다른 모든 경우에는 *Order2*가 *Order1*과 같습니다.

두 개의 매개 변수를 사용하는 `memory_order` 오버로드의 경우 *Order2*의 값은 `memory_order_release` 또는 `memory_order_acq_rel`이 아니어야 하며 *Order1*의 값보다 더 강력하지 않아야 합니다.

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

**\*this**에서 약한 원자 비교 및 교환 작업을 수행 합니다.

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*.Exp*\
*Ty*형식의 값입니다.

*Value*\
*Ty*형식의 값입니다.

*Order1*\
첫 `memory_order` 번째 인수입니다.

*Order2*\
두 번째 `memory_order` 인수입니다.

### <a name="return-value"></a>반환 값

값 비교 결과를 나타내는 **bool** 입니다.

### <a name="remarks"></a>설명

원자 비교 및 교환 작업은 **\*this**에 저장된 값을 *Exp*와 비교합니다. 값이 같으면 작업은 읽기-수정-쓰기 작업을 사용하고 *Order1*로 지정된 메모리 순서 제약 조건을 적용하여 **\*this**에 저장된 값을 *Value*로 바꿉니다. 값이 같지 않으면 작업에서 **\*this**에 저장된 값을 사용하여 *Exp*를 대체하고 *Order2*로 지정된 메모리 순서 제약 조건을 적용합니다.

약한 원자 비교 및 교환 작업은 비교 된 값이 동일한 경우 교환을 수행 합니다. 값이 같지 않으면 작업에서 exchange를 수행 하는 것이 보장 되지 않습니다.

두 번째 `memory_order`를 포함하지 않는 오버로드는 *Order1*의 값을 기반으로 하는 암시적 *Order2*를 사용합니다. *Order1*이 `memory_order_acq_rel`이면 *Order2*는 `memory_order_acquire`입니다. *Order1*이 `memory_order_release`이면 *Order2*는 `memory_order_relaxed`입니다. 다른 모든 경우에는 *Order2*가 *Order1*과 같습니다.

두 개의 매개 변수를 사용하는 `memory_order` 오버로드의 경우 *Order2*의 값은 `memory_order_release` 또는 `memory_order_acq_rel`이 아니어야 하며 *Order1*의 값보다 더 강력하지 않아야 합니다.

## <a name="exchange"></a> atomic::exchange

지정된 값을 사용하여 **\*this**의 저장된 값을 바꿉니다.

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

교환 전 **\*this**의 저장된 값입니다.

### <a name="remarks"></a>설명

이 작업은 *Value*를 사용하여 **\*this**에 저장된 값을 *Order*에 지정된 메모리 제약 조건 내에서 대체하는 읽기-수정-쓰기 작업을 수행합니다.

## <a name="fetch_add"></a> atomic::fetch_add

**\*this**에 저장된 값을 페치한 다음 지정된 값을 저장된 값에 추가합니다.

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

추가하기 전에 **\*this**에 저장된 값을 포함하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

`fetch_add` 메서드는 읽기-수정-쓰기 작업을 수행하여 **\*this**에 저장된 값에 *Value*를 원자 단위로 추가하고 *Order*에 의해 지정된 메모리 제약 조건을 적용합니다.

## <a name="fetch_and"></a> atomic::fetch_and

값과 **\*this**에 저장된 기존 값에 대해 비트 and를 수행합니다.

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

비트 and의 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

`fetch_and` 메서드는 읽기-수정-쓰기 작업을 수행하여 *Order*로 지정된 메모리 제약 조건 내에서 **\*this**의 저장된 값을 *Value* 및 **\*this**에 저장된 현재 값의 비트 and로 바꿉니다.

## <a name="fetch_or"></a> atomic::fetch_or

값 및 **\*this**에 저장된 기존 값에 대해 비트 or를 수행합니다.

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

비트 or의 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

`fetch_or` 메서드는 읽기-수정-쓰기 작업을 수행하여 *Order*로 지정된 제약 조건 내에서 **\*this**에 저장된 값을 *Value* 및 **\*this**에 저장된 현재 값의 비트 or로 바꿉니다.

## <a name="fetch_sub"></a> atomic::fetch_sub

지정된 값을 저장된 값에서 뺍니다.

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

뺄셈 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

`fetch_sub` 메서드는 읽기-수정-쓰기 작업을 수행하여 *Order*로 지정된 메모리 제약 조건 내에서 **\*this**에 저장된 값에서 *Value*를 원자 단위로 뺍니다.

## <a name="fetch_xor"></a> atomic::fetch_xor

값 및 **\*this**에 저장된 기존 값에 대해 비트 배타적 or를 수행합니다.

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty*형식의 값입니다.

*Order*\
`memory_order`

### <a name="return-value"></a>반환 값

배타적 비트 or의 결과를 포함 하는 *Ty* 개체입니다.

### <a name="remarks"></a>설명

`fetch_xor` 메서드는 읽기-수정-쓰기 작업을 수행하여 *Order*로 지정된 제약 조건 내에서 **\*this**에 저장된 값을 *Value* 및 **\*this**에 저장된 현재 값의 비트 배타적 or로 바꿉니다.

## <a name="is_lock_free"></a> atomic::is_lock_free

**\*this**에 대한 원자성 작업이 잠금 해제인지 여부를 지정합니다.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>반환 값

**\*this**에 대한 원자성 작업이 잠금 해제이면 true이고, 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

원자성 형식은 잠금을 사용하는 원자성 연산이 없는 경우 잠금 해제됩니다.

## <a name="load"></a>atomic:: load

지정 된 메모리 제약 조건 내에서 **\*this**의 저장 된 값을 검색 합니다.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>매개 변수

*Order*\
`memory_order` *순서* 는 `memory_order_release` 또는 `memory_order_acq_rel`가 아니어야 합니다.

### <a name="return-value"></a>반환 값

**\*this**에 저장된 검색된 값입니다.

## <a name="store"></a> atomic::store

지정된 값을 저장합니다.

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>매개 변수

*Value*\
*Ty* 개체입니다.

*Order*\
`memory_order` 제약 조건입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 *Order*로 지정 `*this`된 메모리 제약 조건 내에서 *Value* 을 원자 단위로 저장 합니다.

## <a name="see-also"></a>참고자료

[\<atomic>](../standard-library/atomic.md)\
[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)
