---
title: cache_freelist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: d757909d3e54fed35bf42b943b9f9740dffee115
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366744"
---
# <a name="cache_freelist-class"></a>cache_freelist 클래스

단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|
|*최대*|사용 가능한 목록의 최대 크기를 나타내는 최대 클래스입니다. [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) 또는 [max_variable_size](../standard-library/max-variable-size-class.md)일 수 있습니다.|

## <a name="remarks"></a>설명

cache_freelist 클래스 템플릿은 *Sz*크기의 메모리 블록 의 사용 목록을 유지 관리합니다. 사용 권한 있는 목록이 가득 차면 **연산자 삭제를** 사용하여 메모리 블록을 할당 해제합니다. 사용 사용 목록이 비어 있으면 **새 연산자 new를** 사용하여 새 메모리 블록을 할당합니다. 사용 가능한 목록의 최대 크기는 *Max* 매개 변수에 전달된 클래스 최대 클래스에 의해 결정됩니다.

각 메모리 블록에는 사용 가능한 메모리의 *Sz* 바이트와 **연산자 새** 및 **연산자 삭제에** 필요한 데이터가 있습니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[cache_freelist](#cache_freelist)|`cache_freelist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[할당](#allocate)|메모리 블록을 할당합니다.|
|[할당](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a>cache_freelist::할당

메모리 블록을 할당합니다.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*count*|할당할 배열의 요소 수입니다.|

### <a name="return-value"></a>Return Value

할당된 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a>cache_freelist:cache_freelist

`cache_freelist` 형식의 개체를 생성합니다.

```cpp
cache_freelist();
```

### <a name="remarks"></a>설명

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a>cache_freelist::d

지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Ptr*|스토리지에서 할당을 취소할 첫 번째 개체에 대한 포인터입니다.|
|*count*|스토리지에서 할당을 취소할 개체의 수입니다.|

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
