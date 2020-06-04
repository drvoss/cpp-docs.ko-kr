---
title: CHeapPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: f09da968b264463eba759372e4e0756397e9978e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326870"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits 클래스

이 클래스는 힙 포인터 컬렉션을 만들 때 유용한 메서드, 정적 함수 및 typedefs를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션 클래스에 저장할 개체 형식입니다.

*할당자*<br/>
사용할 메모리 할당 클래스입니다. 기본값은 [CCRTAllocator.](../../atl/reference/ccrtallocator-class.md)

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CHeapPtr요소::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[CHeapPtr요소::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 힙 포인터를 포함하는 컬렉션 클래스 개체를 만드는 데 도움이 되는 메서드, 정적 함수 및 typedefs를 제공합니다. 클래스는 `CHeapPtrList` 에서 `CHeapPtrElementTraits`파생됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a>CHeapPtr요소::INARGTYPE

컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a>CHeapPtr요소::OUTARGTYPE

컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>참고 항목

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr 클래스](../../atl/reference/ccomheapptr-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
