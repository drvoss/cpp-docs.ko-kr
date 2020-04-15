---
title: IAxWinHostWindow 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: ebecc611660a788ce59bb11beb95bd60eacaf01b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329991"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow 인터페이스

이 인터페이스는 컨트롤 및 해당 호스트 개체를 조작하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[첨부 제어](#attachcontrol)|호스트 개체에 기존 컨트롤을 연결합니다.|
|[CreateControl](#createcontrol)|컨트롤을 만들고 호스트 개체에 연결합니다.|
|[만들기제어Ex](#createcontrolex)|컨트롤을 만들고 호스트 개체에 연결하고 선택적으로 이벤트 처리기를 설정합니다.|
|[쿼리 제어](#querycontrol)|인터페이스 포인터를 호스트된 컨트롤에 반환합니다.|
|[집합 외부 디스패치](#setexternaldispatch)|외부 `IDispatch` 인터페이스를 설정합니다.|
|[세트외부 UIHandler](#setexternaluihandler)|외부 `IDocHostUIHandlerDispatch` 인터페이스를 설정합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 ATL의 ActiveX 컨트롤 호스팅 개체에 의해 노출됩니다. 이 인터페이스의 메서드를 호출하여 호스트 개체에 컨트롤을 만들거나 연결하거나, 호스트된 컨트롤에서 인터페이스를 얻거나, 웹 브라우저를 호스팅할 때 사용할 외부 dispinterface 또는 UI 처리기를 설정합니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의는 아래와 같이 IDL 또는 C++로 사용할 수 있습니다.

|정의 유형|파일|
|---------------------|----------|
|Idl|아틀리페이스.아이들|
|C++|ATLIFace.h (ATLBase.h에도 포함)|

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>IAxWinHostWindow::연결 제어

*hWnd로*식별된 창을 사용하여 기존(이전에 초기화) 컨트롤을 호스트 개체에 연결합니다.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*펀크 컨트롤*<br/>
【인】 호스트 개체에 `IUnknown` 연결할 컨트롤의 인터페이스에 대한 포인터입니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>IAxWinHostWindow::만들기 제어

컨트롤을 만들고 초기화하며 *hWnd로*식별된 창에서 컨트롤을 호스트합니다.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
【인】 만들 컨트롤을 식별하는 문자열입니다. CLSID(중괄호포함), ProgID, URL 또는 원시 **HTML(MSHTML:** 접두사)일 수 있습니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

*pStream*<br/>
【인】 컨트롤에 대한 초기화 데이터가 포함된 스트림에 대한 인터페이스 포인터입니다. NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 창은 이 인터페이스를 노출하는 호스트 개체에 의해 하위 분류되므로 메시지가 컨트롤에 반영되고 다른 컨테이너 기능이 작동합니다.

이 메서드를 호출하는 것은 [IAxWinHostWindow::CreateControlEx](#createcontrolex)를 호출하는 것과 같습니다.

라이센스가 부여된 ActiveX 컨트롤을 만들려면 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)을 참조하십시오.

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>IAxWinHostWindow::만들기 제어 Ex

ActiveX 컨트롤을 만들고 초기화하며 [IAxWinHostWindow::CreateControl](#createcontrol)과 유사한 지정된 창에서 호스트합니다.

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
【인】 만들 컨트롤을 식별하는 문자열입니다. CLSID(중괄호포함), ProgID, URL 또는 원시 **HTML(MSHTML 접두사:**)일 수 있습니다.

*Hwnd*<br/>
【인】 호스팅에 사용할 창에 대한 핸들입니다.

*pStream*<br/>
【인】 컨트롤에 대한 초기화 데이터가 포함된 스트림에 대한 인터페이스 포인터입니다. NULL일 수 있습니다.

*ppunk*<br/>
【아웃】 생성된 컨트롤의 `IUnknown` 인터페이스를 수신하는 포인터의 주소입니다. NULL일 수 있습니다.

*리드어드*<br/>
【인】 포함된 개체에 나가는 인터페이스의 인터페이스 식별자입니다. IID_NULL 수 있습니다.

*펑크어드바이드*<br/>
【인】 에 의해 `IUnknown` 지정된 포함된 개체의 연결 점에 연결할 싱크 개체의 `iidSink`인터페이스에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

메서드와 `CreateControl` 달리 `CreateControlEx` 새로 만든 컨트롤에 대한 인터페이스 포인터를 수신하고 컨트롤에서 발생된 이벤트를 수신하도록 이벤트 싱크를 설정할 수도 있습니다.

라이센스가 부여된 ActiveX 컨트롤을 만들려면 [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)를 참조하십시오.

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>IAxWinHostWindow::쿼리 제어

호스트된 컨트롤에서 제공하는 지정된 인터페이스 포인터를 반환합니다.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
【인】 요청되는 컨트롤의 인터페이스 ID입니다.

*ppvObject*<br/>
【아웃】 생성된 컨트롤의 지정된 인터페이스를 수신하는 포인터의 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>IAxWinHostWindow::Set외부 디스패치

[IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 메서드를 통해 포함 된 컨트롤에 사용할 수 있는 외부 dispinterface를 설정 합니다.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
【인】 인터페이스에 대한 `IDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>IAxWinHostWindow::SetexternalUIHandler

이 함수를 호출하여 개체에 대한 외부 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 인터페이스를 설정합니다. `CAxWindow`

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
【인】 인터페이스에 대한 `IDocHostUIHandlerDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 인터페이스에 대한 호스트의 사이트를 쿼리하는 컨트롤(예: `IDocHostUIHandlerDispatch` 웹 브라우저 컨트롤)에서 사용됩니다.

## <a name="see-also"></a>참고 항목

[IAxWinAmbientDispatch 인터페이스](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::쿼리 호스트](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
