---
title: Concurrency 네임스페이스 함수(AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::all_memory_fence
- amp/Concurrency::atomic_compare_exchange
- amp/Concurrency::atomic_fetch_dec
- amp/Concurrency::atomic_fetch_max
- amp/Concurrency::atomic_fetch_min
- amp/Concurrency::copy
- amp/Concurrency::direct3d_abort
- amp/Concurrency::direct3d_printf
- amp/Concurrency::global_memory_fence
- amp/Concurrency::tile_static_memory_fence
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
ms.openlocfilehash: 1187b745a6d8c903c22958185be8d98a6e3d0204
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376342"
---
# <a name="concurrency-namespace-functions-amp"></a>Concurrency 네임스페이스 함수(AMP)

||||
|-|-|-|
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|
|[atomic_exchange 함수(C++ AMP)](#atomic_exchange)|[atomic_fetch_add 함수(C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and 함수(C++ AMP)](#atomic_fetch_and)|
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or 함수(C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub 기능(C++ AMP)](#atomic_fetch_sub)|
|[atomic_fetch_xor 함수(C++ AMP)](#atomic_fetch_xor)|[copy](#copy)|[copy_async](#copy_async)|
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|
|[global_memory_fence](#global_memory_fence)|[parallel_for_each 함수(C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|

## <a name="all_memory_fence"></a><a name="all_memory_fence"></a>all_memory_fence

모든 메모리 액세스가 완료될 때까지 타일의 모든 스레드 실행을 차단합니다. 이렇게 하면 모든 메모리 액세스가 스레드 타일의 다른 스레드에 표시되고 프로그램 순서대로 실행됩니다.

```cpp
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Barrier*<br/>
`tile_barrier` 개체입니다.

## <a name="amp_uninitialize"></a><a name="amp_uninitialize"></a>amp_uninitialize

C++ AMP 런타임을 초기화하지 않습니다. 응용 프로그램 수명 동안 이 함수를 여러 번 호출하는 것은 합법적입니다. 이 함수를 호출한 후 C++ AMP API를 호출하면 C++ AMP 런타임이 다시 초기화됩니다. 이 함수에 대한 호출에서 C++ AMP 개체를 사용하는 것은 불법이며 이렇게 하면 정의되지 않은 동작이 발생합니다. 또한 이 함수와 다른 AMP API를 동시에 호출하는 것은 불법이며 정의되지 않은 동작이 발생합니다.

```cpp
void __cdecl amp_uninitialize();
```

## <a name="atomic_compare_exchange"></a><a name="atomic_compare_exchange"></a>atomic_compare_exchange

같음의 첫 번째 인수에 지정된 메모리 위치에 저장된 값을 두 번째 지정된 인수의 값과 원자적으로 비교하고 값이 동일한 경우 메모리 위치의 값이 세 번째 지정된 인수의 값으로 변경됩니다.

```cpp
inline bool atomic_compare_exchange(
    _Inout_ int* _Dest,
    _Inout_ int* _Expected_value,
    int value
    ) restrict(amp)

inline bool atomic_compare_exchange(
    _Inout_ unsigned int* _Dest,
    _Inout_ unsigned int* _Expected_value,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
비교할 값 중 하나를 읽고 새 값(있는 경우)을 저장할 위치입니다.

*_Expected_value*<br/>
비교할 두 번째 값을 읽는 위치입니다.

*value*<br/>
에 지정된 메모리 위치에 저장할 값은 `_Dest` `_Dest` `_Expected_value`와 같습니다.

### <a name="return-value"></a>Return Value

작업이 성공하면 **true입니다.** 그렇지 **않으면, 거짓**.

## <a name="atomic_exchange-function-c-amp"></a><a name="atomic_exchange"></a>atomic_exchange 기능(C++ AMP)

원자 단위 작업으로 대상 위치의 값을 설정합니다.

```cpp
inline int atomic_exchange(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_exchange(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)

inline float atomic_exchange(
    _Inout_ float* _Dest,
    float value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
대상 위치에 대한 포인터입니다.

*value*<br/>
새 값입니다.

### <a name="return-value"></a>Return Value

대상 위치의 원본 값입니다.

## <a name="atomic_fetch_add-function-c-amp"></a><a name="atomic_fetch_add"></a>atomic_fetch_add 기능(C++ AMP)

메모리 위치 값에 원자적으로 값을 추가합니다.

```cpp
inline int atomic_fetch_add(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_add(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
메모리 위치에 대한 포인터입니다.

*value*<br/>
추가할 값입니다.

### <a name="return-value"></a>Return Value

메모리 위치의 원본 값입니다.

## <a name="atomic_fetch_and-function-c-amp"></a><a name="atomic_fetch_and"></a>atomic_fetch_and 기능(C++ AMP)

원자적으로 비트로 AND 작업값과 메모리 위치의 값을 수행합니다.

```cpp
inline int atomic_fetch_and(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_and(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
메모리 위치에 대한 포인터입니다.

*value*<br/>
비트별 및 계산에 사용할 값입니다.

### <a name="return-value"></a>Return Value

메모리 위치의 원본 값입니다.

## <a name="atomic_fetch_dec"></a><a name="atomic_fetch_dec"></a>atomic_fetch_dec

지정된 메모리 위치에 저장된 값을 원자적으로 감소시입니다.

```cpp
inline int atomic_fetch_dec(_Inout_ int* _Dest
    ) restrict(amp)

inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
값의 메모리에 있는 위치입니다.

### <a name="return-value"></a>Return Value

메모리 위치에 저장된 원래 값입니다.

## <a name="atomic_fetch_inc"></a><a name="atomic_fetch_inc"></a>atomic_fetch_inc

지정된 메모리 위치에 저장된 값을 원자적으로 증가시입니다.

```cpp
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
증분할 값의 메모리 위치입니다.

### <a name="return-value"></a>Return Value

메모리 위치에 저장된 원래 값입니다.

## <a name="atomic_fetch_max"></a><a name="atomic_fetch_max"></a>atomic_fetch_max

원자적으로 첫 번째 인수에 지정된 메모리 위치에 저장된 값과 두 번째 인수에 지정된 값 사이의 최대값을 계산하고 동일한 메모리 위치에 저장합니다.

```cpp
inline int atomic_fetch_max(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_max(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
비교할 값 중 하나를 읽고 두 값의 최대값을 저장할 위치입니다.

*value*<br/>
지정된 위치의 값과 비교할 값입니다.

### <a name="return-value"></a>Return Value

지정된 위치에 저장된 원래 값입니다.

## <a name="atomic_fetch_min"></a><a name="atomic_fetch_min"></a>atomic_fetch_min

원자적으로 첫 번째 인수에 지정된 메모리 위치에 저장된 값과 두 번째 인수에 지정된 값 사이의 최소값을 계산하고 동일한 메모리 위치에 저장합니다.

```cpp
inline int atomic_fetch_min(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_min(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
비교할 값 중 하나를 읽고 두 값의 최소값을 저장할 위치입니다.

*value*<br/>
지정된 위치의 값과 비교할 값입니다.

### <a name="return-value"></a>Return Value

지정된 위치에 저장된 원래 값입니다.

## <a name="atomic_fetch_or-function-c-amp"></a><a name="atomic_fetch_or"></a>atomic_fetch_or 기능(C++ AMP)

값 및 메모리 위치의 값으로 비트 OR 연산을 원자 단위로 수행합니다.

```cpp
inline int atomic_fetch_or(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_or(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
메모리 위치에 대한 포인터입니다.

*value*<br/>
비트 OR 계산에 사용할 값입니다.

### <a name="return-value"></a>Return Value

메모리 위치의 원본 값입니다.

## <a name="atomic_fetch_sub-function-c-amp"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub 기능(C++ AMP)

메모리 위치에서 값을 원자적으로 뺍니다.

```cpp
inline int atomic_fetch_sub(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_sub(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
대상 위치에 대한 포인터입니다.

*value*<br/>
빼는 값입니다.

### <a name="return-value"></a>Return Value

메모리 위치의 원본 값입니다.

## <a name="atomic_fetch_xor-function-c-amp"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor 기능(C++ AMP)

원자적으로 값과 메모리 위치의 비트 XOR 작업을 수행합니다.

```cpp
inline int atomic_fetch_xor(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_xor(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
메모리 위치에 대한 포인터입니다.

*value*<br/>
XOR 계산에 사용할 값입니다.

### <a name="return-value"></a>Return Value

메모리 위치의 원본 값입니다.

## <a name="copy"></a><a name="copy"></a>복사

C++ AMP 개체를 복사합니다. 모든 동기 데이터 전송 요구 사항이 충족됩니다. 액셀러레이터에서 코드를 실행할 때는 데이터를 복사할 수 없습니다. 이 함수의 일반적인 `copy(src, dest)`형태는 .

```cpp
template <typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    array<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
   OutputIterator _DestIter);

template <typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<const value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<const value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    array_view<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    OutputIterator _DestIter);
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
복사할 개체입니다.

*_DestIter*<br/>
대상의 시작 위치로 의 출력 거터레이터입니다.

*InputIterator*<br/>
입력 반복기의 형식입니다.

*출력이터*<br/>
출력 거터레이터의 유형입니다.

*_Rank*<br/>
복사할 개체의 순위 또는 복사할 개체의 순위입니다.

*_Src*<br/>
복사할 것을 반대합니다.

*_SrcFirst*<br/>
소스 컨테이너에 대한 시작 이터레이터입니다.

*_SrcLast*<br/>
소스 컨테이너에 대한 끝 이터레이터입니다.

*Value_type*<br/>
복사되는 요소의 데이터 형식입니다.

## <a name="copy_async"></a><a name="copy_async"></a>copy_async

C++ AMP 개체를 복사하고 기다릴 수 있는 [completion_future](completion-future-class.md) 개체를 반환합니다. 액셀러레이터에서 코드를 실행할 때는 데이터를 복사할 수 없습니다.  이 함수의 일반적인 `copy(src, dest)`형태는 .

```cpp
template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst,
    array<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src, OutputIterator _DestIter);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst,
    array_view<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src, OutputIterator _DestIter);
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
복사할 개체입니다.

*_DestIter*<br/>
대상의 시작 위치로 의 출력 거터레이터입니다.

*InputIterator*<br/>
입력 반복기의 형식입니다.

*출력이터*<br/>
출력 거터레이터의 유형입니다.

*_Rank*<br/>
복사할 개체의 순위 또는 복사할 개체의 순위입니다.

*_Src*<br/>
복사할 것을 반대합니다.

*_SrcFirst*<br/>
소스 컨테이너에 대한 시작 이터레이터입니다.

*_SrcLast*<br/>
소스 컨테이너에 대한 끝 이터레이터입니다.

*Value_type*<br/>
복사되는 요소의 데이터 형식입니다.

### <a name="return-value"></a>Return Value

기다릴 `future<void>` 수 있는 A.

## <a name="direct3d_abort"></a><a name="direct3d_abort"></a>direct3d_abort

`restrict(amp)` 제한 절이 있는 함수의 실행을 중단합니다. AMP 런타임이 호출을 감지하면 "Reference Rasterizer: Shader abort instruction hit" 오류 메시지로 [runtime_exception](runtime-exception-class.md) 예외를 발생시킵니다.

```cpp
void direct3d_abort() restrict(amp);
```

## <a name="direct3d_errorf"></a><a name="direct3d_errorf"></a>direct3d_errorf

형식이 지정된 문자열을 Visual Studio 출력 창에 인쇄합니다. 제한 절이 있는 함수에서 호출됩니다. `restrict(amp)` AMP 런타임이 호출을 감지하면 동일한 서식 문자열에 [runtime_exception](runtime-exception-class.md) 예외가 발생합니다.

```cpp
void direct3d_errorf(
    const char *,
...) restrict(amp);
```

## <a name="direct3d_printf"></a><a name="direct3d_printf"></a>direct3d_printf

형식이 지정된 문자열을 Visual Studio 출력 창에 인쇄합니다. 제한 절이 있는 함수에서 호출됩니다. `restrict(amp)`

```cpp
void direct3d_printf(
    const char *,
...) restrict(amp);
```

## <a name="global_memory_fence"></a><a name="global_memory_fence"></a>global_memory_fence

모든 전역 메모리 액세스가 완료될 때까지 타일의 모든 스레드 실행을 차단합니다. 이렇게 하면 전역 메모리 액세스가 스레드 타일의 다른 스레드에 표시되고 프로그램 순서대로 실행됩니다.

```cpp
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Barrier*<br/>
tile_barrier 개체

## <a name="parallel_for_each-function-c-amp"></a><a name="parallel_for_each"></a>parallel_for_each 기능(C++ AMP)

계산 도메인 에서 함수를 실행합니다. 자세한 내용은 [C++ AMP 개요를](../../../parallel/amp/cpp-amp-overview.md)참조하십시오.

```cpp
template <int _Rank, typename _Kernel_type>
void parallel_for_each(
    const extent<_Rank>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
   const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Rank, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const extent<_Rank>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0>& _Compute_domain,
    const _Kernel_type& _Kernel);
```

### <a name="parameters"></a>매개 변수

*_Accl_view*<br/>
병렬 `accelerator_view` 계산을 실행할 개체입니다.

*_Compute_domain*<br/>
계산에 대한 데이터를 포함하는 `extent` 개체입니다.

*_Dim0*<br/>
개체의 차원입니다. `tiled_extent`

*_Dim1*<br/>
개체의 차원입니다. `tiled_extent`

*_Dim2*<br/>
개체의 차원입니다. `tiled_extent`

*_Kernel*<br/>
"인덱스\<_Rank>" 형식의 인수를 취하고 병렬 계산을 수행하는 람다 또는 함수 개체입니다.

*_Kernel_type*<br/>
람다 또는 펑터.

*_Rank*<br/>
익스텐스(익스텐더)의 순위입니다.

## <a name="tile_static_memory_fence"></a><a name="tile_static_memory_fence"></a>tile_static_memory_fence

모든 미해결 `tile_static` 메모리 액세스가 완료될 때까지 타일의 모든 스레드 실행을 차단합니다. 이렇게 하면 `tile_static` 스레드 타일의 다른 스레드에 메모리 액세스가 표시되고 해당 액세스는 프로그램 순서대로 실행됩니다.

```cpp
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Barrier*<br/>
tile_barrier 개체입니다.

## <a name="see-also"></a>참고 항목

[동시성 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
