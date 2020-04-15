---
title: C컴티어오프오브젝트 클래스
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: de7528d3972991c233ee4b9037f609b89d0f7434
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327318"
---
# <a name="ccomtearoffobject-class"></a>C컴티어오프오브젝트 클래스

이 클래스는 해제 인터페이스를 구현합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
찢어짐 개체가 지원하려는 `CComTearOffObjectBase` 인터페이스와 파생된 분리 클래스입니다.

ATL은 두 단계로 찢어짐 인터페이스를 구현합니다 `CComTearOffObjectBase` - 메서드는 `QueryInterface`참조 `CComTearOffObject` 수를 처리하고 , [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown)구현하는 동안 .

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComTearOff개체::CComTearOff오브젝트](#ccomtearoffobject)|생성자입니다.|
|[CComTearOff개체::~CComTearOff개체](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComTearOff개체::애드레프](#addref)|개체에 대한 참조 수를 `CComTearOffObject` 증가합니다.|
|[CComTearOff개체::쿼리 인터페이스](#queryinterface)|해제 클래스 또는 소유자 클래스에서 요청된 인터페이스에 대한 포인터를 반환합니다.|
|[CComTearOff개체::릴리스](#release)|`CComTearOffObject` 개체에 대한 참조 수를 삭제하고 삭제합니다.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOff개체베이스 방법

|||
|-|-|
|[C컴티어오프오브젝트베이스](#ccomtearoffobjectbase)|생성자입니다.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOff개체베이스 데이터 멤버

|||
|-|-|
|[m_pOwner](#m_powner)|소유자 클래스에서 `CComObject` 파생된 포인터입니다.|

## <a name="remarks"></a>설명

`CComTearOffObject`은 해당 인터페이스가 쿼리될 때만 인스턴스화되는 별도의 개체로 분리 인터페이스를 구현합니다. 참조 수가 0이 되면 찢어짐이 삭제됩니다. 일반적으로 찢어짐을 사용하면 기본 개체의 모든 인스턴스에서 vtable 포인터를 저장하므로 거의 사용되지 않는 인터페이스에 대해 해제 인터페이스를 빌드합니다.

제거 개체를 지원할 인터페이스에서 `CComTearOffObjectBase` 분리를 구현하는 클래스를 파생시켜야 합니다. `CComTearOffObjectBase`은 소유자 클래스 및 스레드 모델에서 템플릿화됩니다. 소유자 클래스는 해제가 구현되는 개체의 클래스입니다. 스레드 모델을 지정하지 않으면 기본 스레드 모델이 사용됩니다.

해체 클래스에 대한 COM 맵을 만들어야 합니다. ATL이 찢어짐을 `CComTearOffObject<CYourTearOffClass>` `CComCachedTearOffObject<CYourTearOffClass>`인스턴스화하면.

예를 들어 BEEPER 샘플에서 `CBeeper2` 클래스는 분리 클래스이고 `CBeeper` 클래스는 소유자 클래스입니다.

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a>CComTearOff개체::애드레프

`CComTearOffObject` 개체의 참조 수를 하나씩 증분합니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 및 테스트에 유용할 수 있는 값입니다.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a>CComTearOff개체::CComTearOff오브젝트

생성자입니다.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*태양광 발전*<br/>
【인】 개체에 대한 포인터로 변환되는 `CComObject<Owner>` 포인터입니다.

### <a name="remarks"></a>설명

소유자의 참조 수를 하나씩 증분합니다.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a>CComTearOff개체::~CComTearOff개체

소멸자입니다.

```
~CComTearOffObject();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 파이널릴리스를 호출하며 모듈 잠금 수를 감소시입니다.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a>CComTearOff개체::CComTearOff오브젝트베이스

생성자입니다.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>설명

[m_pOwner](#m_powner) 멤버를 NULL로 초기화합니다.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a>CComTearOff개체::m_pOwner

*소유자에서*파생 된 [CComObject](../../atl/reference/ccomobject-class.md) 개체에 대 한 포인터입니다.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>매개 변수

*소유자*<br/>
【인】 해체가 구현되는 클래스입니다.

### <a name="remarks"></a>설명

포인터는 생성 하는 동안 NULL로 초기화 됩니다.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComTearOff개체::쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 IID입니다.

*ppvObject*<br/>
【아웃】 인터페이스를 찾을 수 없는 경우 *iid*또는 NULL로 식별된 인터페이스 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

먼저 찢어짐 클래스의 인터페이스에 대한 쿼리를 합니다. 인터페이스가 없는 경우 소유자 개체의 인터페이스에 대한 쿼리를 쿼리합니다. 요청된 인터페이스가 `IUnknown`있는 `IUnknown` 경우 소유자의 반환을 반환합니다.

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a>CComTearOff개체::릴리스

참조 수를 하나씩 삭제하고 참조 수가 0이면 `CComTearOffObject`을 삭제합니다.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Return Value

디버그가 아닌 빌드에서는 항상 0을 반환합니다. 디버그 빌드에서 진단 또는 테스트에 유용할 수 있는 값을 반환합니다.

## <a name="see-also"></a>참고 항목

[CComCachedTearOffObject 클래스](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
