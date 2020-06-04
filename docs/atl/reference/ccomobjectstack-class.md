---
title: CComObjectStack 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 8c3fd56635da8b80c84f6151009586b7bd2b4341
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327582"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack 클래스

이 클래스는 임시 COM 개체를 만들고 `IUnknown`의 골격 구현을 제공합니다.

## <a name="syntax"></a>구문

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComObject스택::CComObjectStack](#ccomobjectstack)|생성자입니다.|
|[CComObject스택::~CComObject스택](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComObject스택::추가](#addref)|0을 반환합니다. 디버그 모드에서는 `_ASSERTE`를 호출합니다.|
|[CComObject스택::쿼리 인터페이스](#queryinterface)|E_NOINTERFACE 반환합니다. 디버그 모드에서는 `_ASSERTE`를 호출합니다.|
|[CComObject스택::릴리스](#release)|0을 반환합니다. 디버그 모드에서는 `_ASSERTE`를 호출합니다. ~|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComObject스택::m_hResFinalConstruct](#m_hresfinalconstruct)|개체를 구성하는 동안 반환된 HRESULT를 포함합니다. `CComObjectStack`|

## <a name="remarks"></a>설명

`CComObjectStack`임시 COM 개체를 만들고 개체에 `IUnknown`의 골격 구현을 제공하는 데 사용됩니다. 일반적으로 개체는 하나의 함수(즉, 스택에 푸시)내에서 로컬 변수로 사용됩니다. 함수가 완료되면 개체가 소멸되므로 효율성을 높이기 위해 참조 카운트가 수행되지 않습니다.

다음 예제에서는 함수 내에서 사용되는 COM 개체를 만드는 방법을 보여 주며 있습니다.

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

임시 개체가 `Tempobj` 스택에 푸시되고 함수가 완료되면 자동으로 사라집니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObjectStack`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a>CComObject스택::추가

0을 반환합니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

0을 반환합니다.

### <a name="remarks"></a>설명

디버그 모드에서는 `_ASSERTE`를 호출합니다.

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>CComObject스택::CComObjectStack

생성자입니다.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>설명

호출한 `FinalConstruct` 다음 에서 반환되는 HRESULT로 [m_hResFinalConstruct](#m_hresfinalconstruct) 설정합니다. `FinalConstruct` [CComObjectRoot에서](../../atl/reference/ccomobjectroot-class.md)기본 클래스를 파생하지 않은 경우 고유한 `FinalConstruct` 메서드를 제공해야 합니다. 이 소멸자는 `FinalRelease`을 호출합니다.

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a>CComObject스택::~CComObject스택

소멸자입니다.

```
CComObjectStack();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](ccomobjectrootex-class.md#finalrelease)호출합니다.

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObject스택::m_hResFinalConstruct

개체를 구성하는 동안 `FinalConstruct` 호출에서 `CComObjectStack` 반환된 HRESULT를 포함합니다.

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>CComObject스택::쿼리 인터페이스

E_NOINTERFACE 반환합니다.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Return Value

E_NOINTERFACE 반환합니다.

### <a name="remarks"></a>설명

디버그 모드에서는 `_ASSERTE`를 호출합니다.

## <a name="ccomobjectstackrelease"></a><a name="release"></a>CComObject스택::릴리스

0을 반환합니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

0을 반환합니다.

### <a name="remarks"></a>설명

디버그 모드에서는 `_ASSERTE`를 호출합니다.

## <a name="see-also"></a>참고 항목

[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal 클래스](../../atl/reference/ccomobjectglobal-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
