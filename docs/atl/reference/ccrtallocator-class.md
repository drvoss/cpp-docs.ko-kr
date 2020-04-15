---
title: CCRTAllocator 클래스
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 2f6bae3818fa0f1639e0e3cee4e09121580da768
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327176"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator 클래스

이 클래스는 CRT 메모리 루틴을 사용하여 메모리를 관리하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
class ATL::CCRTAllocator
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCRT알로카이터::할당](#allocate)|(정적) 메모리를 할당하려면 이 메서드를 호출합니다.|
|[CCRT알로카이터:무료](#free)|(정적) 이 메서드를 호출하여 메모리를 확보합니다.|
|[CCRT알로카이터::재할당](#reallocate)|(정적) 메모리를 다시 할당하려면 이 메서드를 호출합니다.|

## <a name="remarks"></a>설명

이 클래스는 CRT 메모리 할당 루틴을 제공하기 위해 [CHeapPtr에서](../../atl/reference/cheapptr-class.md) 사용됩니다. 대응 클래스인 [CComAllocator는](../../atl/reference/ccomallocator-class.md)COM 루틴을 사용하여 동일한 메서드를 제공합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a>CCRT알로카이터::할당

메모리를 할당하려면 이 정적 함수를 호출합니다.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
할당할 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당된 공간에 대한 void 포인터 또는 사용 가능한 메모리가 부족한 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

메모리를 할당합니다. 자세한 내용은 [malloc을](../../c-runtime-library/reference/malloc.md) 참조하십시오.

## <a name="ccrtallocatorfree"></a><a name="free"></a>CCRT알로카이터:무료

이 정적 함수를 호출하여 메모리를 확보합니다.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
할당된 메모리에 대한 포인터입니다.

### <a name="remarks"></a>설명

할당된 메모리를 해제합니다. 자세한 내용은 [무료를](../../c-runtime-library/reference/free.md) 참조하십시오.

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRT알로카이터::재할당

메모리를 다시 할당하려면 이 정적 함수를 호출합니다.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*P*<br/>
할당된 메모리에 대한 포인터입니다.

*n바이트*<br/>
다시 할당할 바이트 수입니다.

### <a name="return-value"></a>Return Value

할당된 공간에 대한 void 포인터 또는 메모리가 부족한 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

할당된 메모리의 크기를 조정합니다. 자세한 내용은 [realloc을](../../c-runtime-library/reference/realloc.md) 참조하십시오.

## <a name="see-also"></a>참고 항목

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator 클래스](../../atl/reference/ccomallocator-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
