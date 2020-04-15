---
title: CComObjectNoLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: c190f495e284e98b27a6c6dc2099a8dfc4b1693d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327620"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock 클래스

이 클래스는 `IUnknown` 집계되지 않은 개체에 대해 구현되지만 생성자의 모듈 잠금 수를 증가시키지 않습니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>매개 변수

*기본*<br/>
[클래스는 CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx에서](../../atl/reference/ccomobjectrootex-class.md)파생된 클래스뿐만 아니라 개체에서 지원하려는 다른 인터페이스에서 파생됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|생성자입니다.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|개체의 참조 개수를 증가시입니다.|
|[CComObjectNoLock::쿼리 인터페이스](#queryinterface)|요청된 인터페이스에 대한 포인터를 반환합니다.|
|[CComObjectNoLock::릴리스](#release)|개체의 참조 수를 감소시입니다.|

## <a name="remarks"></a>설명

`CComObjectNoLock`집계되지 않은 개체에 대해 [IUnknown을](/windows/win32/api/unknwn/nn-unknwn-iunknown) 구현한다는 점에서 [CComObject와](../../atl/reference/ccomobject-class.md) 유사합니다. 그러나 `CComObjectNoLock` 생성자의 모듈 잠금 수를 증가시키지 않습니다.

ATL은 `CComObjectNoLock` 클래스 공장에 내부적으로 사용합니다. 일반적으로 이 클래스는 직접 사용하지 않습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="ccomobjectnolockaddref"></a><a name="addref"></a>CComObjectNoLock::AddRef

개체의 참조 개수를 증가시입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Return Value

진단 또는 테스트에 유용할 수 있는 값입니다.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock

생성자입니다. [CComObject와](../../atl/reference/ccomobject-class.md)달리 모듈 잠금 수는 증가하지 않습니다.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>매개 변수

<em>void\*</em><br/>
【인】 이 명명되지 않은 매개 변수는 사용되지 않습니다. 다른 `CComXXXObjectXXX` 생성자와 대칭을 위해 존재합니다.

## <a name="ccomobjectnolockccomobjectnolock"></a><a name="dtor"></a>CComObjectNoLock::~CComObjectNoLock

소멸자입니다.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>설명

할당된 모든 리소스를 해제하고 [FinalRelease를](ccomobjectrootex-class.md#finalrelease)호출합니다.

## <a name="ccomobjectnolockqueryinterface"></a><a name="queryinterface"></a>CComObjectNoLock::쿼리 인터페이스

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 요청되는 인터페이스의 식별자입니다.

*ppvObject*<br/>
【아웃】 *iid*. 개체가 이 인터페이스를 지원하지 않으면 *ppvObject가* NULL로 설정됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="ccomobjectnolockrelease"></a><a name="release"></a>CComObjectNoLock::릴리스

개체의 참조 수를 감소시입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Return Value

디버그 빌드에서 `Release` 진단 또는 테스트에 유용할 수 있는 값을 반환합니다. 디버그가 아닌 빌드에서는 `Release` 항상 0을 반환합니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
