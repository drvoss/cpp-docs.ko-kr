---
title: CComHeap 클래스
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: a38d1147e718870c03af84ec1487e226805b956e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327828"
---
# <a name="ccomheap-class"></a>CComHeap 클래스

이 클래스는 COM 메모리 할당 함수를 사용하여 [IAtlMemMgr을](../../atl/reference/iatlmemmgr-class.md) 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComHeap::할당](#allocate)|메모리 블록을 할당하려면 이 메서드를 호출합니다.|
|[CComHeap::무료](#free)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.|
|[CComHeap::GetSize](#getsize)|이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록의 크기를 가져옵니다.|
|[CComHeap::재할당](#reallocate)|이 메모리 관리자에 의해 할당된 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

`CComHeap`Com 할당 함수를 사용하여 메모리 할당 함수를 구현합니다( [코태스크메알록,](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree), [IMalloc::GetSize,](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)및 [CoTaskMemRealloc)](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)등 . 할당할 수 있는 최대 메모리 양은 INT_MAX(2147483647) 바이트와 같습니다.

## <a name="example"></a>예제

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)에 대한 예제를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>요구 사항

**헤더:** ATLComMem.h

## <a name="ccomheapallocate"></a><a name="allocate"></a>CComHeap::할당

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

[CComHeap 호출::무료](#free) 또는 [CComHeap::이](#reallocate) 메서드에 의해 할당 된 메모리를 해제 하려면 재할당.

[CoTaskMemAlloc를](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)사용하여 구현 .

## <a name="ccomheapfree"></a><a name="free"></a>CComHeap::무료

이 메서드를 호출하여 이 메모리 관리자가 할당한 메모리 블록을 해제합니다.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
이 메모리 관리자에 의해 이전에 할당된 메모리에 대한 포인터입니다. NULL은 유효한 값이며 아무 것도 하지 않습니다.

### <a name="remarks"></a>설명

[CoTaskMemFree를](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)사용하여 구현 .

## <a name="ccomheapgetsize"></a><a name="getsize"></a>CComHeap::GetSize

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

[IMalloc를 사용하여 구현::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize).

## <a name="ccomheapreallocate"></a><a name="reallocate"></a>CComHeap::재할당

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

[CComHeap 호출:::이](#free) 메서드에 의해 할당 된 메모리를 해제 무료.

[CoTaskMemRealloc을](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)사용하여 구현 .

## <a name="see-also"></a>참고 항목

[동적 소비자 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CWin32Heap 클래스](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 클래스](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 클래스](../../atl/reference/cglobalheap-class.md)<br/>
[CCRT힙 클래스](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr 클래스](../../atl/reference/iatlmemmgr-class.md)
