---
title: CWin32Heap 클래스
ms.date: 11/04/2016
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: 2d79de308b1afb3059cf04ad40b63b6e603073c8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746039"
---
# <a name="cwin32heap-class"></a>CWin32Heap 클래스

이 클래스는 Win32 힙 할당 함수를 사용하여 [IAtlMemMgr을](../../atl/reference/iatlmemmgr-class.md) 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CWin32Heap::CWin32Heap](#cwin32heap)|생성자입니다.|
|[CWin32Heap::~CWin32Heap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CWin32Heap::할당](#allocate)|힙 개체에서 메모리 블록을 할당합니다.|
|[CWin32Heap::연결](#attach)|힙 개체를 기존 힙에 연결합니다.|
|[CWin32Heap::D에타흐](#detach)|힙 개체를 기존 힙에서 분리합니다.|
|[CWin32Heap::무료](#free)|이전에 힙에서 할당된 메모리를 해제합니다.|
|[CWin32Heap::GetSize](#getsize)|힙 개체에서 할당된 메모리 블록의 크기를 반환합니다.|
|[CWin32Heap::재할당](#reallocate)|힙 개체에서 메모리 블록을 다시 할당합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|힙 핸들의 현재 소유권을 결정하는 데 사용되는 플래그입니다.|
|[CWin32Heap::m_hHeap](#m_hheap)|힙 개체에 핸들을 보입니다.|

## <a name="remarks"></a>설명

`CWin32Heap`[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc) 및 [HeapFree를](/windows/win32/api/heapapi/nf-heapapi-heapfree)포함하여 Win32 힙 할당 함수를 사용하여 메모리 할당 메서드를 구현합니다. 다른 힙 클래스와 `CWin32Heap` 달리 메모리를 할당하기 전에 유효한 힙 핸들을 제공해야 합니다. 핸들은 생성자 또는 [CWin32Heap::Attach](#attach) 메서드에 공급될 수 있습니다. 자세한 내용은 [CWin32Heap::CWin32Heap](#cwin32heap) 방법을 참조하십시오.

## <a name="example"></a>예제

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)에 대한 예제를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀렘.h

## <a name="cwin32heapallocate"></a><a name="allocate"></a>CWin32Heap::할당

힙 개체에서 메모리 블록을 할당합니다.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[CWin32Heap 호출::무료](#free) 또는 [CWin32Heap::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc).

## <a name="cwin32heapattach"></a><a name="attach"></a>CWin32Heap::연결

힙 개체를 기존 힙에 연결합니다.

```cpp
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>매개 변수

*hHeap*<br/>
기존 힙 핸들입니다.

*b테이크소유권*<br/>
개체가 힙의 `CWin32Heap` 리소스에 대한 소유권을 차지할지 나타내는 플래그입니다.

### <a name="remarks"></a>설명

*bTakeOwnershipTRUE인* 경우 `CWin32Heap` 개체는 힙 핸들을 삭제해야 합니다.

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32Heap::CWin32Heap

생성자입니다.

```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```

### <a name="parameters"></a>매개 변수

*hHeap*<br/>
기존 힙 개체입니다.

*dwFlags*<br/>
힙을 만드는 데 사용되는 플래그입니다.

*nInitialSize*<br/>
힙의 초기 크기입니다.

*n맥스 사이즈*<br/>
힙의 최대 크기입니다.

### <a name="remarks"></a>설명

메모리를 할당하기 전에 `CWin32Heap` 개체에 유효한 힙 핸들을 제공해야 합니다. 이는 프로세스 힙을 사용할 수 있는 가장 간단한 방법입니다.

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

또한 새 개체가 힙의 소유권을 계승하지 않는 경우 생성자에게 기존 힙 핸들을 제공할 수 있습니다. `CWin32Heap` 개체를 삭제해도 원래 힙 핸들은 계속해서 유효합니다.

기존 힙은 [CWin32Heap::Attach를](#attach)사용하여 새 개체에 연결할 수도 있습니다.

작업이 하나의 스레드에서 모두 수행된 위치에 힙이 필요한 경우 다음과 같이 개체를 만드는 것이 가장 좋습니다.

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

힙 함수가 성능 향상에 따라 여유 메모리를 할당할 때 매개 변수 HEAP_NO_SERIALIZE가 상호 제외가 사용되지 않도록 지정합니다.

세 번째 매개 변수의 기본값이 0으로 지정되어, 필요에 따라 힙을 증가시킬 수 있습니다. 메모리 크기와 플래그에 대한 설명은 [HeapCreate를](/windows/win32/api/heapapi/nf-heapapi-heapcreate) 참조하십시오.

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32Heap::~CWin32Heap

소멸자입니다.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>설명

`CWin32Heap` 개체에 힙의 소유권이 있는 경우 힙 핸들을 삭제합니다.

## <a name="cwin32heapdetach"></a><a name="detach"></a>CWin32Heap::D에타흐

힙 개체를 기존 힙에서 분리합니다.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Return Value

핸들을 개체가 이전에 연결한 힙으로 반환합니다.

## <a name="cwin32heapfree"></a><a name="free"></a>CWin32Heap::무료

[이전에 CWin32Heap에](#allocate) 의해 힙에서 할당 된 메모리를 해제 ::할당 또는 [CWin32Heap::재할당](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
메모리 블록을 사용하여 해제할 수 있습니다. NULL은 유효한 값이며 아무 것도 하지 않습니다.

## <a name="cwin32heapgetsize"></a><a name="getsize"></a>CWin32Heap::GetSize

힙 개체에서 할당된 메모리 블록의 크기를 반환합니다.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
메서드가 가져올 크기의 메모리 블록에 대한 포인터입니다. 이것은 [CWin32Heap에](#allocate) 의해 반환 된 포인터입니다 ::할당 또는 [CWin32Heap ::재할당](#reallocate).

### <a name="return-value"></a>Return Value

할당된 메모리 블록의 크기를 바이트로 반환합니다.

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a>CWin32Heap::m_bOwnHeap

[m_hHeap](#m_hheap)저장된 힙 핸들의 현재 소유권을 확인하는 데 사용되는 플래그입니다.

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a>CWin32Heap::m_hHeap

힙 개체에 핸들을 보입니다.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>설명

힙 개체에 핸들을 저장하는 데 사용되는 변수입니다.

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a>CWin32Heap::재할당

힙 개체에서 메모리 블록을 다시 할당합니다.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
다시 할당할 메모리 블록에 대한 포인터입니다.

*n바이트*<br/>
할당된 블록의 새 크기(바이트)입니다. 블록은 더 크거나 작을 수 있습니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

*p가* NULL이면 메모리 블록이 아직 할당되지 않았고 [CWin32Heap::할당이](#allocate) *호출되고 nBytes*인수가 호출됩니다.

## <a name="see-also"></a>참조

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[CCRT힙 클래스](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap 클래스](../../atl/reference/ccomheap-class.md)
