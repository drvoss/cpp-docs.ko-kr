---
title: CInterfaceArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
helpviewer_keywords:
- CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
ms.openlocfilehash: e6efe31989b06f0977ecff156a8f64053dc64ad1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326795"
---
# <a name="cinterfacearray-class"></a>CInterfaceArray 클래스

이 클래스는 COM 인터페이스 포인터의 배열을 생성할 때 유용한 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class I, const IID* piid=& __uuidof(I)>
class CInterfaceArray :
   public CAtlArray<ATL::CComQIPtr<I, piid>,
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
|[CInterface배열::인터페이스배열](#cinterfacearray)|인터페이스 배열의 생성자입니다.|

## <a name="remarks"></a>설명

이 클래스는 COM 인터페이스 포인터 배열을 만들기 위한 생성자 및 파생 메서드를 제공합니다. 목록이 필요한 경우 [CInterfaceList를](../../atl/reference/cinterfacelist-class.md) 사용합니다.

자세한 내용은 [ATL 컬렉션 클래스를](../../atl/atl-collection-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CAtlArray`

`CInterfaceArray`

## <a name="requirements"></a>요구 사항

**헤더:** 아틀콜.h

## <a name="cinterfacearraycinterfacearray"></a><a name="cinterfacearray"></a>CInterface배열::인터페이스배열

생성자입니다.

```
CInterfaceArray() throw();
```

### <a name="remarks"></a>설명

스마트 포인터 배열을 초기화합니다.

## <a name="see-also"></a>참고 항목

[카틀어레이어리 클래스](../../atl/reference/catlarray-class.md)<br/>
[CComQIPtr 클래스](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits 클래스](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
