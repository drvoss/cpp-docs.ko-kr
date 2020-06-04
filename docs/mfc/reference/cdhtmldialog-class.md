---
title: CDHtmlDialog 클래스
ms.date: 03/27/2019
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
ms.openlocfilehash: e2e4306320c52b8276d915848dfa6e460982c92b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753377"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog 클래스

사용자 인터페이스를 구현하기 위해 대화 상자 리소스가 아닌 HTML을 사용하는 대화 상자를 만드는 데 사용됩니다.

## <a name="syntax"></a>구문

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|CDHtmlDialog 개체를 생성합니다.|
|[CDHtmlDialog::~CDHtmlDialog](#_dtorcdhtmldialog)|CDHtmlDialog 개체를 삭제합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|액세스 검사로 호출되는 재정의 가능한 액세스 검사는 로드된 페이지의 스크립팅 개체가 제어 사이트의 외부 디스패치에 액세스할 수 있는지 확인합니다. 디스패치가 스크립팅에 안전한지 또는 현재 영역이 스크립팅에 안전하지 않은 개체를 허용하는지 확인합니다.|
|[CDHtmlDialog::만들기제어사이트](#createcontrolsite)|대화 상자에서 WebBrowser 컨트롤을 호스트하는 컨트롤 사이트 인스턴스를 만드는 데 사용할 수 있습니다.|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|HTML 페이지에서 멤버 변수와 ActiveX 컨트롤의 속성 값 간에 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_체크박스](#ddx_dhtml_checkbox)|HTML 페이지의 멤버 변수와 확인란 간에 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|HTML 페이지에서 멤버 변수와 모든 HTML 요소 속성 간에 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|HTML 페이지에서 멤버 변수와 라디오 단추 간에 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|HTML 페이지에서 목록 상자의 인덱스를 가져옵니다.|
|[CDHtmlDialog::DDX_DHtml_셀렉톨스트링](#ddx_dhtml_selectstring)|HTML 페이지에서 목록 상자 항목(현재 인덱스 기준)의 표시 텍스트를 가져옵니다.|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|HTML 페이지에서 목록 상자 항목(현재 인덱스 기준)의 값을 가져옵니다.|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|모덜리스 대화 상자를 삭제합니다.|
|[CDHtmlDialog::사용 모드 없는](#enablemodeless)|모덜리스 대화 상자를 활성화합니다.|
|[CDHtmlDialog::필터데이터오브젝트](#filterdataobject)|대화 상자가 호스팅된 브라우저에서 만든 클립보드 데이터 개체를 필터링할 수 있습니다.|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|HTML 문서에 `IDispatch` 포함된 ActiveX 컨트롤의 인터페이스를 검색합니다.|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|지정된 ActiveX 컨트롤의 요청된 속성을 검색합니다.|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|현재 문서와 연결된 URL(균일 리소스 로케이터)을 검색합니다.|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|현재 로드된 HTML 문서에서 IHTMLDocument2 인터페이스를 검색합니다.|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|대화 상자가 대체 [IDropTarget을](/windows/win32/api/oleidl/nn-oleidl-idroptarget)제공할 수 있도록 드롭 대상으로 사용되는 경우 포함된 WebBrowser 컨트롤에서 호출합니다.|
|[CDHtmlDialog::GetElement](#getelement)|HTML 요소에 대한 인터페이스를 가져옵니다.|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|HTML 요소의 `innerHTML` 속성을 검색합니다.|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|HTML 요소에서 요청된 인터페이스 포인터를 검색합니다.|
|[CDHtmlDialog::겟엘리먼트프로퍼티](#getelementproperty)|HTML 요소의 속성 값을 검색합니다.|
|[CDHtmlDialog::GetElementText](#getelementtext)|HTML 요소의 `innerText` 속성을 검색합니다.|
|[CDHtmlDialog::GetEvent](#getevent)|현재 `IHTMLEventObj` 이벤트 개체에 대한 포인터를 가져옵니다.|
|[CDHtmlDialog::GetExternal](#getexternal)|호스트의 `IDispatch` 인터페이스를 가져옵니다.|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|호스트의 UI 기능을 검색합니다.|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|사용자 기본 설정이 저장되는 레지스트리 키를 검색합니다.|
|[CDHtmlDialog::HideUI](#hideui)|호스트의 UI를 숨깁니다.|
|[CDHtmlDialog::외부 디스패치세이프](#isexternaldispatchsafe)|호스트의 `IDispatch` 인터페이스가 스크립팅에 안전한지 여부를 나타냅니다.|
|[CDHtmlDialog::로드From리소스](#loadfromresource)|지정된 리소스를 WebBrowser 컨트롤에 로드합니다.|
|[CDHtmlDialog::탐색](#navigate)|지정된 URL로 이동합니다.|
|[CDHtmlDialog::에 이전 탐색](#onbeforenavigate)|탐색 이벤트가 발생하기 전에 프레임워크에서 호출됩니다.|
|[CDHtmlDialog::문서 완료](#ondocumentcomplete)|문서가 READYSTATE_COMPLETE 상태에 도달하면 응용 프로그램에 알리기 위해 프레임워크에서 호출합니다.|
|[CDHtmlDialog::OnDocWindow활성화](#ondocwindowactivate)|문서 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.|
|[CDHtmlDialog:::온프레임 윈도우활성화](#onframewindowactivate)|프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.|
|[CDHtmlDialog::InInitDialog](#oninitdialog)|WM_INITDIALOG 메시지에 대한 응답으로 호출됩니다.|
|[CDHtmlDialog::탐색 완료](#onnavigatecomplete)|탐색 이벤트가 완료된 후 프레임워크에서 호출됩니다.|
|[CDHtmlDialog::크기 조정국경](#resizeborder)|테두리 공간의 크기를 조정해야 하는 개체에 경고합니다.|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|ActiveX 컨트롤의 속성을 새 값으로 설정합니다.|
|[CDHtmlDialog::세트엘리멘타Html](#setelementhtml)|HTML `innerHTML` 요소의 속성을 설정합니다.|
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|HTML 요소의 속성을 설정합니다.|
|[CDHtmlDialog::세트요소텍스트](#setelementtext)|HTML `innerText` 요소의 속성을 설정합니다.|
|[CDHtmlDialog::세트외부 디스패치](#setexternaldispatch)|호스트의 `IDispatch` 인터페이스를 설정합니다.|
|[CDHtmlDialog::세트호스트 플래그](#sethostflags)|호스트의 UI 플래그를 설정합니다.|
|[CDHtmlDialog::쇼컨텍스트메뉴](#showcontextmenu)|컨텍스트 메뉴가 표시될 때 호출됩니다.|
|[CDHtmlDialog::쇼이](#showui)|호스트의 UI를 표시합니다.|
|[CDHtmlDialog::번역가속기](#translateaccelerator)|메뉴 가속기 키 메시지를 처리하기 위해 호출됩니다.|
|[CDHtmlDialog::번역Url](#translateurl)|로드할 URL을 수정하기 위해 호출됩니다.|
|[CDHtmlDialog::업데이트 UI](#updateui)|명령 상태가 변경되었음을 호스트에게 알리기 위해 호출됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|HTML 문서의 제목을 대화 상자 캡션으로 사용할지 여부를 나타냅니다.|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|표시할 HTML 리소스의 리소스 ID입니다.|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|웹 브라우저 응용 프로그램에 대한 포인터입니다.|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|HTML 문서에 대한 포인터입니다.|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|현재 URL입니다.|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|HTML 리소스 ID의 문자열 버전입니다.|

## <a name="remarks"></a>설명

`CDHtmlDialog`HTML 리소스 또는 URL에서 표시할 HTML을 로드할 수 있습니다.

`CDHtmlDialog`또한 HTML 컨트롤과 데이터 교환을 수행하고 단추 클릭과 같은 HTML 컨트롤의 이벤트를 처리할 수도 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdhtml.h

## <a name="ddx_dhtml-helper-macros"></a><a name="ddx_dhtml_helper_macros"></a>DDX_DHtml 도우미 매크로

DDX_DHtml 도우미 매크로를 사용하면 HTML 페이지에서 일반적으로 사용되는 컨트롤 속성에 쉽게 액세스할 수 있습니다.

### <a name="data-exchange-macros"></a>데이터 교환 매크로

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|선택한 컨트롤에서 Value 속성을 설정하거나 검색합니다.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|현재 요소의 시작 및 끝 태그 사이의 텍스트를 설정하거나 검색합니다.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|현재 요소의 시작 및 끝 태그 간에 HTML을 설정하거나 검색합니다.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|대상 URL 또는 앵커 포인트를 설정하거나 검색합니다.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|대상 창 또는 프레임을 설정하거나 검색합니다.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|문서의 이미지 또는 비디오 클립의 이름을 설정하거나 검색합니다.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|연결된 프레임의 URL을 설정하거나 검색합니다.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|연결된 프레임의 URL을 설정하거나 검색합니다.|

## <a name="cdhtmldialogcanaccessexternal"></a><a name="canaccessexternal"></a>CDHtmlDialog::수 액세스 외부

액세스 검사로 호출되는 재정의 가능한 액세스 검사는 로드된 페이지의 스크립팅 개체가 제어 사이트의 외부 디스패치에 액세스할 수 있는지 확인합니다. 디스패치가 스크립팅에 안전한지 또는 현재 영역이 스크립팅에 안전하지 않은 개체를 허용하는지 확인합니다.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog

리소스 기반 동적 HTML 대화 상자를 생성합니다.

```
CDHtmlDialog();

CDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID,
    CWnd *pParentWnd = NULL);

CDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd *pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름인 null-종료된 문자열입니다.

*szHtmlResID*<br/>
HTML 리소스의 이름인 null-종료된 문자열입니다.

*pParentWnd*<br/>
대화 상자 개체가 속한 부모 또는 소유자 창 [개체(CWnd](../../mfc/reference/cwnd-class.md)형식)에 대한 포인터입니다. NULL인 경우 대화 상자 개체의 부모 창이 기본 응용 프로그램 창으로 설정됩니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

*nHtmlResID*<br/>
HTML 리소스의 ID 번호를 포함합니다.

### <a name="remarks"></a>설명

생성자의 두 번째 형식은 템플릿 이름을 통해 대화 상자 리소스에 대한 액세스를 제공합니다. 생성자의 세 번째 형식은 리소스 템플릿의 ID를 통해 대화 상자 리소스에 대한 액세스를 제공합니다. 일반적으로 ID는 **IDD_** 접두사로 시작합니다.

## <a name="cdhtmldialogcdhtmldialog"></a><a name="_dtorcdhtmldialog"></a>CDHtmlDialog::~CDHtmlDialog

CDHtmlDialog 개체를 삭제합니다.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>설명

[CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 멤버 함수는 [CDialog::Create에서](../../mfc/reference/cdialog-class.md#create)만든 모덜리스 대화 상자를 삭제하는 데 사용해야 합니다.

## <a name="cdhtmldialogcreatecontrolsite"></a><a name="createcontrolsite"></a>CDHtmlDialog::만들기제어사이트

대화 상자에서 WebBrowser 컨트롤을 호스트하는 컨트롤 사이트 인스턴스를 만드는 데 사용할 수 있습니다.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>매개 변수

*pContainer*<br/>
[COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) 개체에 대한 포인터

*ppSite*<br/>
[COleControlSite에](../../mfc/reference/colecontrolsite-class.md)대한 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 재정의하여 사용자 고유의 제어 사이트 클래스의 인스턴스를 반환할 수 있습니다.

## <a name="cdhtmldialogddx_dhtml_axcontrol"></a><a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl

HTML 페이지에서 멤버 변수와 ActiveX 컨트롤의 속성 값 간에 데이터를 교환합니다.

```cpp
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
ActiveX 컨트롤에 대 한 HTML 소스에서 개체 태그의 ID 매개 변수의 값입니다.

*디스피드*<br/>
데이터를 교환하려는 속성의 디스패치 ID입니다.

*szPropName*<br/>
속성의 이름입니다.

*var*<br/>
ActiveX 제어 속성과 교환된 값을 보유하는 VARIANT 형식, [COleVariant](../../mfc/reference/colevariant-class.md)또는 [CComVariant의](../../atl/reference/ccomvariant-class.md)데이터 멤버입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

## <a name="cdhtmldialogddx_dhtml_checkbox"></a><a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_체크박스

HTML 페이지의 멤버 변수와 확인란 간에 데이터를 교환합니다.

```cpp
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정한 값입니다.

*value*<br/>
교환되는 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

## <a name="cdhtmldialogddx_dhtml_elementtext"></a><a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_엘리먼트텍스트

HTML 페이지에서 멤버 변수와 모든 HTML 요소 속성 간에 데이터를 교환합니다.

```cpp
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정한 값입니다.

*디스피드*<br/>
데이터를 교환하려는 HTML 요소의 디스패치 ID입니다.

*value*<br/>
교환되는 값입니다.

## <a name="cdhtmldialogddx_dhtml_radio"></a><a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_라디오

HTML 페이지에서 멤버 변수와 라디오 단추 간에 데이터를 교환합니다.

```cpp
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정한 값입니다.

*value*<br/>
교환되는 값입니다.

## <a name="cdhtmldialogddx_dhtml_selectindex"></a><a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_셀렉지드

HTML 페이지에서 목록 상자의 인덱스를 가져옵니다.

```cpp
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 매개 변수에 대해 `id` 지정한 값입니다.

*value*<br/>
교환되는 값입니다.

## <a name="cdhtmldialogddx_dhtml_selectstring"></a><a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_셀렉톨스트링

HTML 페이지에서 목록 상자 항목(현재 인덱스 기준)의 표시 텍스트를 가져옵니다.

```cpp
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정한 값입니다.

*value*<br/>
교환되는 값입니다.

## <a name="cdhtmldialogddx_dhtml_selectvalue"></a><a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_선택값

HTML 페이지에서 목록 상자 항목(현재 인덱스 기준)의 값을 가져옵니다.

```cpp
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
[CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체에 대한 포인터입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정한 값입니다.

*value*<br/>
교환되는 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

## <a name="cdhtmldialogdestroymodeless"></a><a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless

`CDHtmlDialog` 모덜리스 대화 상자를 개체에서 분리하고 오브젝트를 파괴합니다.

```cpp
void DestroyModeless();
```

## <a name="cdhtmldialogenablemodeless"></a><a name="enablemodeless"></a>CDHtmlDialog::사용 모드 없는

모덜리스 대화 상자를 활성화합니다.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>매개 변수

*fEnable*<br/>
[iDocHostUIHandler:::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) SDK에서 사용 모드없는 에서 *fEnable를* 참조하십시오.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::EnableModeless의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogfilterdataobject"></a><a name="filterdataobject"></a>CDHtmlDialog::필터데이터오브젝트

대화 상자가 호스팅된 브라우저에서 만든 클립보드 데이터 개체를 필터링할 수 있습니다.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>매개 변수

*Pdo*<br/>
[IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) Windows SDK에서 *pDO를* 참조하십시오.

*ppDORet*<br/>
윈도우 SDK에서 `IDocHostUIHandler::FilterDataObject` *ppDORet를* 참조하십시오.

### <a name="return-value"></a>Return Value

S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::FilterDataObject의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))구현입니다.

## <a name="cdhtmldialoggetcontroldispatch"></a><a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch

[GetDHtmlDocument](#getdhtmldocument)에서 반환하는 HTML 문서에 포함된 ActiveX 컨트롤에서 인터페이스 `IDispatch`를 검색합니다.

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>매개 변수

*szId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*ppdisp*<br/>
웹 `IDispatch` 페이지에 있는 경우 컨트롤의 인터페이스입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

## <a name="cdhtmldialoggetcontrolproperty"></a><a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty

지정된 ActiveX 컨트롤의 요청된 속성을 검색합니다.

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>매개 변수

*szId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*szPropName*<br/>
현재 사용자의 기본 로캘에 있는 속성의 이름입니다.

*pdispControl*<br/>
ActiveX 컨트롤의 `IDispatch` 포인터입니다.

*디스피드*<br/>
속성의 디스패치 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤 또는 속성을 찾을 수 없는 경우 요청된 속성 또는 빈 변형을 포함하는 변형입니다.

### <a name="remarks"></a>설명

과부하가 가장 효율적이지 는 않습니다.

## <a name="cdhtmldialoggetcurrenturl"></a><a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl

현재 문서와 연결된 URL(균일 리소스 로케이터)을 검색합니다.

```cpp
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>매개 변수

*szUrl*<br/>
검색할 URL을 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

## <a name="cdhtmldialoggetdhtmldocument"></a><a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtml문서

현재 로드된 HTML 문서에서 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 인터페이스를 검색합니다.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>매개 변수

* \* \** HTML 문서에 대한 포인터에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT. 성공하면 S_OK 반환합니다.

## <a name="cdhtmldialoggetdroptarget"></a><a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget

대화 상자가 대체 [IDropTarget을](/windows/win32/api/oleidl/nn-oleidl-idroptarget)제공할 수 있도록 드롭 대상으로 사용되는 경우 포함된 WebBrowser 컨트롤에서 호출합니다.

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>매개 변수

*pDropTarget*<br/>
[IDocHostUIHandler에서 pDropTarget::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) Windows SDK에서 참조 합니다. *pDropTarget*

*ppDropTarget*<br/>
윈도우 SDK에서 `IDocHostUIHandler::GetDropTarget` *ppDropTarget을* 참조하십시오.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::GetDropTarget의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))구현입니다.

## <a name="cdhtmldialoggetelement"></a><a name="getelement"></a>CDHtmlDialog::GetElement

*szElementId*.

```
HRESULT GetElement(
    LPCTSTR szElementId,
    IDispatch** ppdisp,
    BOOL* pbCollection = NULL);

HRESULT GetElement(
    LPCTSTR szElementId,
    IHTMLElement** pphtmlElement);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*ppdisp*<br/>
요청된 요소 또는 요소 컬렉션에 대한 `IDispatch` 포인터입니다.

*pbCollection*<br/>
*PPDISp로* 표시되는 개체가 단일 요소인지 요소 컬렉션인지를 나타내는 BOOL입니다.

*pphtmlElement*<br/>
요청된 `IHTMLElement` 요소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

지정된 ID가 있는 요소가 두 개 이상있을 수 있는 조건을 처리해야 하는 경우 첫 번째 오버로드를 사용합니다. 마지막 매개 변수를 사용하여 반환된 인터페이스 포인터가 컬렉션인지 단일 항목에 있는지 확인할 수 있습니다. 인터페이스 포인터가 컬렉션에 있는 경우 을 `IHTMLElementCollection` 쿼리하고 `item` 해당 속성을 사용하여 서수 위치로 요소를 참조할 수 있습니다.

페이지에 ID가 동일한 요소가 두 개 이상 있는 경우 두 번째 오버로드가 실패합니다.

## <a name="cdhtmldialoggetelementhtml"></a><a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml

`innerHTML` *szElementId로*식별된 HTML 요소의 속성을 검색합니다.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

### <a name="return-value"></a>Return Value

요소를 `innerHTML` 찾을 수 없는 경우 *szElementId* 또는 NULL로 식별된 HTML 요소의 속성입니다.

## <a name="cdhtmldialoggetelementinterface"></a><a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface

*szElementId로*식별된 HTML 요소에서 요청된 인터페이스 포인터를 검색합니다.

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*ppvObj*<br/>
요소가 발견되고 쿼리가 성공하면 요청된 인터페이스 포인터로 채워지는 포인터의 주소입니다.

*refiid*<br/>
요청된 인터페이스의 인터페이스 ID(IID)입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

## <a name="cdhtmldialoggetelementproperty"></a><a name="getelementproperty"></a>CDHtmlDialog::겟엘리먼트프로퍼티

*szElementId로*식별된 HTML 요소에서 *dispId로* 식별된 속성값을 검색합니다.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*디스피드*<br/>
속성의 디스패치 ID입니다.

### <a name="return-value"></a>Return Value

속성 또는 요소를 찾을 수 없는 경우 속성 값 또는 빈 변형입니다.

## <a name="cdhtmldialoggetelementtext"></a><a name="getelementtext"></a>CDHtmlDialog::GetElementText

`innerText` *szElementId로*식별된 HTML 요소의 속성을 검색합니다.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

### <a name="return-value"></a>Return Value

속성 `innerText` 또는 요소를 찾을 수 없는 경우 *szElementId* 또는 NULL로 식별된 HTML 요소의 속성입니다.

## <a name="cdhtmldialoggetevent"></a><a name="getevent"></a>CDHtmlDialog::GetEvent

포인터를 `IHTMLEventObj` 현재 이벤트 개체에 반환합니다.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>매개 변수

*ppEventObj*<br/>
인터페이스 포인터로 채워질 포인터의 `IHTMLEventObj` 주소입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 DHTML 이벤트 처리기 내에서만 호출해야 합니다.

## <a name="cdhtmldialoggetexternal"></a><a name="getexternal"></a>CDHtmlDialog::GetExternal

호스트의 `IDispatch` 인터페이스를 가져옵니다.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>매개 변수

*ppDispatch*<br/>
[IDocHostUIHandler에서](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) *ppDispatch를* 참조하십시오:GetExternal Windows SDK에서.

### <a name="return-value"></a>Return Value

성공 또는 실패 시 E_NOTIMPL S_OK 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))의 구현입니다.

## <a name="cdhtmldialoggethostinfo"></a><a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo

호스트의 UI 기능을 검색합니다.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
IDocHostUIHandler에서 *pInfo를* [참조하십시오::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) 윈도우 SDK에서.

### <a name="return-value"></a>Return Value

S_OK 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::GetHostInfo의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))구현입니다.

## <a name="cdhtmldialoggetoptionkeypath"></a><a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath

사용자 기본 설정이 저장되는 레지스트리 키를 검색합니다.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>매개 변수

*pchKey*<br/>
[IDocHostUIHandler::GetOptionKeyWindows에서](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) Windows SDK에서 *pchKey를* 참조하십시오.

*dw*<br/>
윈도우 SDK에서 `IDocHostUIHandler::GetOptionKeyPath` *dw를* 참조하십시오.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::GetOptionKeyPath의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))구현입니다.

## <a name="cdhtmldialoghideui"></a><a name="hideui"></a>CDHtmlDialog::히데이

호스트의 UI를 숨깁니다.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::HideUI의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogisexternaldispatchsafe"></a><a name="isexternaldispatchsafe"></a>CDHtmlDialog::외부 디스패치세이프

호스트의 `IDispatch` 인터페이스가 스크립팅에 안전한지 여부를 나타냅니다.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>Return Value

FALSE를 반환합니다.

## <a name="cdhtmldialogloadfromresource"></a><a name="loadfromresource"></a>CDHtmlDialog::로드From리소스

지정된 리소스를 DHTML 대화 상자의 WebBrowser 컨트롤에 로드합니다.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>매개 변수

*lpszResource*<br/>
로드할 리소스의 이름이 포함된 문자열에 대한 포인터입니다.

*nRes*<br/>
로드할 리소스의 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE이고, 실패하면 FALSE입니다.

## <a name="cdhtmldialogm_busehtmltitle"></a><a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle

HTML 문서의 제목을 대화 상자 캡션으로 사용할지 여부를 나타냅니다.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>설명

**m**_ **bUseHtmlTitleTRUE인** 경우 대화 상자 캡션은 HTML 문서의 제목과 동일하게 설정됩니다. 그렇지 않으면 대화 상자 리소스의 캡션이 사용됩니다.

## <a name="cdhtmldialogm_nhtmlresid"></a><a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID

표시할 HTML 리소스의 리소스 ID입니다.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

## <a name="cdhtmldialogm_pbrowserapp"></a><a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp

웹 브라우저 응용 프로그램에 대한 포인터입니다.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

## <a name="cdhtmldialogm_sphtmldoc"></a><a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc

HTML 문서에 대한 포인터입니다.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

## <a name="cdhtmldialogm_strcurrenturl"></a><a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl

현재 URL입니다.

```
CString m_strCurrentUrl;
```

## <a name="cdhtmldialogm_szhtmlresid"></a><a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID

HTML 리소스 ID의 문자열 버전입니다.

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

## <a name="cdhtmldialognavigate"></a><a name="navigate"></a>CDHtmlDialog::탐색

*lpszURL에*의해 지정된 URL로 식별된 리소스로 이동합니다.

```cpp
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
대상화할 URL을 포함하는 문자열에 대한 포인터입니다.

*dwFlags*<br/>
기록 목록에 리소스를 추가할지, 캐시에서 읽을지 또는 캐시에서 쓸지 여부, 새 창에 리소스를 표시할지 여부를 지정하는 변수의 플래그입니다. 변수는 [BrowserNavConstants](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) 열거형에 의해 정의된 값의 조합일 수 있습니다.

*lpszTargetFrameName*<br/>
리소스를 표시할 프레임의 이름이 포함된 문자열에 대한 포인터입니다.

*lpszHeaders*<br/>
서버에 보낼 HTTP 헤더를 지정하는 값에 대한 포인터입니다. 이러한 헤더는 기본 Internet Explorer 헤더에 추가됩니다. 헤더는 서버에 필요한 작업, 서버에 전달되는 데이터 유형 또는 상태 코드와 같은 정보를 지정할 수 있습니다. URL이 HTTP URL이 아닌 경우 이 매개 변수는 무시됩니다.

*lpvPostData*<br/>
HTTP POST 트랜잭션으로 보낼 데이터에 대한 포인터입니다. 예를 들어 POST 트랜잭션은 HTML 양식으로 수집된 데이터를 전송하는 데 사용됩니다. 이 매개 변수가 사후 데이터를 `Navigate` 지정하지 않으면 HTTP GET 트랜잭션을 발행합니다. URL이 HTTP URL이 아닌 경우 이 매개 변수는 무시됩니다.

*dwPostDataLen*<br/>
HTTP POST 트랜잭션으로 보낼 데이터입니다. 예를 들어 POST 트랜잭션은 HTML 양식으로 수집된 데이터를 전송하는 데 사용됩니다. 이 매개 변수가 사후 데이터를 `Navigate` 지정하지 않으면 HTTP GET 트랜잭션을 발행합니다. URL이 HTTP URL이 아닌 경우 이 매개 변수는 무시됩니다.

## <a name="cdhtmldialogonbeforenavigate"></a><a name="onbeforenavigate"></a>CDHtmlDialog::에 이전 탐색

탐색이 발생하기 전에 이벤트가 발생하도록 프레임워크에서 호출합니다.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
탐색할 URL이 포함된 문자열에 대한 포인터입니다.

## <a name="cdhtmldialogondocumentcomplete"></a><a name="ondocumentcomplete"></a>CDHtmlDialog::문서 완료

문서가 READYSTATE_COMPLETE 상태를 달성했을 때 응용 프로그램에 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
탐색된 URL이 포함된 문자열에 대한 포인터입니다.

## <a name="cdhtmldialogondocwindowactivate"></a><a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindow활성화

문서 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>매개 변수

*fActivate*<br/>
[IDocHostUIHandler에서 fActivate::OnDocWindow](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) Windows SDK에서 활성화합니다. *fActivate*

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::OnDocWindowActivate의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogonframewindowactivate"></a><a name="onframewindowactivate"></a>CDHtmlDialog:::온프레임 윈도우활성화

프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>매개 변수

*fActivate*<br/>
[IDocHostUIHandler에서 fActivate::OnFrameWindow](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) Windows SDK에서 활성화합니다. *fActivate*

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::OnFrameWindowActivate의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogoninitdialog"></a><a name="oninitdialog"></a>CDHtmlDialog::InInitDialog

WM_INITDIALOG 메시지에 대한 응답으로 호출됩니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

기본 구현은 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메시지는 대화 상자가 표시되기 `Create` `CreateIndirect`직전에 `DoModal` 발생하는 " 또는 호출 중에 대화 상자로 전송됩니다.

대화 상자가 초기화될 때 특별한 처리를 수행해야 하는 경우 이 멤버 함수를 재정의합니다. 재정의된 버전에서는 먼저 기본 클래스를 `OnInitDialog` 호출하지만 반환 값을 무시합니다. 일반적으로 재정의된 멤버 함수에서 TRUE를 반환합니다.

Windows는 `OnInitDialog` 메시지 맵을 통하지 않고 모든 Microsoft Foundation 클래스 라이브러리 대화 상자에 공통적인 표준 글로벌 대화 상자 프로시저를 통해 함수를 호출하므로 이 멤버 함수에 대한 메시지 맵 항목이 필요하지 않습니다.

## <a name="cdhtmldialogonnavigatecomplete"></a><a name="onnavigatecomplete"></a>CDHtmlDialog::탐색 완료

지정된 URL에 대한 탐색 후 프레임워크에서 호출됩니다.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
탐색된 URL이 포함된 문자열에 대한 포인터입니다.

## <a name="cdhtmldialogresizeborder"></a><a name="resizeborder"></a>CDHtmlDialog::크기 조정국경

테두리 공간의 크기를 조정해야 하는 개체에 경고합니다.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>매개 변수

*prcBorder*<br/>
[IDocHostUIHandler::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) SDK에서 *prcBorder* 축소국경을 참조하십시오.

*pUIWindow*<br/>
윈도우 SDK에서 `IDocHostUIHandler::ResizeBorder` *pUI창을* 참조하십시오.

*fFrameWindow*<br/>
윈도우 SDK에서 `IDocHostUIHandler::ResizeBorder` *fFrameWindow를* 참조하십시오.

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

## <a name="cdhtmldialogsetcontrolproperty"></a><a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty

ActiveX 컨트롤의 속성을 새 값으로 설정합니다.

```cpp
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*디스피드*<br/>
설정할 속성의 디스패치 ID입니다.

*pVar*<br/>
새 속성 값을 포함하는 VARIANT에 대한 포인터입니다.

*pdispControl*<br/>
ActiveX 컨트롤의 `IDispatch` 인터페이스에 대한 포인터입니다.

*szPropName*<br/>
설정할 속성의 이름을 포함하는 문자열입니다.

## <a name="cdhtmldialogsetelementhtml"></a><a name="setelementhtml"></a>CDHtmlDialog::세트엘리멘타Html

HTML `innerHTML` 요소의 속성을 설정합니다.

```cpp
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*bstrText*<br/>
`innerHTML` 속성의 새 값입니다.

*punkElem*<br/>
HTML `IUnknown` 요소의 포인터입니다.

## <a name="cdhtmldialogsetelementproperty"></a><a name="setelementproperty"></a>CDHtmlDialog::SetElementProperty

HTML 요소의 속성을 설정합니다.

```cpp
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*디스피드*<br/>
설정할 속성의 디스패치 ID입니다.

*pVar*<br/>
속성의 새 값입니다.

## <a name="cdhtmldialogsetelementtext"></a><a name="setelementtext"></a>CDHtmlDialog::세트요소텍스트

HTML `innerText` 요소의 속성을 설정합니다.

```cpp
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*bstrText*<br/>
`innerText` 속성의 새 값입니다.

*punkElem*<br/>
HTML `IUnknown` 요소의 포인터입니다.

## <a name="cdhtmldialogsetexternaldispatch"></a><a name="setexternaldispatch"></a>CDHtmlDialog::세트외부 디스패치

호스트의 `IDispatch` 인터페이스를 설정합니다.

```cpp
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>매개 변수

*pdispExternal*<br/>
새 `IDispatch` 인터페이스입니다.

## <a name="cdhtmldialogsethostflags"></a><a name="sethostflags"></a>CDHtmlDialog::세트호스트 플래그

호스트 UI 플래그를 설정합니다.

```cpp
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
가능한 값은 Windows SDK의 [DOCHOSTUIFLAG를](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) 참조하십시오.

## <a name="cdhtmldialogshowcontextmenu"></a><a name="showcontextmenu"></a>CDHtmlDialog::쇼컨텍스트메뉴

컨텍스트 메뉴가 표시될 때 호출됩니다.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>매개 변수

*dwID*<br/>
[IDocHostUIHandler::ShowContextMenu에서](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) windows SDK에서 *dwID를* 참조하십시오.

*Ppt*<br/>
윈도우 SDK에서 `IDocHostUIHandler::ShowContextMenu` *PPT를* 참조하십시오.

*pcmdtReserved*<br/>
윈도우 SDK에서 `IDocHostUIHandler::ShowContextMenu` *예약 pcmdt를* 참조하십시오.

*pdispReserved*<br/>
윈도우 SDK에서 `IDocHostUIHandler::ShowContextMenu` *예약 pdispreserved를* 참조하십시오.

### <a name="return-value"></a>Return Value

S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::ShowContextMenu의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogshowui"></a><a name="showui"></a>CDHtmlDialog::쇼이

호스트의 UI를 표시합니다.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>매개 변수

*dwID*<br/>
[IDocHostUIHandler::ShowUI에서](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) Windows SDK에서 *dwID를* 참조하십시오.

*pActiveObject*<br/>
Windows SDK에서 `IDocHostUIHandler::ShowUI` *d pActiveObject를* 참조하십시오.

*pCommandTarget*<br/>
Windows SDK에서 `IDocHostUIHandler::ShowUI` *pCommandTarget을* 참조하십시오.

*pFrame*<br/>
Windows `IDocHostUIHandler::ShowUI` SDK에서 *pFrame을* 참조하십시오.

*pDoc*<br/>
Windows SDK에서 `IDocHostUIHandler::ShowUI` *pDoc을* 참조하십시오.

### <a name="return-value"></a>Return Value

S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::ShowUI의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogtranslateaccelerator"></a><a name="translateaccelerator"></a>CDHtmlDialog::번역가속기

메뉴 가속기 키 메시지를 처리하기 위해 호출됩니다.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>매개 변수

*lpMsg*<br/>
[IDocHostUIHandler:::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) SDK에서 번역 가속기에서 *lpMsg를* 참조하십시오.

*pguidCmdGroup*<br/>
윈도우 SDK에서 `IDocHostUIHandler::TranslateAccelerator` *pguidCmd그룹을* 참조하십시오.

*nCmdID*<br/>
Windows SDK에서 `IDocHostUIHandler::TranslateAccelerator` *nCmdID를* 참조하십시오.

### <a name="return-value"></a>Return Value

S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::TranslateAccelerator의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogtranslateurl"></a><a name="translateurl"></a>CDHtmlDialog::번역Url

로드할 URL을 수정하기 위해 호출됩니다.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>매개 변수

*dwTranslate*<br/>
[IDocHostUIHandler에서](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) *dwTranslate::번역Url* 윈도우 SDK에서 참조.

*pchURLIn*<br/>
윈도우 SDK에서 `IDocHostUIHandler::TranslateUrl` *pchURLIn을* 참조하십시오.

*ppchURLOut*<br/>
윈도우 SDK에서 `IDocHostUIHandler::TranslateUrl` *ppchURLOut을* 참조하십시오.

### <a name="return-value"></a>Return Value

S_FALSE 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::TranslateUrl의](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))구현입니다.

## <a name="cdhtmldialogupdateui"></a><a name="updateui"></a>CDHtmlDialog::업데이트 UI

명령 상태가 변경되었음을 호스트에게 알리기 위해 호출됩니다.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>Return Value

E_NOTIMPL을 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 CDHtmlDialog의 [IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))구현입니다.

## <a name="see-also"></a>참조

[MFC 샘플 DHtmlExplore](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml 도우미 매크로](#ddx_dhtml_helper_macros)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
