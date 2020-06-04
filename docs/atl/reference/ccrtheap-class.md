---
title: CCRT힙 클래스
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: caf5508079332689c2fff42f130951375dc35512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327156"
---
# <a name="ccrtheap-class"></a>CCRT힙 클래스

이 클래스는 CRT 힙 함수를 사용하여 [IAtlMemgr을](../../atl/reference/iatlmemmgr-class.md) 구현합니다.

## <a name="syntax"></a>구문

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCRTHeap::할당](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[CCRTHeap::무료](#free)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.|
|[CCRTHeap::GetSize](#getsize)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록의 크기를 가져옵니다.|
|[CCRTHeap::재할당](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CCRTHeap`[malloc,](../../c-runtime-library/reference/malloc.md) [free,](../../c-runtime-library/reference/free.md) [realloc](../../c-runtime-library/reference/realloc.md)및 [_msize](../../c-runtime-library/reference/msize.md)포함하여 CRT 힙 함수를 사용하여 메모리 할당 기능을 구현합니다.

## <a name="example"></a>예제

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)에 대한 예제를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀렘.h

## <a name="ccrtheapallocate"></a><a name="allocate"></a>CCRTHeap::할당

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

[CCRTHeap 호출::무료](#free) 또는 [CCRTHeap::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

[malloc.](../../c-runtime-library/reference/malloc.md)

## <a name="ccrtheapfree"></a><a name="free"></a>CCRTHeap::무료

이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 유효한 값이며 아무 것도 하지 않습니다.

### <a name="remarks"></a>설명

[무료를](../../c-runtime-library/reference/free.md)사용하여 구현 .

## <a name="ccrtheapgetsize"></a><a name="getsize"></a>CCRTHeap::GetSize

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

[_msize](../../c-runtime-library/reference/msize.md)을 사용하여 구현되었습니다.

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a>CCRTHeap::재할당

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

[CCRTHeap ::이](#free) 메서드에 의해 할당 된 메모리를 해제 무료 호출합니다. [realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComHeap 클래스](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)
