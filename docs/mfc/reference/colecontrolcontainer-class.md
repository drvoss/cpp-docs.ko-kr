---
title: 콜레컨트롤컨테이너 클래스
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: 83171e012db7ef2cce459d35cfc689746afd062c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749020"
---
# <a name="colecontrolcontainer-class"></a>콜레컨트롤컨테이너 클래스

ActiveX 컨트롤의 컨트롤 컨테이너 역할을 합니다.

## <a name="syntax"></a>구문

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[COleControl 컨테이너::COleControl컨테이너](#colecontrolcontainer)|`COleControlContainer` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COleControl 컨테이너::연결 제어 사이트](#attachcontrolsite)|컨테이너에서 호스팅하는 제어 사이트를 만듭니다.|
|[COleControl 컨테이너::방송 앰비언트속성변경](#broadcastambientpropertychange)|주변 속성이 변경되었음을 모든 호스팅컨트롤에 알립니다.|
|[COleControl 컨테이너::체크DlgButton](#checkdlgbutton)|지정된 단추 컨트롤을 수정합니다.|
|[콜레 컨트롤 컨테이너::체크라디오 버튼](#checkradiobutton)|그룹의 지정된 라디오 단추를 선택합니다.|
|[COleControl컨테이너::만들기제어](#createcontrol)|호스팅된 ActiveX 컨트롤을 만듭니다.|
|[COleControl컨테이너::창조올레폰트](#createolefont)|OLE 글꼴을 만듭니다.|
|[COleControl 컨테이너::찾기항목](#finditem)|지정된 컨트롤의 사용자 지정 사이트를 반환합니다.|
|[COleControl 컨테이너::동결모든 이벤트](#freezeallevents)|컨트롤 사이트에서 이벤트를 수락하는지 여부를 확인합니다.|
|[COleControl 컨테이너::GetAmbientProp](#getambientprop)|지정된 주변 속성을 검색합니다.|
|[COleControl 컨테이너::GetDlg항목](#getdlgitem)|지정된 대화 상자 컨트롤을 검색합니다.|
|[COleControl 컨테이너::GetDlgItemInt](#getdlgitemint)|지정된 대화 상자 컨트롤의 값을 검색합니다.|
|[COleControl 컨테이너::GetDlg항목텍스트](#getdlgitemtext)|지정된 대화 상자 컨트롤의 캡션을 검색합니다.|
|[COleControl컨테이너::핸들셋포커스](#handlesetfocus)|컨테이너가 WM_SETFOCUS 메시지를 처리하는지 여부를 결정합니다.|
|[COleControl 컨테이너::핸들윈도우리스메시지](#handlewindowlessmessage)|창 없는 컨트롤에 전송 된 메시지를 처리 합니다.|
|[COleControl 컨테이너::IsDlgButton 확인](#isdlgbuttonchecked)|지정된 단추의 상태를 결정합니다.|
|[콜레컨트롤 컨테이너::온페인트](#onpaint)|컨테이너의 일부를 다시 그리기 위해 호출됩니다.|
|[콜레컨트롤 컨테이너::온UI활성화](#onuiactivate)|컨트롤이 활성화될 때 호출됩니다.|
|[콜레컨트롤 컨테이너::온UI비활성화](#onuideactivate)|컨트롤이 비활성화될 때 호출됩니다.|
|[COleControl컨테이너::스크롤자식](#scrollchildren)|자식 창에서 스크롤 메시지를 받을 때 프레임워크에서 호출됩니다.|
|[COleControl 컨테이너::SendDlg항목 메시지](#senddlgitemmessage)|지정된 컨트롤에 메시지를 보냅니다.|
|[콜레컨트롤 컨테이너::세트들항목인트](#setdlgitemint)|지정된 컨트롤의 값을 설정합니다.|
|[콜레 컨트롤 컨테이너::SetDlg항목텍스트](#setdlgitemtext)|지정된 컨트롤의 텍스트를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[콜레컨트롤 컨테이너::m_crBack](#m_crback)|컨테이너의 배경색입니다.|
|[콜레컨트롤 컨테이너::m_crFore](#m_crfore)|컨테이너의 전경 색상입니다.|
|[COleControl 컨테이너::m_listSitesOrWnds](#m_listsitesorwnds)|지원되는 제어 사이트의 목록입니다.|
|[콜레컨트롤 컨테이너::m_nWindowlessControls](#m_nwindowlesscontrols)|호스트된 창 없는 컨트롤의 수입니다.|
|[콜레컨트롤 컨테이너::m_pOleFont](#m_polefont)|사용자 지정 제어 사이트의 OLE 글꼴에 대한 포인터입니다.|
|[콜레컨트롤 컨테이너::m_pSiteCapture](#m_psitecapture)|캡처 제어 사이트에 대한 포인터입니다.|
|[콜레컨트롤 컨테이너::m_pSiteFocus](#m_psitefocus)|현재 입력 포커스가 있는 컨트롤에 대한 포인터입니다.|
|[콜레컨트롤 컨테이너::m_pSiteUIActive](#m_psiteuiactive)|현재 활성화된 위치에 있는 컨트롤에 대한 포인터입니다.|
|[콜레컨트롤 컨테이너::m_pWnd](#m_pwnd)|컨트롤 컨테이너를 구현하는 창에 대한 포인터입니다.|
|[콜레컨트롤 컨테이너::m_siteMap](#m_sitemap)|사이트 맵입니다.|

## <a name="remarks"></a>설명

이 작업은 하나 이상의 ActiveX 제어 사이트(구현)에 `COleControlSite`대한 지원을 제공하여 수행됩니다. `COleControlContainer`[IOleInPlaceFrame](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceframe) 및 [IOleContainer](/windows/win32/api/oleidl/nn-oleidl-iolecontainer) 인터페이스를 완벽하게 구현하여 포함된 ActiveX 컨트롤이 내부 항목으로서의 자격을 충족할 수 있도록 합니다.

일반적으로 이 클래스는 하나 `COccManager` 이상의 `COleControlSite` ActiveX 컨트롤에 대한 사용자 지정 사이트와 함께 사용자 지정 ActiveX 컨트롤 컨테이너를 구현하고 구현하는 데 사용됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>요구 사항

**헤더:** afxocc.h

## <a name="colecontrolcontainerattachcontrolsite"></a><a name="attachcontrolsite"></a>COleControl 컨테이너::연결 제어 사이트

컨트롤 사이트를 만들고 연결하기 위해 프레임워크에서 호출합니다.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다.

*nIDC*<br/>
연결할 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

이 프로세스를 사용자 지정하려는 경우 이 함수를 재정의합니다.

> [!NOTE]
> MFC 라이브러리에 정적으로 연결하는 경우 이 함수의 첫 번째 형식을 사용합니다. MFC 라이브러리에 동적으로 연결하는 경우 두 번째 양식을 사용합니다.

## <a name="colecontrolcontainerbroadcastambientpropertychange"></a><a name="broadcastambientpropertychange"></a>COleControl 컨테이너::방송 앰비언트속성변경

주변 속성이 변경되었음을 모든 호스팅컨트롤에 알립니다.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
변경되는 주변 속성의 디스패치 ID입니다.

### <a name="remarks"></a>설명

앰비언트 속성이 값을 변경했을 때 이 함수는 프레임워크에서 호출됩니다. 이 함수를 재정의하여 이 동작을 사용자 지정합니다.

## <a name="colecontrolcontainercheckdlgbutton"></a><a name="checkdlgbutton"></a>COleControl 컨테이너::체크DlgButton

단추의 현재 상태를 수정합니다.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>매개 변수

*니드 버튼*<br/>
수정할 단추의 ID입니다.

*nCheck*<br/>
단추의 상태를 지정합니다. 다음 중 하나일 수 있습니다.

- BST_CHECKED 단추 상태를 선택합니다.

- BST_INDETERMINATE 단추 상태를 회색으로 설정하여 확정되지 않은 상태를 나타냅니다. 단추에 BS_3STATE 또는 BS_AUTO3STATE 스타일이 있는 경우에만 이 값을 사용합니다.

- BST_UNCHECKED 단추 상태를 지울 수 있도록 설정합니다.

## <a name="colecontrolcontainercheckradiobutton"></a><a name="checkradiobutton"></a>콜레 컨트롤 컨테이너::체크라디오 버튼

그룹에서 지정된 라디오 단추를 선택하고 그룹의 나머지 단추를 지웁습니다.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>매개 변수

*니드퍼스트버튼*<br/>
그룹의 첫 번째 라디오 단추의 식별자를 지정합니다.

*니드라스트 버튼*<br/>
그룹의 마지막 라디오 단추의 식별자를 지정합니다.

*니드 체크 버튼*<br/>
확인할 라디오 단추의 식별자를 지정합니다.

## <a name="colecontrolcontainercolecontrolcontainer"></a><a name="colecontrolcontainer"></a>COleControl 컨테이너::COleControl컨테이너

`COleControlContainer` 개체를 생성합니다.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤 컨테이너의 상위 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

개체가 성공적으로 만들어지면 `AttachControlSite`에 대한 호출이 있는 사용자 지정 제어 사이트를 추가합니다.

## <a name="colecontrolcontainercreatecontrol"></a><a name="createcontrol"></a>COleControl컨테이너::만들기제어

지정된 `COleControlSite` 개체에서 호스팅하는 ActiveX 컨트롤을 만듭니다.

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
컨트롤을 나타내는 창 개체에 대한 포인터입니다.

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszWindowName*<br/>
컨트롤에 표시할 텍스트에 대한 포인터입니다. 컨트롤의 캡션 또는 텍스트 속성(있는 경우)의 값을 설정합니다. NULL이면 컨트롤의 캡션 또는 텍스트 속성이 변경되지 않습니다.

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

*ppNewSite*<br/>
생성되는 컨트롤을 호스트할 기존 제어 사이트에 대한 포인터입니다. 기본값은 NULL로 새 컨트롤 사이트가 자동으로 만들어지고 새 컨트롤에 첨부됨을 나타냅니다.

*Ppt*<br/>
컨트롤의 `POINT` 왼쪽 위 모서리를 포함하는 구조체에 대한 포인터입니다. 컨트롤의 크기는 *psize*값에 의해 결정됩니다. *ppt* 및 *psize* 값은 컨트롤의 크기와 위치를 지정하는 선택적 방법입니다.

*크기 조정*<br/>
컨트롤의 크기를 `SIZE` 포함하는 구조에 대한 포인터입니다. 왼쪽 위 모서리는 *ppt*값에 의해 결정됩니다. *ppt* 및 *psize* 값은 컨트롤의 크기와 위치를 지정하는 선택적 방법입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows *dwStyle* 플래그의 하위 집합만 `CreateControl`다음에서 지원됩니다.

- WS_VISIBLE 처음에 표시되는 창을 만듭니다. 일반 창과 같이 컨트롤을 즉시 표시하려면 필수입니다.

- WS_DISABLED 처음에 사용하지 않도록 설정한 창을 만듭니다. 비활성화된 창은 사용자로부터 입력을 받을 수 없습니다. 컨트롤에 Enabled 속성이 있는 경우 설정할 수 있습니다.

- WS_BORDER 줄 테두리가 있는 창을 만듭니다. 컨트롤에 BorderStyle 속성이 있는 경우 설정할 수 있습니다.

- WS_GROUP 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다. 사용자는 방향 키를 사용하여 그룹의 한 컨트롤에서 다음 컨트롤로 키보드 포커스를 변경할 수 있습니다. 첫 번째 컨트롤 이후에 WS_GROUP 스타일로 정의된 모든 컨트롤은 동일한 그룹에 속합니다. WS_GROUP 스타일로 다음 컨트롤은 그룹을 종료하고 다음 그룹을 시작합니다.

- WS_TABSTOP 사용자가 TAB 키를 누를 때 키보드 포커스를 받을 수 있는 컨트롤을 지정합니다. TAB 키를 누르면 키보드 초점이 WS_TABSTOP 스타일의 다음 컨트롤로 변경됩니다.

두 번째 오버로드를 사용하여 기본 크기의 컨트롤을 만듭니다.

## <a name="colecontrolcontainercreateolefont"></a><a name="createolefont"></a>COleControl컨테이너::창조올레폰트

OLE 글꼴을 만듭니다.

```cpp
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤 컨테이너에서 사용할 글꼴에 대한 포인터입니다.

## <a name="colecontrolcontainerfinditem"></a><a name="finditem"></a>COleControl 컨테이너::찾기항목

지정된 항목을 호스트하는 사용자 지정 사이트를 찾습니다.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
찾을 항목의 식별자입니다.

### <a name="return-value"></a>Return Value

지정된 항목의 사용자 지정 사이트에 대한 포인터입니다.

## <a name="colecontrolcontainerfreezeallevents"></a><a name="freezeallevents"></a>COleControl 컨테이너::동결모든 이벤트

컨테이너가 연결된 제어 사이트의 이벤트를 무시하거나 수락할지 여부를 결정합니다.

```cpp
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>매개 변수

*bFreeze*<br/>
이벤트가 처리될 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

> [!NOTE]
> 컨트롤 컨테이너에서 요청하는 경우 이벤트 발생을 중지할 필요가 없습니다. 계속 실행될 수 있지만 이후의 모든 이벤트는 컨트롤 컨테이너에서 무시됩니다.

## <a name="colecontrolcontainergetambientprop"></a><a name="getambientprop"></a>COleControl 컨테이너::GetAmbientProp

지정된 주변 속성의 값을 검색합니다.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>매개 변수

*p사이트*<br/>
앰비언트 속성이 검색되는 제어 사이트에 대한 포인터입니다.

*디스피드 (것)들*<br/>
원하는 주변 속성의 디스패치 ID입니다.

*pVar결과*<br/>
앰비언트 속성의 값에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="colecontrolcontainergetdlgitem"></a><a name="getdlgitem"></a>COleControl 컨테이너::GetDlg항목

대화 상자 또는 다른 창에서 지정된 컨트롤 또는 자식 창에 대한 포인터를 검색합니다.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
검색할 대화 상자 항목의 식별자입니다.

*phwnd*<br/>
지정된 대화 상자 항목의 창 개체의 핸들에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

대화 상자 항목의 창에 대한 포인터입니다.

## <a name="colecontrolcontainergetdlgitemint"></a><a name="getdlgitemint"></a>COleControl 컨테이너::GetDlgItemInt

지정된 컨트롤의 번역된 텍스트 값을 검색합니다.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpTrans*<br/>
함수 성공/실패 값을 받는 부울 변수에 대한 포인터(TRUE는 성공을 나타내고 FALSE는 실패를 나타냅니다).

*b 서명됨*<br/>
함수가 처음에 마이너스 기호에 대한 텍스트를 검사하고 서명된 정수 값을 찾을 경우 반환할지 여부를 지정합니다. *bSigned* 매개 변수가 TRUE인 경우 검색할 값이 서명된 정수 값임을 지정하면 반환 값을 **int** 유형으로 캐스팅합니다. 확장 오류 정보를 얻으려면 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)를 호출합니다.

### <a name="return-value"></a>Return Value

성공하면 *lpTrans가* 가리키는 변수가 TRUE로 설정되고 반환 값은 컨트롤 텍스트의 변환된 값입니다.

함수가 실패하면 *lpTrans가* 가리키는 변수가 FALSE로 설정되고 반환 값이 0입니다. 0은 가능한 변환 된 값이므로 반환 값 0 자체는 실패를 나타내지 않습니다.

*lpTrans가* NULL이면 함수는 성공 또는 실패에 대한 정보를 반환하지 않습니다.

### <a name="remarks"></a>설명

이 함수는 텍스트의 시작 부분에 여분의 공백을 제거한 다음 소수 자릿수를 변환하여 검색된 텍스트를 변환합니다. 함수는 텍스트의 끝에 도달하거나 숫자가 없는 문자가 발생하면 번역을 중지합니다.

이 함수는 변환된 값이 INT_MAX(서명된 번호의 경우) 또는 UINT_MAX(서명되지 않은 숫자의 경우)보다 큰 경우 0을 반환합니다.

## <a name="colecontrolcontainergetdlgitemtext"></a><a name="getdlgitemtext"></a>COleControl 컨테이너::GetDlg항목텍스트

지정된 컨트롤의 텍스트를 검색합니다.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpStr*<br/>
컨트롤의 텍스트에 대한 포인터입니다.

*n맥스카운트*<br/>
*lpStr로*가리키는 버퍼에 복사할 문자열의 최대 길이(문자)를 지정합니다. 문자열의 길이가 제한을 초과하면 문자열이 잘립니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 null 문자 종료를 포함하지 않고 버퍼에 복사된 문자 수를 지정합니다.

함수가 실패하면 반환 값은 0입니다. 확장 오류 정보를 얻으려면 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)를 호출합니다.

## <a name="colecontrolcontainerhandlesetfocus"></a><a name="handlesetfocus"></a>COleControl컨테이너::핸들셋포커스

컨테이너가 WM_SETFOCUS 메시지를 처리하는지 여부를 결정합니다.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>Return Value

컨테이너가 WM_SETFOCUS 메시지를 처리하는 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="colecontrolcontainerhandlewindowlessmessage"></a><a name="handlewindowlessmessage"></a>COleControl 컨테이너::핸들윈도우리스메시지

창 없는 컨트롤에 대 한 창 메시지를 처리 합니다.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>매개 변수

*message*<br/>
Windows에서 제공하는 창 메시지의 식별자입니다.

*wParam*<br/>
메시지의 매개 변수; 윈도우에서 제공하는. 추가 메시지 관련 정보를 지정합니다. 이 매개 변수의 내용은 *메시지* 매개 변수의 값에 따라 다릅니다.

*lParam*<br/>
메시지의 매개 변수; 윈도우에서 제공하는. 추가 메시지 관련 정보를 지정합니다. 이 매개 변수의 내용은 *메시지* 매개 변수의 값에 따라 다릅니다.

*plResult*<br/>
윈도우 결과 코드입니다. 메시지 처리 결과를 지정하고 보낸 메시지에 따라 다릅니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 창 없는 컨트롤 메시지의 처리를 사용자 지정합니다.

## <a name="colecontrolcontainerisdlgbuttonchecked"></a><a name="isdlgbuttonchecked"></a>COleControl 컨테이너::IsDlgButton 확인

지정된 단추의 상태를 결정합니다.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>매개 변수

*니드 버튼*<br/>
단추 컨트롤의 식별자입니다.

### <a name="return-value"></a>Return Value

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON 또는 BS_3STATE 스타일로 만든 단추에서 반환 값입니다. 다음 중 하나일 수 있습니다.

- BST_CHECKED 버튼이 선택됩니다.

- BST_INDETERMINATE 버튼은 회색으로 표시되어 확정되지 않은 상태를 나타냅니다(단추에 BS_3STATE 또는 BS_AUTO3STATE 스타일이 있는 경우에만 적용).

- BST_UNCHECKED 버튼이 지워집니다.

### <a name="remarks"></a>설명

단추를 세 가지 상태 컨트롤인 경우 멤버 함수는 흐리게 지정, 검사 또는 둘 중 어느 쪽인지 여부를 결정합니다.

## <a name="colecontrolcontainerm_crback"></a><a name="m_crback"></a>콜레컨트롤 컨테이너::m_crBack

컨테이너의 배경색입니다.

```
COLORREF m_crBack;
```

## <a name="colecontrolcontainerm_crfore"></a><a name="m_crfore"></a>콜레컨트롤 컨테이너::m_crFore

컨테이너의 전경 색상입니다.

```
COLORREF m_crFore;
```

## <a name="colecontrolcontainerm_listsitesorwnds"></a><a name="m_listsitesorwnds"></a>COleControl 컨테이너::m_listSitesOrWnds

컨테이너에서 호스트하는 제어 사이트의 목록입니다.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

## <a name="colecontrolcontainerm_nwindowlesscontrols"></a><a name="m_nwindowlesscontrols"></a>콜레컨트롤 컨테이너::m_nWindowlessControls

컨트롤 컨테이너에서 호스트하는 창 없는 컨트롤의 수입니다.

```
int m_nWindowlessControls;
```

## <a name="colecontrolcontainerm_polefont"></a><a name="m_polefont"></a>콜레컨트롤 컨테이너::m_pOleFont

사용자 지정 제어 사이트의 OLE 글꼴에 대한 포인터입니다.

```
LPFONTDISP m_pOleFont;
```

## <a name="colecontrolcontainerm_psitecapture"></a><a name="m_psitecapture"></a>콜레컨트롤 컨테이너::m_pSiteCapture

캡처 제어 사이트에 대한 포인터입니다.

```
COleControlSite* m_pSiteCapture;
```

## <a name="colecontrolcontainerm_psitefocus"></a><a name="m_psitefocus"></a>콜레컨트롤 컨테이너::m_pSiteFocus

현재 입력 포커스가 있는 컨트롤 사이트에 대한 포인터입니다.

```
COleControlSite* m_pSiteFocus;
```

## <a name="colecontrolcontainerm_psiteuiactive"></a><a name="m_psiteuiactive"></a>콜레컨트롤 컨테이너::m_pSiteUIActive

활성화된 위치에 있는 컨트롤 사이트에 대한 포인터입니다.

```
COleControlSite* m_pSiteUIActive;
```

## <a name="colecontrolcontainerm_pwnd"></a><a name="m_pwnd"></a>콜레컨트롤 컨테이너::m_pWnd

컨테이너와 연결된 창 개체에 대한 포인터입니다.

```
CWnd* m_pWnd;
```

## <a name="colecontrolcontainerm_sitemap"></a><a name="m_sitemap"></a>콜레컨트롤 컨테이너::m_siteMap

사이트 맵입니다.

```
CMapPtrToPtr m_siteMap;
```

## <a name="colecontrolcontaineronpaint"></a><a name="onpaint"></a>콜레컨트롤 컨테이너::온페인트

WM_PAINT 요청을 처리하기 위해 프레임워크에서 호출됩니다.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨테이너에서 사용하는 장치 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

메시지가 처리된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 재정의하여 페인팅 프로세스를 사용자 지정합니다.

## <a name="colecontrolcontaineronuiactivate"></a><a name="onuiactivate"></a>콜레컨트롤 컨테이너::온UI활성화

*pSite가*가리키는 제어 사이트가 현재 활성화될 때 프레임워크에서 호출됩니다.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>매개 변수

*p사이트*<br/>
위치에 활성화될 제어 사이트에 대한 포인터입니다.

### <a name="remarks"></a>설명

내부 활성화는 컨테이너의 주 메뉴가 내부 복합 메뉴로 대체된다는 것을 의미합니다.

## <a name="colecontrolcontaineronuideactivate"></a><a name="onuideactivate"></a>콜레컨트롤 컨테이너::온UI비활성화

*pSite로*가리키는 제어 사이트가 비활성화될 때 프레임워크에서 호출됩니다.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>매개 변수

*p사이트*<br/>
비활성화될 제어 사이트에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 알림이 수신되면 컨테이너는 사용자 인터페이스를 다시 설치하고 초점을 맞춰야 합니다.

## <a name="colecontrolcontainerscrollchildren"></a><a name="scrollchildren"></a>COleControl컨테이너::스크롤자식

자식 창에서 스크롤 메시지를 받을 때 프레임워크에서 호출됩니다.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>매개 변수

*Dx*<br/>
x축을 따라 스크롤하는 양(픽셀 단위)입니다.

*Dy*<br/>
y축을 따라 스크롤하는 양(픽셀 단위)입니다.

## <a name="colecontrolcontainersenddlgitemmessage"></a><a name="senddlgitemmessage"></a>COleControl 컨테이너::SendDlg항목 메시지

지정된 컨트롤에 메시지를 보냅니다.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
메시지를 수신하는 컨트롤의 식별자를 지정합니다.

*message*<br/>
보낼 메시지를 지정합니다.

*wParam*<br/>
추가 메시지 관련 정보를 지정합니다.

*lParam*<br/>
추가 메시지 관련 정보를 지정합니다.

## <a name="colecontrolcontainersetdlgitemint"></a><a name="setdlgitemint"></a>콜레컨트롤 컨테이너::세트들항목인트

대화 상자에서 컨트롤의 텍스트를 지정된 정수 값의 문자열 표현으로 설정합니다.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*n값*<br/>
표시할 정수 값입니다.

*b 서명됨*<br/>
*nValue* 매개 변수가 서명되었는지 서명되지 않았는지 또는 서명되지 않았는지 지정합니다. 이 매개 변수가 TRUE이면 *nValue가* 서명됩니다. 이 매개 변수가 TRUE이고 *nValue가* 0보다 작은 경우 문자열의 첫 번째 숫자 앞에 빼기 기호가 배치됩니다. 이 매개 변수가 FALSE이면 *nValue가* 서명되지 않습니다.

## <a name="colecontrolcontainersetdlgitemtext"></a><a name="setdlgitemtext"></a>콜레 컨트롤 컨테이너::SetDlg항목텍스트

*lpszString에*포함된 텍스트를 사용하여 지정된 컨트롤의 텍스트를 설정합니다.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpszString*<br/>
컨트롤의 텍스트에 대한 포인터입니다.

## <a name="see-also"></a>참조

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[콜레컨트롤사이트 클래스](../../mfc/reference/colecontrolsite-class.md)<br/>
[코크매니저 클래스](../../mfc/reference/coccmanager-class.md)
