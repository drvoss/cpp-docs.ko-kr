---
title: ICollectionOnSTLImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: a8ccab08b89da8c1b8ef56c8932e27a6c74e62aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329902"
---
# <a name="icollectiononstlimpl-class"></a>ICollectionOnSTLImpl 클래스

이 클래스는 컬렉션 클래스에서 사용하는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
COM 컬렉션 인터페이스입니다.

*CollType*<br/>
C++ 표준 라이브러리 컨테이너 클래스입니다.

*Itemtype*<br/>
컨테이너 인터페이스에서 노출되는 항목의 유형입니다.

*복사 항목*<br/>
[복사 정책 클래스](../../atl/atl-copy-policy-classes.md).

*에이넘 타입*<br/>
[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)호환 열거자 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[ICollectionOnSTLImpl::get__NewEnum](#newenum)|컬렉션에 대한 열거자 개체를 반환합니다.|
|[ICollectionOnSTLImpl::getcount](#get_count)|컬렉션의 요소 수를 반환합니다.|
|[ICollectionOnSTLImpl::get_Item](#get_item)|컬렉션에서 요청된 항목을 반환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[ICollectionOnSTLImpl::m_coll](#m_coll)|컬렉션입니다.|

## <a name="remarks"></a>설명

이 클래스는 컬렉션 인터페이스의 세 가지 메서드인 [getcount,](#get_count) [get_Item](#get_item)및 [get__NewEnum](#newenum).

이 클래스를 사용하려면 다음을 수행하십시오.

- 구현하려는 컬렉션 인터페이스를 정의(또는 대여)합니다.

- 이 컬렉션 인터페이스를 `ICollectionOnSTLImpl` 기반으로 하는 전문화에서 클래스를 파생합니다.

- 파생 클래스를 사용하여 `ICollectionOnSTLImpl`에서 처리하지 않는 컬렉션 인터페이스에서 메서드를 구현합니다.

> [!NOTE]
> 컬렉션 인터페이스가 이중 인터페이스인 경우 ATL이 메서드의 구현을 제공하려는 경우 `ICollectionOnSTLImpl` 전문화 특성을 첫 번째 템플릿 `IDispatch` 매개 변수로 전달하는 [IDispatchImpl에서](../../atl/reference/idispatchimpl-class.md)클래스를 파생합니다.

- [m_coll](#m_coll) 멤버에 항목을 추가하여 컬렉션을 채웁니다.

자세한 정보 및 예제는 [ATL 컬렉션 및 열거자를](../../atl/atl-collections-and-enumerators.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a>ICollectionOnSTLImpl::getcount

이 메서드는 컬렉션의 항목 수를 반환합니다.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>매개 변수

*pcount*<br/>
【아웃】 컬렉션의 요소 수입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a>ICollectionOnSTLImpl::get_Item

이 메서드는 컬렉션에서 지정 된 항목을 반환 합니다.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>매개 변수

*인덱스*<br/>
【인】 컬렉션에 있는 항목의 1기반 인덱스입니다.

*pvar*<br/>
【아웃】 *인덱스에*해당하는 항목입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

항목은 `ICollectionOnSTLImpl` 전문화 에서 템플릿 인수로 전달 된 [복사 정책 클래스의](../../atl/atl-copy-policy-classes.md) 복사 방법을 사용하여 [m_coll](#m_coll) 지정된 위치에 데이터를 복사하여 가져옵니다.

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a>ICollectionOnSTLImpl::get__NewEnum

컬렉션에 대한 열거자 개체를 반환합니다.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>매개 변수

*ppunk*<br/>
【아웃】 새로 만든 열거체 개체의 **IUnknown** 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

새로 생성된 열거자는 원래 컬렉션의 `m_coll`이터레이터를 유지 관리하며(복사본이 만들어지지 않도록) 컬렉션 개체에 COM 참조를 보유하여 뛰어난 열거자가 있는 동안 컬렉션이 살아 있는지 확인합니다.

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a>ICollectionOnSTLImpl::m_coll

이 멤버는 컬렉션으로 표시되는 항목을 보유합니다.

```
CollType m_coll;
```

## <a name="see-also"></a>참고 항목

[ATL컬렉션 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
