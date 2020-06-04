---
title: 크파네디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: ad1225034cc5eca8ca53b042ebe3b55db4a2cf09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364133"
---
# <a name="cpanedialog-class"></a>크파네디아로그 클래스

클래스는 `CPaneDialog` 모데리스, 도킹 가능한 대화 상자를 지원합니다.

## <a name="syntax"></a>구문

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|기본 생성자입니다.|
|`CPaneDialog::~CPaneDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPaneDialog::만들기](#create)|도킹 가능한 대화 상자를 만들고 `CPaneDialog` 개체에 연결합니다.|
|`CPaneDialog::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CPaneDialog::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CPaneDialog::핸들InItDialog](#handleinitdialog)|[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) 메시지를 처리합니다. (재정의.) `CBasePane::HandleInitDialog`|
|`CPaneDialog::OnEraseBkgnd`|[WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) 메시지를 처리합니다. [(CWnd 재정의::OnEraseBkgnd.)](../../mfc/reference/cwnd-class.md#onerasebkgnd)|
|`CPaneDialog::OnLButtonDblClk`|[WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk) 메시지를 처리합니다. [(CWnd 재정의::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|[WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) 메시지를 처리합니다. [(CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)재정의.)|
|`CPaneDialog::OnUpdateCmdUI`|대화 상자 창을 업데이트하는 프레임워크에서 호출합니다. [(CDockablePane 재정의::OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|[WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) 메시지를 처리합니다. [(CWnd::OnWindowPos변경.)](../../mfc/reference/cwnd-class.md#onwindowposchanging)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE 제어 컨테이너인 대화 상자에 대한 템플릿을 지정합니다.|

## <a name="remarks"></a>설명

두 `CPaneDialog` 단계로 개체를 생성합니다. 먼저 코드에서 개체를 생성합니다. 둘째, [CPaneDialog::Create를](#create)호출합니다. 유효한 리소스 템플릿 이름 또는 템플릿 ID를 지정하고 포인터를 부모 창에 전달해야 합니다. 그렇지 않으면 생성 프로세스가 실패합니다. 대화 상자는 WS_CHILD 및 WS_VISIBLE 스타일을 지정해야 합니다. WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 스타일을 지정하는 것이 좋습니다. 자세한 내용은 [창 스타일](styles-used-by-mfc.md#window-styles)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[크파네디아로그](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpanedialog.h

## <a name="cpanedialogcreate"></a><a name="create"></a>CPaneDialog::만들기

도킹 대화 상자를 만들고 `CPaneDialog` 개체에 연결합니다.

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszWindowName*<br/>
【인】 도킹 대화 상자의 이름입니다.

*pParentWnd*<br/>
【인】 상위 창을 가리킵니다.

*bHas그리퍼*<br/>
【인】 TRUE 캡션 (그리퍼)와 도킹 대화 상자를 만들려면; 그렇지 않으면 false입니다.

*lpszTemplateName*<br/>
【인】 리소스 대화 상자 템플릿의 이름입니다.

*nStyle*<br/>
【인】 윈도우 스타일입니다.

*nID*<br/>
【인】 컨트롤 ID입니다.

*nIDTemplate*<br/>
【인】 대화 상자 템플릿의 리소스 ID입니다.

*드탭스타일*<br/>
【인】 사용자가 다른 컨트롤 창을 이 컨트롤 창의 캡션으로 드래그할 때 발생하는 탭된 창의 스타일입니다. 기본값은 AFX_CBRS_REGULAR_TABS. 자세한 내용은 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) 메서드의 비고 섹션을 참조하십시오.

*dw컨트롤바스타일*<br/>
【인】 추가 스타일 특성입니다. 기본값은 AFX_DEFAULT_DOCKING_PANE_STYLE. 자세한 내용은 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) 메서드의 비고 섹션을 참조하십시오.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 `Create` `CPaneDialog` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 예제는 [창 크기 설정 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

## <a name="cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>CPaneDialog::핸들InItDialog

[WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) 메시지를 처리합니다.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*wParam*<br/>
【인】 기본 키보드 포커스를 수신할 컨트롤을 처리합니다.

*lParam*<br/>
【인】 추가 초기화 데이터를 지정합니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다. 또한 TRUE는 키보드 포커스를 *wParam* 매개 변수에 의해 지정된 컨트롤로 설정합니다. FALSE는 기본 키보드 포커스를 설정하는 것을 방지합니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 사용하여 컨트롤과 대화 상자의 모양을 초기화합니다. 프레임워크는 대화 상자를 표시하기 전에 이 메서드를 호출합니다.

## <a name="cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo

OLE 제어 컨테이너인 대화 상자에 대한 템플릿을 지정합니다.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
【인】 대화 상자 개체를 만드는 데 사용되는 대화 상자 템플릿에 대한 포인터입니다. 이 매개 변수의 값은 이후에 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) 메서드로 전달됩니다.

### <a name="return-value"></a>Return Value

항상 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 OLE 제어 사이트 및 ActiveX 컨트롤을 관리하는 [COccManager](../../mfc/reference/coccmanager-class.md) 클래스를 지원합니다. _AFX_OCC_DIALOG_INFO 구조는 afxocc.h 헤더 파일에 정의되어 있습니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)
