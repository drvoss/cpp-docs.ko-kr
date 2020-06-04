---
title: CComHeapPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 78cadfff9a278cf080393ab919f3891b201c91aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327771"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr 클래스

힙 포인터를 관리하기 위한 스마트 포인터 클래스입니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
힙에 저장할 개체 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|생성자입니다.|

## <a name="remarks"></a>설명

`CComHeapPtr`에서 `CHeapPtr`파생되지만 [CComAllocator를](../../atl/reference/ccomallocator-class.md) 사용하여 COM 루틴을 사용하여 메모리를 할당합니다. 사용 가능한 방법에 대한 [CHeapPtr](../../atl/reference/cheapptr-class.md) 및 [CHeapPtrBase를](../../atl/reference/cheapptrbase-class.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr

생성자입니다.

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>매개 변수

*Pdata*<br/>
기존 `CComHeapPtr` 개체입니다.

### <a name="remarks"></a>설명

힙 포인터는 기존 `CComHeapPtr` 개체를 사용하여 선택적으로 만들 수 있습니다. 이 경우 새 `CComHeapPtr` 개체는 새 포인터 및 리소스를 관리해야 합니다.

## <a name="see-also"></a>참고 항목

[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase 클래스](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator 클래스](../../atl/reference/ccomallocator-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
