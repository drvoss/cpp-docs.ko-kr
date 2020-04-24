---
title: CFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
helpviewer_keywords:
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
ms.openlocfilehash: 3bb93420b39be5d6fb9a6691cec8300fdccb0e73
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754982"
---
# <a name="cframewnd-class"></a>CFrameWnd 클래스

창 관리를 위한 멤버와 함께 겹쳐진 Windows SDI(단일 문서 인터페이스) 또는 팝업 프레임 창의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CFrameWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFrameWnd::CFrameWnd](#cframewnd)|`CFrameWnd` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFrameWnd::활성화 프레임](#activateframe)|사용자가 프레임을 표시하고 사용할 수 있도록 합니다.|
|[CFrameWnd::BeginModalState](#beginmodalstate)|프레임 창을 모달로 설정합니다.|
|[CFrameWnd::Create](#create)|개체와 연결된 Windows 프레임 창을 만들고 `CFrameWnd` 초기화하려면 호출합니다.|
|[CFrameWnd::CreateView](#createview)|`CView`에서 파생되지 않은 프레임 내에서 뷰를 만듭니다.|
|[CFrameWnd::DockControlBar](#dockcontrolbar)|컨트롤 바를 도킹합니다.|
|[CFrameWnd::인에이블도킹](#enabledocking)|컨트롤 막대를 도킹할 수 있습니다.|
|[CFrameWnd::엔드모달 스테이트](#endmodalstate)|프레임 창의 모달 상태를 종료합니다. `BeginModalState`에서 모든 창을 사용하지 않도록 설정합니다.|
|[CFrameWnd::플로트 컨트롤바](#floatcontrolbar)|컨트롤 바를 부동합니다.|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|활성 개체를 반환합니다. `CDocument`|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|활성 개체를 반환합니다. `CFrameWnd`|
|[CFrameWnd::GetActiveView](#getactiveview)|활성 개체를 반환합니다. `CView`|
|[CFrameWnd::GetControlBar](#getcontrolbar)|컨트롤 막대를 검색합니다.|
|[CFrameWnd::GetDockState](#getdockstate)|프레임 창의 도크 상태를 검색합니다.|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 검색합니다.|
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|현재 MFC 응용 프로그램에서 메뉴의 기본 동작이 숨김또는 표시되는지 여부를 나타냅니다.|
|[CFrameWnd::GetMessageBar](#getmessagebar)|프레임 창에 속한 상태 표시줄에 대한 포인터를 반환합니다.|
|[CFrameWnd::GetMessageString](#getmessagestring)|명령 ID에 해당하는 메시지를 검색합니다.|
|[CFrameWnd::GetTitle](#gettitle)|관련 컨트롤 막대의 제목을 검색합니다.|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|프레임 `OnInitialUpdate` 창의 모든 뷰에 속하는 멤버 함수를 호출합니다.|
|[CFrameWnd::InModalState](#inmodalstate)|프레임 창이 모달 상태에 있는지 여부를 나타내는 값을 반환합니다.|
|[CFrameWnd::IsTracking](#istracking)|스플리터 막대가 현재 이동중인지 여부를 결정합니다.|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|가속기 테이블을 로드하려면 호출합니다.|
|[CFrameWnd::LoadBarState](#loadbarstate)|컨트롤 막대 설정을 복원하려면 호출합니다.|
|[CFrameWnd::LoadFrame](#loadframe)|리소스 정보에서 프레임 창을 동적으로 만들려면 호출합니다.|
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|프레임 창에서 테두리 공간을 협상합니다.|
|[CFrameWnd::OnBarCheck](#onbarcheck)|지정된 컨트롤 막대에서 작업이 수행될 때마다 호출됩니다.|
|[CFrameWnd::OnContextHelp](#oncontexthelp)|시프트+F1 인플레이스 항목에 대한 도움말을 처리합니다.|
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|인쇄 미리 보기 모드에서 응용 프로그램의 기본 프레임 창을 입력 및 출력으로 설정합니다.|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|연결된 메뉴가 업데이트될 때 프레임워크에서 호출됩니다.|
|[CFrameWnd::RecalcLayout](#recalclayout)|개체의 컨트롤 막대를 `CFrameWnd` 재배치합니다.|
|[CFrameWnd::SaveBarState](#savebarstate)|호출하여 컨트롤 막대 설정을 저장합니다.|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|지정된 뷰를 [조회]에 대한 활성 보기로 지정합니다.|
|[CFrameWnd::SetActiveView](#setactiveview)|활성 개체를 설정합니다. `CView`|
|[CFrameWnd::SetDockState](#setdockstate)|호출하여 기본 창에서 프레임 창을 도킹합니다.|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|현재 MFC 응용 프로그램의 메뉴 표시 상태를 숨김 또는 표시로 설정합니다.|
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|현재 MFC 응용 프로그램에서 메뉴의 기본 동작을 숨김 또는 표시하도록 설정합니다.|
|[CFrameWnd::SetMessageText](#setmessagetext)|표준 상태 표시줄의 텍스트를 설정합니다.|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|작업 표시줄에 표시되는 Windows 7 진행률 표시줄의 현재 위치를 설정합니다.|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|작업 표시줄에 표시되는 Windows 7 진행률 표시줄의 범위를 설정합니다.|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|작업 표시줄 단추에 표시되는 진행률 표시기의 유형 및 상태를 설정합니다.|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|오버로드되었습니다. 작업 표시줄 단추에 오버레이를 적용하여 응용 프로그램 상태 또는 사용자에게 알림을 나타냅니다.|
|[CFrameWnd::SetTitle](#settitle)|관련 컨트롤 막대의 제목을 설정합니다.|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|호출하여 컨트롤 막대를 표시합니다.|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|개체의 하위 항목인 모든 `CFrameWnd` 창을 표시합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|프레임에 대한 클라이언트 창을 만듭니다.|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|현재 MFC 응용 프로그램의 메뉴가 숨김 앞에 호출됩니다.|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|현재 MFC 응용 프로그램의 메뉴가 표시되기 전에 호출됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|메뉴 항목에 대한 자동 사용 및 비활성화 기능을 제어합니다.|
|[CFrameWnd::rectDefault](#rectdefault)|Windows에서 `CRect` 창의 초기 크기와 `CFrameWnd` 위치를 선택할 수 있도록 개체를 만들 때 이 정적을 매개 변수로 전달합니다.|

## <a name="remarks"></a>설명

응용 프로그램에 대한 유용한 프레임 창을 만들려면 `CFrameWnd`에서 클래스를 파생합니다. 파생 클래스에 멤버 변수를 추가하여 응용 프로그램에 특정한 데이터를 저장합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.

프레임 창을 구성하는 방법에는 세 가지가 있습니다.

- [Create](#create)를 사용하여 직접 생성합니다.

- LoadFrame 을 사용하여 직접 [생성합니다.](#loadframe)

- 문서 템플릿을 사용하여 간접적으로 구성합니다.

`Create` 호출하기 `LoadFrame`전에 C++ **새** 연산자를 사용하여 힙에서 프레임 창 개체를 구성해야 합니다. 호출하기 `Create`전에 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) 글로벌 함수에 창 클래스를 등록하여 프레임의 아이콘 및 클래스 스타일을 설정할 수도 있습니다.

멤버 `Create` 함수를 사용하여 프레임의 생성 매개변수를 즉각적인 인수로 전달합니다.

`LoadFrame`은 보다 `Create`적은 인수를 필요로 하며 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 포함하여 리소스에서 대부분의 기본 값을 검색합니다. `LoadFrame`에 액세스할 수 있도록 이러한 모든 리소스에는 동일한 리소스 ID(예: IDR_MAINFRAME)가 있어야 합니다.

개체에 `CFrameWnd` 뷰와 문서가 포함된 경우 프로그래머가 직접 작성하지 않고 프레임워크에 의해 간접적으로 만들어집니다. 개체는 `CDocTemplate` 프레임 작성, 포함된 뷰 작성 및 뷰를 해당 문서에 연결하도록 오케스트레이션합니다. `CDocTemplate` 생성자의 매개 변수는 관련된 `CRuntimeClass` 세 클래스(문서, 프레임 및 뷰)를 지정합니다. `CRuntimeClass` 개체는 사용자가 지정한 경우(예: 파일 새 명령 또는 여러 문서 인터페이스(MDI) 창 새 명령을 사용하여) 새 프레임을 동적으로 만들기 위해 프레임워크에서 사용됩니다.

위의 RUNTIME_CLASS 메커니즘이 올바르게 `CFrameWnd` 작동하려면 프레임 창 클래스를 DECLARE_DYNCREATE 함께 선언해야 합니다.

A에는 `CFrameWnd` Windows용 일반 응용 프로그램에서 주 창의 다음 기능을 수행하는 기본 구현이 포함되어 있습니다.

- 프레임 `CFrameWnd` 창은 Windows 활성 창 또는 현재 입력 포커스와 독립적인 현재 활성 보기를 추적합니다. 프레임이 다시 활성화되면 를 호출하여 `CView::OnActivateView`활성 보기에 알림이 전송됩니다.

- `OnSetFocus`명령 메시지와 의 에서 `OnHScroll`처리되는 메시지 및 `OnVScroll` `CWnd`의 기능을 포함한 많은 일반적인 프레임 `CFrameWnd` 알림 메시지는 현재 활성 보기에 프레임 창에 의해 위임됩니다.

- 현재 활성 뷰(또는 MDI 프레임의 경우 현재 활성 MDI 자식 프레임 창)는 프레임 창의 캡션을 결정할 수 있습니다. 이 기능은 프레임 창의 FWS_ADDTOTITLE 스타일 비트를 해제하여 비활성화할 수 있습니다.

- 프레임 `CFrameWnd` 창은 프레임 창의 클라이언트 영역 내의 컨트롤 막대, 뷰 및 기타 하위 창의 위치를 관리합니다. 또한 프레임 창은 도구 모음 및 기타 컨트롤 바 단추의 유휴 시간 업데이트를 수행합니다. `CFrameWnd` 프레임 창에는 도구 모음 및 상태 표시줄의 켜기 및 끄기를 전환하기 위한 명령의 기본 구현도 있습니다.

- 프레임 `CFrameWnd` 창은 주 메뉴 모음을 관리합니다. 팝업 메뉴가 표시되면 프레임 창은 UPDATE_COMMAND_UI 메커니즘을 사용하여 사용, 비활성화 또는 확인해야 하는 메뉴 항목을 결정합니다. 사용자가 메뉴 항목을 선택하면 프레임 창이 해당 명령에 대한 메시지 문자열로 상태 표시줄을 업데이트합니다.

- `CFrameWnd` 프레임 창에는 키보드 가속기를 자동으로 변환하는 선택 사양인 액셀러레이터 테이블이 있습니다.

- `CFrameWnd` 프레임 창에는 상황에 맞는 도움말에 사용되는 선택적 도움말 ID `LoadFrame` 집합이 있습니다. 프레임 창은 상황에 맞는 도움말(SHIFT+F1) 및 인쇄 미리 보기 모드와 같은 세미모달 상태의 주요 오케스트레이터입니다.

- `CFrameWnd` 프레임 창은 파일 관리자에서 드래그하여 프레임 창에 떨어뜨린 파일을 엽니다. 파일 확장자가 등록되어 응용 프로그램과 연결된 경우 프레임 창은 사용자가 파일 관리자에서 데이터 파일을 열거나 `ShellExecute` Windows 함수가 호출될 때 발생하는 동적 데이터 교환(DDE) 열기 요청에 응답합니다.

- 프레임 창이 주 응용 프로그램 창(즉, `CWinThread::m_pMainWnd`사용자가 응용 프로그램을 닫을 때)인 경우 프레임 창은 `OnClose` 수정된 문서를 저장하라는 메시지를 사용자에게 표시합니다. `OnQueryEndSession`

- 프레임 창이 기본 응용 프로그램 창인 경우 프레임 창은 WinHelp를 실행하기 위한 컨텍스트입니다. 프레임 창을 닫으면 WINHELP가 종료됩니다. EXE는이 응용 프로그램에 대한 도움말을 위해 시작된 경우.

C++ **delete** 연산자사용을 사용하여 프레임 창을 파괴하지 마십시오. 대신 `CWnd::DestroyWindow`를 사용하세요. 구현은 `CFrameWnd` `PostNcDestroy` 창이 소멸될 때 C++ 개체를 삭제합니다. 사용자가 프레임 창을 닫으면 기본 `OnClose` 처리기가 `DestroyWindow`호출합니다.

자세한 `CFrameWnd`내용은 프레임 [창](../../mfc/frame-windows.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::활성화 프레임

이 멤버 함수를 호출하여 프레임 창을 활성화하고 복원하여 사용자가 표시하고 사용할 수 있도록 합니다.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>매개 변수

*nCmdShow*<br/>
[CWnd::ShowWindow에](../../mfc/reference/cwnd-class.md#showwindow)전달할 매개 변수를 지정합니다. 기본적으로 프레임이 표시되고 올바르게 복원됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 일반적으로 DDE, OLE 또는 프레임 창 또는 그 내용을 사용자에게 표시할 수 있는 기타 이벤트와 같은 비사용자 인터페이스 이벤트 후에 호출됩니다.

기본 구현은 프레임을 활성화하고 Z 순서의 맨 위로 가져오며 필요한 경우 응용 프로그램의 주 프레임 창에 대해 동일한 단계를 수행합니다.

이 멤버 함수를 재정의하여 프레임이 활성화되는 방식을 변경합니다. 예를 들어 MDI 자식 창을 최대화하도록 강제할 수 있습니다. 적절한 기능을 추가한 다음 명시적 *nCmdShow*를 사용 하 여 기본 클래스 버전을 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::시작모달 상태

프레임 창을 모달로 만들기 위해 이 멤버 함수를 호출합니다.

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd

개체를 `CFrameWnd` 생성하지만 표시되는 프레임 창을 만들지는 않습니다.

```
CFrameWnd();
```

### <a name="remarks"></a>설명

호출하여 `Create` 표시되는 창을 만듭니다.

## <a name="cframewndcreate"></a><a name="create"></a>CFrameWnd::만들기

개체와 연결된 Windows 프레임 창을 만들고 `CFrameWnd` 초기화하려면 호출합니다.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CWnd* pParentWnd = NULL,
    LPCTSTR lpszMenuName = NULL,
    DWORD dwExStyle = 0,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
Windows 클래스의 이름을 지정하는 null 종료된 문자 문자열을 가리킵니다. 클래스 이름은 전역 함수 또는 `AfxRegisterWndClass` `RegisterClass` Windows 함수에 등록된 모든 이름일 수 있습니다. NULL인 경우 미리 정의된 `CFrameWnd` 기본 특성을 사용합니다.

*lpszWindowName*<br/>
창 이름을 나타내는 null 종료된 문자 문자열을 가리킵니다. 제목 표시줄의 텍스트로 사용됩니다.

*dwStyle*<br/>
창 [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 특성을 지정합니다. 제목 표시줄에 창에 표시된 문서의 이름을 자동으로 표시하려면 FWS_ADDTOTITLE 스타일을 포함합니다.

*rect*<br/>
창의 크기와 위치를 지정합니다. *rectDefault* 값을 사용하면 Windows에서 새 창의 크기와 위치를 지정할 수 있습니다.

*pParentWnd*<br/>
이 프레임 창의 상위 창을 지정합니다. 최상위 프레임 창의 경우 이 매개 변수는 NULL이어야 합니다.

*lpszMenuName*<br/>
창과 함께 사용할 메뉴 리소스의 이름을 식별합니다. 메뉴에 문자열 대신 정수 ID가 있는 경우 MAKEINTRESOURCE를 사용합니다. 이 매개 변수는 NULL일 수 있습니다.

*dwExStyle*<br/>
창 확장 [스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) 속성을 지정합니다.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조에 대한 포인터를 지정합니다. 이 매개 변수는 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

초기화가 성공하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 `CFrameWnd` 단계로 개체를 생성합니다. 먼저 `CFrameWnd` 개체를 생성하는 생성기를 호출한 다음 `Create`호출하여 Windows 프레임 창을 만들고 개체에 `CFrameWnd` 연결합니다. `Create`에서는 창의 클래스 이름과 창 이름을 초기화하고 스타일, 부모 및 연결된 메뉴에 대한 기본값을 등록합니다.

인수를 `LoadFrame` `Create` 지정하는 대신 리소스에서 프레임 창을 로드하는 대신 사용합니다.

## <a name="cframewndcreateview"></a><a name="createview"></a>CFrameWnd::만들기보기

프레임 `CreateView` 내에서 뷰를 작성하려면 호출합니다.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
뷰 및 문서의 유형을 지정합니다.

*nID*<br/>
뷰의 ID 번호입니다.

### <a name="return-value"></a>Return Value

성공하면 `CWnd` 개체에 대한 포인터; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 멤버 함수를 사용하여 프레임 내에서 `CView`파생되지 않은 "뷰"를 만듭니다. 호출한 `CreateView`후 수동으로 보기를 활성으로 설정하고 표시하도록 설정해야 합니다. 이러한 작업은 에서 자동으로 `CreateView`수행되지 않습니다.

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::D오크컨트롤바

컨트롤 막대를 프레임 창에 도킹합니다.

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
도킹할 컨트롤 바를 가리킵니다.

*nDockBarID*<br/>
도킹을 고려할 프레임 창의 측면을 결정합니다. 0 또는 다음 중 하나 이상이 될 수 있습니다.

- AFX_IDW_DOCKBAR_TOP 프레임 창의 위쪽으로 도킹합니다.

- AFX_IDW_DOCKBAR_BOTTOM 프레임 창의 아래쪽에 도킹합니다.

- AFX_IDW_DOCKBAR_LEFT 프레임 창의 왼쪽에 도킹합니다.

- AFX_IDW_DOCKBAR_RIGHT 프레임 창의 오른쪽에 도킹합니다.

0이면 대상 프레임 창에서 도킹을 사용하도록 설정된 모든 측면에 컨트롤 막대를 도킹할 수 있습니다.

*Lprect*<br/>
화면 좌표에서 대상 프레임 창의 비클라이언트 영역에 컨트롤 막대가 도킹되는 위치를 결정합니다.

### <a name="remarks"></a>설명

컨트롤 막대는 [CControlBar:::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking) 및 [CFrameWnd:::EnableDocking](#enabledocking)에 대한 호출에 지정된 프레임 창의 측면 중 하나에 도킹됩니다. 선택한 면은 *nDockBarID에*의해 결정됩니다.

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::인에이블도킹

프레임 창에서 도킹 가능한 컨트롤 막대를 사용하도록 설정하려면 이 함수를 호출합니다.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
프레임 창의 어느 측면이 컨트롤 막대의 도킹 사이트로 사용될 수 있는지 지정합니다. 다음 중 하나 이상이 될 수 있습니다.

- CBRS_ALIGN_TOP 클라이언트 영역의 맨 위에 도킹할 수 있습니다.

- CBRS_ALIGN_BOTTOM 클라이언트 영역 의 맨 아래에 도킹을 허용합니다.

- CBRS_ALIGN_LEFT 클라이언트 영역의 왼쪽에 도킹을 허용합니다.

- CBRS_ALIGN_RIGHT 클라이언트 영역의 오른쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_ANY 클라이언트 영역의 모든 측면에 도킹을 허용합니다.

### <a name="remarks"></a>설명

기본적으로 컨트롤 막대는 위쪽, 아래쪽, 왼쪽, 오른쪽 순서로 프레임 창의 측면에 도킹됩니다.

### <a name="example"></a>예제

  [CToolBar::만들기에](../../mfc/reference/ctoolbar-class.md#create)대한 예제를 참조하십시오.

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::엔드모달 스테이트

프레임 창을 모달에서 모덜리스로 변경하려면 이 멤버 함수를 호출합니다.

```
virtual void EndModalState();
```

### <a name="remarks"></a>설명

`EndModalState`[BeginModalState에서](#beginmodalstate)비활성화된 모든 창을 활성화합니다.

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd::플로트 컨트롤바

이 함수를 호출하여 컨트롤 막대가 프레임 창에 도킹되지 않도록 합니다.

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
부동 할 컨트롤 바를 가리킵니다.

*지점*<br/>
컨트롤 막대의 왼쪽 상단 모서리가 배치되는 화면 좌표의 위치입니다.

*dwStyle*<br/>
컨트롤 막대를 새 프레임 창 내에서 가로 또는 세로로 정렬할지 여부를 지정합니다. 다음 중 하나일 수 있습니다.

- CBRS_ALIGN_TOP 컨트롤 막대를 수직으로 방향을 지정합니다.

- CBRS_ALIGN_BOTTOM 컨트롤 막대를 수직으로 방향을 지정합니다.

- CBRS_ALIGN_LEFT 컨트롤 막대를 수평으로 방향을 지정합니다.

- CBRS_ALIGN_RIGHT 컨트롤 막대를 수평으로 방향을 지정합니다.

가로 및 세로 방향을 모두 지정하여 스타일을 전달하면 도구 모음의 방향이 수평으로 지정됩니다.

### <a name="remarks"></a>설명

일반적으로 이 작업은 프로그램이 이전 실행에서 설정을 복원할 때 응용 프로그램 시작 시 수행됩니다.

이 함수는 사용자가 도킹에 사용할 수 없는 위치에 컨트롤 막대를 드래그하는 동안 왼쪽 마우스 단추를 해제하여 드롭 작업을 수행하면 프레임워크에서 호출됩니다.

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActive문서

이 멤버 함수를 호출하여 현재 `CDocument` 활성 뷰에 연결된 현재 에 대한 포인터를 가져옵니다.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Return Value

현재 [CDocument에](../../mfc/reference/cdocument-class.md)대한 포인터입니다. 현재 문서가 없는 경우 NULL을 반환합니다.

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame

MDI 프레임 창의 활성 다중 문서 인터페이스(MDI) 자식 창에 대한 포인터를 얻으려면 이 멤버 함수를 호출합니다.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Return Value

활성 MDI 자식 창에 대한 포인터입니다. 응용 프로그램이 SDI 응용 프로그램이거나 MDI 프레임 창에 활성 문서가 없는 경우 암시적 **이** 포인터가 반환됩니다.

### <a name="remarks"></a>설명

활성 MDI 자식이 없거나 응용 프로그램이 단일 문서 인터페이스(SDI)인 경우 암시적 **이** 포인터가 반환됩니다.

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView

프레임 창()에 `CFrameWnd`연결된 활성 뷰(있는 경우)에 대한 포인터를 얻으려면 이 멤버 함수를 호출합니다.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Return Value

현재 [CView에](../../mfc/reference/cview-class.md)대한 포인터입니다. 현재 뷰가 없는 경우 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 함수는 MDI 주 프레임 창()에 `CMDIFrameWnd`대 한 호출 될 때 NULL을 반환 합니다. MDI 응용 프로그램에서 MDI 주 프레임 창에는 연결된 뷰가 없습니다. 대신 각 개별 자식 창() `CMDIChildWnd`에는 하나 이상의 연결된 보기가 있습니다. MDI 응용 프로그램의 활성 보기는 먼저 활성 MDI 자식 창을 찾은 다음 해당 자식 창에 대한 활성 보기를 찾아서 가져올 수 있습니다. 활성 MDI 자식 창은 함수를 `MDIGetActive` `GetActiveFrame` 호출하거나 다음에서 설명한 대로 찾을 수 있습니다.

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar

ID와 연결된 컨트롤 모음에 대한 액세스 권한을 얻으려면 호출합니다. `GetControlBar`

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤 막대의 ID 번호입니다.

### <a name="return-value"></a>Return Value

ID와 연결된 컨트롤 막대에 대한 포인터입니다.

### <a name="remarks"></a>설명

*nID* 매개 변수는 컨트롤 막대의 `Create` 메서드에 전달된 고유 식별자를 나타냅니다. 컨트롤 막대에 대한 자세한 내용은 [컨트롤 막대라는](../../mfc/control-bars.md)제목의 항목을 참조하십시오.

`GetControlBar`이 부동하고 따라서 현재 프레임의 자식 창이 아닌 경우에도 컨트롤 막대를 반환합니다.

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState

이 멤버 함수를 호출하여 프레임 창의 컨트롤 모음에 대한 상태 정보를 `CDockState` 개체에 저장합니다.

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
반환 시 프레임 창의 컨트롤 막대의 현재 상태를 포함합니다.

### <a name="remarks"></a>설명

그런 다음 또는 `CDockState` `CDockState::SaveState` `Serialize`을 사용하여 저장소에 내용을 쓸 수 있습니다. 나중에 컨트롤 막대를 이전 상태로 복원하려면 상태를 로드하거나 `CDockState::LoadState` `Serialize` `SetDockState` 호출하여 이전 상태를 프레임 창의 컨트롤 막대에 적용합니다.

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::겟메뉴바스테이트

현재 MFC 응용 프로그램에서 메뉴의 표시 상태를 검색합니다.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Return Value

반환 값에는 다음 값이 있을 수 있습니다.

- AFX_MBS_VISIBLE(0x01) - 메뉴가 표시됩니다.

- AFX_MBS_HIDDEN (0x02) - 메뉴가 숨겨져 있습니다.

### <a name="remarks"></a>설명

런타임 오류가 발생하면 이 메서드는 디버그 모드에서 어설션하고 [CException](../../mfc/reference/cexception-class.md) 클래스에서 파생된 예외를 발생시게 됩니다.

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBar 가시성

현재 MFC 응용 프로그램의 메뉴의 기본 상태가 숨겨져 있는지 또는 표시되는지 여부를 나타냅니다.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Return Value

이 메서드는 다음 값 중 하나를 반환합니다.

- AFX_MBV_KEEPVISIBLE(0x01) - 메뉴가 항상 표시되며 기본적으로 포커스가 없습니다.

- AFX_MBV_DISPLAYONFOCUS(0x02) - 메뉴는 기본적으로 숨김입니다. 메뉴가 숨겨져 있으면 ALT 키를 눌러 메뉴를 표시하고 포커스를 지정합니다. 메뉴가 표시되면 ALT 또는 ESC 키를 눌러 숨깁니다.

- AFX_MBV_ 디스플레이온포커스(0x02) &#124; AFX_MBV_DISPLAYONF10(0x04) (비트 조합(OR)) - 메뉴는 기본적으로 숨김입니다. 메뉴가 숨겨져 있으면 F10 키를 눌러 메뉴를 표시하고 포커스를 지정합니다. 메뉴가 표시되면 F10 키를 눌러 메뉴의 초점을 전환하거나 해제합니다. ALT 또는 ESC 키를 눌러 숨길 때까지 메뉴가 표시됩니다.

### <a name="remarks"></a>설명

런타임 오류가 발생하면 이 메서드는 디버그 모드에서 어설션하고 [CException](../../mfc/reference/cexception-class.md) 클래스에서 파생된 예외를 발생시게 됩니다.

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar

상태 표시줄에 대한 포인터를 얻으려면 이 멤버 함수를 호출합니다.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Return Value

상태 표시줄 창에 대한 포인터입니다.

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString

명령 아이디에 대한 사용자 지정 문자열을 제공하기 위해 이 함수를 재정의합니다.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
원하는 메시지의 리소스 ID입니다.

*rMessage*<br/>
`CString`메시지를 배치할 개체입니다.

### <a name="remarks"></a>설명

기본 구현은 리소스 파일에서 *nID로* 지정된 문자열을 로드하기만 하면 됩니다. 이 함수는 상태 표시줄의 메시지 문자열을 업데이트해야 하는 경우 프레임워크에서 호출됩니다.

## <a name="cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle

창 개체의 제목을 검색합니다.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Return Value

창 개체의 현재 제목을 포함하는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::초기 업데이트 프레임

을 `IntitialUpdateFrame` 통해 새 프레임을 `Create`만든 후 호출합니다.

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>매개 변수

*pDoc*<br/>
프레임 창이 연결된 문서를 가리킵니다. NULL일 수 있습니다.

*bMakeVisible*<br/>
TRUE이면 프레임이 표시되고 활성화되어야 한다는 것을 나타냅니다. FALSE이면 하위 항목이 표시되지 않습니다.

### <a name="remarks"></a>설명

이렇게 하면 해당 프레임 창의 `OnInitialUpdate` 모든 뷰가 호출을 수신합니다.

또한 이전에 활성 뷰가 없는 경우 프레임 창의 기본 보기가 활성화됩니다. 기본 보기는 AFX_IDW_PANE_FIRST 자식 ID가 있는 보기입니다. 마지막으로 *bMakeVisible가* 영해가 아닌 경우 프레임 창이 표시됩니다. *bMakeVisible가* 0이면 프레임 창의 현재 초점과 표시되는 상태는 변경되지 않습니다. 프레임워크의 파일 새 및 파일 열기 구현을 사용할 때 이 함수를 호출할 필요는 없습니다.

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::인모달스테이트

이 멤버 함수를 호출하여 프레임 창이 모달인지 모덜리스인지 확인합니다.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Return Value

비영점 그렇다면 예; 그렇지 않으면 0.

## <a name="cframewndistracking"></a><a name="istracking"></a>CFrameWnd::추적

이 멤버 함수를 호출하여 창의 스플리터 막대가 현재 이동중인지 확인합니다.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Return Value

스플리터 작업이 진행 중인 경우 0이 아닌 경우; 그렇지 않으면 0.

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::로드Acceltable

지정된 가속기 테이블을 로드하려면 호출합니다.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
가속기 리소스의 이름을 식별합니다. 리소스가 정수 ID로 식별된 경우 MAKEINTRESOURCE를 사용합니다.

### <a name="return-value"></a>Return Value

가속기 테이블이 성공적으로 로드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

한 번에 하나의 테이블만 로드할 수 있습니다.

리소스에서 로드된 액셀러레이터 테이블은 응용 프로그램이 종료되면 자동으로 해제됩니다.

프레임 창을 `LoadFrame` 만들기 위해 호출하는 경우 프레임워크는 메뉴 및 아이콘 리소스와 함께 가속기 테이블을 로드하고 이 멤버 함수에 대한 후속 호출은 필요하지 않습니다.

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::로드바스테이트

이 함수를 호출하여 프레임 창이 소유한 각 컨트롤 막대의 설정을 복원합니다.

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화(INI) 파일의 섹션 이름 또는 상태 정보가 저장되는 Windows 레지스트리의 키입니다.

### <a name="remarks"></a>설명

복원된 정보에는 가시성, 수평/수직 방향, 도킹 상태 및 제어 막대 위치가 포함됩니다.

복원하려는 설정은 호출하기 `LoadBarState`전에 레지스트리에 기록되어야 합니다. [CWinApp::SetRegistryKey를](../../mfc/reference/cwinapp-class.md#setregistrykey)호출하여 레지스트리에 정보를 작성합니다. [SaveBarState](#savebarstate)를 호출하여 INI 파일에 정보를 작성합니다.

## <a name="cframewndloadframe"></a><a name="loadframe"></a>프레임수지::로드프레임

리소스 정보에서 프레임 창을 동적으로 만들려면 호출합니다.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
프레임 창과 연결된 공유 리소스의 ID입니다.

*dwDefaultStyle*<br/>
프레임의 [스타일입니다.](../../mfc/reference/styles-used-by-mfc.md#window-styles) 제목 표시줄에 창에 표시된 문서의 이름을 자동으로 표시하려면 FWS_ADDTOTITLE 스타일을 포함합니다.

*pParentWnd*<br/>
프레임의 부모에 대한 포인터입니다.

*pContext*<br/>
CCreateContext 구조에 대한 [포인터입니다.](../../mfc/reference/ccreatecontext-structure.md) 이 매개 변수는 NULL일 수 있습니다.

### <a name="remarks"></a>설명

두 `CFrameWnd` 단계로 개체를 생성합니다. 먼저 `CFrameWnd` 개체를 생성하는 생성기를 호출한 다음 Windows 프레임 `LoadFrame`창 및 관련 리소스를 로드하고 프레임 창을 `CFrameWnd` 개체에 연결하는 호출합니다. *nIDResource* 매개 변수는 메뉴, 가속기 테이블, 아이콘 및 프레임 창에 대 한 제목의 문자열 리소스를 지정 합니다.

프레임 `Create` 창의 생성 `LoadFrame` 매개변수를 모두 지정하려는 경우가 아니라 멤버 함수를 사용합니다.

프레임워크는 `LoadFrame` 문서 템플릿 개체를 사용하여 프레임 창을 만들 때 호출합니다.

프레임워크는 *pContext* 인수를 사용하여 포함된 뷰 개체를 포함하여 프레임 창에 연결할 개체를 지정합니다. 을 호출할 `LoadFrame`때 *pContext* 인수를 NULL로 설정할 수 있습니다.

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable

이 데이터 멤버를 사용하도록 설정하면(기본값) 사용자가 메뉴를 끌어낼 때 ON_UPDATE_COMMAND_UI 또는 ON_COMMAND 처리기가 없는 메뉴 항목은 자동으로 비활성화됩니다.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>설명

ON_COMMAND 처리기가 있지만 ON_UPDATE_COMMAND_UI 처리기가 없는 메뉴 항목은 자동으로 활성화됩니다.

이 데이터 멤버를 설정하면 도구 모음 단추를 사용하도록 설정된 것과 같은 방식으로 메뉴 항목이 자동으로 활성화됩니다.

> [!NOTE]
> `m_bAutoMenuEnable`최상위 메뉴 항목에는 영향을 주지 않습니다.

이 데이터 멤버는 현재 선택 항목에 따라 선택적 명령의 구현을 단순화하고 메뉴 항목을 활성화 및 비활성화하기 위한 ON_UPDATE_COMMAND_UI 처리기를 작성할 필요가 줄어듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::협상국경공간

이 멤버 함수를 호출하여 OLE 인플레이스 활성화 중에 프레임 창에서 테두리 공간을 협상합니다.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>매개 변수

*nBorderCmd*<br/>
`enum BorderCmd`다음 값 중 하나를 포함합니다.

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 테두리의 좌표를 지정하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 OLE 테두리 공간 협상을 `CFrameWnd` 구현합니다.

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::온바체크

지정된 컨트롤 막대에서 작업이 수행될 때마다 호출됩니다.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
표시되는 컨트롤 막대의 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤 바가 존재하는 경우 비영; 그렇지 않으면 0.

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd::온컨텍스트 도움말

시프트+F1 인플레이스 항목에 대한 도움말을 처리합니다.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>설명

상황에 맞는 도움말을 사용하려면

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

클래스 메시지 `CFrameWnd` 맵에 문및 가속기 테이블 항목(일반적으로 SHIFT+F1)을 추가하여 이 멤버 함수를 활성화합니다.

응용 프로그램이 OLE 컨테이너인 `OnContextHelp` 경우 프레임 창 개체 내에 포함된 모든 내부 항목을 도움말 모드로 전환합니다. 커서가 화살표와 물음표로 변경되고 사용자는 마우스 포인터를 이동하고 왼쪽 마우스 버튼을 눌러 대화 상자, 창, 메뉴 또는 명령 단추를 선택할 수 있습니다. 이 멤버 함수는 `WinHelp` 커서 아래에 있는 개체의 도움말 컨텍스트를 통해 Windows 함수를 호출합니다.

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::온크레이드 클라이언트

을 실행 하는 동안 `OnCreate`프레임 워크에 의해 호출 됩니다.

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>매개 변수

*lpcs*<br/>
Windows [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) 구조에 대한 포인터입니다.

*pContext*<br/>
CCreateContext 구조에 대한 [포인터입니다.](../../mfc/reference/ccreatecontext-structure.md)

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출하지 마십시오.

이 함수의 기본 구현은 가능하면 `CView` *pContext*에 제공된 정보에서 개체를 만듭니다.

`CCreateContext` 이 함수를 재정의하여 개체에서 전달된 값을 재정의하거나 프레임 창의 주 클라이언트 영역에서 컨트롤이 만들어지는 방식을 변경합니다. 재정의할 수 있는 `CCreateContext`멤버는 [ccreatecontext](../../mfc/reference/ccreatecontext-structure.md) 클래스에서 설명합니다.

> [!NOTE]
> 구조에 전달된 `CREATESTRUCT` 값을 대체하지 마십시오. 정보 용으로만 사용할 수 있습니다. 예를 들어 초기 창 사각형을 재정의하려면 `CWnd` 멤버 함수 [PreCreateWindow를](../../mfc/reference/cwnd-class.md#precreatewindow)재정의합니다.

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::온하이드메뉴바

이 함수는 시스템이 현재 MFC 응용 프로그램에서 메뉴 막대를 숨기려고 할 때 호출됩니다.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>설명

이 이벤트 처리기를 사용하면 시스템이 메뉴를 숨기려고 할 때 응용 프로그램에서 사용자 지정 작업을 수행할 수 있습니다. 메뉴가 숨겨지는 것을 방지할 수는 없지만 다른 메서드를 호출하여 메뉴 스타일이나 상태를 검색할 수 있습니다.

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::온셋프리뷰모드

애플리케이션의 주 프레임 창을 인쇄 미리 보기 모드 내부 및 외부로 설정하려면 이 멤버 함수를 호출합니다.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>매개 변수

*bPreview*<br/>
응용 프로그램을 인쇄 미리 보기 모드로 배치할지 여부를 지정합니다. 인쇄 미리 보기에 배치하려면 TRUE로 설정, FALSE를 취소하려면 미리 보기 모드.

*pState*<br/>
구조에 대한 `CPrintPreviewState` 포인터입니다.

### <a name="remarks"></a>설명

기본 구현은 모든 표준 도구 모음을 비활성화하고 주 메뉴와 주 클라이언트 창을 숨깁니다. 이렇게 하면 MDI 프레임 창이 임시 SDI 프레임 창으로 바뀝니다.

이 멤버 함수를 재정의하여 인쇄 미리 보기 중에 컨트롤 막대 및 기타 프레임 창 부분의 숨기기 및 표시를 사용자 지정합니다. 재정의된 버전 내에서 기본 클래스 구현을 호출합니다.

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::온쇼메뉴바

이 함수는 시스템이 현재 MFC 응용 프로그램에 메뉴 막대를 표시하려고 할 때 호출됩니다.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>설명

이 이벤트 처리기를 사용하면 메뉴가 표시될 때 응용 프로그램에서 사용자 지정 작업을 수행할 수 있습니다. 메뉴가 표시되지 않도록 할 수는 없지만 다른 메서드를 호출하여 메뉴 스타일이나 상태를 검색할 수 있습니다.

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::에 업데이트 컨트롤 바 메뉴

연결된 메뉴가 업데이트될 때 프레임워크에서 호출됩니다.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
업데이트 명령을 생성한 메뉴를 나타내는 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체에 대한 포인터입니다. 업데이트 처리기는 *pCmdUI*을 통해 `CCmdUI`개체의 [Enable](../../mfc/reference/ccmdui-class.md#enable) member 함수를 호출하여 사용자 인터페이스를 업데이트합니다.

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd::리콜레이아웃

표준 컨트롤 막대가 켜지거나 꺼지거나 프레임 창의 크기가 조정될 때 프레임워크에서 호출됩니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*bNotify*<br/>
프레임 창에 대한 활성 인플레이스 항목이 레이아웃 변경 알림을 받는지 여부를 결정합니다. TRUE이면 항목에 알림이 전송됩니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 멤버 함수의 기본 `CWnd` 구현은 `RepositionBars` 멤버 함수를 호출하여 프레임과 주 클라이언트 창(일반적으로 `CView` MDICLIENT)의 모든 컨트롤 막대를 재배치합니다.

프레임 창의 레이아웃이 변경된 후 컨트롤 막대의 모양과 동작을 제어하려면 이 멤버 함수를 재정의합니다. 예를 들어 컨트롤 막대를 켜거나 끄거나 다른 컨트롤 막대를 추가할 때 호출합니다.

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::정류기본

Windows가 `CRect` 창의 초기 크기와 위치를 선택할 수 있도록 창을 만들 때 이 정적을 매개 변수로 전달합니다.

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::저장 바스테이트

프레임 창이 소유한 각 컨트롤 막대에 대한 정보를 저장하려면 이 함수를 호출합니다.

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
초기화 파일의 섹션 이름 또는 상태 정보가 저장되는 Windows 레지스트리의 키입니다.

### <a name="remarks"></a>설명

이 정보는 [LoadBarState](#loadbarstate)를 사용하여 초기화 파일에서 읽을 수 있습니다. 저장된 정보에는 가시성, 수평/수직 방향, 도킹 상태 및 제어 막대 위치가 포함됩니다.

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::설정활성 미리보기보기

지정된 뷰를 [조회]에 대한 활성 보기로 지정합니다.

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>매개 변수

*pViewNew*<br/>
활성화할 뷰에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::설정활성 보기

이 멤버 함수를 호출하여 활성 보기를 설정합니다.

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*pViewNew*<br/>
활성 뷰가 없는 [경우 CView](../../mfc/reference/cview-class.md) 개체 또는 NULL에 대한 포인터를 지정합니다.

*bNotify*<br/>
뷰에 활성화 알림을 받을지 여부를 지정합니다. `OnActivateView` TRUE인 경우 새 보기에 대 한 호출 됩니다. FALSE인 경우 는 그렇지 않습니다.

### <a name="remarks"></a>설명

사용자가 포커스를 프레임 창 내의 뷰로 변경하면 프레임워크가 이 함수를 자동으로 호출합니다. 명시적으로 호출하여 `SetActiveView` 포커스를 지정된 뷰로 변경할 수 있습니다.

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState

이 멤버 함수를 호출하여 `CDockState` 개체에 저장된 상태 정보를 프레임 창의 컨트롤 모음에 적용합니다.

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>매개 변수

*상태*<br/>
저장된 상태를 프레임 창의 컨트롤 막대에 적용합니다.

### <a name="remarks"></a>설명

컨트롤 막대의 이전 상태를 복원하려면 저장된 상태를 `CDockState::LoadState` 로드하거나 `Serialize`프레임 `SetDockState` 창의 컨트롤 막대에 적용하는 데 사용할 수 있습니다. 이전 상태는 개체에 `CDockState` 저장됩니다.`GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::세트메뉴바스테이트

현재 MFC 응용 프로그램의 메뉴 표시 상태를 숨김 또는 표시로 설정합니다.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*nState*|【인】 메뉴를 표시하거나 숨길지 여부를 지정합니다. *nState* 매개 변수에는 다음 값이 있을 수 있습니다.<br /><br />- AFX_MBS_VISIBLE (0x01) - 숨겨진 경우 메뉴를 표시하지만, 볼 경우 효과가 없습니다.<br />- AFX_MBS_HIDDEN (0x02) - 표시되는 경우 메뉴를 숨깁니다,하지만 숨겨진 경우 효과가 없습니다.|

### <a name="return-value"></a>Return Value

이 메서드가 메뉴 상태를 성공적으로 변경하는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

런타임 오류가 발생하면 이 메서드는 디버그 모드에서 어설션하고 [CException](../../mfc/reference/cexception-class.md) 클래스에서 파생된 예외를 발생시게 됩니다.

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::세트메뉴바 가시성

현재 MFC 응용 프로그램에서 메뉴의 기본 동작을 숨김 또는 표시하도록 설정합니다.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*nStyle*|【인】 메뉴가 기본적으로 숨겨져 있는지 또는 표시되고 포커스가 있는지 여부를 지정합니다. *nStyle* 매개 변수에는 다음 값이 있을 수 있습니다.<br /><br />- AFX_MBV_KEEPVISIBLE (0x01) -<br />     메뉴는 항상 표시되며 기본적으로 포커스가 없습니다.<br />- AFX_MBV_DISPLAYONFOCUS (0x02) -<br />     메뉴는 기본적으로 숨김입니다. 메뉴가 숨겨져 있으면 ALT 키를 눌러 메뉴를 표시하고 포커스를 지정합니다. 메뉴가 표시되면 ALT 또는 ESC 키를 눌러 메뉴를 숨깁니다.<br />- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (BITWISE 조합(OR)) - 메뉴는 기본적으로 숨김입니다. 메뉴가 숨겨져 있으면 F10 키를 눌러 메뉴를 표시하고 포커스를 지정합니다. 메뉴가 표시되면 F10 키를 눌러 메뉴의 초점을 전환하거나 해제합니다. ALT 또는 ESC 키를 눌러 숨길 때까지 메뉴가 표시됩니다.|

### <a name="remarks"></a>설명

*nStyle* 매개 변수의 값이 유효하지 않은 경우 이 메서드는 디버그 모드에서 어설션하고 릴리스 모드에서 [CInvalidArgException을](../../mfc/reference/cinvalidargexception-class.md) 발생시면 됩니다. 다른 런타임 오류의 경우 이 메서드는 디버그 모드에서 어설션하고 [CException](../../mfc/reference/cexception-class.md) 클래스에서 파생된 예외를 발생시게 됩니다.

이 메서드는 Windows Vista 및 이후 응용 프로그램에서 메뉴 상태에 영향을 줍니다.

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText

ID가 0인 상태 표시줄 창에 문자열을 배치하려면 이 함수를 호출합니다.

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
상태 표시줄에 배치할 문자열을 가리킵니다.

*nID*<br/>
상태 표시줄에 배치할 문자열의 문자열 리소스 ID입니다.

### <a name="remarks"></a>설명

일반적으로 상태 표시줄의 가장 왼쪽이고 가장 긴 창입니다.

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::설정진행바포지션

작업 표시줄에 표시되는 Windows 7 진행률 표시줄의 현재 위치를 설정합니다.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>매개 변수

*nProgressPos*<br/>
설정할 위치를 지정합니다. 에 의해 `SetProgressBarRange`설정된 범위 내에 있어야 합니다.

### <a name="remarks"></a>설명

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::설정진행바레인지

작업 표시줄에 표시되는 Windows 7 진행률 표시줄의 범위를 설정합니다.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>매개 변수

*nRangeMin*<br/>
최소한의 값입니다.

*nRangeMax*<br/>
최대 값입니다.

### <a name="remarks"></a>설명

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::설정진행률바스테이트

작업 표시줄 단추에 표시되는 진행률 표시기의 유형 및 상태를 설정합니다.

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>매개 변수

*tbpFlags*<br/>
진행률 단추의 현재 상태를 제어하는 플래그입니다. TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED 모든 상태가 상호 배타적이기 때문에 다음 플래그 중 하나만 지정합니다.

### <a name="remarks"></a>설명

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::설정 작업 표시줄 오버레이아이콘

오버로드되었습니다. 작업 표시줄 단추에 오버레이를 적용하여 응용 프로그램 상태를 나타내거나 사용자에게 알립니다.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
오버레이로 사용할 아이콘의 리소스 ID를 지정합니다. 자세한 내용은 *hIcon에* 대한 설명을 참조하십시오.

*lpcszDescr*<br/>
접근성을 위해 오버레이에서 전달하는 정보의 대체 텍스트 버전을 제공하는 문자열에 대한 포인터입니다.

*hIcon*<br/>
오버레이로 사용할 아이콘의 핸들입니다. 이 아이콘은 인치당 96도(dpi)에서 16x16 픽셀을 측정하는 작은 아이콘이어야 합니다. 작업 표시줄 단추에 오버레이 아이콘이 이미 적용된 경우 기존 오버레이가 대체됩니다. 이 값은 NULL일 수 있습니다. NULL 값을 처리하는 방법은 작업 표시줄 단추가 단일 창을 나타내는지 아니면 창 그룹을 나타내는지에 따라 달라집니다. 더 이상 필요하지 않은 경우 *hIcon을* 해제하는 것은 호출 응용 프로그램의 책임입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE; OS 버전이 Windows 7보다 작거나 아이콘을 설정하는 오류가 발생하는 경우 FALSE.

### <a name="remarks"></a>설명

## <a name="cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::설정 제목

창 개체의 제목을 설정합니다.

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>매개 변수

*lpszTitle*<br/>
창 개체의 제목을 포함하는 문자열에 대한 포인터입니다.

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::쇼컨트롤바

컨트롤 막대를 표시하거나 숨기려면 이 멤버 함수를 호출합니다.

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
표시하거나 숨길 컨트롤 막대에 대한 포인터입니다.

*bShow*<br/>
TRUE이면 컨트롤 막대가 표시되도록 지정합니다. FALSE인 경우 컨트롤 막대를 숨길 수 있도록 지정합니다.

*bDelay*<br/>
TRUE이면 컨트롤 막대 표시를 지연합니다. FALSE인 경우 컨트롤 막대를 즉시 표시합니다.

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::쇼소유윈도우

`CFrameWnd` 이 멤버 함수를 호출하여 개체의 하위 창인 모든 창을 표시합니다.

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
소유한 창을 표시할지 숨길지 여부를 지정합니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd 클래스](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDI차일드 클래스](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[크런타임클래스 구조](../../mfc/reference/cruntimeclass-structure.md)
