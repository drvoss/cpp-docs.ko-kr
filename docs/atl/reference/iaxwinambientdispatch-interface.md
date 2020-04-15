---
title: IAxWinAmbientDispatch 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: 6a4f5322d957b1e978bd123db3b4796be6b300da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330003"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch 인터페이스

이 인터페이스는 호스트된 컨트롤 또는 컨테이너의 특성을 지정하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.|
|[get_AllowShowUI](#get_allowshowui)|속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.|
|[get_BackColor](#get_backcolor)|속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.|
|[get_DocHostFlags](#get_dochostflags)|속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.|
|[get_Font](#get_font)|속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.|
|[get_ForeColor](#get_forecolor)|속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.|
|[get_LocaleID](#get_localeid)|속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.|
|[get_MessageReflect](#get_messagereflect)|앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.|
|[get_OptionKeyPath](#get_optionkeypath)|속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles` 주변 속성을 사용하면 컨트롤이 그랩 핸들로 자신을 그려야 하는지 확인할 수 있습니다.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching` 앰비언트 속성을 사용하면 컨트롤이 해치된 자체를 그려야 하는지 확인할 수 있습니다.|
|[get_UserMode](#get_usermode)|속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.|
|[put_AllowContextMenu](#put_allowcontextmenu)|속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.|
|[put_AllowShowUI](#put_allowshowui)|속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.|
|[put_BackColor](#put_backcolor)|속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.|
|[put_DocHostFlags](#put_dochostflags)|속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.|
|[put_Font](#put_font)|속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.|
|[put_ForeColor](#put_forecolor)|속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.|
|[put_LocaleID](#put_localeid)|속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.|
|[put_MessageReflect](#put_messagereflect)|앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.|
|[put_OptionKeyPath](#put_optionkeypath)|속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.|
|[put_UserMode](#put_usermode)|속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 ATL의 ActiveX 컨트롤 호스팅 개체에 의해 노출됩니다. 이 인터페이스의 메서드를 호출하여 호스트된 컨트롤에서 사용할 수 있는 앰비언트 속성을 설정하거나 컨테이너 동작의 다른 측면을 지정합니다. 에서 `IAxWinAmbientDispatch`제공하는 속성을 보완하려면 [IAxWinAmbientDispatchEx를](../../atl/reference/iaxwinambientdispatchex-interface.md)사용합니다.

<xref:System.Windows.Forms.AxHost>코드포함 `IAxWinAmbientDispatchEx` typelib에서 `IAxWinAmbientDispatch` 형식 정보를 로드하려고 합니다.

ATL90.dll에 연결하는 경우 **AXHost는** DLL의 typelib에서 형식 정보를 로드합니다.

자세한 내용은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의는 아래 표와 같이 여러 형태로 제공됩니다.

|정의 유형|파일|
|---------------------|----------|
|Idl|아틀리페이스.idl|
|형식 라이브러리|ATL.dll|
|C++|atliface.h (ATLBase.h에도 포함)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a>IAxWin 앰비언트 디스패치::get_AllowContextMenu

속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*pbAllow컨텍스트메뉴*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a>IAxWin 앰비언트 디스패치::get_AllowShowUI

속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*pbAllowShowui*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a>IAxWin 앰비언트 디스패치::get_AllowWindowlessActivation

이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*pbAllow창없는*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a>IAxWin 앰비언트 디스패치::get_BackColor

속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>매개 변수

*pclr배경*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 COLOR_BTNFACE 또는 COLOR_WINDOW 이 속성의 기본값으로 사용합니다(호스트 창의 부모가 대화 상자인지 여부에 따라 다름).

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a>IAxWin 앰비언트 디스패치::get_DisplayAsDefault

`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*pbDisplayAsDefault*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a>IAxWin 앰비언트 디스패치::get_DocHostDoubleClickFlags

속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHost더블클릭플래그*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIDBLCLK_DEFAULT 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a>IAxWin 앰비언트 디스패치::get_DocHostFlags

속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostFlags*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIFLAG_NO3DBORDER 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a>IAxWin 앰비언트 디스패치::get_Font

속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【아웃】 이 속성의 `IFontDisp` 현재 값을 수신하는 데 사용되는 인터페이스 포인터의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 기본 GUI 글꼴 또는 시스템 글꼴을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a>IAxWin 앰비언트 디스패치::get_ForeColor

속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>매개 변수

*pclr 전경*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 시스템 창 텍스트 색상을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a>IAxWin 앰비언트 디스패치::get_LocaleID

속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*plcidLocaleID*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 사용자의 기본 로캘을 이 속성의 기본값으로 사용합니다.

이 메서드를 사용 하 여 앰비언트 LocalID, 즉 컨트롤이 사용 되는 프로그램의 LocaleID를 검색할 수 있습니다. LocaleID를 알게 되면 코드를 호출하여 리소스 파일 또는 위성 DLL에서 로캘별 캡션, 오류 메시지 텍스트 등을 로드할 수 있습니다.

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a>IAxWin 앰비언트 디스패치::get_MessageReflect

앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>매개 변수

*pbMessage반사*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a>IAxWin 앰비언트 디스패치::get_OptionKeyPath

속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*pbstr옵션키패스*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a>IAxWin 앰비언트 디스패치::get_ShowGrabHandles

`ShowGrabHandles` 주변 속성을 사용하면 컨트롤이 그랩 핸들로 자신을 그려야 하는지 확인할 수 있습니다.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*pbShowGrab핸들즈*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 항상 VARIANT_FALSE 이 속성의 값으로 반환합니다.

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a>IAxWin 앰비언트 디스패치::get_ShowHatching

`ShowHatching` 앰비언트 속성을 사용하면 컨트롤이 해치된 자체를 그려야 하는지 확인할 수 있습니다.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>매개 변수

*pbShowHatching*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 항상 VARIANT_FALSE 이 속성의 값으로 반환합니다.

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a>IAxWin 앰비언트 디스패치::get_UserMode

속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>매개 변수

*pbUserMode*<br/>
【아웃】 이 속성의 현재 값을 수신하는 변수의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a>IAxWin 앰비언트 디스패치::put_allowContextMenu

속성은 `AllowContextMenu` 호스트된 컨트롤이 자체 컨텍스트 메뉴를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*b허용컨텍스트메뉴*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a>IAxWin앰비언트 디스패치::put_AllowShowUI

속성은 `AllowShowUI` 호스팅된 컨트롤이 자체 사용자 인터페이스를 표시할 수 있는지 여부를 지정합니다.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*bAllowShowui*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a>IAxWin 앰비언트 디스패치::putut_AllowWindow없는 활성화

이 `AllowWindowlessActivation` 속성은 컨테이너가 창 없는 활성화를 허용할지 여부를 지정합니다.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*bAllow창없는*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a>IAxWin앰비언트 디스패치::put_BackColor

속성은 `BackColor` 컨테이너의 주변 배경색을 지정합니다.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>매개 변수

*clrBackground*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 COLOR_BTNFACE 또는 COLOR_WINDOW 이 속성의 기본값으로 사용합니다(호스트 창의 부모가 대화 상자인지 여부에 따라 다름).

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a>IAxWin 앰비언트 디스패치::putut_DisplayAsDefault

`DisplayAsDefault`는 컨트롤이 기본 컨트롤인지 확인할 수 있는 앰비언트 속성입니다.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_FALSE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a>IAxWin앰비언트 디스패치::put_DocHost더블클릭플래그

속성은 `DocHostDoubleClickFlags` 두 번 클릭에 대 한 응답으로 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHost더블클릭플래그*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIDBLCLK_DEFAULT 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a>IAxWin앰비언트 디스패치::put_DocHostFlags

속성은 `DocHostFlags` 호스트 개체의 사용자 인터페이스 기능을 지정합니다.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostFlags*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 DOCHOSTUIFLAG_NO3DBORDER 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a>IAxWin 앰비언트 디스패치::put_글꼴

속성은 `Font` 컨테이너의 주변 글꼴을 지정합니다.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 기본 GUI 글꼴 또는 시스템 글꼴을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a>IAxWin앰비언트 디스패치::put_ForeColor

속성은 `ForeColor` 컨테이너의 주변 전경 색상을 지정합니다.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>매개 변수

*클러 포그라운드*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 시스템 창 텍스트 색상을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a>IAxWin앰비언트 디스패치::put_LocaleID

속성은 `LocaleID` 컨테이너의 주변 로캘 ID를 지정합니다.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*lcidLocaleID*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 사용자의 기본 로캘을 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a>IAxWin 앰비언트 디스패치::put_MessageReflect

앰비언트 속성은 `MessageReflect` 컨테이너가 호스트된 컨트롤에 메시지를 반영할지 여부를 지정합니다.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a>IAxWin 앰비언트 디스패치::put_OptionKeyPath

속성은 `OptionKeyPath` 사용자 설정에 대한 레지스트리 키 경로를 지정합니다.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*브스트옵션키패스*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a>IAxWin 앰비언트 디스패치::put_UserMode

속성은 `UserMode` 컨테이너의 주변 사용자 모드를 지정합니다.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
【인】 이 속성의 새 값입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현은 VARIANT_TRUE 이 속성의 기본값으로 사용합니다.

## <a name="see-also"></a>참고 항목

[IAxWinAmbientDispatchEx 인터페이스](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow 인터페이스](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::쿼리 호스트](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
