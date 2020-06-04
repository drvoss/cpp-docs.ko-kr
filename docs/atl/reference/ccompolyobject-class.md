---
title: CComPolyObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: c880d170a03196d0e15ea8741c786e560d90ddc4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747776"
---
# <a name="ccompolyobject-class"></a>CComPolyObject 클래스

이 클래스는 `IUnknown` 집계된 개체 또는 집계되지 않은 개체에 대해 구현합니다.

## <a name="syntax"></a>구문

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*포함*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|생성자입니다.|
|[CComPolyObject::~CComPolyObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|개체의 참조 수를 증가합니다.|
|[CComPolyObject::만들기 인스턴스](#createinstance)|(정적) [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)의 오버헤드 없이 새 **CComPolyObject<** `contained` **>** 개체를 만들 수 있습니다.|
|[CComPolyObject::최종 구성](#finalconstruct)|의 `m_contained`최종 초기화를 수행합니다.|
|[CComPolyObject::FinalRelease](#finalrelease)|의 최종 `m_contained`소멸을 수행합니다.|
|[CComPolyObject::쿼리 인터페이스](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComPolyObject::Release](#release)|개체의 참조 수를 감소시입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|대리자는 `IUnknown` 개체가 집계되는 경우 알 수 없는 `IUnknown` 외부를 호출하거나 개체가 집계되지 않은 경우 개체를 호출합니다.|

## <a name="remarks"></a>설명

`CComPolyObject`집계된 개체 또는 집계되지 않은 개체에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다.

인스턴스가 `CComPolyObject` 생성되면 알 수 없는 외부의 값이 선택됩니다. NULL인 `IUnknown` 경우 집계되지 않은 개체에 대해 구현됩니다. 외부 알 수 없는 `IUnknown` NULL이 아닌 경우 집계된 개체에 대해 구현됩니다.

이 `CComPolyObject` 사용의 장점은 집계된 서비스 케이스와 집계되지 않은 사례를 처리하기 위해 모듈에 [CComAggObject](../../atl/reference/ccomaggobject-class.md) 및 [CComObject를](../../atl/reference/ccomobject-class.md) 모두 사용하지 않아도 된다는 것입니다. 단일 `CComPolyObject` 개체는 두 경우를 모두 처리합니다. 즉, vtable 의 복사본 은 모듈에 하나의 복사본과 함수의 복사본 이 하나만 존재합니다. vtable이 큰 경우 모듈 크기를 크게 줄일 수 있습니다. 그러나 vtable이 작으면 집계되거나 집계되지 않은 개체에 최적화되지 않으므로 모듈 크기가 약간 커질 `CComPolyObject` `CComAggObject` 수 `CComObject`있습니다.

개체의 클래스 정의에 DECLARE_POLY_AGGREGATABLE 매크로가 `CComPolyObject` 지정되면 개체를 만드는 데 사용됩니다. DECLARE_POLY_AGGREGATABLE 모든 컨트롤 또는 Internet Explorer 컨트롤을 만들려면 ATL 프로젝트 마법사를 사용 하는 경우 자동으로 선언 됩니다.

집계된 경우 `CComPolyObject` 개체는 외부 `IUnknown`개체의 `IUnknown`에서 분리된 자체 를 가지며 자체 참조 수를 유지관리합니다. `CComPolyObject`[CComContained개체를](../../atl/reference/ccomcontainedobject-class.md) 사용하여 알 수 없는 외부로 위임합니다.

집계에 대한 자세한 내용은 [ATL COM 개체의 기본](../../atl/fundamentals-of-atl-com-objects.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccompolyobjectaddref"></a><a name="addref"></a>CComPolyObject::AddRef

개체의 참조 개수를 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

## <a name="ccompolyobjectccompolyobject"></a><a name="ccompolyobject"></a>CComPolyObject::CComPolyObject

생성자입니다.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
【인】 개체를 집계할 경우 알 수 없는 외부에 대한 포인터 또는 개체가 집계되지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

[M_contained](#m_contained)`CComContainedObject`데이터 멤버를 초기화하고 모듈 잠금 수를 늘립니다.

소멸자는 모듈 잠금 수를 감소시입니다.

## <a name="ccompolyobjectccompolyobject"></a><a name="dtor"></a>CComPolyObject::~CComPolyObject

소멸자입니다.

```
~CComPolyObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](#finalrelease)호출하며 모듈 잠금 수를 감소시입니다.

## <a name="ccompolyobjectcreateinstance"></a><a name="createinstance"></a>CComPolyObject::만들기 인스턴스

[CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)의 오버헤드 없이 새 **CComPolyObject<** `contained` **>** 개체를 만들 수 있습니다.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>매개 변수

*Pp*<br/>
【아웃】 **CComPolyObject<** `contained` **>** 포인터에 대한 포인터입니다. `CreateInstance` 실패하면 *pp가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환된 개체의 참조 수는 0이므로 `AddRef` 즉시 호출한 다음 완료되면 개체 포인터에서 참조를 해제하는 데 사용합니다. `Release`

개체에 직접 액세스할 필요가 없지만 `CoCreateInstance`의 오버헤드 없이 새 개체를 만들려면 [대신 CComCoClass::CreateInstance를](../../atl/reference/ccomcoclass-class.md#createinstance) 사용합니다.

## <a name="ccompolyobjectfinalconstruct"></a><a name="finalconstruct"></a>CComPolyObject::최종 구성

개체 생성의 최종 단계에서 호출되는 이 메서드는 [m_contained](#m_contained) 데이터 멤버에 대한 최종 초기화를 수행합니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccompolyobjectfinalrelease"></a><a name="finalrelease"></a>CComPolyObject::최종 릴리스

개체 소멸 중에 호출되는 이 메서드는 [m_contained](#m_contained) 데이터 멤버를 해제합니다.

```cpp
void FinalRelease();
```

## <a name="ccompolyobjectm_contained"></a><a name="m_contained"></a>CComPolyObject::m_contained

클래스에서 파생된 [CComContained개체](../../atl/reference/ccomcontainedobject-class.md) 개체 개체입니다.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*포함*<br/>
【인】 [클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

### <a name="remarks"></a>설명

`IUnknown`호출은 `m_contained` 개체가 집계되는 경우 알 수 없는 외부로 `IUnknown` 위임되거나 개체가 집계되지 않은 경우 이 개체의 호출에 위임됩니다.

## <a name="ccompolyobjectqueryinterface"></a><a name="queryinterface"></a>CComPolyObject::쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>매개 변수

*Q*<br/>
COM 인터페이스입니다.

*Iid*<br/>
【인】 요청되는 인터페이스의 식별자입니다.

*ppvObject*<br/>
【아웃】 *iid*. 개체가 이 인터페이스를 지원하지 않으면 *ppvObject가* NULL로 설정됩니다.

*Pp*<br/>
【아웃】 에서 식별된 인터페이스에 `__uuidof(Q)`대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

집계된 개체의 경우 요청된 `IUnknown`인터페이스가 있는 `QueryInterface` 경우 집계된 개체의 `IUnknown` 자체 포인터에 대한 포인터를 반환하고 참조 수를 증가시입니다. 그렇지 않으면 이 메서드는 데이터 `CComContainedObject` 멤버를 통해 인터페이스에 대해 [m_contained.](#m_contained)

## <a name="ccompolyobjectrelease"></a><a name="release"></a>CComPolyObject::릴리스

개체의 참조 수를 감소시입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그 빌드에서 `Release` 진단 또는 테스트에 유용할 수 있는 값을 반환합니다. 비디버그 빌드에서는 `Release` 항상 0을 반환합니다.

## <a name="see-also"></a>참조

[CComObject루트텍스 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
