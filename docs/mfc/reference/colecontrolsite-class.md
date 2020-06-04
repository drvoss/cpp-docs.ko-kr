---
title: 콜레컨트롤사이트 클래스
ms.date: 11/04/2016
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
ms.openlocfilehash: 90c41a1be1a66cdceebb3f045a98167e56b7cf4c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753952"
---
# <a name="colecontrolsite-class"></a>콜레컨트롤사이트 클래스

사용자 지정 클라이언트 측 컨트롤 인터페이스를 지원합니다.

## <a name="syntax"></a>구문

```
class COleControlSite : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레 컨트롤 사이트::콜레 제어 사이트](#colecontrolsite)|`COleControlSite` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[콜레컨트롤사이트:바인딩디폴속성](#binddefaultproperty)|호스트된 컨트롤의 기본 속성을 데이터 원본에 바인딩합니다.|
|[콜레컨트롤사이트::바인드프로퍼티](#bindproperty)|호스트된 컨트롤의 속성을 데이터 원본에 바인딩합니다.|
|[COleControlSite::만들기 제어](#createcontrol)|호스팅된 ActiveX 컨트롤을 만듭니다.|
|[콜레컨트롤사이트::D에스트로이컨트롤](#destroycontrol)|호스트된 컨트롤을 삭제합니다.|
|[콜레컨트롤사이트::D](#doverb)|호스트된 컨트롤의 특정 동사를 실행합니다.|
|[콜레컨트롤사이트::인에이블DSC](#enabledsc)|제어 사이트에 대한 데이터 소싱을 활성화합니다.|
|[COleControlSite::인에이블윈도우](#enablewindow)|제어 사이트를 활성화합니다.|
|[콜레 컨트롤 사이트::동결 이벤트](#freezeevents)|컨트롤 사이트에서 이벤트를 수락하는지 지정합니다.|
|[콜레 컨트롤 사이트::GetDefBtnCode](#getdefbtncode)|호스팅된 컨트롤의 기본 단추 코드를 검색합니다.|
|[콜레컨트롤사이트::겟들크럴리드](#getdlgctrlid)|컨트롤의 식별자를 검색합니다.|
|[콜레 컨트롤 사이트::GetEventIID](#geteventiid)|호스트된 컨트롤에 대 한 이벤트 인터페이스의 ID를 검색 합니다.|
|[콜레컨트롤사이트::겟엑스스타일](#getexstyle)|컨트롤 사이트의 확장된 스타일을 검색합니다.|
|[콜레컨트롤사이트::겟프로퍼티](#getproperty)|호스트된 컨트롤의 특정 속성을 검색합니다.|
|[콜레컨트롤사이트:겟스타일](#getstyle)|제어 사이트의 스타일을 검색합니다.|
|[콜레 컨트롤 사이트::GetWindow텍스트](#getwindowtext)|호스트된 컨트롤의 텍스트를 검색합니다.|
|[COleControlSite::호출 도우미](#invokehelper)|호스트된 컨트롤의 특정 메서드를 호출합니다.|
|[COleControlSite::호출헬퍼V](#invokehelperv)|호스트된 컨트롤의 특정 메서드를 변수 인수 목록으로 호출합니다.|
|[COle컨트롤사이트::기본설정버튼](#isdefaultbutton)|컨트롤이 창의 기본 단추인지 확인합니다.|
|[콜레컨트롤사이트::이윈도우 사용 가능](#iswindowenabled)|제어 사이트의 표시되는 상태를 확인합니다.|
|[COle컨트롤사이트::수정 스타일](#modifystyle)|컨트롤 사이트의 현재 확장 스타일을 수정합니다.|
|[COle컨트롤사이트::수정스타일엑스](#modifystyleex)|컨트롤 사이트의 현재 스타일을 수정합니다.|
|[콜레컨트롤사이트::이동창](#movewindow)|제어 사이트의 위치를 변경합니다.|
|[COleControlSite::빠른 활성화](#quickactivate)|빠르게 호스팅된 컨트롤을 활성화합니다.|
|[콜레컨트롤사이트::세이프셋속성](#safesetproperty)|예외를 throw하지 않고 컨트롤의 속성 또는 메서드를 설정합니다.|
|[COle컨트롤사이트::설정기본버튼](#setdefaultbutton)|창에서 기본 단추를 설정합니다.|
|[콜레 컨트롤 사이트::세트딜트르리드](#setdlgctrlid)|컨트롤의 식별자를 검색합니다.|
|[콜레 컨트롤 사이트::설정 포커스](#setfocus)|컨트롤 사이트에 포커스를 설정합니다.|
|[콜레컨트롤사이트::셋프로퍼티](#setproperty)|호스트된 컨트롤의 특정 속성을 설정합니다.|
|[콜레컨트롤사이트::세트프로퍼티V](#setpropertyv)|호스트된 컨트롤의 특정 속성을 변수 인수 목록으로 설정합니다.|
|[콜레 컨트롤 사이트::세트윈도우포스](#setwindowpos)|제어 사이트의 위치를 설정합니다.|
|[콜레 컨트롤 사이트::세트윈도우텍스트](#setwindowtext)|호스트된 컨트롤의 텍스트를 설정합니다.|
|[콜레컨트롤사이트::쇼윈도우](#showwindow)|제어 사이트를 표시하거나 숨깁니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[콜레컨트롤사이트::겟컨트롤정보](#getcontrolinfo)|호스트된 컨트롤에 대한 키보드 정보 및 니모닉을 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레컨트롤사이트:m_bIsWindowless](#m_biswindowless)|호스트된 컨트롤이 창 없는 컨트롤인지 확인합니다.|
|[콜레컨트롤사이트:m_ctlInfo](#m_ctlinfo)|컨트롤에 대한 키보드 처리에 대한 정보가 들어 있습니다.|
|[콜레컨트롤사이트:m_dwEventSink](#m_dweventsink)|컨트롤 연결 지점의 쿠키입니다.|
|[콜레컨트롤사이트:m_dwMiscStatus](#m_dwmiscstatus)|호스트된 컨트롤에 대한 기타 상태입니다.|
|[콜레컨트롤사이트:m_dwPropNotifySink](#m_dwpropnotifysink)|컨트롤의 `IPropertyNotifySink` 쿠키입니다.|
|[콜레컨트롤사이트:m_dwStyle](#m_dwstyle)|호스트된 컨트롤의 스타일입니다.|
|[콜레컨트롤사이트:m_hWnd](#m_hwnd)|제어 사이트의 핸들입니다.|
|[콜레컨트롤사이트:m_iidEvents](#m_iidevents)|호스트된 컨트롤에 대한 이벤트 인터페이스의 ID입니다.|
|[콜레컨트롤사이트:m_nID](#m_nid)|호스팅된 컨트롤의 ID입니다.|
|[콜레컨트롤사이트:m_pActiveObject](#m_pactiveobject)|호스트된 컨트롤의 개체에 대한 `IOleInPlaceActiveObject` 포인터입니다.|
|[콜레컨트롤사이트::m_pCtrlCont](#m_pctrlcont)|호스트된 컨트롤의 컨테이너입니다.|
|[콜레컨트롤사이트::m_pInPlaceObject](#m_pinplaceobject)|호스트된 컨트롤의 개체에 대한 `IOleInPlaceObject` 포인터입니다.|
|[콜레컨트롤사이트:m_pObject](#m_pobject)|컨트롤의 인터페이스에 대한 `IOleObjectInterface` 포인터입니다.|
|[콜레컨트롤사이트:m_pWindowlessObject](#m_pwindowlessobject)|컨트롤의 인터페이스에 대한 `IOleInPlaceObjectWindowless` 포인터입니다.|
|[콜레컨트롤사이트:m_pWndCtrl](#m_pwndctrl)|호스트된 컨트롤의 창 개체에 대한 포인터입니다.|
|[콜레컨트롤사이트:m_rect](#m_rect)|제어 사이트의 크기입니다.|

## <a name="remarks"></a>설명

이 지원은 임베디드 ActiveX 컨트롤이 해당 표시 사이트의 위치 및 범위, 모니커, 사용자 인터페이스, 해당 주변 속성 및 해당 컨테이너에서 제공하는 기타 리소스에 대한 정보를 가져오는 기본 수단입니다. `COleControlSite`[IOleControlSite,](/windows/win32/api/ocidl/nn-ocidl-iolecontrolsite) [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleClientSite](/windows/win32/api/oleidl/nn-oleidl-ioleclientsite), [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) `INotifyDBEvents`, , `IBoundObjectSite` [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) 인터페이스를 완전히 구현합니다. 또한 IDispatch 인터페이스(주변 속성 및 이벤트 싱크에 대한 지원 제공)도 구현됩니다.

을 사용하여 `COleControlSite`ActiveX 컨트롤 사이트를 만들려면 `COleControlSite`에서 클래스를 파생합니다. 컨테이너에 `CWnd`대한 -derived 클래스(예: 대화 상자)에서 함수를 `CWnd::CreateControlSite` 재정의합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlSite`

## <a name="requirements"></a>요구 사항

**헤더:** afxocc.h

## <a name="colecontrolsitebinddefaultproperty"></a><a name="binddefaultproperty"></a>콜레컨트롤사이트:바인딩디폴속성

형식 라이브러리에 표시된 호출 개체의 기본 단순 바인딩 속성을 DataSource, UserName, 암호 및 데이터 원본 컨트롤의 SQL 속성에 의해 정의된 기본 커서에 바인딩합니다.

```
virtual void BindDefaultProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    LPCTSTR szFieldName,
    CWnd* pDSCWnd);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
데이터 원본 컨트롤에 바인딩할 데이터 바인딩된 컨트롤에서 속성의 DISPID를 지정합니다.

*vtProp*<br/>
바인딩할 속성의 유형(예: VT_BSTR, VT_VARIANT 등)을 지정합니다.

*szField네임*<br/>
속성이 바인딩될 데이터 원본 컨트롤에서 제공하는 커서에서 열의 이름을 지정합니다.

*pDSCWnd*<br/>
속성이 `CWnd`바인딩될 데이터 원본 컨트롤을 호스트하는 -derived 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 `CWnd` 함수를 호출하는 개체는 데이터 바인딩된 컨트롤이어야 합니다.

## <a name="colecontrolsitebindproperty"></a><a name="bindproperty"></a>콜레컨트롤사이트::바인드프로퍼티

형식 라이브러리에 표시된 것처럼 호출 하는 개체의 간단한 바인딩된 속성을 DataSource, UserName, 암호 및 데이터 원본 컨트롤의 SQL 속성에 의해 정의 된 기본 커서에 바인딩합니다.

```
virtual void BindProperty(
    DISPID dwDispId,
    CWnd* pWndDSC);
```

### <a name="parameters"></a>매개 변수

*dwDispId*<br/>
데이터 원본 컨트롤에 바인딩할 데이터 바인딩된 컨트롤에서 속성의 DISPID를 지정합니다.

*pWndDSC*<br/>
속성이 `CWnd`바인딩될 데이터 원본 컨트롤을 호스트하는 -derived 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 `CWnd` 함수를 호출하는 개체는 데이터 바인딩된 컨트롤이어야 합니다.

## <a name="colecontrolsitecolecontrolsite"></a><a name="colecontrolsite"></a>콜레 컨트롤 사이트::콜레 제어 사이트

새 `COleControlSite` 개체를 생성합니다.

```
explicit COleControlSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>매개 변수

*pCtrlCont*<br/>
컨트롤의 컨테이너에 대한 포인터(AtiveX 컨트롤을 호스트하는 창을 나타냅니다).

### <a name="remarks"></a>설명

이 함수는 [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) 함수에서 호출합니다. 컨테이너 만들기 사용자 지정에 대한 자세한 내용은 [COccManager:CreateSite](../../mfc/reference/coccmanager-class.md#createsite)을 참조하십시오.

## <a name="colecontrolsitecreatecontrol"></a><a name="createcontrol"></a>COleControlSite::만들기 제어

개체에서 호스팅하는 ActiveX `COleControlSite` 컨트롤을 만듭니다.

```
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);

virtual HRESULT CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist = NULL,
    BOOL bStorage = FALSE,
    BSTR bstrLicKey = NULL);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
컨트롤을 나타내는 창 개체에 대한 포인터입니다.

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszWindowName*<br/>
컨트롤에 표시할 텍스트에 대한 포인터입니다. winodw의 캡션 또는 텍스트 속성(있는 경우)의 값을 설정합니다.

*dwStyle*<br/>
윈도우 스타일. 사용 가능한 스타일은 **비고** 섹션 아래에 나열됩니다.

*rect*<br/>
컨트롤의 크기와 위치를 지정합니다. 개체 또는 `CRect` `RECT` 구조체일 수 있습니다.

*nID*<br/>
컨트롤의 하위 창 ID를 지정합니다.

*pPersist*<br/>
컨트롤에 대 `CFile` 한 영구 상태를 포함 하는 포인터입니다. 기본값은 NULL로, 컨트롤이 영구 저장소에서 상태를 복원하지 않고 자체를 초기화한다는 것을 나타냅니다. NULL이 아닌 경우 스트림 또는 `CFile`저장소의 형태로 컨트롤의 영구 데이터를 포함하는 -derived 개체에 대한 포인터여야 합니다. 이 데이터는 클라이언트의 이전 활성화에 저장되었을 수 있습니다. 다른 `CFile` 데이터를 포함할 수 있지만 호출 시 영구 데이터의 첫 번째 바이트로 설정된 읽기 `CreateControl`쓰기 포인터가 있어야 합니다.

*b스토리지*<br/>
*pPersist의* 데이터를 데이터로 `IStorage` `IStream` 해석할지 여부를 나타냅니다. *pPersist의* 데이터가 저장소인 경우 *bStorage는* TRUE여야 합니다. *pPersist의* 데이터가 스트림인 경우 *bStorage는* FALSE여야 합니다. 기본값은 FALSE입니다.

*블스트릭키*<br/>
옵션 라이센스 키 데이터. 이 데이터는 런타임 라이센스 키가 필요한 컨트롤을 만드는 데만 필요합니다. 컨트롤이 라이선스를 지원하는 경우 성공하려면 컨트롤을 만들 수 있는 라이센스 키를 제공해야 합니다. 기본값은 NULL입니다.

*Ppt*<br/>
컨트롤의 `POINT` 왼쪽 위 모서리를 포함하는 구조체에 대한 포인터입니다. 컨트롤의 크기는 *psize*값에 의해 결정됩니다. *ppt* 및 *psize* 값은 컨트롤의 크기와 위치 opf를 지정하는 선택적 방법입니다.

*크기 조정*<br/>
컨트롤의 크기를 `SIZE` 포함하는 구조에 대한 포인터입니다. 왼쪽 위 모서리는 *ppt*값에 의해 결정됩니다. *ppt* 및 *psize* 값은 컨트롤의 크기와 위치 opf를 지정하는 선택적 방법입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

Windows *dwStyle* 플래그의 하위 집합만 `CreateControl`다음에서 지원됩니다.

- WS_VISIBLE 처음에 표시되는 창을 만듭니다. 일반 창과 같이 컨트롤을 즉시 표시하려면 필수입니다.

- WS_DISABLED 처음에 사용하지 않도록 설정한 창을 만듭니다. 비활성화된 창은 사용자로부터 입력을 받을 수 없습니다. 컨트롤에 Enabled 속성이 있는 경우 설정할 수 있습니다.

- WS_BORDER 줄 테두리가 있는 창을 만듭니다. 컨트롤에 BorderStyle 속성이 있는 경우 설정할 수 있습니다.

- WS_GROUP 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다. 사용자는 방향 키를 사용하여 그룹의 한 컨트롤에서 다음 컨트롤로 키보드 포커스를 변경할 수 있습니다. 첫 번째 컨트롤 이후에 WS_GROUP 스타일로 정의된 모든 컨트롤은 동일한 그룹에 속합니다. WS_GROUP 스타일로 다음 컨트롤은 그룹을 종료하고 다음 그룹을 시작합니다.

- WS_TABSTOP 사용자가 TAB 키를 누를 때 키보드 포커스를 받을 수 있는 컨트롤을 지정합니다. TAB 키를 누르면 키보드 초점이 WS_TABSTOP 스타일의 다음 컨트롤로 변경됩니다.

두 번째 오버로드를 사용하여 기본 크기의 컨트롤을 만듭니다.

## <a name="colecontrolsitedestroycontrol"></a><a name="destroycontrol"></a>콜레컨트롤사이트::D에스트로이컨트롤

개체를 `COleControlSite` 삭제합니다.

```
virtual BOOL DestroyControl();
```

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

### <a name="remarks"></a>설명

완료되면 개체가 메모리에서 해제되고 개체에 대한 포인터가 더 이상 유효하지 않습니다.

## <a name="colecontrolsitedoverb"></a><a name="doverb"></a>콜레컨트롤사이트::D

지정된 동사를 실행합니다.

```
virtual HRESULT DoVerb(
    LONG nVerb,
    LPMSG lpMsg = NULL);
```

### <a name="parameters"></a>매개 변수

*nVerb*<br/>
실행할 동사를 지정합니다. 다음 중 하나를 포함할 수 있습니다.

|값|의미|기호|
|-----------|-------------|------------|
|0|기본 동사|OLEIVERB_PRIMARY|
|-1|보조 동사|(없음)|
|1|편집할 객체를 표시합니다.|OLEIVERB_SHOW|
|-2|별도의 창에서 항목을 편집합니다.|OLEIVERB_OPEN|
|-3|개체를 숨깁니다.|OLEIVERB_HIDE|
|-4|컨트롤을 활성화합니다.|OLEIVERB_UIACTIVATE|
|-5|추가 사용자 인터페이스 요소 없이 컨트롤을 활성화합니다.|OLEIVERB_INPLACEACTIVATE|
|-7|컨트롤의 속성을 표시합니다.|OLEIVERB_PROPERTIES|

*lpMsg*<br/>
항목을 활성화한 메시지에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수는 컨트롤의 `IOleObject` 인터페이스를 통해 직접 호출하여 지정된 동사를 실행합니다. 이 함수 호출의 결과로 예외가 throw되면 HRESULT 오류 코드가 반환됩니다.

자세한 내용은 Windows SDK의 [IOleObject::Doverb를](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) 참조하십시오.

## <a name="colecontrolsiteenabledsc"></a><a name="enabledsc"></a>콜레컨트롤사이트::인에이블DSC

제어 사이트에 대한 데이터 소싱을 활성화합니다.

```
virtual void EnableDSC();
```

### <a name="remarks"></a>설명

제어 사이트에 대한 데이터 소싱을 활성화하고 초기화하기 위해 프레임워크에서 호출합니다. 이 함수를 재정의하여 사용자 지정된 동작을 제공합니다.

## <a name="colecontrolsiteenablewindow"></a><a name="enablewindow"></a>COleControlSite::인에이블윈도우

제어 사이트에 대한 마우스 및 키보드 입력을 활성화하거나 사용하지 않도록 설정합니다.

```
virtual BOOL EnableWindow(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
창을 활성화 또는 비활성화할지 여부를 지정합니다: TRUE 창 입력을 사용하도록 설정하려면 TRUE( 그렇지 않으면 FALSE).

### <a name="return-value"></a>Return Value

창이 이전에 비활성화된 경우 0이 아닌 0입니다.

## <a name="colecontrolsitefreezeevents"></a><a name="freezeevents"></a>콜레 컨트롤 사이트::동결 이벤트

컨트롤 사이트에서 컨트롤에서 발생한 이벤트를 처리하거나 무시할지 여부를 지정합니다.

```cpp
void FreezeEvents(BOOL bFreeze);
```

### <a name="parameters"></a>매개 변수

*bFreeze*<br/>
컨트롤 사이트에서 이벤트 수락을 중지하려는지를 지정합니다. 컨트롤이 이벤트를 수락하지 않는 경우 0이 아님을 그렇지 않으면 0.

### <a name="remarks"></a>설명

*bFreeze가* TRUE이면 컨트롤 사이트에서 컨트롤을 요청하여 프린지 이벤트를 중지합니다. *bFreeze가* FALSE이면 컨트롤 사이트에서 이벤트를 계속 실행하도록 컨트롤을 요청합니다.

> [!NOTE]
> 컨트롤이 제어 사이트에서 요청하는 경우 이벤트 발생을 중지할 필요가 없습니다. 계속 실행될 수 있지만 이후의 모든 이벤트는 제어 사이트에서 무시됩니다.

## <a name="colecontrolsitegetcontrolinfo"></a><a name="getcontrolinfo"></a>콜레컨트롤사이트::겟컨트롤정보

컨트롤의 키보드 비니모닉 및 키보드 동작에 대한 정보를 검색합니다.

```cpp
void GetControlInfo();
```

### <a name="remarks"></a>설명

정보는 [COleControlSite::m_ctlInfo](#m_ctlinfo)에 저장됩니다.

## <a name="colecontrolsitegetdefbtncode"></a><a name="getdefbtncode"></a>콜레 컨트롤 사이트::GetDefBtnCode

컨트롤이 기본 푸시 단추인지 확인합니다.

```
DWORD GetDefBtnCode();
```

### <a name="return-value"></a>Return Value

다음 값 중 하나를 사용할 수 있습니다.

- DLGC_DEFPUSHBUTTON 컨트롤은 대화 상자의 기본 단추입니다.

- DLGC_UNDEFPUSHBUTTON 컨트롤은 대화 상자의 기본 버튼이 아닙니다.

- **0** 컨트롤은 버튼이 아닙니다.

## <a name="colecontrolsitegetdlgctrlid"></a><a name="getdlgctrlid"></a>콜레컨트롤사이트::겟들크럴리드

컨트롤의 식별자를 검색합니다.

```
virtual int GetDlgCtrlID() const;
```

### <a name="return-value"></a>Return Value

컨트롤의 대화 상자 항목 식별자입니다.

## <a name="colecontrolsitegeteventiid"></a><a name="geteventiid"></a>콜레 컨트롤 사이트::GetEventIID

컨트롤의 기본 이벤트 인터페이스에 대한 포인터를 검색합니다.

```
BOOL GetEventIID(IID* piid);
```

### <a name="parameters"></a>매개 변수

*piid*<br/>
인터페이스 ID에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다. 성공하면 *piid는* 컨트롤의 기본 이벤트 인터페이스에 대한 인터페이스 ID를 포함합니다.

## <a name="colecontrolsitegetexstyle"></a><a name="getexstyle"></a>콜레컨트롤사이트::겟엑스스타일

창의 확장된 스타일을 검색합니다.

```
virtual DWORD GetExStyle() const;
```

### <a name="return-value"></a>Return Value

컨트롤 창의 확장된 스타일입니다.

### <a name="remarks"></a>설명

일반 스타일을 검색하려면 [COleControlSite::GetStyle](#getstyle)을 호출합니다.

## <a name="colecontrolsitegetproperty"></a><a name="getproperty"></a>콜레컨트롤사이트::겟프로퍼티

*dwDispID에*의해 지정된 컨트롤 속성을 가져옵니다.

```
virtual void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
검색할 컨트롤의 기본 `IDispatch` 인터페이스에 있는 속성의 디스패치 ID를 식별합니다.

*vtProp*<br/>
검색할 속성의 형식을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*pvProp*<br/>
속성 값을 받을 변수의 주소입니다. *vtProp*에서 지정한 형식과 일치해야 합니다.

### <a name="remarks"></a>설명

값은 *pvProp.*

## <a name="colecontrolsitegetstyle"></a><a name="getstyle"></a>콜레컨트롤사이트:겟스타일

제어 사이트의 스타일을 검색합니다.

```
virtual DWORD GetStyle() const;
```

### <a name="return-value"></a>Return Value

창의 스타일입니다.

### <a name="remarks"></a>설명

가능한 값 목록은 Windows [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오. 제어 사이트의 확장 된 스타일을 검색하려면 [COleControlSite::GetExStyle](#getexstyle)을 호출합니다.

## <a name="colecontrolsitegetwindowtext"></a><a name="getwindowtext"></a>콜레 컨트롤 사이트::GetWindow텍스트

컨트롤의 현재 텍스트를 검색합니다.

```
virtual void GetWindowText(CString& str) const;
```

### <a name="parameters"></a>매개 변수

*Str*<br/>
컨트롤의 `CString` 현재 텍스트를 포함하는 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

컨트롤이 Caption stock 속성을 지원하는 경우 이 값이 반환됩니다. Caption 스톡 속성이 지원되지 않으면 Text 속성의 값이 반환됩니다.

## <a name="colecontrolsiteinvokehelper"></a><a name="invokehelper"></a>COleControlSite::호출 도우미

wFlags 에 의해 지정된 컨텍스트에서 *dwDispID에*의해 지정된 메서드 또는 속성을 *호출합니다.*

```
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
호출할 컨트롤의 인터페이스에 있는 속성 또는 메서드의 `IDispatch` 디스패치 ID를 식별합니다.

*wFlags*<br/>
IDispatch::Invoke 호출의 컨텍스트를 설명하는 플래그입니다. 가능한 *wFlags* 값은 `IDispatch::Invoke` Windows SDK를 참조하십시오.

*vtRet*<br/>
반환 값 형식을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*pvRet*<br/>
속성 값이나 반환 값을 받을 변수의 주소입니다. *vtRet*.

*pbParamInfo*<br/>
*pbParamInfo*다음 매개 변수의 형식을 지정 하는 바이트의 null-종료 된 문자열에 대 한 포인터 . 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*...*<br/>
매개 변수의 변수 목록, *pbParamInfo에*지정된 형식 .

### <a name="remarks"></a>설명

*pbParamInfo* 매개 변수는 메서드 또는 속성에 전달 된 매개 변수의 형식을 지정 합니다. 인수의 변수 목록은 구문 선언에서 ...로 표시됩니다.

이 함수는 매개 변수를 VARIANTARG 값으로 변환한 다음 컨트롤에서 메서드를 `IDispatch::Invoke` 호출합니다. `IDispatch::Invoke` 호출에 실패하면 이 함수가 예외를 throw합니다. 반환되는 `IDispatch::Invoke` 상태 코드의 `DISP_E_EXCEPTION`경우 는 이 `COleDispatchException` 함수가 개체를 `COleException`throw하고 그렇지 않으면 을 throw합니다.

## <a name="colecontrolsiteinvokehelperv"></a><a name="invokehelperv"></a>COleControlSite::호출헬퍼V

wFlags 에 의해 지정된 컨텍스트에서 *dwDispID에*의해 지정된 메서드 또는 속성을 *호출합니다.*

```
virtual void InvokeHelperV(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo,
    va_list argList);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
호출할 컨트롤의 인터페이스에 있는 속성 또는 메서드의 `IDispatch` 디스패치 ID를 식별합니다.

*wFlags*<br/>
IDispatch::Invoke 호출의 컨텍스트를 설명하는 플래그입니다.

*vtRet*<br/>
반환 값 형식을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*pvRet*<br/>
속성 값이나 반환 값을 받을 변수의 주소입니다. *vtRet*.

*pbParamInfo*<br/>
*pbParamInfo*다음 매개 변수의 형식을 지정 하는 바이트의 null-종료 된 문자열에 대 한 포인터 . 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*Arglist*<br/>
변수 인수 목록에 대한 포인터입니다.

### <a name="remarks"></a>설명

*pbParamInfo* 매개 변수는 메서드 또는 속성에 전달 된 매개 변수의 형식을 지정 합니다. 호출되는 메서드 또는 속성에 대한 추가 매개 변수는 *va_list* 매개 변수를 사용하여 전달할 수 있습니다.

일반적으로 이 함수는 `COleControlSite::InvokeHelper`에서 호출됩니다.

## <a name="colecontrolsiteisdefaultbutton"></a><a name="isdefaultbutton"></a>COle컨트롤사이트::기본설정버튼

컨트롤이 기본 단추인지 확인합니다.

```
BOOL IsDefaultButton();
```

### <a name="return-value"></a>Return Value

컨트롤이 창의 기본 단추인 경우 0이 아닌 경우 0입니다.

## <a name="colecontrolsiteiswindowenabled"></a><a name="iswindowenabled"></a>콜레컨트롤사이트::이윈도우 사용 가능

제어 사이트가 활성화되어 있는지 확인합니다.

```
virtual BOOL IsWindowEnabled() const;
```

### <a name="return-value"></a>Return Value

컨트롤이 활성화된 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

값은 컨트롤의 Enabled stock 속성에서 검색됩니다.

## <a name="colecontrolsitem_biswindowless"></a><a name="m_biswindowless"></a>콜레컨트롤사이트:m_bIsWindowless

개체가 창 없는 컨트롤인지 확인합니다.

```
BOOL m_bIsWindowless;
```

### <a name="remarks"></a>설명

컨트롤에 창이 없는 경우 비영( 그렇지 않으면 0).

## <a name="colecontrolsitem_ctlinfo"></a><a name="m_ctlinfo"></a>콜레컨트롤사이트:m_ctlInfo

컨트롤에서 키보드 입력을 처리하는 방법에 대한 정보입니다.

```
CONTROLINFO m_ctlInfo;
```

### <a name="remarks"></a>설명

이 정보는 [CONTROLINFO](/windows/win32/api/ocidl/ns-ocidl-controlinfo) 구조에 저장됩니다.

## <a name="colecontrolsitem_dweventsink"></a><a name="m_dweventsink"></a>콜레컨트롤사이트:m_dwEventSink

컨트롤의 이벤트 싱크에서 연결 지점의 쿠키를 포함 합니다.

```
DWORD m_dwEventSink;
```

## <a name="colecontrolsitem_dwmiscstatus"></a><a name="m_dwmiscstatus"></a>콜레컨트롤사이트:m_dwMiscStatus

컨트롤에 대한 기타 정보가 포함되어 있습니다.

```
DWORD m_dwMiscStatus;
```

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [OLEMISC를](/windows/win32/api/oleidl/ne-oleidl-olemisc)참조하십시오.

## <a name="colecontrolsitem_dwpropnotifysink"></a><a name="m_dwpropnotifysink"></a>콜레컨트롤사이트:m_dwPropNotifySink

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 쿠키를 포함합니다.

```
DWORD m_dwPropNotifySink;
```

## <a name="colecontrolsitem_dwstyle"></a><a name="m_dwstyle"></a>콜레컨트롤사이트:m_dwStyle

컨트롤의 창 스타일을 포함 합니다.

```
DWORD m_dwStyle;
```

## <a name="colecontrolsitem_hwnd"></a><a name="m_hwnd"></a>콜레컨트롤사이트:m_hWnd

컨트롤의 HWND 또는 컨트롤이 창없는 경우 NULL을 포함합니다.

```
HWND m_hWnd;
```

## <a name="colecontrolsitem_iidevents"></a><a name="m_iidevents"></a>콜레컨트롤사이트:m_iidEvents

컨트롤의 기본 이벤트 싱크 인터페이스의 인터페이스 ID를 포함 합니다.

```
IID m_iidEvents;
```

## <a name="colecontrolsitem_nid"></a><a name="m_nid"></a>콜레컨트롤사이트:m_nID

컨트롤의 대화 상자 항목 ID를 포함 합니다.

```
UINT m_nID;
```

## <a name="colecontrolsitem_pactiveobject"></a><a name="m_pactiveobject"></a>콜레컨트롤사이트:m_pActiveObject

컨트롤의 [IOleInPlaceActive개체](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) 인터페이스를 포함합니다.

```
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;
```

## <a name="colecontrolsitem_pctrlcont"></a><a name="m_pctrlcont"></a>콜레컨트롤사이트::m_pCtrlCont

컨트롤의 컨테이너(양식을 나타내는)를 포함합니다.

```
COleControlContainer* m_pCtrlCont;
```

## <a name="colecontrolsitem_pinplaceobject"></a><a name="m_pinplaceobject"></a>콜레컨트롤사이트::m_pInPlaceObject

컨트롤의 `IOleInPlaceObject` [IOleInPlace개체](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject) 인터페이스를 포함합니다.

```
LPOLEINPLACEOBJECT m_pInPlaceObject;
```

## <a name="colecontrolsitem_pobject"></a><a name="m_pobject"></a>콜레컨트롤사이트:m_pObject

컨트롤의 `IOleObjectInterface` 인터페이스를 포함합니다.

```
LPOLEOBJECT m_pObject;
```

## <a name="colecontrolsitem_pwindowlessobject"></a><a name="m_pwindowlessobject"></a>콜레컨트롤사이트:m_pWindowlessObject

`IOleInPlaceObjectWindowless` [컨트롤의 IOleInPlace개체없는](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) 인터페이스를 포함합니다.

```
IOleInPlaceObjectWindowless* m_pWindowlessObject;
```

## <a name="colecontrolsitem_pwndctrl"></a><a name="m_pwndctrl"></a>콜레컨트롤사이트:m_pWndCtrl

컨트롤 자체를 나타내는 `CWnd` 개체에 대한 포인터를 포함합니다.

```
CWnd* m_pWndCtrl;
```

## <a name="colecontrolsitem_rect"></a><a name="m_rect"></a>콜레컨트롤사이트:m_rect

컨테이너의 창을 기준으로 컨트롤의 경계를 포함 합니다.

```
CRect m_rect;
```

## <a name="colecontrolsitemodifystyle"></a><a name="modifystyle"></a>COle컨트롤사이트::수정 스타일

컨트롤의 스타일을 수정합니다.

```
virtual BOOL ModifyStyle(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*dwRemove*<br/>
현재 창 스타일에서 제거할 스타일입니다.

*dwAdd*<br/>
현재 창 스타일에서 추가할 스타일입니다.

*nFlags*<br/>
창 위치 지정 플래그입니다. 가능한 값 목록은 Windows SDK의 [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) 함수를 참조하십시오.

### <a name="return-value"></a>Return Value

스타일이 변경된 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

컨트롤의 주식 사용 속성은 WS_DISABLED 설정과 일치하도록 수정됩니다. 컨트롤의 스톡 테두리 스타일 속성은 WS_BORDER 대해 요청된 설정과 일치하도록 수정됩니다. 다른 모든 스타일이 있는 경우 컨트롤의 창 핸들에 직접 적용됩니다.

컨트롤의 창 스타일을 수정합니다. 추가하거나 제거할 스타일은 비트별 OR(&#124;) 연산자를 사용하여 결합할 수 있다. 사용 가능한 창 스타일에 대한 자세한 내용은 Windows SDK의 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 함수를 참조하십시오.

*nFlags가* 영하지 `ModifyStyle` 않은 경우 Win32 함수를 `SetWindowPos`호출하고 *nFlags를* 다음 네 개의 플래그와 결합하여 창을 다시 그립니다.

- SWP_NOSIZE 현재 크기를 유지합니다.

- SWP_NOMOVE 현재 위치를 유지합니다.

- SWP_NOZORDER 현재 Z 순서를 유지합니다.

- SWP_NOACTIVATE 창을 활성화하지 않습니다.

창의 확장 스타일을 수정하려면 [수정StyleEx](#modifystyleex)를 호출합니다.

## <a name="colecontrolsitemodifystyleex"></a><a name="modifystyleex"></a>COle컨트롤사이트::수정스타일엑스

컨트롤의 확장 된 스타일을 수정 합니다.

```
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,
    DWORD dwAdd,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*dwRemove*<br/>
현재 창 스타일에서 제거할 확장 스타일입니다.

*dwAdd*<br/>
현재 창 스타일에서 추가할 확장 스타일입니다.

*nFlags*<br/>
창 위치 지정 플래그입니다. 가능한 값 목록은 Windows SDK의 [SetWindowPos](/windows/win32/api/winuser/nf-winuser-setwindowpos) 함수를 참조하십시오.

### <a name="return-value"></a>Return Value

스타일이 변경된 경우 0이 아닌 0입니다.

### <a name="remarks"></a>설명

컨트롤의 스톡 모양 속성이 WS_EX_CLIENTEDGE 설정과 일치하도록 수정됩니다. 다른 모든 확장된 창 스타일이 있는 경우 컨트롤의 창 핸들에 직접 적용됩니다.

컨트롤 사이트 개체의 창 확장 스타일을 수정합니다. 추가하거나 제거할 스타일은 비트별 OR(&#124;) 연산자를 사용하여 결합할 수 있다. 사용 가능한 창 스타일에 대한 자세한 내용은 Windows SDK의 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 함수를 참조하십시오.

*nFlags가* 영하지 `ModifyStyleEx` 않은 경우 Win32 함수를 `SetWindowPos`호출하고 *nFlags를* 다음 네 개의 플래그와 결합하여 창을 다시 그립니다.

- SWP_NOSIZE 현재 크기를 유지합니다.

- SWP_NOMOVE 현재 위치를 유지합니다.

- SWP_NOZORDER 현재 Z 순서를 유지합니다.

- SWP_NOACTIVATE 창을 활성화하지 않습니다.

창의 확장 스타일을 수정하려면 [수정 스타일](#modifystyle)을 호출합니다.

## <a name="colecontrolsitemovewindow"></a><a name="movewindow"></a>콜레컨트롤사이트::이동창

컨트롤의 위치를 변경합니다.

```
virtual void MoveWindow(
    int x,
    int y,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
창 왼쪽의 새 위치입니다.

*Y*<br/>
창 상단의 새 위치입니다.

*nWidth*<br/>
창의 새 너비

*nHeight*<br/>
창의 새 높이입니다.

## <a name="colecontrolsitequickactivate"></a><a name="quickactivate"></a>COleControlSite::빠른 활성화

포함된 컨트롤을 빠르게 활성화합니다.

```
virtual BOOL QuickActivate();
```

### <a name="return-value"></a>Return Value

컨트롤 사이트가 활성화된 경우 비영, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 사용자가 컨트롤의 만들기 프로세스를 재정의하는 경우에만 호출해야 합니다.

및 `IPersist*::Load` `IPersist*::InitNew` 메서드는 빠른 활성화가 발생한 후 호출해야 합니다. 컨트롤은 빠른 활성화 중에 컨테이너의 싱크에 대한 연결을 설정해야 합니다. 그러나 이러한 연결은 호출될 때까지 `IPersist*::Load` 라이브 또는 `IPersist*::InitNew` 호출되지 않습니다.

## <a name="colecontrolsitesafesetproperty"></a><a name="safesetproperty"></a>콜레컨트롤사이트::세이프셋속성

*dwDispID에*의해 지정된 제어 속성을 설정합니다.

```
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
설정할 컨트롤의 인터페이스에 있는 속성 또는 메서드의 `IDispatch` 디스패치 ID를 식별합니다.

*vtProp*<br/>
설정할 속성 유형을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*...*<br/>
*vtProp에*의해 지정된 형식의 단일 매개 변수입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 와 `SetProperty` `SetPropertyV`는 달리 오류가 발생 하는 경우 (예: 존재 하지 않는 속성을 설정 하려고), 예외가 throw 되지 않습니다.

## <a name="colecontrolsitesetdefaultbutton"></a><a name="setdefaultbutton"></a>COle컨트롤사이트::설정기본버튼

컨트롤을 기본 단추로 설정합니다.

```cpp
void SetDefaultButton(BOOL bDefault);
```

### <a name="parameters"></a>매개 변수

*bDefault*<br/>
컨트롤이 기본 단추가 되어야 하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤에는 OLEMISC_ACTSLIKEBUTTON 상태 비트가 설정되어 있어야 합니다.

## <a name="colecontrolsitesetdlgctrlid"></a><a name="setdlgctrlid"></a>콜레 컨트롤 사이트::세트딜트르리드

컨트롤의 대화 상자 항목 식별자 값을 변경 합니다.

```
virtual int SetDlgCtrlID(int nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
새 식별자 값입니다.

### <a name="return-value"></a>Return Value

성공하면 창의 이전 대화 상자 항목 식별자입니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

## <a name="colecontrolsitesetfocus"></a><a name="setfocus"></a>콜레 컨트롤 사이트::설정 포커스

컨트롤에 포커스를 설정합니다.

```
virtual CWnd* SetFocus();
virtual CWnd* SetFocus(LPMSG lpmsg);
```

### <a name="parameters"></a>매개 변수

*lpmsg*<br/>
[MSG 구조에](/windows/win32/api/winuser/ns-winuser-msg)대한 포인터입니다. 이 구조에는 현재 제어 `SetFocus` 사이트에 포함된 컨트롤에 대한 요청을 트리거하는 Windows 메시지가 포함되어 있습니다.

### <a name="return-value"></a>Return Value

이전에 포커스가 있었던 창에 대한 포인터입니다.

## <a name="colecontrolsitesetproperty"></a><a name="setproperty"></a>콜레컨트롤사이트::셋프로퍼티

*dwDispID에*의해 지정된 제어 속성을 설정합니다.

```
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
설정할 컨트롤의 인터페이스에 있는 속성 또는 메서드의 `IDispatch` 디스패치 ID를 식별합니다.

*vtProp*<br/>
설정할 속성 유형을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*...*<br/>
*vtProp에*의해 지정된 형식의 단일 매개 변수입니다.

### <a name="remarks"></a>설명

오류가 `SetProperty` 발생하면 예외가 throw됩니다.

예외 유형은 속성 또는 메서드를 설정하려는 시도의 반환 값에 의해 결정됩니다. 반환 값이 `DISP_E_EXCEPTION`있는 경우 `COleDispatchExcpetion` a가 throw됩니다. 그렇지 `COleException`않으면 .

## <a name="colecontrolsitesetpropertyv"></a><a name="setpropertyv"></a>콜레컨트롤사이트::세트프로퍼티V

*dwDispID에*의해 지정된 제어 속성을 설정합니다.

```
virtual void SetPropertyV(
    DISPID dwDispID,
    VARTYPE vtProp,
    va_list argList);
```

### <a name="parameters"></a>매개 변수

*dwDispID*<br/>
설정할 컨트롤의 인터페이스에 있는 속성 또는 메서드의 `IDispatch` 디스패치 ID를 식별합니다.

*vtProp*<br/>
설정할 속성 유형을 지정합니다. 가능한 값에 대해서는 [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)의 설명 섹션을 참조하세요.

*Arglist*<br/>
인수 목록에 대한 포인터입니다.

### <a name="remarks"></a>설명

호출되는 메서드 또는 속성에 대한 추가 매개 변수는 *arg_list* 매개 변수를 사용하여 전달할 수 있습니다. 오류가 `SetProperty` 발생하면 예외가 throw됩니다.

예외 유형은 속성 또는 메서드를 설정하려는 시도의 반환 값에 의해 결정됩니다. 반환 값이 `DISP_E_EXCEPTION`있는 경우 `COleDispatchExcpetion` a가 throw됩니다. 그렇지 `COleException`않으면 .

## <a name="colecontrolsitesetwindowpos"></a><a name="setwindowpos"></a>콜레 컨트롤 사이트::세트윈도우포스

제어 사이트의 크기, 위치 및 Z 순서를 설정합니다.

```
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,
    int x,
    int y,
    int cx,
    int cy,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*pWnd인더*<br/>
창에 대한 포인터입니다.

*x*<br/>
창 왼쪽의 새 위치입니다.

*Y*<br/>
창 상단의 새 위치입니다.

*Cx*<br/>
창의 새 너비

*Cy*<br/>
창의 새 높이입니다.

*nFlags*<br/>
창 크기 조정 및 위치 지정 플래그를 지정합니다. 가능한 값은 Windows SDK의 [SetWindowPos에](/windows/win32/api/winuser/nf-winuser-setwindowpos) 대한 비고 섹션을 참조하십시오.

### <a name="return-value"></a>Return Value

성공하지 못하면 0이 아닌 0입니다.

## <a name="colecontrolsitesetwindowtext"></a><a name="setwindowtext"></a>콜레 컨트롤 사이트::세트윈도우텍스트

컨트롤 사이트의 텍스트를 설정합니다.

```
virtual void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*lpszString*<br/>
새 제목 또는 컨트롤 텍스트로 사용할 null 종료 된 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 먼저 캡션 스톡 속성을 설정하려고 시도합니다. Caption 스톡 속성이 지원되지 않으면 Text 속성이 대신 설정됩니다.

## <a name="colecontrolsiteshowwindow"></a><a name="showwindow"></a>콜레컨트롤사이트::쇼윈도우

창의 표시 상태를 설정합니다.

```
virtual BOOL ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>매개 변수

*nCmdShow*<br/>
제어 사이트를 표시하는 방법을 지정합니다. 다음 값 중 하나여야 합니다.

- SW_HIDE 이 창을 숨기고 활성화를 다른 창으로 전달합니다.

- SW_MINIMIZE 창을 최소화하고 시스템 목록의 최상위 창을 활성화합니다.

- SW_RESTORE 창을 활성화하고 표시합니다. 창이 최소화되거나 최대화되면 Windows는 창을 원래 크기와 위치로 복원합니다.

- SW_SHOW 창을 활성화하고 현재 크기와 위치에 표시합니다.

- SW_SHOWMAXIMIZED 창을 활성화하고 최대화 된 창으로 표시합니다.

- SW_SHOWMINIMIZED 창을 활성화하고 아이콘으로 표시합니다.

- SW_SHOWMINNOACTIVE 창을 아이콘으로 표시합니다. 현재 활성 상태인 창은 활성 상태로 유지됩니다.

- SW_SHOWNA 창을 현재 상태로 표시합니다. 현재 활성 상태인 창은 활성 상태로 유지됩니다.

- SW_SHOWNOACTIVATE 창을 가장 최근 크기와 위치로 표시합니다. 현재 활성 상태인 창은 활성 상태로 유지됩니다.

- SW_SHOWNORMAL 활성화하고 창을 표시합니다. 창이 최소화되거나 최대화되면 Windows는 창을 원래 크기와 위치로 복원합니다.

### <a name="return-value"></a>Return Value

창이 이전에 표시되면 0이 아닙니다. 창이 이전에 숨겨져 있는 경우 0입니다.

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레컨트롤컨테이너 클래스](../../mfc/reference/colecontrolcontainer-class.md)
