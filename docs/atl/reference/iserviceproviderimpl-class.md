---
title: IServiceProviderImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: ef0ee4f77441cb8d19ea2d6dcada1fed9faf2782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329425"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl 클래스

이 클래스는 인터페이스의 `IServiceProvider` 기본 구현을 제공합니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IServiceProviderImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IServiceProvider Impl::쿼리 서비스](#queryservice)|지정된 서비스를 만들거나 액세스하고 서비스에 대해 지정된 인터페이스에 인터페이스 포인터를 반환합니다.|

## <a name="remarks"></a>설명

인터페이스는 `IServiceProvider` GUID에 의해 지정된 서비스를 찾고 서비스에 대해 요청된 인터페이스에 대한 인터페이스 포인터를 반환합니다. 클래스는 `IServiceProviderImpl` 이 인터페이스의 기본 구현을 제공합니다.

`IServiceProviderImpl`한 가지 방법을 지정합니다: [QueryService](#queryservice)는 지정된 서비스를 만들거나 액세스하고 서비스에 대한 지정된 인터페이스에 인터페이스 포인터를 반환합니다.

`IServiceProviderImpl`[BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) 시작하여 [END_SERVICE_MAP](service-map-macros.md#end_service_map)종료하는 서비스 맵을 사용합니다.

서비스 맵에는 개체에서 지원하는 지정된 서비스 id(SID)를 나타내는 [SERVICE_ENTRY](service-map-macros.md#service_entry)및 다른 `QueryService` 개체에 체인을 호출하는 [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain)라는 두 개의 항목이 포함되어 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProvider Impl::쿼리 서비스

지정된 서비스를 만들거나 액세스하고 서비스에 대해 지정된 인터페이스에 인터페이스 포인터를 반환합니다.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*가이드 서비스*<br/>
【인】 서비스 식별자(SID)에 대한 포인터입니다.

*riid*<br/>
【인】 호출자가 액세스 권한을 얻기 위한 인터페이스의 식별자입니다.

*ppvObj*<br/>
【아웃】 요청된 인터페이스에 대한 간접 포인터입니다.

### <a name="return-value"></a>Return Value

반환된 HRESULT 값은 다음 중 하나입니다.

|반환 값|의미|
|------------------|-------------|
|S_OK|서비스가 성공적으로 만들어지거나 검색되었습니다.|
|E_INVALIDARG|하나 이상의 인수가 잘못된 경우|
|E_OUTOFMEMORY|메모리가 부족하여 서비스를 만들 수 없습니다.|
|E_UNEXPECTED|알 수 없는 오류가 발생했습니다.|
|E_NOINTERFACE|요청된 인터페이스가 이 서비스의 일부가 아니거나 서비스를 알 수 없습니다.|

### <a name="remarks"></a>설명

`QueryService`은 지정된 서비스에서 요청된 인터페이스에 대한 간접 포인터를 반환합니다. 호출자는 더 이상 필요하지 않은 경우 이 포인터를 해제할 책임이 있습니다.

호출할 `QueryService`때 서비스 식별자(guidService)와 인터페이스 식별자(riid)를 모두 전달합니다.*guidService**riid* *guidService는* 액세스를 원하는 서비스를 지정하고 *riid는* 서비스의 일부인 인터페이스를 식별합니다. 그 대신 인터페이스에 대한 간접 포인터를 받게 됩니다.

인터페이스를 구현하는 개체는 다른 서비스의 일부인 인터페이스를 구현할 수도 있습니다. 다음을 고려해 보세요.

- 이러한 인터페이스 중 일부는 선택 사항일 수 있습니다. 서비스 설명에 정의된 모든 인터페이스가 서비스의 모든 구현 또는 반환된 모든 개체에 반드시 존재하는 것은 아닙니다.

- 에 대한 `QueryInterface`호출과 달리 다른 서비스 식별자를 전달한다고 해서 반드시 다른 구성 요소 개체 모델(COM) 개체가 반환되는 것은 아닙니다.

- 반환된 개체에는 서비스 정의의 일부가 아닌 추가 인터페이스가 있을 수 있습니다.

SID_SMyService 및 SID_SYourService 같은 두 개의 서로 다른 서비스는 인터페이스의 구현이 두 서비스 간에 공통점이 없더라도 동일한 인터페이스의 사용을 지정할 수 있습니다. 이는 호출(SID_SMyService, `QueryService` IID_IDispatch)이 `QueryService` 다른 개체(SID_SYourService, IID_IDispatch)와 다른 개체를 반환할 수 있기 때문에 작동합니다. 다른 서비스 식별자를 지정할 때 개체 ID가 가정되지 않습니다.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
