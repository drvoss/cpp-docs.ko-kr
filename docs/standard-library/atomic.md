---
title: '&lt;atomic&gt;'
description: 표준 c + + 라이브러리의 원자성 헤더에서 사용할 수 있는 형식 및 함수에 대해 설명 합니다.
ms.date: 12/06/2019
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
ms.openlocfilehash: 3c5f732dbda701eb7744b1b25a9a8e7426f7a3e2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203903"
---
# <a name="ltatomicgt"></a>&lt;atomic&gt;

원자 단위 연산을 지 원하는 형식을 만드는 데 사용할 클래스 및 클래스 템플릿을 정의 합니다.

## <a name="syntax"></a>구문

```cpp
#include <atomic>
```

## <a name="remarks"></a>설명

> [!NOTE]
> [/Clr: pure](../build/reference/clr-common-language-runtime-compilation.md)를 사용 하 여 컴파일된 코드에서이 헤더는 차단 됩니다. **/Clr: pure** 및 **/clr: Safe** 는 Visual Studio 2017 이상 버전에서 더 이상 사용 되지 않습니다.

원자 연산에는 뮤텍스 잠금을 사용하지 않은 채 여러 스레드를 사용하여 개체를 올바르게 조작하는 데 도움이 되는 두 가지 주요 속성이 있습니다.

- 원자성 작업은 나눌 이기 때문에 다른 스레드의 동일한 개체에 대 한 두 번째 원자성 작업은 첫 번째 원자성 작업 전후에 개체의 상태를 가져올 수 있습니다.

- [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 인수를 기반으로 하는 원자 연산은 동일한 스레드에 있는 다른 원자 연산의 효과를 가시화하기 위해 순서 요구 사항을 설정합니다. 그 결과 순서 요구 사항을 위반하는 컴파일러 최적화는 금지됩니다.

일부 플랫폼에서는 `mutex` 잠금을 사용하지 않고서는 몇몇 형식의 원자 연산을 효율적으로 구현하지 못할 수 있습니다. 원자성 형식은 잠금을 사용 하는 원자성 연산이 없는 경우 *잠금 해제* 입니다.

**C + + 11**: 신호 처리기에서 `obj` `obj.is_lock_free()` 또는 `atomic_is_lock_free(x)` 가 true 인 경우 개체에 대해 원자 단위 작업을 수행할 수 있습니다.

클래스 [atomic_flag](../standard-library/atomic-flag-structure.md) 는 플래그를 포함 하는 최소 원자 형식을 제공 합니다 **`bool`** . 해당 연산은 항상 잠금 해제입니다.

클래스 템플릿은 `atomic<T>` 해당 인수 형식의 개체를 저장 하 `T` 고 저장 된 값에 대 한 원자성 액세스를 제공 합니다. [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)를 사용하여 복사할 수 있고 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)를 사용하여 같음을 테스트할 수 있는 모든 형식을 사용하여 인스턴스화할 수 있습니다. 특히 이 클래스는 이러한 요구 사항을 충족하는 사용자 정의 형식과 함께, 그리고 많은 경우 부동 소수점 형식과 함께 사용할 수 있습니다.

템플릿에는 또한 정수 형식에 대한 특수화 집합 및 포인터에 대한 부분 특수화가 포함됩니다. 이러한 특수화는 기본 템플릿을 통해 사용할 수 없는 추가 작업을 제공 합니다.

## <a name="pointer-specializations"></a>포인터 특수화

`atomic<T *>` 부분 특수화는 모든 포인터 형식에 적용되며, 포인터 산술 연산에 대한 메서드를 제공합니다.

## <a name="integral-specializations"></a>정수 계열 특수화

`atomic<integral>` 특수화는 모든 정수 형식에 적용되며, 기본 템플릿을 통해 사용할 수 없는 추가 작업을 제공 합니다.

각 `atomic<integral>` 형식에는 컴파일 시간에 해당 형식에 대한 연산이 잠금 해제인지를 확인하기 위해 `if directive`에서 사용할 수 있는 해당 매크로가 있습니다. 매크로의 값이 0 이면 해당 형식에 대 한 작업은 잠금이 해제 되지 않습니다. 값이 1이면 연산은 잠금 해제일 수 있으며, 런타임 확인이 필요합니다. 값이 2이면 연산은 잠금 해제입니다. 형식에 대한 연산이 잠금 해제인지를 런타임 시 확인하려면 `atomic_is_lock_free` 함수를 사용할 수 있습니다.

각 정수 계열 형식에 대해 해당 정수 계열 형식의 개체를 관리 하는 해당 하는 명명 된 원자성 형식이 있습니다. 각 `atomic_integral` 형식에는 `atomic<T>`의 해당 인스턴스화와 동일한 멤버 함수 집합이 있으며, 이 형식은 비 멤버 원자성 함수 중 하나로 전달될 수 있습니다.

|`atomic_integral` 형식|정수 형식|`atomic_is_lock_free` 매크로|
|----------------------------|-------------------|---------------------------------|
|`atomic_char`|**`char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_schar`|**`signed char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_uchar`|**`unsigned char`**|ATOMIC_CHAR_LOCK_FREE|
|`atomic_char16_t`|**`char16_t`**|ATOMIC_CHAR16_T_LOCK_FREE|
|`atomic_char32_t`|**`char32_t`**|ATOMIC_CHAR32_T_LOCK_FREE|
|`atomic_wchar_t`|**`wchar_t`**|ATOMIC_WCHAR_T_LOCK_FREE|
|`atomic_short`|**`short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_ushort`|**`unsigned short`**|ATOMIC_SHORT_LOCK_FREE|
|`atomic_int`|**`int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_uint`|**`unsigned int`**|ATOMIC_INT_LOCK_FREE|
|`atomic_long`|**`long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_ulong`|**`unsigned long`**|ATOMIC_LONG_LOCK_FREE|
|`atomic_llong`|**`long long`**|ATOMIC_LLONG_LOCK_FREE|
|`atomic_ullong`|**`unsigned long long`**|ATOMIC_LLONG_LOCK_FREE|

Typedef 이름은 헤더에 정의 된 형식 중 일부에 대 한 원자성 템플릿의 특수화에 대해 존재 \<inttypes.h> 합니다.

|원자성 형식|Typedef 이름|
|-----------------|------------------|
|`atomic_int8_t`|`atomic<int8_t>`|
|`atomic_uint8_t`|`atomic<uint8_t>`|
|`atomic_int16_t`|`atomic<int16_t>`|
|`atomic_uint16_t`|`atomic<uint16_t>`|
|`atomic_int32_t`|`atomic<int32_t>`|
|`atomic_uint32_t`|`atomic<uint32_t>`|
|`atomic_int64_t`|`atomic<int64_t>`|
|`atomic_uint64_t`|`atomic<uint64_t>`|
|`atomic_int_least8_t`|`atomic<int_least8_t>`|
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|
|`atomic_int_least16_t`|`atomic<int_least16_t>`|
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|
|`atomic_int_least32_t`|`atomic<int_least32_t>`|
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|
|`atomic_int_least64_t`|`atomic<int_least64_t>`|
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|
|`atomic_intptr_t`|`atomic<intptr_t>`|
|`atomic_uintptr_t`|`atomic<uintptr_t>`|
|`atomic_size_t`|`atomic<size_t>`|
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|
|`atomic_intmax_t`|`atomic<intmax_t>`|
|`atomic_uintmax_t`|`atomic<uintmax_t>`|

## <a name="structs"></a>구조체

|Name|설명|
|----------|-----------------|
|[atomic 구조체](../standard-library/atomic-structure.md)|저장된 값에 대해 원자 연산을 수행하는 개체를 설명합니다.|
|[atomic_flag 구조체](../standard-library/atomic-flag-structure.md)|플래그를 원자 단위로 설정 하 고 지우는 개체를 설명 합니다 **`bool`** .|

## <a name="enums"></a>열거형

|Name|설명|
|----------|-----------------|
|[memory_order 열거형](../standard-library/atomic-enums.md#memory_order_enum)|메모리 위치에서 동기화 연산에 대한 기호 이름을 제공합니다. 이러한 연산은 하나의 스레드의 할당이 다른 스레드에 표시될 방법에 영향을 미칩니다.|

## <a name="functions"></a>Functions

다음 목록에서로 끝나지 않는 함수는 `_explicit` `_explicit` 의 암시적 [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 인수를 포함 하는 경우를 제외 하 고 해당의 의미 체계를 갖습니다 `memory_order_seq_cst` .

|Name|설명|
|----------|-----------------|
|[atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong)|*원자 비교 및 교환* 작업을 수행합니다.|
|[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)|*원자 비교 및 교환* 작업을 수행합니다.|
|[atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak)|*약한 원자 비교 및 교환* 작업을 수행합니다.|
|[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)|*약한 원자 비교 및 교환* 작업을 수행합니다.|
|[atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange)|저장된 값을 대체합니다.|
|[atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit)|저장된 값을 대체합니다.|
|[atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add)|기존의 저장된 값에 지정된 값을 더합니다.|
|[atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit)|기존의 저장된 값에 지정된 값을 더합니다.|
|[atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and)|지정된 값 및 기존의 저장된 값에 대해 비트 `and`를 수행합니다.|
|[atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit)|지정된 값 및 기존의 저장된 값에 대해 비트 `and`를 수행합니다.|
|[atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or)|지정된 값 및 기존의 저장된 값에 대해 비트 `or`를 수행합니다.|
|[atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit)|지정된 값 및 기존의 저장된 값에 대해 비트 `or`를 수행합니다.|
|[atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub)|기존의 저장된 값에서 지정된 값을 뺍니다.|
|[atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit)|기존의 저장된 값에서 지정된 값을 뺍니다.|
|[atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor)|지정된 값 및 기존의 저장된 값에 대해 비트 `exclusive or`를 수행합니다.|
|[atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit)|지정된 값 및 기존의 저장된 값에 대해 비트 `exclusive or`를 수행합니다.|
|[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)|개체의 플래그를 `atomic_flag` 로 설정 합니다 **`false`** .|
|[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)|개체의 플래그를 `atomic_flag` 로 설정 합니다 **`false`** .|
|[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)|개체의 플래그를 `atomic_flag` 로 설정 합니다 **`true`** .|
|[atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit)|개체의 플래그를 `atomic_flag` 로 설정 합니다 **`true`** .|
|[atomic_init](../standard-library/atomic-functions.md#atomic_init)|`atomic` 개체에서 저장된 값을 설정합니다.|
|[atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free)|지정된 개체에 대한 원자 연산이 잠금 해제인지를 지정합니다.|
|[atomic_load](../standard-library/atomic-functions.md#atomic_load)|값을 원자 단위로 검색합니다.|
|[atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit)|값을 원자 단위로 검색합니다.|
|[atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence)|동일한 스레드에서 실행되는 신호 처리기가 있는 호출 스레드에서 fence 간 메모리 순서 요구 사항을 설정하는 *fence* 역할을 수행합니다.|
|[atomic_store](../standard-library/atomic-functions.md#atomic_store)|값을 원자 단위로 저장합니다.|
|[atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit)|값을 원자 단위로 저장합니다.|
|[atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence)|다른 fence와 관련하여 메모리 순서 요구 사항을 설정하는 *fence* 역할을 수행합니다.|
|[kill_dependency](../standard-library/atomic-functions.md#kill_dependency)|가능한 종속성 체인을 중단합니다.|

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[C + + 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)
