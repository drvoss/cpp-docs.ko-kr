---
title: CComAggObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: b9200c9c396fc16b6df3f4c2f4c66fb7976316d4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748168"
---
# <a name="ccomaggobject-class"></a>CComAggObject 클래스

이 클래스는 집계된 개체에 대해 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 인터페이스를 구현합니다. 정의에 따라 집계된 개체는 외부 개체 내에 포함됩니다. 클래스는 `CComAggObject` 외부 클라이언트에 직접 액세스할 수 있는 인터페이스를 노출한다는 점을 제외하면 [CComObject 클래스와](../../atl/reference/ccomobject-class.md)유사합니다.

## <a name="syntax"></a>구문

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*포함*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|생성자입니다.|
|[CComAggObject::~CComAggObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComAggObject::애드레프](#addref)|집계된 개체의 참조 개수를 증가시입니다.|
|[CComAggObject::만들기 인스턴스](#createinstance)|이 정적 함수를 사용하면 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)의 오버헤드 없이 새 **CComAggObject<** `contained` **>** 개체를 만들 수 있습니다.|
|[CComAggObject::FinalConstruct](#finalconstruct)|의 `m_contained`최종 초기화를 수행합니다.|
|[CComAggObject::FinalRelease](#finalrelease)|의 최종 `m_contained`소멸을 수행합니다.|
|[CComAggObject::쿼리 인터페이스](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComAggObject::릴리스](#release)|집계된 개체의 참조 수를 삭제합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|대리자는 `IUnknown` 알 수 없는 외부를 호출합니다.|

## <a name="remarks"></a>설명

`CComAggObject`은 집계된 개체에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다. `CComAggObject`외부 개체의 `IUnknown` `IUnknown` 인터페이스와 분리된 자체 인터페이스를 가지며 자체 참조 수를 유지관리합니다.

집계에 대한 자세한 내용은 [ATL COM 개체의 기본](../../atl/fundamentals-of-atl-com-objects.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject::애드레프

집계된 개체의 참조 개수를 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject

생성자입니다.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
【인】 알 수 없는 외부.

### <a name="remarks"></a>설명

`CComContainedObject`[M_contained](#m_contained) 멤버를 초기화하고 모듈 잠금 수를 늘립니다.

소멸자는 모듈 잠금 수를 감소시입니다.

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a>CComAggObject::~CComAggObject

소멸자입니다.

```
~CComAggObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](#finalrelease)호출하며 모듈 잠금 수를 감소시입니다.

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::만들기 인스턴스

이 정적 함수를 사용하면 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)의 오버헤드 없이 새 **CComAggObject<** `contained` **>** 개체를 만들 수 있습니다.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>매개 변수

*Pp*<br/>
【아웃】 **CComAggObject에\<** 대한 포인터에는 포인터가<em>포함되어 있습니다.</em> **>** `CreateInstance` 실패하면 *pp가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환된 개체의 참조 수는 0이므로 `AddRef` 즉시 호출한 다음 완료되면 개체 포인터에서 참조를 해제하는 데 사용합니다. `Release`

개체에 직접 액세스할 필요가 없지만 `CoCreateInstance`의 오버헤드 없이 새 개체를 만들려면 대신 [CComCoClass::CreateInstance를](../../atl/reference/ccomcoclass-class.md#createinstance) 사용합니다.

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::최종 구성

개체 생성의 최종 단계에서 호출되는 이 메서드는 [m_contained](#m_contained) 멤버에 대한 최종 초기화를 수행합니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::최종 릴리스

개체 소멸 중에 호출되는 이 메서드는 [m_contained](#m_contained) 멤버를 해제합니다.

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a>CComAggObject::m_contained

클래스에서 파생된 [CComContained개체](../../atl/reference/ccomcontainedobject-class.md) 개체 개체입니다.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*포함*<br/>
【인】 [클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

### <a name="remarks"></a>설명

모든 `IUnknown` `m_contained` 호출은 알 수 없는 외부로 위임됩니다.

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 식별자입니다.

*ppvObject*<br/>
【아웃】 *iid*. 개체가 이 인터페이스를 지원하지 않으면 *ppvObject가* NULL로 설정됩니다.

*Pp*<br/>
【아웃】 유형으로 `Q`식별된 인터페이스 포인터에 대한 포인터입니다. 개체가 이 인터페이스를 지원하지 않으면 *pp가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

요청된 인터페이스가 `IUnknown` `QueryInterface` 있는 경우 집계된 개체의 자체 `IUnknown` 포인터에 대한 포인터를 반환하고 참조 수를 증가시입니다. 그렇지 않으면 이 메서드는 멤버를 `CComContainedObject` 통해 인터페이스에 대해 [m_contained.](#m_contained)

## <a name="ccomaggobjectrelease"></a><a name="release"></a>CComAggObject::릴리스

집계된 개체의 참조 수를 삭제합니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그 빌드에서 `Release` 진단 또는 테스트에 유용할 수 있는 값을 반환합니다. 디버그가 아닌 빌드에서는 `Release` 항상 0을 반환합니다.

## <a name="see-also"></a>참조

[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
