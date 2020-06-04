---
title: cache_chunklist 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: d0dd6176a34bd625069511106c491225d1467d08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366751"
---
# <a name="cache_chunklist-class"></a>cache_chunklist 클래스

단일 크기의 메모리 블록을 할당하고 할당 취소하는 [블록 할당자](../standard-library/allocators-header.md)를 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Sz*|할당할 배열의 요소 수입니다.|

## <a name="remarks"></a>설명

이 클래스 템플릿은 **새 연산자 new를** 사용하여 원시 메모리의 청크를 할당하고 블록을 종속하여 필요할 때 메모리 블록에 대한 저장소를 할당합니다. 할당 해제된 메모리 블록을 각 청크에 대해 별도의 사용 가능 목록에 저장하고 **연산자 삭제를** 사용하여 메모리 블록이 사용되지 않을 때 청크를 할당 해제합니다.

각 메모리 블록에는 사용 가능한 메모리의 *Sz* 바이트와 해당 메모리가 속한 청크에 대한 포인터가 있습니다. 각 청크는 메모리 블록, 세 개의 포인터, int 및 **연산자 새** 및 `Nelts` **연산자 삭제에** 필요한 데이터를 보유합니다.


### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[할당](#allocate)|메모리 블록을 할당합니다.|
|[할당](#deallocate)|지정된 위치부터 시작하여 스토리지에서 지정된 개수의 개체를 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a>cache_chunklist::할당

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a>cache_chunklist:cache_chunklist

`cache_chunklist` 형식의 개체를 생성합니다.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>설명

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a>cache_chunklist::d

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
