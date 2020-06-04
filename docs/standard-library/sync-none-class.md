---
title: sync_none 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
ms.openlocfilehash: 046cbca30b6cdef2dc4e7dbbe2791d52384d9f25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376565"
---
# <a name="sync_none-class"></a>sync_none 클래스

동기화를 제공하지 않는 [동기화 필터에](../standard-library/allocators-header.md) 대해 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Cache`|동기화 필터와 연결된 캐시 형식입니다. [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) 또는 [cache_suballoc](../standard-library/cache-suballoc-class.md)일 수 있습니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[할당](#allocate)|메모리 블록을 할당합니다.|
|[할당](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|
|[equals](#equals)|두 캐시가 같은지 비교합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="sync_noneallocate"></a><a name="allocate"></a>sync_none::할당

메모리 블록을 할당합니다.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*count*|할당할 배열의 요소 수입니다.|

### <a name="remarks"></a>설명

구성원 함수는 `cache.allocate(count)`를 반환합니다. 여기서 `cache`는 캐시 개체입니다.

## <a name="sync_nonedeallocate"></a><a name="deallocate"></a>sync_none::d

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

구성원 함수는 `cache.deallocate(ptr, count)`를 호출합니다. 여기서 `cache`는 캐시 개체를 나타냅니다.

## <a name="sync_noneequals"></a><a name="equals"></a>sync_none::같음

두 캐시가 같은지 비교합니다.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*캐시*|동기화 필터의 캐시 개체입니다.|
|*기타*|같은지 비교할 캐시 개체입니다.|

### <a name="return-value"></a>Return Value

멤버 함수는 항상 **true를 반환합니다.**

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
