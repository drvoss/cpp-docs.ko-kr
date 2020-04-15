---
title: IDispEventImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: fa6e9f972accd0115d9f1e3248bd97ddde0c3c63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329767"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl 클래스

이 클래스는 `IDispatch` 메서드의 구현을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>매개 변수

*nID*<br/>
소스 개체에 대한 고유 식별자입니다. 복합 `IDispEventImpl` 컨트롤의 기본 클래스인 경우 이 매개 변수에 대해 원하는 포함된 컨트롤의 리소스 ID를 사용합니다. 다른 경우에는 임의의 양수 정수를 사용합니다.

*T*<br/>
에서 파생되는 사용자의 클래스입니다. `IDispEventImpl`

*피디드 (것)들*<br/>
이 클래스에서 구현한 이벤트 디스프인터페이스의 IID에 대한 포인터입니다. 이 인터페이스는 *plibid,* *wMajor*및 *wMinor로*표시된 형식 라이브러리에 정의되어야 합니다.

*plibid*<br/>
*pdiid로*가리키는 디스패치 인터페이스를 정의하는 형식 라이브러리에 대한 포인터입니다. **&GUID_NULL**경우 이벤트를 소싱하는 개체에서 형식 라이브러리가 로드됩니다.

*wMajor*<br/>
형식 라이브러리의 주 버전입니다. 기본값은 0입니다.

*wMinor*<br/>
형식 라이브러리의 부 버전입니다. 기본값은 0입니다.

*tihclass*<br/>
*T에*대 한 형식 정보를 관리 하는 데 사용 하는 클래스입니다. 기본값은 형식의 `CComTypeInfoHolder`클래스입니다. 그러나 `CComTypeInfoHolder`이 템플릿 매개 변수를 재정의할 수 있습니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|속성|Description|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|형식 정보를 관리하는 데 사용되는 클래스입니다. 기본적으로 `CComTypeInfoHolder`입니다.|

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IDispEvent Impl::GetFuncInfoFromId](#getfuncinfofromid)|지정된 디스패치 식별자의 함수 인덱스를 찾습니다.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|단일 멤버와 선택적 인수 이름 집합을 해당 정수 DISPID 집합에 매핑합니다.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|개체에 대한 형식 정보를 검색합니다.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|형식 정보 인터페이스 수를 검색합니다.|
|[IDispEventImpl::GetUser정의 유형](#getuserdefinedtype)|사용자 정의 형식의 기본 형식을 검색합니다.|

## <a name="remarks"></a>설명

`IDispEventImpl`는 해당 인터페이스의 모든 메서드/이벤트에 대한 구현 코드를 제공할 필요 없이 이벤트 dispinterface를 구현하는 방법을 제공합니다. `IDispEventImpl``IDispatch` 메서드의 구현을 제공합니다. 처리하려는 이벤트에 대한 구현만 제공하면 됩니다.

`IDispEventImpl`클래스의 이벤트 싱크 맵과 함께 작동하여 이벤트를 적절한 처리기 함수로 라우팅합니다. 이 클래스를 사용하려면 다음을 수행하십시오.

처리하려는 각 개체의 각 이벤트에 대한 이벤트 싱크 맵에 [SINK_ENTRY](composite-control-macros.md#sink_entry) 또는 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) 매크로를 추가합니다. 복합 `IDispEventImpl` 컨트롤의 기본 클래스로 사용하는 경우 [AtlAdviseSinkMap을](connection-point-global-functions.md#atladvisesinkmap) 호출하여 이벤트 싱크 맵의 모든 항목에 대한 이벤트 소스와의 연결을 설정하고 끊을 수 있습니다. 다른 경우 또는 더 큰 제어를 위해 [DispEventAdvise를](idispeventsimpleimpl-class.md#dispeventadvise) 호출하여 원본 개체와 기본 클래스 간의 연결을 설정합니다. [DispEventUnadvise에](idispeventsimpleimpl-class.md#dispeventunadvise) 전화하여 연결을 끊습니다.

이벤트를 처리해야 `IDispEventImpl` 하는 각 개체에 대해 *(nID에*대한 고유 값을 사용하여) 파생해야 합니다. 한 소스 개체에 대해 조언을 하지 않고 다른 소스 개체에 대해 조언하여 기본 클래스를 재사용할 수 있지만 한 번에 단일 개체에서 `IDispEventImpl` 처리할 수 있는 최대 소스 개체 수는 기본 클래스 수에 따라 제한됩니다.

`IDispEventImpl`_ATL_FUNC_INFO [구조에](../../atl/reference/atl-func-info-structure.md) 대한 포인터로 제공되는 대신 형식 라이브러리에서 인터페이스에 대한 형식 정보를 얻는 것을 제외하고는 [IDispEventSimpleImpl과](../../atl/reference/idispeventsimpleimpl-class.md)동일한 기능을 제공합니다. 이벤트 `IDispEventSimpleImpl` 인터페이스를 설명하는 형식 라이브러리가 없거나 형식 라이브러리 사용과 관련된 오버헤드를 방지하려는 경우에 사용합니다.

> [!NOTE]
> `IDispEventImpl`또한 `IDispEventSimpleImpl` 각 `IUnknown::QueryInterface` `IDispEventImpl` 클래스와 `IDispEventSimpleImpl` 기본 클래스가 별도의 COM ID 역할을 할 수 있도록 하는 동시에 주 COM 개체의 클래스 멤버에 직접 액세스할 수 있도록 하는 고유한 구현을 제공합니다.

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

자세한 내용은 [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="idispeventimplgetfuncinfofromid"></a><a name="getfuncinfofromid"></a>IDispEvent Impl::GetFuncInfoFromId

지정된 디스패치 식별자의 함수 인덱스를 찾습니다.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 함수의 ID에 대한 참조입니다.

*디스피드회원*<br/>
【인】 함수의 디스패치 ID입니다.

*lcid*<br/>
【인】 함수 ID의 로캘 컨텍스트입니다.

*info*<br/>
【인】 함수가 호출되는 방법을 나타내는 구조입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="idispeventimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames

[IDispatch::Invoke에](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)대한 후속 호출에서 사용할 수 있는 해당 정수 DISPID 집합에 단일 멤버 및 선택적 인수 이름 집합을 매핑합니다.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>설명

[IDispatch::GetIDsName](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK에서 참조 합니다.

## <a name="idispeventimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo

인터페이스의 형식 정보를 가져오는 데 사용할 수 있는 개체의 형식 정보를 검색합니다.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>설명

## <a name="idispeventimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount

개체에서 제공하는 형식 정보 인터페이스의 수를 검색합니다(0 또는 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>설명

[IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK를 참조하십시오.

## <a name="idispeventimplgetuserdefinedtype"></a><a name="getuserdefinedtype"></a>IDispEventImpl::GetUser정의 유형

사용자 정의 형식의 기본 형식을 검색합니다.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>매개 변수

*Pti*<br/>
【인】 사용자 정의 형식을 포함하는 [ITypeInfo](/windows/win32/api/oaidl/nn-oaidl-itypeinfo) 인터페이스에 대한 포인터입니다.

*Hrt*<br/>
【인】 검색할 형식 설명에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

변형의 유형입니다.

### <a name="remarks"></a>설명

[ITypeInfo::GetRefTypeInfo](/windows/win32/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo)를 참조하십시오.

## <a name="idispeventimplidispeventimpl"></a><a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl

생성자입니다. 클래스 템플릿 매개 변수 *plibid,* *pdiid,* *wMajor*및 *wMinor의*값을 저장합니다.

```
IDispEventImpl();
```

## <a name="idispeventimpltihclass"></a><a name="tihclass"></a>IDispEventImpl::tihclass

이 typedef는 클래스 템플릿 매개 변수 *tihclass의*인스턴스입니다.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>설명

기본적으로 클래스는 `CComTypeInfoHolder`. `CComTypeInfoHolder`클래스의 형식 정보를 관리합니다.

## <a name="see-also"></a>참고 항목

[_ATL_FUNC_INFO 구조체](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl 클래스](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
