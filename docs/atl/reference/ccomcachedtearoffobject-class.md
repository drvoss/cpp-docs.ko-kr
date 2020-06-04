---
title: CComCachedTearOffObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: 019b90c932de144d05fbf05f3ca339f4e5d6edd1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748095"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject 클래스

이 클래스는 찢어짐 인터페이스에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다.

## <a name="syntax"></a>구문

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*포함*<br/>
찢어짐 개체가 지원하려는 `CComTearOffObjectBase` 인터페이스와 파생된 분리 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComCached티어오프오브젝트::CComCached티어오프오브젝트](#ccomcachedtearoffobject)|생성자입니다.|
|[CComCached티어오프오브젝트::~CComCached티어오프오브젝트](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|개체에 대한 참조 수를 `CComCachedTearOffObject` 증가합니다.|
|[CComCached티어오프오브젝트::파이널컨스트럭트](#finalconstruct)|`m_contained::FinalConstruct` (해제 클래스' 메서드)를 호출합니다.|
|[CComCachedTearOff개체::최종 릴리스](#finalrelease)|`m_contained::FinalRelease` (해제 클래스' 메서드)를 호출합니다.|
|[CComCachedTearOff개체::쿼리 인터페이스](#queryinterface)|개체의 포인터 또는 떼어놓는 클래스(클래스)에서 `contained`요청된 인터페이스에 대한 포인터를 반환합니다. `IUnknown` `CComCachedTearOffObject`|
|[CComCachedTearOff개체::릴리스](#release)|`CComCachedTearOffObject` 개체에 대한 참조 수를 삭제하고 참조 수가 0인 경우 개체를 삭제합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|분리 `CComContainedObject` 클래스(클래스)에서 `contained`파생된 개체입니다.|

## <a name="remarks"></a>설명

`CComCachedTearOffObject`은 찢어짐 인터페이스에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다. `CComTearOffObject` 이 클래스는 `CComCachedTearOffObject` 소유자 `IUnknown` `IUnknown` 개체의 개체와 는 별개의 자체 클래스가 있는 것과 다릅니다(소유자는 분리가 생성되는 개체입니다). `CComCachedTearOffObject`는 자체 참조 수를 `IUnknown` 유지 관리하고 참조 수가 0이되면 자체를 삭제합니다. 그러나 분리 된 인터페이스에 대 한 쿼리 하는 경우 소유자 개체의 `IUnknown` 참조 수가 증가 됩니다.

분리를 `CComCachedTearOffObject` 구현하는 개체가 이미 인스턴스화되어 있고 분리 인터페이스가 다시 쿼리되면 동일한 `CComCachedTearOffObject` 개체가 다시 사용됩니다. 반대로 a에서 `CComTearOffObject` 구현한 분리 인터페이스가 소유자 개체를 통해 다시 쿼리되면 다른 `CComTearOffObject` 인터페이스가 인스턴스화됩니다.

소유자 클래스는 `FinalRelease` 에 `Release` 대해 캐시된 `IUnknown` 을 `CComCachedTearOffObject`구현하고 호출해야 하며, 이 에 대한 참조 수는 감소됩니다. 이렇게 하면 `CComCachedTearOffObject`호출되고 `FinalRelease` 찢어짐이 삭제됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOff개체::애드레프

`CComCachedTearOffObject` 개체의 참조 수를 1로 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 및 테스트에 유용할 수 있는 값입니다.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCached티어오프오브젝트::CComCached티어오프오브젝트

생성자입니다.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
【인】 의 포인터에 `IUnknown` `CComCachedTearOffObject`대한 포인터

### <a name="remarks"></a>설명

[M_contained](#m_contained)`CComContainedObject`멤버를 초기화합니다.

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCached티어오프오브젝트::~CComCached티어오프오브젝트

소멸자입니다.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](#finalrelease)호출합니다.

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCached티어오프오브젝트::파이널컨스트럭트

`m_contained::FinalConstruct` 생성하기 `m_contained`위한 `CComContainedObject` <  `contained` 호출은> 해제 클래스에서 구현한 인터페이스에 액세스하는 데 사용되는 개체입니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOff개체::최종 릴리스

> `m_contained::FinalRelease` 개체를 `m_contained` `CComContainedObject` <  `contained` 무료로 호출합니다.

```cpp
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a>CComCachedTearOff개체::m_contained

제거 클래스에서 파생된 [CComContained개체](../../atl/reference/ccomcontainedobject-class.md) 개체 개체입니다.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*포함*<br/>
【인】 찢어짐 개체가 지원하려는 `CComTearOffObjectBase` 인터페이스와 파생된 분리 클래스입니다.

### <a name="remarks"></a>설명

상속 `m_contained` 메서드는 캐시된 분리 개체의 및 `QueryInterface` `FinalConstruct` `FinalRelease`을 통해 분리 클래스의 분리 인터페이스에 액세스하는 데 사용됩니다.

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOff개체::쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 *iid*또는 NULL로 식별된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

요청된 인터페이스가 `IUnknown`있는 경우 는 `CComCachedTearOffObject`포인터를 `IUnknown` 자체 포인터에 반환하고 참조 수를 증가시입니다. 그렇지 않으면 에서 상속된 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 메서드를 사용하여 제거 클래스의 `CComObjectRootEx`인터페이스에 대한 쿼리를 사용합니다.

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOff개체::릴리스

참조 수를 1로 삭제하고 참조 수가 0이면 개체를 `CComCachedTearOffObject` 삭제합니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그가 아닌 빌드에서는 항상 0을 반환합니다. 디버그 빌드에서 진단 또는 테스트에 유용할 수 있는 값을 반환합니다.

## <a name="see-also"></a>참조

[C컴티어오프오브젝트 클래스](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
