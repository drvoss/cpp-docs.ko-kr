---
title: CAxWindow 클래스
ms.date: 11/04/2016
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
ms.openlocfilehash: 6f5629370bc1f821dac0a08cc76b5df1450f7a5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318729"
---
# <a name="caxwindow-class"></a>CAxWindow 클래스

이 클래스는 ActiveX 컨트롤을 호스팅하는 창을 조작하는 메서드를 제공합니다.

> [!IMPORTANT]
> 이 클래스와 해당 멤버는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAxWindow : public CWindow
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[첨부 제어](#attachcontrol)|기존 ActiveX 컨트롤을 개체에 연결합니다. `CAxWindow`|
|[CAxWindow](#caxwindow)|`CAxWindow` 개체를 생성합니다.|
|[CreateControl](#createcontrol)|ActiveX 컨트롤을 만들고 초기화한 다음 창에서 `CAxWindow` 호스트합니다.|
|[만들기제어Ex](#createcontrolex)|ActiveX 컨트롤을 만들고 컨트롤에서 인터페이스 포인터(또는 포인터)를 검색합니다.|
|[GetWnd클래스 이름](#getwndclassname)|(정적) 개체의 미리 정의된 클래스 `CAxWindow` 이름을 검색합니다.|
|[쿼리 제어](#querycontrol)|호스팅된 `IUnknown` ActiveX 컨트롤의 를 검색합니다.|
|[쿼리 호스트](#queryhost)|개체의 `IUnknown` 포인터를 `CAxWindow` 검색합니다.|
|[집합 외부 디스패치](#setexternaldispatch)|개체에서 사용하는 외부 디스패치 인터페이스를 `CAxWindow` 설정합니다.|
|[세트외부 UIHandler](#setexternaluihandler)|개체에서 `IDocHostUIHandler` 사용하는 외부 `CAxWindow` 인터페이스를 설정합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator_eq)|기존 `CAxWindow` 개체에 HWND를 할당합니다.|

## <a name="remarks"></a>설명

이 클래스는 ActiveX 컨트롤을 호스트하는 창을 조작하는 메서드를 제공합니다. 호스팅은 **"AtlAxWin80"에**의해 제공되며, `CAxWindow`에 의해 포장됩니다.

클래스는 `CAxWindow` `CAxWindowT` 클래스의 전문화로 구현됩니다. 이 전문화는 다음과 같이 선언됩니다.

`typedef CAxWindowT<CWindow> CAxWindow;`

기본 클래스를 변경해야 하는 경우 `CAxWindowT` 새 기본 클래스를 템플릿 인수로 사용하고 지정할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

## <a name="caxwindowattachcontrol"></a><a name="attachcontrol"></a>CAxWindow::연결 제어

아직 존재하지 않고 지정된 컨트롤을 호스트에 연결하는 경우 새 호스트 개체를 만듭니다.

```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
【인】 컨트롤의 `IUnknown` 포인터입니다.

*ppUnk컨테이너*<br/>
【아웃】 `IUnknown` 호스트(개체)에 대한 포인터입니다. `AxWin`

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결되는 컨트롤 개체를 호출하기 `AttachControl`전에 올바르게 초기화해야 합니다.

## <a name="caxwindowcaxwindow"></a><a name="caxwindow"></a>CAxWindow::CAxWindow

기존 창 `CAxWindow` 개체 핸들을 사용하여 개체를 생성합니다.

```
CAxWindow(HWND hWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
기존 창 개체에 대한 핸들입니다.

## <a name="caxwindowcreatecontrol"></a><a name="createcontrol"></a>CAxWindow::만들기 제어

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤을 만드는 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다. ProgID 및 CLSID만 Windows 모바일 플랫폼에서 지원됩니다. WINDOWS CE 임베디드 플랫폼, WINDOWS Ie에 대 한 지원 과 Windows 모바일 이외의 ProgID, CLSID, URL, 활성 문서에 대 한 참조 및 HTML의 조각을 포함 하 여 모든 형식을 지원 합니다.

*pStream*<br/>
【인】 컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
【아웃】 컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*dwResID*<br/>
HTML 리소스의 리소스 ID입니다. WebBrowser 컨트롤이 만들어지고 지정된 리소스와 함께 로드됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 메서드의 두 번째 버전을 사용 하는 경우 HTML 컨트롤이 만들어지고 *dwResID로*식별 된 리소스에 바인딩됩니다.

이 메서드는 호출과 동일한 결과를 제공합니다.

[!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]

[CAxWindow2T:CreateControlLic을](../../atl/reference/caxwindow2t-class.md#createcontrollic) 참조하여 라이선스가 부여된 ActiveX 컨트롤을 생성, 초기화 및 호스팅합니다.

### <a name="example"></a>예제

을 사용하는 `CreateControl`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="caxwindowcreatecontrolex"></a><a name="createcontrolex"></a>CAxWindow::만들기 제어 Ex

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤을 만드는 문자열에 대한 포인터입니다. 다음 방법 중 하나로 서식을 지정해야 합니다.

- 같은 ProgID`"MSCAL.Calendar.7"`

- CLSID 와 같은`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- 다음과 같은 URL`"<https://www.microsoft.com>"`

- 활성 문서에 대한 참조와 같은`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML 의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`MSHTML 스트림으로 지정되도록 HTML 조각 앞에 와야 합니다. ProgID 및 CLSID만 Windows 모바일 플랫폼에서 지원됩니다. WINDOWS CE 임베디드 플랫폼, WINDOWS Ie에 대 한 지원 과 Windows 모바일 이외의 ProgID, CLSID, URL, 활성 문서에 대 한 참조 및 HTML의 조각을 포함 하 여 모든 형식을 지원 합니다.

*pStream*<br/>
【인】 컨트롤의 속성을 초기화하는 데 사용되는 스트림에 대한 포인터입니다. NULL일 수 있습니다.

*ppUnk컨테이너*<br/>
【아웃】 컨테이너를 수신할 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*ppUnk제어*<br/>
【아웃】 컨트롤을 받을 `IUnknown` 포인터의 주소입니다. NULL일 수 있습니다.

*아이드싱크*<br/>
【인】 포함된 개체에 나가는 인터페이스의 인터페이스 식별자입니다. IID_NULL 수 있습니다.

*펑크 싱크*<br/>
【인】 `IUnknown` *iidSink에서*지정한 포함된 개체의 연결 지점에 연결할 싱크 개체의 인터페이스에 대한 포인터입니다.

*dwResID*<br/>
【인】 HTML 리소스의 리소스 ID입니다. WebBrowser 컨트롤이 만들어지고 지정된 리소스와 함께 로드됩니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 메서드는 [CAxWindow:CreateControl과](#createcontrol)유사하지만 이 `CreateControlEx` 메서드와 달리 새로 만든 컨트롤에 대한 인터페이스 포인터를 수신하고 컨트롤에서 발생되는 이벤트를 수신하도록 이벤트 싱크를 설정할 수도 있습니다.

[CAxWindow2T:CreateControlLicEx를](../../atl/reference/caxwindow2t-class.md#createcontrollicex) 참조하여 라이선스가 부여된 ActiveX 컨트롤을 생성, 초기화 및 호스팅합니다.

### <a name="example"></a>예제

을 사용하는 `CreateControlEx`샘플은 [ATL AXHost를 사용하여 ActiveX 컨트롤 호스팅을](../../atl/hosting-activex-controls-using-atl-axhost.md) 참조하십시오.

## <a name="caxwindowgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow::GetWndClassName

창 클래스의 이름을 검색합니다.

```
static LPCTSTR GetWndClassName();
```

### <a name="return-value"></a>Return Value

라이선스가 없는 ActiveX 컨트롤을 호스트할 수 있는 창 클래스의 이름이 포함된 문자열에 대한 포인터입니다.

## <a name="caxwindowoperator-"></a><a name="operator_eq"></a>CAxWindow::연산자 =

기존 `CAxWindow` 개체에 HWND를 할당합니다.

```
CAxWindow<TBase>& operator=(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
기존 창에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

현재 개체에 대한 `CAxWindow` 참조를 반환합니다.

## <a name="caxwindowquerycontrol"></a><a name="querycontrol"></a>CAxWindow::쿼리 제어

호스트된 컨트롤의 지정된 인터페이스를 검색합니다.

```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 컨트롤 인터페이스의 IID를 지정합니다.

*ppunk*<br/>
【아웃】 컨트롤의 인터페이스에 대한 포인터입니다. 이 메서드의 템플릿 버전에서는 연결된 UUID가 있는 형식인터페이스가 전달되는 한 참조 ID가 필요하지 않습니다.

*Q*<br/>
【인】 쿼리되는 인터페이스입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="caxwindowqueryhost"></a><a name="queryhost"></a>CAxWindow::쿼리 호스트

호스트의 지정된 인터페이스를 반환합니다.

```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 컨트롤 인터페이스의 IID를 지정합니다.

*ppunk*<br/>
【아웃】 호스트의 인터페이스에 대한 포인터입니다. 이 메서드의 템플릿 버전에서는 연결된 UUID가 있는 형식인터페이스가 전달되는 한 참조 ID가 필요하지 않습니다.

*Q*<br/>
【인】 쿼리되는 인터페이스입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

호스트의 인터페이스를 사용하면 에 의해 `AxWin`구현된 창 호스팅 코드의 기본 기능에 액세스할 수 있습니다.

## <a name="caxwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>CAxWindow::설정 외부 디스패치

개체에 대한 외부 `CAxWindow` 디스패치 인터페이스를 설정합니다.

```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
【인】 인터페이스에 대한 `IDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="caxwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>CAxWindow::SetexternalUIHandler

개체에 대한 외부 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 인터페이스를 설정합니다. `CAxWindow`

```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```

### <a name="parameters"></a>매개 변수

*푸이 핸들러*<br/>
【인】 인터페이스에 대한 `IDocHostUIHandlerDispatch` 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

외부 `IDocHostUIHandlerDispatch` 인터페이스는 인터페이스에 대한 호스트의 사이트를 쿼리하는 컨트롤에서 사용됩니다. `IDocHostUIHandlerDispatch` WebBrowser 컨트롤은 이 작업을 수행하는 하나의 컨트롤입니다.

## <a name="see-also"></a>참고 항목

[아LCON 샘플](../../overview/visual-cpp-samples.md)<br/>
[C윈도우 클래스](../../atl/reference/cwindow-class.md)<br/>
[복합 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)
