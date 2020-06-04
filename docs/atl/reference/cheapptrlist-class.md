---
title: CHeapPtrList 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 0500ab8f76049aeaf1c89355ea5450a93243b734
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326868"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList 클래스

이 클래스는 힙 포인터 목록을 생성할 때 유용한 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>매개 변수

*전자*<br/>
컬렉션 클래스에 저장할 개체 형식입니다.

*할당자*<br/>
사용할 메모리 할당 클래스입니다. 기본값은 [CCRTAllocator.](../../atl/reference/ccrtallocator-class.md)

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 생성자 및 [CAtlList](../../atl/reference/catllist-class.md) 및 [CHeapPtrElementTraits에서](../../atl/reference/cheapptrelementtraits-class.md) 메서드를 파생 하여 힙 포인터를 저장하는 컬렉션 클래스 개체를 만드는 데 도움이 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList

생성자입니다.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
블록의 크기입니다.

### <a name="remarks"></a>설명

블록 크기는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다.

## <a name="see-also"></a>참고 항목

[CAtlList 클래스](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr 클래스](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrElementTraits 클래스](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
