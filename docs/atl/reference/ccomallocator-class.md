---
title: CComAllocator 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: 165cdb8b0b16a4872214f4556c26ee141e6a4d89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321147"
---
# <a name="ccomallocator-class"></a>CComAllocator 클래스

이 클래스는 COM 메모리 루틴을 사용하여 메모리를 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class CComAllocator
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComAllocator::할당](#allocate)|이 정적 메서드를 호출하여 메모리를 할당합니다.|
|[CComAllocator::무료](#free)|할당된 메모리를 해제하려면 이 정적 메서드를 호출합니다.|
|[CComAllocator::재할당](#reallocate)|메모리를 다시 할당하려면 이 정적 메서드를 호출합니다.|

## <a name="remarks"></a>설명

이 클래스는 COM 메모리 할당 루틴을 제공하기 위해 [CComHeapPtr에서](../../atl/reference/ccomheapptr-class.md) 사용됩니다. 대응하는 클래스인 [CCRTAllocator는](../../atl/reference/ccrtallocator-class.md)CRT 루틴을 사용하여 동일한 메서드를 제공합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::할당

메모리를 할당하려면 이 정적 함수를 호출합니다.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
할당할 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당된 공간에 대한 void 포인터 또는 사용 가능한 메모리가 부족한 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

메모리를 할당합니다. 자세한 내용은 [CoTaskMemAlloc을](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) 참조하십시오.

## <a name="ccomallocatorfree"></a><a name="free"></a>CComAllocator::무료

할당된 메모리를 해제하려면 이 정적 함수를 호출합니다.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
할당된 메모리에 대한 포인터입니다.

### <a name="remarks"></a>설명

할당된 메모리를 해제합니다. 자세한 내용은 [CoTaskMemFree를](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) 참조하십시오.

## <a name="ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator::재할당

메모리를 다시 할당하려면 이 정적 함수를 호출합니다.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
할당된 메모리에 대한 포인터입니다.

*n바이트*<br/>
다시 할당할 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당된 공간에 void 포인터를 반환하거나 메모리가 부족한 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

할당된 메모리의 크기를 조정합니다. 자세한 내용은 [CoTaskMemRealloc을](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) 참조하십시오.

## <a name="see-also"></a>참고 항목

[CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator 클래스](../../atl/reference/ccrtallocator-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
