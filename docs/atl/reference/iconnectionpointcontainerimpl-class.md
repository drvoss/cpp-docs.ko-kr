---
title: IConnectionPointContainerImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: f6009a1341d6715d6d2f170d3ff2aa1aa4ffcb96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329860"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl 클래스

이 클래스는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체의 컬렉션을 관리 하기 위해 연결 지점 컨테이너를 구현 합니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IConnectionPointContainerImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[I커넥트포인트컨테이너임플::에이넘커넥포인트](#enumconnectionpoints)|연결 가능한 개체에서 지원되는 연결 점을 반복할 열거체를 만듭니다.|
|[I커넥스포인트컨테이너임플::찾기커넥션포인트](#findconnectionpoint)|지정된 IID를 지원하는 연결 지점에 대한 인터페이스 포인터를 검색합니다.|

## <a name="remarks"></a>설명

`IConnectionPointContainerImpl`은 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체의 컬렉션을 관리하기 위해 연결 지점 컨테이너를 구현합니다. `IConnectionPointContainerImpl`클라이언트가 연결할 수 있는 개체에 대한 자세한 정보를 검색하기 위해 호출할 수 있는 두 가지 메서드를 제공합니다.

- `EnumConnectionPoints`클라이언트가 개체가 지원하는 나가는 인터페이스를 결정할 수 있습니다.

- `FindConnectionPoint`을 사용하면 클라이언트가 개체가 특정 나가는 인터페이스를 지원하는지 여부를 확인할 수 있습니다.

ATL에서 연결 점 사용에 대한 자세한 내용은 [연결 지점](../../atl/atl-connection-points.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="iconnectionpointcontainerimplenumconnectionpoints"></a><a name="enumconnectionpoints"></a>I커넥트포인트컨테이너임플::에이넘커넥포인트

연결 가능한 개체에서 지원되는 연결 점을 반복할 열거체를 만듭니다.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>설명

[I커넥션포인트 컨테이너::열거형 윈도우](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) SDK의 연결 지점을 참조하십시오.

## <a name="iconnectionpointcontainerimplfindconnectionpoint"></a><a name="findconnectionpoint"></a>I커넥스포인트컨테이너임플::찾기커넥션포인트

지정된 IID를 지원하는 연결 지점에 대한 인터페이스 포인터를 검색합니다.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>설명

[I커넥포인트 컨테이너::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) SDK에서 연결 지점 찾기를 참조하십시오.

## <a name="see-also"></a>참고 항목

[I커넥션포인트컨테이너](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
