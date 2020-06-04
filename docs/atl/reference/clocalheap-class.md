---
title: CLocalHeap 클래스
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 303e3b85ad11c309f862f59d6ec610701c4ef6db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326753"
---
# <a name="clocalheap-class"></a>CLocalHeap 클래스

이 클래스는 Win32 로컬 힙 함수를 사용하여 [IAtlMemgr을](../../atl/reference/iatlmemmgr-class.md) 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CLocalHeap::할당](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[CLocalHeap::무료](#free)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.|
|[CLocalHeap::GetSize](#getsize)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록의 크기를 가져옵니다.|
|[CLocalHeap::재할당](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CLocalHeap`은 Win32 로컬 힙 함수를 사용하여 메모리 할당 기능을 구현합니다.

> [!NOTE]
> 로컬 힙 함수는 다른 메모리 관리 기능보다 느리며 많은 기능을 제공하지 않습니다. 따라서 새 응용 프로그램은 [힙 함수를](/windows/win32/Memory/heap-functions)사용해야 합니다. [CWin32Heap](../../atl/reference/cwin32heap-class.md) 클래스에서 사용할 수 있습니다.

## <a name="example"></a>예제

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)에 대한 예제를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀렘.h

## <a name="clocalheapallocate"></a><a name="allocate"></a>CLocalHeap::할당

메모리 블록을 할당하려면 이 메서드를 호출합니다.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[CLocalHeap 호출::무료](#free) 또는 [CLocalHeap::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

LMEM_FIXED 플래그 매개 변수를 사용하여 [LocalAlloc를](/windows/win32/api/winbase/nf-winbase-localalloc) 사용하여 구현했습니다.

## <a name="clocalheapfree"></a><a name="free"></a>CLocalHeap::무료

이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 유효한 값이며 아무 것도 하지 않습니다.

### <a name="remarks"></a>설명

[LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)를 사용하여 구현 .

## <a name="clocalheapgetsize"></a><a name="getsize"></a>CLocalHeap::GetSize

이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록의 크기를 가져옵니다.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

할당된 메모리 블록의 크기를 바이트로 반환합니다.

### <a name="remarks"></a>설명

[LocalSize](/windows/win32/api/winbase/nf-winbase-localsize).

## <a name="clocalheapreallocate"></a><a name="reallocate"></a>CLocalHeap::재할당

이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다.

*n바이트*<br/>
새 메모리 블록의 요청된 바이트 수입니다.

### <a name="return-value"></a>Return Value

새로 할당된 메모리 블록의 시작 부분에 대한 포인터를 반환합니다.

### <a name="remarks"></a>설명

[CLocalHeap 호출::이](#free) 메서드에 의해 할당 된 메모리를 해제 무료.

[LocalReAlloc을](/windows/win32/api/winbase/nf-winbase-localrealloc)사용하여 구현됩니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComHeap 클래스](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[CCRT힙 클래스](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)
