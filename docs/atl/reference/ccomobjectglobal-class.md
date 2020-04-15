---
title: CComObjectGlobal 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 9a784584179186cdf1e63c1ec43cad4d59391ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327630"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal 클래스

이 클래스는 개체를 포함하는 모듈에 `Base` 대한 참조 수를 관리합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComObject글로벌::CComObject글로벌](#ccomobjectglobal)|생성자입니다.|
|[CComObject글로벌::~CComObject글로벌](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComObject글로벌::애드레프](#addref)|전역 `AddRef`을 구현합니다.|
|[CComObject 전역::쿼리 인터페이스](#queryinterface)|전역 `QueryInterface`을 구현합니다.|
|[CComObject글로벌::릴리스](#release)|전역 `Release`을 구현합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CComObject글로벌:m_hResFinalConstruct](#m_hresfinalconstruct)|개체를 구성하는 동안 반환된 HRESULT를 포함합니다. `CComObjectGlobal`|

## <a name="remarks"></a>설명

`CComObjectGlobal`개체를 포함하는 모듈의 참조 `Base` 수를 관리합니다. `CComObjectGlobal`모듈이 해제되지 않는 한 개체가 삭제되지 않도록 합니다. 전체 모듈의 참조 수가 0으로 바을 때만 개체가 제거됩니다.

예를 들어 `CComObjectGlobal`, 클래스 팩터리를 사용하여 모든 클라이언트에서 공유하는 공통 전역 개체를 보유할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a>CComObject글로벌::애드레프

개체의 참조 수를 1로 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 및 테스트에 유용할 수 있는 값입니다.

### <a name="remarks"></a>설명

`AddRef` 기본적으로 `_Module::Lock`호출 은 `_Module` [CComModule의](../../atl/reference/ccommodule-class.md) 전역 인스턴스 또는 호출에서 파생 된 클래스입니다.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a>CComObject글로벌::CComObject글로벌

생성자입니다. 호출한 `FinalConstruct` 다음 [m_hResFinalConstruct](#m_hresfinalconstruct) `HRESULT` 를 `FinalConstruct`로 설정합니다.

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>설명

[CComObjectRoot에서](../../atl/reference/ccomobjectroot-class.md)기본 클래스를 파생하지 않은 경우 고유한 `FinalConstruct` 메서드를 제공해야 합니다. 이 소멸자는 `FinalRelease`을 호출합니다.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a>CComObject글로벌::~CComObject글로벌

소멸자입니다.

```
CComObjectGlobal();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](ccomobjectrootex-class.md#finalrelease)호출합니다.

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObject글로벌:m_hResFinalConstruct

개체를 구성하는 `FinalConstruct` 동안 호출할 `CComObjectGlobal` HRESULT를 포함합니다.

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a>CComObject 전역::쿼리 인터페이스

요청된 인터페이스 포인터에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 iid 또는 NULL로 식별된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`QueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다.

## <a name="ccomobjectglobalrelease"></a><a name="release"></a>CComObject글로벌::릴리스

개체의 참조 수를 1로 감소시입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그 빌드에서 `Release` 진단 및 테스트에 유용할 수 있는 값을 반환합니다. 디버그가 아닌 빌드에서는 `Release` 항상 0을 반환합니다.

### <a name="remarks"></a>설명

`Release` 기본적으로 `_Module::Unlock`호출 은 `_Module` [CComModule의](../../atl/reference/ccommodule-class.md) 전역 인스턴스 또는 호출에서 파생 된 클래스입니다.

## <a name="see-also"></a>참고 항목

[CComObjectStack 클래스](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
