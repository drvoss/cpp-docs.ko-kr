---
title: CComObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: de6ffb45fe5c6f73ab656d5c6185b70d9f5edd38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327639"
---
# <a name="ccomobject-class"></a>CComObject 클래스

이 클래스는 `IUnknown` 집계되지 않은 개체에 대해 구현합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|생성자입니다.|
|[CComObject::~CComObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComObject::AddRef](#addref)|개체의 참조 개수를 증가시입니다.|
|[CComObject::만들기 인스턴스](#createinstance)|(정적) 새 `CComObject` 개체를 만듭니다.|
|[CComObject::쿼리 인터페이스](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComObject::릴리스](#release)|개체의 참조 수를 감소시입니다.|

## <a name="remarks"></a>설명

`CComObject`집계되지 않은 개체에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현합니다. 그러나 `QueryInterface`에 `AddRef`대한 호출 `Release` 및 에 `CComObjectRootEx`대해 위임됩니다.

사용에 `CComObject`대한 자세한 내용은 [ATL COM 개체의 기본](../../atl/fundamentals-of-atl-com-objects.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomobjectaddref"></a><a name="addref"></a>CComObject::AddRef

개체의 참조 개수를 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

이 함수는 개체에 대한 새 증분 참조 수를 반환합니다. 이 값은 진단 또는 테스트에 유용할 수 있습니다.

## <a name="ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject

생성자는 모듈 잠금 수를 증가시다.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>매개 변수

<em>void\*</em><br/>
【인】 이 명명되지 않은 매개 변수는 사용되지 않습니다. 다른 `CComXXXObjectXXX` 생성자와 대칭을 위해 존재합니다.

### <a name="remarks"></a>설명

소멸자는 그것을 감속합니다.

-derive된 개체가 `CComObject` **새** 연산자를 사용하여 성공적으로 생성되는 경우 초기 참조 수는 0입니다. 참조 수를 적절한 값(1)으로 설정하려면 [AddRef](#addref) 함수를 호출합니다.

## <a name="ccomobjectccomobject"></a><a name="dtor"></a>CComObject::~CComObject

소멸자입니다.

```
CComObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](ccomobjectrootex-class.md#finalrelease)호출하며 모듈 잠금 수를 감소시입니다.

## <a name="ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::만들기 인스턴스

이 정적 함수를 사용하면 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)의 오버헤드 없이 새 **CComObject<** `Base` **>** 개체를 만들 수 있습니다.

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>매개 변수

*Pp*<br/>
【아웃】 **CComObject<** `Base` **>** 포인터에 대한 포인터입니다. `CreateInstance` 실패하면 *pp가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환된 개체의 참조 수는 0이므로 `AddRef` 즉시 호출한 다음 완료되면 개체 포인터에서 참조를 해제하는 데 사용합니다. `Release`

개체에 직접 액세스할 필요가 없지만 `CoCreateInstance`의 오버헤드 없이 새 개체를 만들려면 대신 [CComCoClass::CreateInstance를](../../atl/reference/ccomcoclass-class.md#createinstance) 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

## <a name="ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::쿼리 인터페이스

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

## <a name="ccomobjectrelease"></a><a name="release"></a>CComObject::릴리스

개체의 참조 수를 감소시입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

이 함수는 개체에 대한 새 감소된 참조 수를 반환합니다. 디버그 빌드에서 반환 값은 진단 또는 테스트에 유용할 수 있습니다. 디버그가 아닌 빌드에서는 `Release` 항상 0을 반환합니다.

## <a name="see-also"></a>참고 항목

[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
