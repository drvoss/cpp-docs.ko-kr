---
title: max_variable_size 클래스
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: 79e37d8c464a009e4a5196aeacc8d4a718e355b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370965"
---
# <a name="max_variable_size-class"></a>max_variable_size 클래스

[freelist](../standard-library/freelist-class.md) 개체를 할당된 메모리 블록의 수에 거의 비례하는 최대 길이로 제한하는 [max 클래스](../standard-library/allocators-header.md) 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class max_variable_size
```

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[max_variable_size](#max_variable_size)|`max_variable_size` 형식의 개체를 생성합니다.|

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

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a>max_variable_size::할당

할당된 메모리 블록의 수를 늘립니다.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

이 멤버 *_Nx* 함수는 저장된 `_Nallocs`값에 _Nx 추가합니다. 이 멤버 함수는 `cache_freelist::allocate` **새**연산자에 의해 성공적으로 호출될 때마다 호출됩니다. *_Nx* 인수는 연산자 **new에**의해 할당 된 청크의 메모리 블록 의 수입니다.

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a>max_variable_size::d할당

할당된 메모리 블록의 수를 줄입니다.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*_Nx*|증분 값입니다.|

### <a name="remarks"></a>설명

멤버 함수는 저장된 *_Nx* 값에서 `_Nallocs`_Nx 뺍니다. 이 멤버 함수는 연산자 `cache_freelist::deallocate` **삭제에**대한 호출이 각 후에 호출됩니다. *_Nx* 인수는 연산자 **삭제에**의해 할당 된 청크의 메모리 블록 수입니다.

## <a name="max_variable_sizefull"></a><a name="full"></a>max_variable_size::전체

사용 가능한 목록에 더 많은 메모리 블록을 추가할지 여부를 지정하는 값을 반환합니다.

```cpp
bool full();
```

### <a name="return-value"></a>Return Value

**true** `_Nallocs / 16 + 16 <= _Nblocks`경우 .

### <a name="remarks"></a>설명

이 멤버 함수는 `cache_freelist::deallocate`에서 호출됩니다. 호출이 **true를** `deallocate` 반환하면 메모리 블록을 사용 중 목록에 넣습니다. false를 `deallocate` 반환하는 경우 **운영자가 삭제하여** 블록을 할당 해제합니다.

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a>max_variable_size:max_variable_size

`max_variable_size` 형식의 개체를 생성합니다.

```cpp
max_variable_size();
```

### <a name="remarks"></a>설명

이 생성자는 저장된 값 `_Nblocks` 및 `_Nallocs`를 0으로 초기화합니다.

## <a name="max_variable_sizereleased"></a><a name="released"></a>max_variable_size::발매

사용 가능한 목록에서 메모리 블록의 수를 줄입니다.

```cpp
void released();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `_Nblocks`를 줄입니다. 현재 max 클래스의 `released` 멤버 함수는 사용 가능한 목록에서 메모리 블록을 제거할 때마다 `cache_freelist::allocate`에서 호출됩니다.

## <a name="max_variable_sizesaved"></a><a name="saved"></a>max_variable_size::저장

사용 가능한 목록에서 메모리 블록의 수를 늘립니다.

```cpp
void saved();
```

### <a name="remarks"></a>설명

이 멤버 함수는 저장된 값 `_Nblocks`를 늘립니다. 이 멤버 함수는 사용 가능한 목록에 메모리 블록을 넣을 때마다 `cache_freelist::deallocate`에서 호출됩니다.

## <a name="see-also"></a>참고 항목

[\<할당자>](../standard-library/allocators-header.md)
