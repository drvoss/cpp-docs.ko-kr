---
title: IConnectionPointImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: c62ac3310a579379674674a7a9a517e3f2fd60e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329850"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl 클래스

이 클래스는 연결 지점을 구현합니다.

## <a name="syntax"></a>구문

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IConnectionPointImpl`

*piid*<br/>
연결 점 개체로 표시되는 인터페이스의 IID에 대한 포인터입니다.

*CDV*<br/>
연결을 관리하는 클래스입니다. 기본값은 무제한 연결을 허용하는 [CComDynamicUnkArray입니다.](../../atl/reference/ccomdynamicunkarray-class.md) 고정된 수의 연결을 지정하는 [CComUnkArray를](../../atl/reference/ccomunkarray-class.md)사용할 수도 있습니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I커넥스포인트임플::조언](#advise)|연결 점과 싱크 사이에 연결을 설정합니다.|
|[I커넥포인트임플::에이넘커넥션](#enumconnections)|연결 점에 대한 연결을 반복할 열거기를 만듭니다.|
|[I커넥포인트임플::GetConnection인터페이스](#getconnectioninterface)|연결 지점으로 표시되는 인터페이스의 IID를 검색합니다.|
|[I커넥포인트임플::겟커넥션포인트컨테이너](#getconnectionpointcontainer)|연결 가능한 개체에 대한 인터페이스 포인터를 검색합니다.|
|[I커넥스포인트임플::조언 해제](#unadvise)|을 통해 `Advise`이전에 설정된 연결을 종료합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[I커넥포인트임플::m_vec](#m_vec)|연결 점에 대한 연결을 관리합니다.|

## <a name="remarks"></a>설명

`IConnectionPointImpl`을 사용하면 개체가 나가는 인터페이스를 클라이언트에 노출할 수 있는 연결 지점을 구현합니다. 클라이언트는 싱크라는 개체에 이 인터페이스를 구현합니다.

ATL은 [IConnectionPointContainerImpl을](../../atl/reference/iconnectionpointcontainerimpl-class.md) 사용하여 연결 가능한 개체를 구현합니다. 연결 가능한 개체 내의 각 연결 지점은 *piid로*식별되는 나가는 인터페이스를 나타냅니다. 클래스 *CDV는* 연결 점과 싱크 사이의 연결을 관리합니다. 각 연결은 "쿠키"로 고유하게 식별됩니다.

ATL에서 연결 점 사용에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a>I커넥스포인트임플::조언

연결 점과 싱크 사이에 연결을 설정합니다.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>설명

[조언 해제를](#unadvise) 사용하여 연결 호출을 종료합니다.

[I커넥스포인트::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) SDK에서 조언.

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>I커넥포인트임플::에이넘커넥션

연결 점에 대한 연결을 반복할 열거기를 만듭니다.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>설명

[I커넥트 포인트::열거형](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) Windows SDK의 연결.

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>I커넥포인트임플::GetConnection인터페이스

연결 지점으로 표시되는 인터페이스의 IID를 검색합니다.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>설명

[I커넥션 포인트::GetConnectionWindows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) SDK의 인터페이스를 참조하십시오.

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>I커넥포인트임플::겟커넥션포인트컨테이너

연결 가능한 개체에 대한 인터페이스 포인터를 검색합니다.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>설명

[I커넥스포인트::GetConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) Windows SDK의 컨테이너를 참조하십시오.

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a>I커넥포인트임플::m_vec

연결 점 개체와 싱크 사이의 연결을 관리합니다.

```
CDV m_vec;
```

### <a name="remarks"></a>설명

기본적으로 `m_vec` [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)형식입니다.

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a>I커넥스포인트임플::조언 해제

[조언을](#advise)통해 이전에 설정된 연결을 종료합니다.

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>설명

[I커넥스포인트::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) SDK에서 조언 해제를 참조하십시오.

## <a name="see-also"></a>참고 항목

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
