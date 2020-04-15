---
title: CElementTraitsBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: 5a29e8778cf2f3400df25b55574950a005bad995
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327009"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase 클래스

이 클래스는 컬렉션 클래스에 대한 기본 복사 및 이동 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CElementTraits베이스::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|
|[CElementTraits베이스::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색하는 데 사용할 데이터 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CElementTraits베이스::복사 요소](#copyelements)|컬렉션 클래스 개체에 저장된 요소를 복사하려면 이 메서드를 호출합니다.|
|[CElementTraits베이스::재배치요소](#relocateelements)|이 메서드를 호출하여 컬렉션 클래스 개체에 저장된 요소를 재배치합니다.|

## <a name="remarks"></a>설명

이 기본 클래스는 컬렉션 클래스에서 요소를 복사하고 재배치하는 메서드를 정의합니다. 클래스 [CDefaultElementTraits,](../../atl/reference/cdefaultelementtraits-class.md) [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)및 [CStringElementTraitsI에](../../atl/reference/cstringelementtraitsi-class.md)의해 활용됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a>CElementTraits베이스::복사 요소

컬렉션 클래스 개체에 저장된 요소를 복사하려면 이 메서드를 호출합니다.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
복사된 데이터를 수신할 첫 번째 요소에 대한 포인터입니다.

*pSrc*<br/>
복사할 첫 번째 요소에 대한 포인터입니다.

*n엘리먼츠*<br/>
복사할 요소의 수입니다.

### <a name="remarks"></a>설명

원본 및 대상 요소가 겹치지 않아야 합니다.

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a>CElementTraits베이스::INARGTYPE

컬렉션에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a>CElementTraits베이스::OUTARGTYPE

컬렉션에서 요소를 검색하는 데 사용할 데이터 형식입니다.

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a>CElementTraits베이스::재배치요소

이 메서드를 호출하여 컬렉션 클래스 개체에 저장된 요소를 재배치합니다.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
재배치된 데이터를 수신할 첫 번째 요소에 대한 포인터입니다.

*pSrc*<br/>
재배치할 첫 번째 요소에 대한 포인터입니다.

*n엘리먼츠*<br/>
재배치할 요소 의 수입니다.

### <a name="remarks"></a>설명

이 메서드는 대부분의 데이터 형식에 충분 한 [memmove를](../../c-runtime-library/reference/memmove-wmemmove.md)호출 합니다. 이동 중인 개체에 자체 멤버에 대한 포인터가 포함되어 있는 경우 이 메서드를 재정의해야 합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
