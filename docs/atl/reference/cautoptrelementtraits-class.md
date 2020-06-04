---
title: CAutoPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: ac29116dc9beedf587c42cc0e52f8c9dbaf3d782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318883"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits 클래스

이 클래스는 스마트 포인터 의 컬렉션을 만들 때 유용한 메서드, 정적 함수 및 typedefs를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
포인터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[코토프트르엘리먼트트::이나르그타입](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[코토프트르엘리먼트트::아웃라그타입](#outargtype)|컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 스마트 포인터를 포함하는 컬렉션 클래스 개체를 만드는 데 도움이 되는 메서드, 정적 함수 및 typedefs를 제공합니다. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및 [CAutoPtrList에서](../../atl/reference/cautoptrlist-class.md) `CAutoPtrElementTraits`파생 됩니다. 벡터 를 필요로 하는 스마트 포인터 컬렉션을 빌드하는 경우 새 연산자 및 삭제 연산자 대신 [CAutoVectorPtrElementTraits를](../../atl/reference/cautovectorptrelementtraits-class.md) 사용합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a>코토프트르엘리먼트트::이나르그타입

컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a>코토프트르엘리먼트트::아웃라그타입

컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>참고 항목

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
