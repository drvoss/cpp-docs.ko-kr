---
title: IDispEventSimpleImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 779e143094760c7bd868ad33f590f7fd8f004762
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329732"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl 클래스

이 클래스는 형식 `IDispatch` 라이브러리에서 형식 정보를 얻지 않고 메서드의 구현을 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>매개 변수

*nID*<br/>
소스 개체에 대한 고유 식별자입니다. 복합 `IDispEventSimpleImpl` 컨트롤의 기본 클래스인 경우 이 매개 변수에 대해 원하는 포함된 컨트롤의 리소스 ID를 사용합니다. 다른 경우에는 임의의 양수 정수를 사용합니다.

*T*<br/>
에서 파생되는 사용자의 클래스입니다. `IDispEventSimpleImpl`

*피디드 (것)들*<br/>
이 클래스에서 구현한 이벤트 디스프인터페이스의 IID에 대한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[IDispEvent심플임임플::조언](#advise)|기본 이벤트 소스와의 연결을 설정합니다.|
|[IDispEvent심플::DispEventAdvise](#dispeventadvise)|이벤트 소스와의 연결을 설정합니다.|
|[IDispEventSimple Impl::DispEventUnadvise](#dispeventunadvise)|이벤트 소스와의 연결을 끊습니다.|
|[IDispEventSimple Impl::GetIDsOfNames](#getidsofnames)|E_NOTIMPL을 반환합니다.|
|[IDispEventSimple 임플::GetTypeInfo](#gettypeinfo)|E_NOTIMPL을 반환합니다.|
|[IDispEvent Simple Impl::GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL을 반환합니다.|
|[IDispEvent심플임임플::호출](#invoke)|이벤트 싱크 맵에 나열된 이벤트 처리기를 호출합니다.|
|[IDispEvent심플임임플::조언 불굴의](#unadvise)|기본 이벤트 소스와의 연결을 끊습니다.|

## <a name="remarks"></a>설명

`IDispEventSimpleImpl`는 해당 인터페이스의 모든 메서드/이벤트에 대한 구현 코드를 제공할 필요 없이 이벤트 dispinterface를 구현하는 방법을 제공합니다. `IDispEventSimpleImpl``IDispatch` 메서드의 구현을 제공합니다. 처리하려는 이벤트에 대한 구현만 제공하면 됩니다.

`IDispEventSimpleImpl`클래스의 이벤트 싱크 맵과 함께 작동하여 이벤트를 적절한 처리기 함수로 라우팅합니다. 이 클래스를 사용하려면 다음을 수행하십시오.

- 처리하려는 각 개체의 각 이벤트에 대한 이벤트 싱크 맵에 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) 매크로를 추가합니다.

- 각 항목에 매개 변수로 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 구조에 포인터를 전달 하 여 각 이벤트에 대 한 형식 정보를 제공 합니다. x86 `_ATL_FUNC_INFO.cc` 플랫폼에서는 __stdcall 콜백 함수 호출 메서드를 사용하여 값을 CC_CDECL 합니다.

- [호출 DispEventSource](#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다.

- [DispEventUnadvise에](#dispeventunadvise) 전화하여 연결을 끊습니다.

이벤트를 처리해야 `IDispEventSimpleImpl` 하는 각 개체에 대해 *(nID에*대한 고유 값을 사용하여) 파생해야 합니다. 한 소스 개체에 대해 조언을 하지 않고 다른 소스 개체에 대해 조언하여 기본 클래스를 재사용할 수 있지만 한 번에 단일 개체에서 `IDispEventSimpleImpl` 처리할 수 있는 최대 소스 개체 수는 기본 클래스 수에 따라 제한됩니다.

`IDispEventSimplImpl`형식 라이브러리에서 인터페이스에 대한 형식 정보를 얻지 못하는 경우를 제외하고 [IDispEventImpl과](../../atl/reference/idispeventimpl-class.md)동일한 기능을 제공합니다. 마법사는 을 기반으로 `IDispEventImpl`코드를 생성하지만 직접 `IDispEventSimpleImpl` 코드를 추가하여 사용할 수 있습니다. 이벤트 `IDispEventSimpleImpl` 인터페이스를 설명하는 형식 라이브러리가 없거나 형식 라이브러리 사용과 관련된 오버헤드를 방지하려는 경우에 사용합니다.

> [!NOTE]
> `IDispEventImpl`또한 `IDispEventSimpleImpl` 각 `IDispEventImpl` 또는 `IDispEventSimpleImpl` `IUnknown::QueryInterface` 기본 클래스가 별도의 COM ID 역할을 할 수 있도록 하는 동시에 주 COM 개체의 클래스 멤버에 직접 액세스할 수 있도록 하는 고유한 구현을 제공합니다.

ActiveX 이벤트 싱크의 CE ATL 구현은 HRESULT 형식의 반환 값만 지원하거나 이벤트 처리기 메서드에서 void만 지원합니다. 다른 반환 값은 지원되지 않으며 해당 동작은 정의되지 않습니다.

자세한 내용은 [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="idispeventsimpleimpladvise"></a><a name="advise"></a>IDispEvent심플임임플::조언

이 메서드를 호출하여 *pUnk로*표시되는 이벤트 소스와의 연결을 설정합니다.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 이벤트 소스 `IUnknown` 개체의 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

S_OK 또는 실패 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결이 설정되면 *pUnk에서* 발생한 이벤트는 이벤트 싱크 맵을 통해 클래스의 처리기로 라우팅됩니다.

> [!NOTE]
> 클래스가 여러 `IDispEventSimpleImpl` 클래스에서 파생되는 경우 관심 있는 특정 기본 클래스로 호출범위를 지정하여 이 메서드에 대한 호출을 모호하게 처리해야 합니다.

`Advise`기본 이벤트 소스와의 연결을 설정하면 [AtlGetObjectSourceInterface에](composite-control-global-functions.md#atlgetobjectsourceinterface)의해 결정된 대로 개체의 기본 이벤트 소스의 IID를 가져옵니다.

## <a name="idispeventsimpleimpldispeventadvise"></a><a name="dispeventadvise"></a>IDispEvent심플::DispEventAdvise

이 메서드를 호출하여 *pUnk로*표시되는 이벤트 소스와의 연결을 설정합니다.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 이벤트 소스 `IUnknown` 개체의 인터페이스에 대한 포인터입니다.

*piid*<br/>
이벤트 소스 개체의 IID에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

S_OK 또는 실패 HRESULT 값입니다.

### <a name="remarks"></a>설명

그런 다음 *pUnk에서* 발생한 이벤트는 이벤트 싱크 맵을 통해 클래스의 처리기로 라우팅됩니다.

> [!NOTE]
> 클래스가 여러 `IDispEventSimpleImpl` 클래스에서 파생되는 경우 관심 있는 특정 기본 클래스로 호출범위를 지정하여 이 메서드에 대한 호출을 모호하게 처리해야 합니다.

`DispEventAdvise`에 지정된 이벤트 소스와의 연결을 `pdiid`설정합니다.

## <a name="idispeventsimpleimpldispeventunadvise"></a><a name="dispeventunadvise"></a>IDispEventSimple Impl::DispEventUnadvise

*pUnk로*표시되는 이벤트 소스와의 연결이 끊어집니다.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 이벤트 소스 `IUnknown` 개체의 인터페이스에 대한 포인터입니다.

*piid*<br/>
이벤트 소스 개체의 IID에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

S_OK 또는 실패 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결이 끊어지면 이벤트는 더 이상 이벤트 싱크 맵에 나열된 처리기 함수로 라우팅되지 않습니다.

> [!NOTE]
> 클래스가 여러 `IDispEventSimpleImpl` 클래스에서 파생되는 경우 관심 있는 특정 기본 클래스로 호출범위를 지정하여 이 메서드에 대한 호출을 모호하게 처리해야 합니다.

`DispEventAdvise``pdiid`에서 지정된 이벤트 원본으로 설정된 연결이 끊어집니다.

## <a name="idispeventsimpleimplgetidsofnames"></a><a name="getidsofnames"></a>IDispEventSimple Impl::GetIDsOfNames

`IDispatch::GetIDsOfNames` 이 반환 구현은 E_NOTIMPL.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>설명

[IDispatch::GetIDsName](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK에서 참조 합니다.

## <a name="idispeventsimpleimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispEventSimple 임플::GetTypeInfo

`IDispatch::GetTypeInfo` 이 반환 구현은 E_NOTIMPL.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>설명

[IDispatch::GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) Windows SDK를 참조하십시오.

## <a name="idispeventsimpleimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispEvent Simple Impl::GetTypeInfoCount

`IDispatch::GetTypeInfoCount` 이 반환 구현은 E_NOTIMPL.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>설명

[IDispatch::GetTypeInfoCount](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK를 참조하십시오.

## <a name="idispeventsimpleimplinvoke"></a><a name="invoke"></a>IDispEvent심플임임플::호출

이 구현에서는 `IDispatch::Invoke` 이벤트 싱크 맵에 나열된 이벤트 처리기를 호출합니다.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>설명

[IDispatch::호출을](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)참조하십시오.

## <a name="idispeventsimpleimplunadvise"></a><a name="unadvise"></a>IDispEvent심플임임플::조언 불굴의

*pUnk로*표시되는 이벤트 소스와의 연결이 끊어집니다.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
【인】 이벤트 소스 `IUnknown` 개체의 인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

S_OK 또는 실패 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결이 끊어지면 이벤트는 더 이상 이벤트 싱크 맵에 나열된 처리기 함수로 라우팅되지 않습니다.

> [!NOTE]
> 클래스가 여러 `IDispEventSimpleImpl` 클래스에서 파생되는 경우 관심 있는 특정 기본 클래스로 호출범위를 지정하여 이 메서드에 대한 호출을 모호하게 처리해야 합니다.

`Unadvise`에서 지정된 기본 이벤트 원본으로 설정된 `pdiid`연결을 끊습니다.

`Unavise`기본 이벤트 소스와의 연결을 끊으면 [AtlGetObjectSourceInterface에](composite-control-global-functions.md#atlgetobjectsourceinterface)의해 결정된 대로 개체의 기본 이벤트 소스의 IID를 가져옵니다.

## <a name="see-also"></a>참고 항목

[_ATL_FUNC_INFO 구조체](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl 클래스](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
