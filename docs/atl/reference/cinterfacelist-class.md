---
title: CInterfaceList 클래스
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 0a7fd781c63e4ea084cf078e49fc9efb9cfa2d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326783"
---
# <a name="cinterfacelist-class"></a>CInterfaceList 클래스

이 클래스는 COM 인터페이스 포인터 목록을 생성할 때 유용한 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
저장할 포인터 유형을 지정하는 COM 인터페이스입니다.

*piid*<br/>
*I의*IID에 대한 포인터 .

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C인터페이스 목록::CInterfaceList](#cinterfacelist)|인터페이스 목록의 생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 COM 인터페이스 포인터 목록을 만들기 위한 생성자 및 파생 메서드를 제공합니다. 배열이 필요한 경우 [CInterfaceArray를](../../atl/reference/cinterfacearray-class.md) 사용합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a>C인터페이스 목록::CInterfaceList

인터페이스 목록의 생성자입니다.

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
기본값인 블록 크기(기본값은 10)입니다.

### <a name="remarks"></a>설명

블록 크기는 새 요소가 필요할 때 할당된 메모리 양을 측정한 값입니다. 블록 크기가 클수록 메모리 할당 루틴에 대한 호출이 줄어들지만 더 많은 리소스를 사용합니다.

## <a name="see-also"></a>참고 항목

[CAtlList 클래스](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr 클래스](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
