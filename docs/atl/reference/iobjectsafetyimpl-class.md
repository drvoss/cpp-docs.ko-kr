---
title: IObjectSafetyImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: 6eee7585bc3c5587e106ab6b0cefb4b7129df59f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329657"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl 클래스

이 클래스는 클라이언트가 `IObjectSafety` 개체의 안전 수준을 검색하고 설정할 수 있도록 인터페이스의 기본 구현을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 파생된 클래스입니다. `IObjectSafetyImpl`

*dw 지원안전*<br/>
컨트롤에 지원되는 안전 옵션을 지정합니다. 다음 값 중 하나를 사용할 수 있습니다.

- INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) 매개 변수로 `riid` 식별 된 인터페이스는 스크립팅에 대 한 안전 하 게 해야 합니다.

- INTERFACESAFE_FOR_UNTRUSTED_DATA 매개 변수로 `SetInterfaceSafetyOptions` `riid` 식별된 인터페이스는 초기화 중에 신뢰할 수 없는 데이터에 대해 안전하게 만들어야 합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IObjectSafetyImpl::GetInterface안전옵션](#getinterfacesafetyoptions)|개체에서 지원하는 안전 옵션과 현재 개체에 대해 설정된 안전 옵션을 검색합니다.|
|[IObjectSafetyImpl::SetInterface안전옵션](#setinterfacesafetyoptions)|초기화 또는 스크립팅에 대 한 개체를 안전 하 게 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|객체의 현재 안전 수준을 저장합니다.|

## <a name="remarks"></a>설명

클래스는 `IObjectSafetyImpl` 의 기본 `IObjectSafety`구현을 제공합니다. 인터페이스를 `IObjectSafety` 통해 클라이언트는 개체의 안전 수준을 검색하고 설정할 수 있습니다. 예를 들어 웹 브라우저는 `IObjectSafety::SetInterfaceSafetyOptions` 초기화에 대한 컨트롤을 안전하게 만들거나 스크립팅에 안전하도록 호출할 수 있습니다.

CATID_SafeForScripting 및 CATID_SafeForInitializing 구성 요소 범주와 [함께 IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) 매크로를 사용하면 구성 요소가 안전한지 지정하는 다른 방법이 제공됩니다.

**관련 기사** [ATL 자습서,](../../atl/active-template-library-atl-tutorial.md) [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterface안전옵션

개체에서 지원하는 안전 옵션과 현재 개체에 대해 설정된 안전 옵션을 검색합니다.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>설명

구현은 개체의 `IUnknown::QueryInterface`구현에서 지원하는 모든 인터페이스에 대해 적절한 값을 반환합니다.

> [!IMPORTANT]
> 지원하는 `IObjectSafety` 모든 개체는 자체 보안및 위임하는 모든 개체의 보안을 담당합니다. 프로그래머는 사용자의 컨텍스트에서 코드를 실행하고 사이트 간 스크립팅을 수행하여 발생하는 문제를 고려하고 적절한 영역 검사를 수행해야 합니다.

[IObjectSafety::GetInterface안전옵션은](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) Windows SDK에서 확인합니다.

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety

객체의 현재 안전 수준을 저장합니다.

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterface안전옵션

[m_dwCurrentSafety](#m_dwcurrentsafety) 멤버를 적절한 값으로 설정하여 초기화 또는 스크립팅에 개체를 안전하게 만듭니다.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>설명

구현은 개체의 구현에서 지원되지 않는 인터페이스에 `IUnknown::QueryInterface`대한 E_NOINTERFACE 반환합니다.

> [!IMPORTANT]
> 지원하는 `IObjectSafety` 모든 개체는 자체 보안및 위임하는 모든 개체의 보안을 담당합니다. 프로그래머는 사용자의 컨텍스트에서 코드를 실행하고 사이트 간 스크립팅을 수행하여 발생하는 문제를 고려하고 적절한 영역 검사를 수행해야 합니다.

[IObjectSafety::SetInterface안전옵션은](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) Windows SDK에서 확인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[IObjectSafety 인터페이스](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[클래스 개요](../../atl/atl-class-overview.md)
