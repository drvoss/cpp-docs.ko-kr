---
title: IObjectWithSiteImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: 034e5dd42f6e10286520bb2a08effc40b0aca71a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329638"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl 클래스

이 클래스는 개체가 해당 사이트와 통신할 수 있는 메서드를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IObjectWithSiteImpl`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|인터페이스 포인터에 대 한 사이트를 쿼리 합니다.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|개체에 사이트의 `IUnknown` 포인터를 제공합니다.|
|[IObjectWithSiteImpl::SetSite](#setsite)|개체에 사이트의 `IUnknown` 포인터를 제공합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|사이트의 `IUnknown` 포인터를 관리합니다.|

## <a name="remarks"></a>설명

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 인터페이스를 사용하면 개체가 해당 사이트와 통신할 수 있습니다. 클래스는 `IObjectWithSiteImpl` 디버그 빌드에서 덤프 `IUnknown` 장치에 정보를 전송하여 이 인터페이스및 구현의 기본 구현을 제공합니다.

`IObjectWithSiteImpl`두 가지 방법을 지정합니다. 클라이언트가 먼저 `SetSite`호출하여 사이트의 `IUnknown` 포인터를 전달합니다. 이 포인터는 개체 내에 저장되며 나중에 `GetSite`에 대한 호출을 통해 검색할 수 있습니다.

일반적으로 컨트롤이 아닌 `IObjectWithSiteImpl` 개체를 만들 때 클래스를 파생합니다. 컨트롤의 경우 사이트 포인터를 제공하는 [IOleObjectImpl에서](../../atl/reference/ioleobjectimpl-class.md)클래스를 파생합니다. 클래스를 둘 다에서 `IObjectWithSiteImpl` `IOleObjectImpl`파생시키지 마십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a>IObjectWithSiteImpl::GetSite

`riid`에서 식별된 인터페이스에 대한 포인터에 대한 사이트를 쿼리합니다.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>설명

사이트가 이 인터페이스를 지원하는 경우 포인터는 을 통해 `ppvSite`반환됩니다. 그렇지 `ppvSite` 않으면 NULL로 설정됩니다.

[IObjectWithSite::GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) Windows SDK를 참조하십시오.

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite

사이트의 `IUnknown` 포인터를 관리합니다.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>설명

`m_spUnkSite`처음에 [SetSite](#setsite)에 대한 호출을 통해 이 포인터를 받습니다.

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite

개체에 사이트의 `IUnknown` 포인터를 제공합니다.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>매개 변수

*펀사이트*<br/>
【인】 이 개체를 `IUnknown` 관리하는 사이트의 인터페이스 포인터에 대한 포인터입니다. NULL인 경우 개체는 `IUnknown::Release` 개체가 해당 사이트를 더 이상 알지 않는 기존 사이트를 호출해야 합니다.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a>IObjectWithSiteImpl::SetSite

개체에 사이트의 `IUnknown` 포인터를 제공합니다.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>설명

[IObjectWithSite::Windows](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) SDK의 설정 사이트를 참조하십시오.

## <a name="see-also"></a>참고 항목

[클래스 개요](../../atl/atl-class-overview.md)
