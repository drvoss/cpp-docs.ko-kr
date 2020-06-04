---
title: 자동 PtrList 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 48c7ad6fe13c5f5fbbe5829c25ce1c27896841be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318796"
---
# <a name="cautoptrlist-class"></a>자동 PtrList 클래스

이 클래스는 스마트 포인터 목록을 생성할 때 유용한 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>매개 변수

*전자*<br/>
포인터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[오토프리스트::자동Ptrlist](#cautoptrlist)|생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 생성자 및 [CAtlList](../../atl/reference/catllist-class.md) 및 [CAutoPtrElementTraits에서](../../atl/reference/cautoptrelementtraits-class.md) 메서드를 파생 하여 스마트 포인터를 저장하는 목록 개체를 만드는 데 도움이 됩니다. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 배열 개체에 대 한 유사한 함수를 제공 합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a>오토프리스트::자동Ptrlist

생성자입니다.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
기본값인 블록 크기(기본값은 10)입니다.

### <a name="remarks"></a>설명

블록 크기는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다.

## <a name="see-also"></a>참고 항목

[CAtlList 클래스](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits 클래스](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
