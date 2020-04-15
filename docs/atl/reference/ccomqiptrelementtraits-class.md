---
title: CComQIPtrElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 19f2669c157310be02f746672b22f6c0ed005075
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327406"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits 클래스

이 클래스는 COM 인터페이스 포인터의 컬렉션을 만들 때 유용한 메서드, 정적 함수 및 typedefs를 제공합니다.

## <a name="syntax"></a>구문

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
저장할 포인터 유형을 지정하는 COM 인터페이스입니다.

*piid*<br/>
*I의*IID에 대한 포인터 .

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.|

## <a name="remarks"></a>설명

이 클래스는 메서드를 파생 하 고 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터 개체의 컬렉션 클래스를 만들 때 유용한 typedef를 제공 합니다. 이 클래스는 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 및 [CInterfaceList](../../atl/reference/cinterfacelist-class.md) 클래스 모두에서 사용됩니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가하는 데 사용할 데이터 형식입니다.

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>참고 항목

[CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
