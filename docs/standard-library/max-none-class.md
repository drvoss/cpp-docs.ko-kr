---
title: max_none 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: c49ceec72be62d8ff3125f04d97bbb6952501677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370985"
---
# <a name="max_none-class"></a>max_none 클래스

[freelist](../standard-library/freelist-class.md) 개체를 최대 길이 0으로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*최대*|`freelist`에 저장할 요소의 최대 수를 결정하는 max 클래스입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[allocated](#allocated)|할당된 메모리 블록의 수를 늘립니다.|
|[할당](#deallocated)|할당된 메모리 블록의 수를 줄입니다.|
|[전체](#full)|사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.|
|[출시](#released)|사용 가능한 목록에서 메모리 블록의 수를 줄입니다.|
|[saved](#saved)|사용 가능한 목록에서 메모리 블록의 수를 늘립니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<allocators>

**네임스페이스:** stdext

## <a name="max_noneallocated"></a><a name="allocated"></a>max_none::할당

할당된 메모리 블록의 수를 늘립니다.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 아무 작업도 수행하지 않습니다. 새 연산자에 의해 `cache_freelist::allocate` 각 **new**성공적인 호출 후에 호출됩니다. *_Nx* 인수는 연산자 **new에**의해 할당 된 청크의 메모리 블록 의 수입니다.

## <a name="max_nonedeallocated"></a><a name="deallocated"></a>max_none::d 할당

할당된 메모리 블록의 수를 줄입니다.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 연산자 `cache_freelist::deallocate` **삭제에**대한 호출이 각 후에 호출됩니다. *_Nx* 인수는 연산자 **삭제에**의해 할당 된 청크의 메모리 블록 수입니다.

## <a name="max_nonefull"></a><a name="full"></a>max_none::전체

사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.

```cpp
bool full();
```

### <a name="return-value"></a>Return Value

이 멤버 함수는 항상 **true를 반환합니다.**

### <a name="remarks"></a>설명

이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출이 **true를** `deallocate` 반환하면 메모리 블록을 사용 중 목록에 넣습니다. **false를** `deallocate` 반환하는 경우 **운영자가 삭제하여** 블록을 할당 해제합니다.

## <a name="max_nonereleased"></a><a name="released"></a>max_none::발매

사용 가능한 목록에서 메모리 블록의 수를 줄입니다.

```cpp
void released();
```

### <a name="remarks"></a>설명

이 멤버 함수는 아무 작업도 수행하지 않습니다. 현재 max 클래스의 `released` 멤버 함수는 사용 가능한 목록에서 메모리 블록을 제거할 때마다 `cache_freelist::allocate`에서 호출됩니다.

## <a name="max_nonesaved"></a><a name="saved"></a>max_none::저장

사용 가능한 목록에서 메모리 블록의 수를 늘립니다.

```cpp
void saved();
```

### <a name="remarks"></a>설명

이 멤버 함수는 아무 작업도 수행하지 않습니다. 이 멤버 함수는 사용 가능한 목록에 메모리 블록을 넣을 때마다 `cache_freelist::deallocate`에서 호출됩니다.

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
