---
title: C컴에이피어드오브젝트 클래스
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 72ba27c3be6576621995ffb8c98995c6abc9324c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320790"
---
# <a name="ccomcontainedobject-class"></a>C컴에이피어드오브젝트 클래스

이 클래스는 소유자 개체의 `IUnknown`에 위임하여 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)을 구현합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComContained개체::C컴포함오브젝트](#ccomcontainedobject)|생성자입니다. 소유자 개체의 에 대한 멤버 포인터를 초기화합니다. `IUnknown`|
|[CComContained 개체::~CComContained개체](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|소유자 개체의 참조 개수를 증가시입니다.|
|[CComcontained개체::Get제어알 수 없음](#getcontrollingunknown)|소유자 개체의 를 `IUnknown`검색합니다.|
|[CComContainedObject::QueryInterface](#queryinterface)|소유자 개체에 요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComContainedObject::Release](#release)|소유자 개체의 참조 수를 감소시입니다.|

## <a name="remarks"></a>설명

ATL은 `CComContainedObject` 클래스 [CComAggObject,](../../atl/reference/ccomaggobject-class.md) [CComPolyObject](../../atl/reference/ccompolyobject-class.md)및 [CComCachedTearOffObject에서](../../atl/reference/ccomcachedtearoffobject-class.md)사용합니다. `CComContainedObject`소유자 개체의 `IUnknown`를 위임하여 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)을 구현합니다. 소유자는 집계의 외부 개체 또는 분리 인터페이스를 만들 때 개체입니다. `CComContainedObject` 의 `CComObjectRootEx` `OuterQueryInterface`를 `OuterAddRef`호출합니다 `OuterRelease`. `Base`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComContainedObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a>CComContained개체::추가 참조

소유자 개체의 참조 개수를 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CComContained개체::C컴포함오브젝트

생성자입니다.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
【인】 소유자 개체의 `IUnknown`.

### <a name="remarks"></a>설명

`m_pOuterUnknown` 멤버 포인터(클래스를 `Base` 통해 상속)를 *pv로*설정합니다.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>CComContained 개체::~CComContained개체

소멸자입니다.

```
~CComContainedObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제합니다.

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComcontained개체::Get제어알 수 없음

소유자 `m_pOuterUnknown` 개체의 를 보유 하는 멤버 포인터(Base 클래스를 `IUnknown`통해 상속)를 반환합니다. *Base*

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Return Value

소유자 개체의 `IUnknown`.

### <a name="remarks"></a>설명

`Base`가 [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) 매크로를 선언한 경우 이 메서드는 virtual 일 수 있습니다.

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CComContained 개체::쿼리 인터페이스

소유자 개체에 요청된 인터페이스에 대한 포인터를 검색합니다.

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

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a>CComContained개체::릴리스

소유자 개체의 참조 수를 감소시입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그 빌드에서 `Release` 진단 또는 테스트에 유용할 수 있는 값을 반환합니다. 디버그가 아닌 빌드에서는 `Release` 항상 0을 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
