---
title: C스플리터Wnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
ms.openlocfilehash: a872854af1695b8b2b347b21d73165d259b3a986
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753070"
---
# <a name="csplitterwnd-class"></a>C스플리터Wnd 클래스

여러 개의 창이 포함된 창인 분할자 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C스플리터Wnd:::C스플리터Wnd](#csplitterwnd)|개체를 생성하기 위해 호출합니다. `CSplitterWnd`|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C스플리터Wnd::활성화다음](#activatenext)|다음 창 또는 이전 창 명령을 수행합니다.|
|[C스플리터Wnd::캔활성화다음](#canactivatenext)|다음 창 또는 이전 창 명령이 현재 가능한지 확인합니다.|
|[C스플리터Wnd::만들기](#create)|동적 스플리터 창을 만들고 개체에 `CSplitterWnd` 연결하려면 호출합니다.|
|[C스플리터Wnd::만들기스크롤바Ctrl](#createscrollbarctrl)|공유 스크롤 막대 컨트롤을 만듭니다.|
|[C스플리터Wnd::정적 만들기](#createstatic)|호출하여 정적 분할자 창을 만들고 개체에 `CSplitterWnd` 연결합니다.|
|[C스플리터Wnd::만들기보기](#createview)|스플리터 창에서 창을 만들려면 호출합니다.|
|[C스플리터Wnd::DeleteColumn](#deletecolumn)|스플리터 창에서 열을 삭제합니다.|
|[C스플리터Wnd::DeleteRow](#deleterow)|스플리터 창에서 행을 삭제합니다.|
|[C스플리터Wnd::DeleteView](#deleteview)|스플리터 창에서 보기를 삭제합니다.|
|[C스플리터Wnd::Do 키보드 스플리트](#dokeyboardsplit)|키보드 분할 명령을 수행합니다(일반적으로 "창 분할").|
|[C스플리터Wnd::Do스크롤](#doscroll)|분할 창의 동기화된 스크롤을 수행합니다.|
|[C스플리터Wnd::Do스크롤비](#doscrollby)|지정된 픽셀 수로 분할 창을 스크롤합니다.|
|[C스플리터Wnd::GetActivePane](#getactivepane)|프레임의 포커스 또는 활성 뷰에서 활성 창을 결정합니다.|
|[C스플리터Wnd::GetColumnCount](#getcolumncount)|현재 창 열 수를 반환합니다.|
|[C스플리터Wnd::GetColumnInfo](#getcolumninfo)|지정된 열에 대한 정보를 반환합니다.|
|[C스플리터Wnd::GetPane](#getpane)|지정된 행 과 열에서 창을 반환합니다.|
|[C스플리터Wnd::GetRowCount](#getrowcount)|현재 창 행 수를 반환합니다.|
|[C스플리터Wnd::GetRowInfo](#getrowinfo)|지정된 행에 대한 정보를 반환합니다.|
|[C스플리터Wnd::Get스크롤 스타일](#getscrollstyle)|공유 스크롤 막대 스타일을 반환합니다.|
|[C스플리터Wnd::IdFromRowCol](#idfromrowcol)|지정된 행 및 열에서 창의 자식 창 ID를 반환합니다.|
|[C스플리터Wnd::이차일드파인](#ischildpane)|호출하여 창이 현재 이 스플리터 창의 자식 창인지 확인합니다.|
|[C스플리터Wnd::추적](#istracking)|스플리터 막대가 현재 이동중인지 여부를 결정합니다.|
|[C스플리터Wnd::리콜크 레이아웃](#recalclayout)|행 또는 열 크기를 조정한 후 스플리터 창을 다시 표시하려면 호출합니다.|
|[C스플리터Wnd::설정액티브파인](#setactivepane)|창을 프레임의 활성 창으로 설정합니다.|
|[C스플리터Wnd::SetColumnInfo](#setcolumninfo)|호출하여 지정된 열 정보를 설정합니다.|
|[C스플리터Wnd::SetRowInfo](#setrowinfo)|호출하여 지정된 행 정보를 설정합니다.|
|[C스플리터Wnd::세트스크롤 스타일](#setscrollstyle)|스플리터 창의 공유 스크롤 막대 지원을 위한 새 스크롤 막대 스타일을 지정합니다.|
|[C스플리터Wnd::분할열](#splitcolumn)|프레임 창이 세로로 분할되는 위치를 나타냅니다.|
|[C스플리터Wnd::스플리트로우](#splitrow)|프레임 창이 가로로 분할되는 위치를 나타냅니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C스플리터Wnd::온드로우](#ondraw)|스플리터 창을 그리는 프레임 워크에 의해 호출 됩니다.|
|[C스플리터Wnd::온드로우 스플리터](#ondrawsplitter)|분할 창의 이미지를 렌더링합니다.|
|[C스플리터Wnd::온인버트트래커](#oninverttracker)|분할 창의 이미지를 프레임 창과 동일한 크기 및 모양으로 렌더링합니다.|

## <a name="remarks"></a>설명

창은 일반적으로 [CView에서](../../mfc/reference/cview-class.md)파생된 응용 프로그램별 개체이지만 적절한 자식 창 ID가 있는 [모든 CWnd](../../mfc/reference/cwnd-class.md) 개체일 수 있습니다.

개체는 `CSplitterWnd` 일반적으로 상위 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체에 포함 됩니다. 다음 `CSplitterWnd` 단계를 사용하여 개체를 만듭니다.

1. 상위 프레임에 `CSplitterWnd` 멤버 변수를 포함합니다.

2. 상위 프레임의 [CFrameWnd::OnCreate클라이언트](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수를 재정의합니다.

3. 재정의된 `OnCreateClient`내에서 의 [Create](#create) 또는 [CreateStatic](#createstatic) 멤버 `CSplitterWnd`함수를 호출합니다.

멤버 `Create` 함수를 호출하여 동적 스플리터 창을 만듭니다. 동적 분할자 창은 일반적으로 동일한 문서의 여러 개별 창 또는 보기를 만들고 스크롤하는 데 사용됩니다. 프레임워크는 스플리터에 대한 초기 창을 자동으로 만듭니다. 그런 다음 프레임워크는 사용자가 스플리터 창의 컨트롤을 작동할 때 추가 창을 만들고 크기를 조정하고 삭제합니다.

호출할 `Create`때 창이 너무 작아 완전히 표시되지 않는 시기를 결정하는 최소 행 높이와 열 너비를 지정합니다. 호출 `Create`한 후 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수를 호출하여 이러한 최소를 조정할 수 있습니다.

또한 `SetColumnInfo` 및 `SetRowInfo` 멤버 함수를 사용하여 열에 대한 "이상적인" 너비와 행에 대한 "이상적인" 높이를 설정합니다. 프레임워크에 스플리터 창이 표시되면 먼저 부모 프레임, 스플리터 창을 표시합니다. 그런 다음 프레임워크는 이상적인 차원에 따라 열과 행에 창을 배치하여 스플리터 창의 클라이언트 영역의 왼쪽 위부터 오른쪽 아래 모서리로 작업합니다.

동적 스플리터 창의 모든 창은 동일한 클래스여야 합니다. 동적 스플리터 윈도우를 지원하는 친숙한 응용 프로그램은 마이크로 소프트 워드와 마이크로 소프트 엑셀을 포함한다.

멤버 `CreateStatic` 함수를 사용하여 정적 분할자 창을 만듭니다. 사용자는 정적 분할창의 창 크기만 변경할 수 있으며, 해당 창은 자신의 번호나 순서가 아닙니다.

정적 스플리터를 만들 때 모든 정적 스플리터의 창을 특별히 만들어야 합니다. 상위 프레임의 `OnCreateClient` 멤버 함수가 반환되기 전에 모든 창을 만들거나 프레임워크에 창이 올바르게 표시되지 않는지 확인합니다.

멤버 `CreateStatic` 함수는 최소 행 높이와 열 너비가 0인 정적 스플리터를 자동으로 초기화합니다. 호출 `Create`한 후 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수를 호출 하여 이러한 최소를 조정 합니다. 또한 `SetColumnInfo` 사용 `SetRowInfo` 하 `CreateStatic` 고 호출 후 원하는 이상적인 창 크기를 나타내는.

정적 분할기의 개별 창은 종종 다른 클래스에 속합니다. 정적 스플리터 창의 예는 그래픽 편집기와 Windows 파일 관리자를 참조하십시오.

스플리터 창은 특수 스크롤 막대를 지원합니다(창이 있을 수 있는 스크롤 막대 제외). 이러한 스크롤 막대는 `CSplitterWnd` 개체의 자식이며 창과 공유됩니다.

스플리터 창을 만들 때 이러한 특수 스크롤 막대를 만듭니다. 예를 들어 `CSplitterWnd` 행이 하나, 두 개의 열이 있고 WS_VSCROLL 스타일에는 두 창에서 공유하는 세로 스크롤 막대가 표시됩니다. 사용자가 스크롤 막대를 이동하면 WM_VSCROLL 메시지가 두 창으로 전송됩니다. 창이 스크롤 막대 위치를 설정하면 공유 스크롤 막대가 설정됩니다.

스플리터 창에 대한 자세한 내용은 [기술 참고 29를](../../mfc/tn029-splitter-windows.md)참조하십시오.

동적 스플리터 창을 만드는 방법에 대한 자세한 내용은 다음을 참조하십시오.

- MFC 샘플 [낙서](../../overview/visual-cpp-samples.md)

- MFC 샘플 [뷰EX](../../overview/visual-cpp-samples.md).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxt.h

## <a name="csplitterwndactivatenext"></a><a name="activatenext"></a>C스플리터Wnd::활성화다음

다음 창 또는 이전 창 명령을 수행 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>매개 변수

*bPrev*<br/>
활성화할 창을 나타냅니다. 이전의 경우 **True;** 다음에 대 한 **false입니다.**

### <a name="remarks"></a>설명

이 멤버 함수는 [CView](../../mfc/reference/cview-class.md) 클래스에서 구현에 위임하는 데 `CSplitterWnd` 사용되는 상위 수준 명령입니다.

## <a name="csplitterwndcanactivatenext"></a><a name="canactivatenext"></a>C스플리터Wnd::캔활성화다음

다음 창 또는 이전 창 명령이 현재 가능한지 확인하기 위해 프레임 워크에서 호출합니다.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>매개 변수

*bPrev*<br/>
활성화할 창을 나타냅니다. 이전의 경우 **True;** 다음에 대 한 **false입니다.**

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 [CView](../../mfc/reference/cview-class.md) 클래스에서 구현에 위임하는 데 `CSplitterWnd` 사용되는 상위 수준 명령입니다.

## <a name="csplitterwndcreate"></a><a name="create"></a>C스플리터Wnd::만들기

동적 스플리터 창을 만들려면 `Create` 멤버 함수를 호출합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    int nMaxRows,
    int nMaxCols,
    SIZE sizeMin,
    CCreateContext* pContext,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
스플리터 창의 부모 프레임 창입니다.

*nMaxRows*<br/>
스플리터 창의 최대 행 수입니다. 이 값은 2를 초과해서는 안 됩니다.

*앤맥스콜스*<br/>
스플리터 창의 최대 열 수입니다. 이 값은 2를 초과해서는 안 됩니다.

*크기민*<br/>
창이 표시될 수 있는 최소 크기를 지정합니다.

*pContext*<br/>
CCreateContext 구조에 대한 [포인터입니다.](../../mfc/reference/ccreatecontext-structure.md) 대부분의 경우 부모 프레임 창에 전달되는 *pContext일* 수 있습니다.

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할창이 다른 스플리터 창 내에 중첩되지 않는 한 ID는 AFX_IDW_PANE_FIRST 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

다음 단계를 수행하여 상위 `CSplitterWnd` [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체에 포함할 수 있습니다.

1. 상위 프레임에 `CSplitterWnd` 멤버 변수를 포함합니다.

1. 상위 프레임의 [CFrameWnd::OnCreate클라이언트](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수를 재정의합니다.

1. 재정의된 `Create` 내에서 멤버 함수를 `OnCreateClient`호출합니다.

상위 프레임 내에서 스플리터 창을 만들 때 부모 프레임의 *pContext* 매개 변수를 스플리터 창으로 전달합니다. 그렇지 않으면 이 매개 변수가 NULL일 수 있습니다.

동적 분할자 창의 초기 최소 행 높이 및 열 너비는 *sizeMin* 매개 변수로 설정됩니다. 창이 너무 작아서 전체에 표시할 수 없는지 여부를 결정하는 이러한 최소값은 [SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수를 사용하여 변경할 수 있습니다.

동적 분할창에 대한 자세한 내용은 [문서 여러 문서 유형, 보기 및 프레임 창,](../../mfc/multiple-document-types-views-and-frame-windows.md)기술 참고 `CSplitterWnd` [29](../../mfc/tn029-splitter-windows.md)및 클래스 개요의 "Splitter Windows"를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

## <a name="csplitterwndcreatescrollbarctrl"></a><a name="createscrollbarctrl"></a>C스플리터Wnd::만들기스크롤바Ctrl

공유 스크롤 막대 컨트롤을 만들기 위해 프레임워크에서 호출합니다.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할창이 다른 스플리터 창 내에 중첩되지 않는 한 ID는 AFX_IDW_PANE_FIRST 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

스크롤 `CreateScrollBarCtrl` 막대 옆에 추가 컨트롤을 포함하도록 재정의합니다. 기본 동작은 일반 Windows 스크롤 막대 컨트롤을 만드는 것입니다.

## <a name="csplitterwndcreatestatic"></a><a name="createstatic"></a>C스플리터Wnd::정적 만들기

정적 분할자 창을 만들려면 `CreateStatic` 멤버 함수를 호출합니다.

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
스플리터 창의 부모 프레임 창입니다.

*nRows*<br/>
행의 수입니다. 이 값은 16을 초과해서는 안 됩니다.

*nCols*<br/>
열의 수입니다. 이 값은 16을 초과해서는 안 됩니다.

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할창이 다른 스플리터 창 내에 중첩되지 않는 한 ID는 AFX_IDW_PANE_FIRST 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

A는 `CSplitterWnd` 일반적으로 다음 `CFrameWnd` 단계를 수행하여 부모 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체에 포함됩니다.

1. 상위 프레임에 `CSplitterWnd` 멤버 변수를 포함합니다.

1. 상위 프레임의 `OnCreateClient` 멤버 함수를 재정의합니다.

1. 재정의된 `CreateStatic` [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)내에서 멤버 함수를 호출합니다.

정적 분할자 창에는 고정된 수의 창이 포함되어 있으며, 종종 다른 클래스에서 발생합니다.

정적 분할자 창을 만들 때 동시에 모든 창을 만들어야 합니다. [CreateView](#createview) 멤버 함수는 일반적으로 이 용도로 사용되지만 다른 비보기 클래스도 만들 수 있습니다.

정적 분할자 창의 초기 최소 행 높이 및 열 너비는 0입니다. 창이 너무 작아 전체로 표시할 수 없는 경우를 결정하는 이러한 최소값은 [SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수를 사용하여 변경할 수 있습니다.

정적 스플리터 창에 스크롤 막대를 추가하려면 WS_HSCROLL 및 WS_VSCROLL 스타일을 *dwStyle에*추가합니다.

[여러 문서 유형, 보기 및 프레임 창,](../../mfc/multiple-document-types-views-and-frame-windows.md) [기술 참고 29](../../mfc/tn029-splitter-windows.md)및 정적 `CSplitterWnd` 분할창에 대한 자세한 내용은 클래스 개요의 "스플리터 Windows"를 참조하십시오.

## <a name="csplitterwndcreateview"></a><a name="createview"></a>C스플리터Wnd::만들기보기

정적 분할자 창에 대한 창을 만듭니다.

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>매개 변수

*행*<br/>
새 뷰를 배치할 스플리터 창 행을 지정합니다.

*col*<br/>
새 뷰를 배치할 분할자 창 열을 지정합니다.

*pView클래스*<br/>
새 뷰의 [CRuntimeClass를](../../mfc/reference/cruntimeclass-structure.md) 지정합니다.

*크기이리트*<br/>
새 뷰의 초기 크기를 지정합니다.

*pContext*<br/>
뷰를 만드는 데 사용되는 생성 컨텍스트에 대한 포인터(일반적으로 *pContext가* 스플리터 창이 생성되는 부모 프레임의 재정의된 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수로 전달됨).

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

프레임워크에 스플리터를 표시하기 전에 정적 분할자 창의 모든 창을 만들어야 합니다.

또한 프레임워크는 동적 스플리터 창의 사용자가 창, 행 또는 열을 분할할 때 새 창을 만들기 위해 이 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

## <a name="csplitterwndcsplitterwnd"></a><a name="csplitterwnd"></a>C스플리터Wnd:::C스플리터Wnd

개체를 생성하기 위해 호출합니다. `CSplitterWnd`

```
CSplitterWnd();
```

### <a name="remarks"></a>설명

두 `CSplitterWnd` 단계로 개체를 생성합니다. 먼저 `CSplitterWnd` 개체를 만드는 생성자 호출 한 다음 splitter 창을 만들고 개체에 연결 하는 [create](#create) `CSplitterWnd` member 함수를 호출 합니다.

## <a name="csplitterwnddeletecolumn"></a><a name="deletecolumn"></a>C스플리터Wnd::DeleteColumn

스플리터 창에서 열을 삭제합니다.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>매개 변수

*콜삭제*<br/>
삭제할 열을 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 동적 스플리터 창의 논리를 구현하기 위해 프레임워크에서 호출됩니다(즉, 스플리터 창에 SPLS_DYNAMIC_SPLIT 스타일이 있는 경우). 그것은 가상 기능 [CreateView와](#createview)함께, 사용자 정의 할 수 있습니다, 더 고급 동적 스플리터를 구현합니다.

## <a name="csplitterwnddeleterow"></a><a name="deleterow"></a>C스플리터Wnd::DeleteRow

스플리터 창에서 행을 삭제합니다.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>매개 변수

*행삭제*<br/>
삭제할 행을 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 동적 스플리터 창의 논리를 구현하기 위해 프레임워크에서 호출됩니다(즉, 스플리터 창에 SPLS_DYNAMIC_SPLIT 스타일이 있는 경우). 그것은 가상 기능 [CreateView와](#createview)함께, 사용자 정의 할 수 있습니다, 더 고급 동적 스플리터를 구현합니다.

## <a name="csplitterwnddeleteview"></a><a name="deleteview"></a>C스플리터Wnd::DeleteView

스플리터 창에서 보기를 삭제합니다.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>매개 변수

*행*<br/>
뷰를 삭제할 스플리터 창 행을 지정합니다.

*col*<br/>
뷰를 삭제할 스플리터 창 열을 지정합니다.

### <a name="remarks"></a>설명

활성 보기가 삭제되는 경우 다음 뷰가 활성화됩니다. 기본 구현에서는 [뷰가 PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)에서 자동으로 삭제된다고 가정합니다.

이 멤버 함수는 동적 스플리터 창의 논리를 구현하기 위해 프레임워크에서 호출됩니다(즉, 스플리터 창에 SPLS_DYNAMIC_SPLIT 스타일이 있는 경우). 그것은 가상 기능 [CreateView와](#createview)함께, 사용자 정의 할 수 있습니다, 더 고급 동적 스플리터를 구현합니다.

## <a name="csplitterwnddokeyboardsplit"></a><a name="dokeyboardsplit"></a>C스플리터Wnd::Do 키보드 스플리트

키보드 분할 명령을 수행합니다(일반적으로 "창 분할").

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 [CView](../../mfc/reference/cview-class.md) 클래스에서 구현에 위임하는 데 `CSplitterWnd` 사용되는 상위 수준 명령입니다.

## <a name="csplitterwnddoscroll"></a><a name="doscroll"></a>C스플리터Wnd::Do스크롤

분할 창의 동기화된 스크롤을 수행합니다.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pViewFrom*<br/>
스크롤 메시지가 시작되는 뷰에 대한 포인터입니다.

*n스크롤 코드*<br/>
사용자의 스크롤 요청을 나타내는 스크롤 바로 표시 줄 코드입니다. 이 매개 변수는 가로로 발생하는 스크롤 유형을 결정하는 낮은 순서바이트와 세로로 발생하는 스크롤 유형을 결정하는 고차 바이트의 두 부분으로 구성됩니다.

- SB_BOTTOM 아래로 스크롤합니다.

- SB_LINEDOWN 한 줄 아래로 스크롤합니다.

- SB_LINEUP 한 줄을 스크롤합니다.

- SB_PAGEDOWN 한 페이지 아래로 스크롤합니다.

- SB_PAGEUP 한 페이지 위로 스크롤합니다.

- SB_TOP 스크롤합니다.

*b도스크롤*<br/>
지정된 스크롤 작업이 발생하는지 여부를 확인합니다. *bDoScroll이* TRUE인 경우(즉, 자식 창이 있는 경우 분할 창에 스크롤 범위가 있는 경우) 지정된 스크롤 작업이 수행될 수 있습니다. *bDoScroll이* FALSE인 경우(즉, 자식 창이 없거나 분할 뷰에 스크롤 범위가 없는 경우) 스크롤이 발생하지 않습니다.

### <a name="return-value"></a>Return Value

동기화된 스크롤이 발생하는 경우 영하지 않습니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 뷰가 스크롤 메시지를 수신할 때 분할 창의 동기화된 스크롤을 수행하기 위해 프레임워크에서 호출됩니다. 동기화된 스크롤이 허용되기 전에 사용자의 작업을 요구하도록 재정의합니다.

## <a name="csplitterwnddoscrollby"></a><a name="doscrollby"></a>C스플리터Wnd::Do스크롤비

지정된 픽셀 수로 분할 창을 스크롤합니다.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pViewFrom*<br/>
스크롤 메시지가 시작되는 뷰에 대한 포인터입니다.

*크기스크롤*<br/>
가로 및 세로로 스크롤할 픽셀 수입니다.

*b도스크롤*<br/>
지정된 스크롤 작업이 발생하는지 여부를 확인합니다. *bDoScroll이* TRUE인 경우(즉, 자식 창이 있는 경우 분할 창에 스크롤 범위가 있는 경우) 지정된 스크롤 작업이 수행될 수 있습니다. *bDoScroll이* FALSE인 경우(즉, 자식 창이 없거나 분할 뷰에 스크롤 범위가 없는 경우) 스크롤이 발생하지 않습니다.

### <a name="return-value"></a>Return Value

동기화된 스크롤이 발생하는 경우 영하지 않습니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 스크롤 메시지에 대한 응답으로 프레임워크에서 호출되어 *sizeScroll*로 표시된 양(픽셀 단위)만큼 분할 창의 동기화된 스크롤을 수행합니다. 양수 값은 아래와 오른쪽으로 스크롤함을 나타냅니다. 음수 값은 위와 왼쪽으로 스크롤함을 나타냅니다.

스크롤을 허용하기 전에 사용자가 작업을 요구하도록 재정의합니다.

## <a name="csplitterwndgetactivepane"></a><a name="getactivepane"></a>C스플리터Wnd::GetActivePane

프레임의 포커스 또는 활성 뷰에서 활성 창을 결정합니다.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>매개 변수

*pRow*<br/>
활성 창의 행 번호를 검색하는 **int에** 대한 포인터입니다.

*pCol*<br/>
활성 창의 열 번호를 검색하는 **int에** 대한 포인터입니다.

### <a name="return-value"></a>Return Value

활성 창에 대한 포인터입니다. 활성 창이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 스플리터 창에서 활성 창을 결정하기 위해 프레임워크에서 호출됩니다. 활성 창을 얻기 전에 사용자가 작업을 요구하도록 재정의합니다.

## <a name="csplitterwndgetcolumncount"></a><a name="getcolumncount"></a>C스플리터Wnd::GetColumnCount

현재 창 열 수를 반환합니다.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>Return Value

스플리터의 현재 열 수를 반환합니다. 정적 스플리터의 경우 최대 열 수이기도 합니다.

## <a name="csplitterwndgetcolumninfo"></a><a name="getcolumninfo"></a>C스플리터Wnd::GetColumnInfo

지정된 열에 대한 정보를 반환합니다.

```cpp
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>매개 변수

*col*<br/>
열을 지정합니다.

*cxCur*<br/>
열의 현재 너비로 설정할 **int에** 대한 참조입니다.

*cxMin*<br/>
열의 현재 최소 너비로 설정할 **int에** 대한 참조입니다.

## <a name="csplitterwndgetpane"></a><a name="getpane"></a>C스플리터Wnd::GetPane

지정된 행 과 열에서 창을 반환합니다.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>매개 변수

*행*<br/>
행을 지정합니다.

*col*<br/>
열을 지정합니다.

### <a name="return-value"></a>Return Value

지정된 행 과 열에서 창을 반환합니다. 반환된 창은 일반적으로 [CView](../../mfc/reference/cview-class.md)-파생 클래스입니다.

## <a name="csplitterwndgetrowcount"></a><a name="getrowcount"></a>C스플리터Wnd::GetRowCount

현재 창 행 수를 반환합니다.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Return Value

스플리터 창에서 현재 행 수를 반환합니다. 정적 분할자 창의 경우 최대 행 수이기도 합니다.

## <a name="csplitterwndgetrowinfo"></a><a name="getrowinfo"></a>C스플리터Wnd::GetRowInfo

지정된 행에 대한 정보를 반환합니다.

```cpp
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>매개 변수

*행*<br/>
행을 지정합니다.

*사이커*<br/>
픽셀 단위로 행의 현재 높이로 설정할 **int에** 대한 참조입니다.

*시민 (것)에 의해*<br/>
픽셀 단위로 행의 현재 최소 높이로 설정할 **int에** 대한 참조입니다.

### <a name="remarks"></a>설명

지정된 행에 대한 정보를 가져오려면 이 멤버 함수를 호출합니다. *cyCur* 매개변수는 지정된 행의 현재 높이로 채워지고 *cyMin은* 행의 최소 높이로 채워져 있습니다.

## <a name="csplitterwndgetscrollstyle"></a><a name="getscrollstyle"></a>C스플리터Wnd::Get스크롤 스타일

스플리터 창에 대한 공유 스크롤 막대 스타일을 반환합니다.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 다음 창 스타일 플래그 중 하나 이상이 표시됩니다.

- WS_HSCROLL 스플리터가 현재 공유 가로 스크롤 막대를 관리하는 경우.

- WS_VSCROLL 스플리터가 현재 공유 세로 스크롤 막대를 관리하는 경우.

0이면 스플리터 창은 현재 공유 스크롤 막대를 관리하지 않습니다.

## <a name="csplitterwndidfromrowcol"></a><a name="idfromrowcol"></a>C스플리터Wnd::IdFromRowCol

지정된 행 및 열에서 창에 대한 자식 창 ID를 가져옵니다.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>매개 변수

*행*<br/>
스플리터 창 행을 지정합니다.

*col*<br/>
스플리터 창 열을 지정합니다.

### <a name="return-value"></a>Return Value

창의 자식 창 ID입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 비뷰를 창으로 만드는 데 사용되며 창이 존재하기 전에 호출될 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

## <a name="csplitterwndischildpane"></a><a name="ischildpane"></a>C스플리터Wnd::이차일드파인

*pWnd가* 현재 이 스플리터 창의 자식 창인지 여부를 결정합니다.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
테스트할 CWnd 개체에 대한 [포인터입니다.](../../mfc/reference/cwnd-class.md)

*pRow*<br/>
행 번호를 저장할 **int에** 대한 포인터입니다.

*pCol*<br/>
열 번호를 저장할 **int에** 대한 포인터입니다.

### <a name="return-value"></a>Return Value

영하지 않은 경우 *pWnd는* 현재 이 스플리터 창의 자식 창이고 *pRow* 및 *pCol은* 스플리터 창의 창 위치로 채워집니다. *pWnd가* 이 스플리터 창의 자식 창이 아닌 경우 0이 반환됩니다.

### <a name="remarks"></a>설명

6.0 이전의 Visual C++ 버전에서는 이 함수가

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

이 버전은 이제 더 이상 사용되지 않으며 사용할 수 없습니다.

## <a name="csplitterwndistracking"></a><a name="istracking"></a>C스플리터Wnd::추적

이 멤버 함수를 호출하여 창의 스플리터 막대가 현재 이동중인지 확인합니다.

```
BOOL IsTracking();
```

### <a name="return-value"></a>Return Value

스플리터 작업이 진행 중인 경우 0이 아닌 경우; 그렇지 않으면 0.

## <a name="csplitterwndondrawsplitter"></a><a name="ondrawsplitter"></a>C스플리터Wnd::온드로우 스플리터

분할 창의 이미지를 렌더링합니다.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그릴 장치 컨텍스트에 대한 포인터입니다. *pDC가* NULL이면 [CWnd::RedrawWindow가](../../mfc/reference/cwnd-class.md#redrawwindow) 프레임워크에서 호출되고 분할 창이 그려지지 않습니다.

*nType*<br/>
의 값은 `enum ESplitType`다음 중 하나가 될 수 있습니다.

- `splitBox`스플리터 드래그 상자입니다.

- `splitBar`두 분할 창 사이에 나타나는 막대입니다.

- `splitIntersection`분할 창의 교차점입니다. Windows 95/98에서 실행할 때이 요소가 호출 되지 않습니다.

- `splitBorder`분할 창 테두리입니다.

*rect*<br/>
분할 창의 크기와 모양을 지정하는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 스플리터 창의 정확한 특성을 그리고 지정하기 위해 프레임워크에서 호출됩니다. 스플리터 창의 다양한 그래픽 구성 요소에 대한 이미지의 고급 사용자 지정을 위해 재정의합니다. `OnDrawSplitter` 기본 이미지는 스플리터 바의 교차점이 함께 혼합된다는 점에서, 윈도우 또는 마이크로 소프트 윈도우 95/98에 대한 마이크로 소프트 의 스플리터와 유사하다.

동적 분할창에 대한 자세한 내용은 [문서 여러 문서 유형, 보기 및 프레임 창,](../../mfc/multiple-document-types-views-and-frame-windows.md)기술 참고 `CSplitterWnd` [29](../../mfc/tn029-splitter-windows.md)및 클래스 개요의 "Splitter Windows"를 참조하십시오.

## <a name="csplitterwndoninverttracker"></a><a name="oninverttracker"></a>C스플리터Wnd::온인버트트래커

분할 창의 이미지를 프레임 창과 동일한 크기 및 모양으로 렌더링합니다.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
추적 사각형을 `CRect` 지정하는 개체를 참조합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 스플리터 의 크기 조정 중에 프레임워크에서 호출됩니다. 스플리터 창의 이미지의 고급 사용자 지정을 위해 재정의합니다. `OnInvertTracker` 기본 이미지는 스플리터 바의 교차점이 함께 혼합된다는 점에서, 윈도우 또는 마이크로 소프트 윈도우 95/98에 대한 마이크로 소프트 의 스플리터와 유사하다.

동적 분할창에 대한 자세한 내용은 [문서 여러 문서 유형, 보기 및 프레임 창,](../../mfc/multiple-document-types-views-and-frame-windows.md)기술 참고 `CSplitterWnd` [29](../../mfc/tn029-splitter-windows.md)및 클래스 개요의 "Splitter Windows"를 참조하십시오.

## <a name="csplitterwndrecalclayout"></a><a name="recalclayout"></a>C스플리터Wnd::리콜크 레이아웃

행 또는 열 크기를 조정한 후 스플리터 창을 다시 표시하려면 호출합니다.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>설명

[SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수를 사용하여 행 및 열 크기를 조정한 후 이 멤버 함수를 호출하여 스플리터 창을 올바르게 다시 표시합니다. 스플리터 창이 표시되기 전에 생성 프로세스의 일부로 행 및 열 크기를 변경하는 경우 이 멤버 함수를 호출할 필요가 없습니다.

프레임워크는 사용자가 스플리터 창의 크기를 조정하거나 분할을 이동할 때마다 이 멤버 함수를 호출합니다.

### <a name="example"></a>예제

  [CSplitterWnd::SetColumnInfo에](#setcolumninfo)대한 예제를 참조하십시오.

## <a name="csplitterwndsetactivepane"></a><a name="setactivepane"></a>C스플리터Wnd::설정액티브파인

창을 프레임의 활성 창으로 설정합니다.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*행*<br/>
*pWnd가* NULL이면 활성화될 창의 행을 지정합니다.

*col*<br/>
*pWnd가* NULL이면 활성화될 창의 열을 지정합니다.

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다. NULL이면 *행* 과 *col에* 의해 지정된 창이 활성으로 설정됩니다. NULL이 아닌 경우 활성으로 설정된 창을 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용자가 프레임 창 내의 창으로 포커스를 변경할 때 창을 활성으로 설정하기 위해 프레임워크에서 호출됩니다. 명시적으로 호출하여 `SetActivePane` 포커스를 지정된 뷰로 변경할 수 있습니다.

행과 열을 **제공하거나** *pWnd*를 제공하여 창을 지정합니다.

## <a name="csplitterwndsetcolumninfo"></a><a name="setcolumninfo"></a>C스플리터Wnd::SetColumnInfo

호출하여 지정된 열 정보를 설정합니다.

```cpp
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>매개 변수

*col*<br/>
스플리터 창 열을 지정합니다.

*cx이상적*<br/>
스플리터 창 열에 대한 이상적인 너비를 픽셀 단위로 지정합니다.

*cxMin*<br/>
스플리터 창 열의 최소 너비를 픽셀 단위로 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 열에 대한 새 최소 너비와 이상적인 너비를 설정합니다. 열 최소값은 열이 너무 작아서 완전히 표시되지 않을 때를 결정합니다.

프레임워크에 스플리터 창이 표시되면 이상적인 차원에 따라 열과 행에 창이 배치되고 왼쪽 위부터 스플리터 창의 클라이언트 영역의 오른쪽 아래 모서리까지 작업합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

## <a name="csplitterwndsetrowinfo"></a><a name="setrowinfo"></a>C스플리터Wnd::SetRowInfo

호출하여 지정된 행 정보를 설정합니다.

```cpp
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>매개 변수

*행*<br/>
스플리터 창 행을 지정합니다.

*사이 이상적*<br/>
스플리터 창 행에 대해 픽셀 단위로 이상적인 높이를 지정합니다.

*시민 (것)에 의해*<br/>
스플리터 창 행의 최소 높이를 픽셀 단위로 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출하여 행에 대한 새 최소 높이와 이상적인 높이를 설정합니다. 행 최소값은 행이 너무 작아서 완전히 표시되지 않을 때를 결정합니다.

프레임워크에 스플리터 창이 표시되면 이상적인 차원에 따라 열과 행에 창이 배치되고 왼쪽 위부터 스플리터 창의 클라이언트 영역의 오른쪽 아래 모서리까지 작업합니다.

## <a name="csplitterwndsetscrollstyle"></a><a name="setscrollstyle"></a>C스플리터Wnd::세트스크롤 스타일

스플리터 창의 공유 스크롤 막대 지원에 대한 새 스크롤 스타일을 지정합니다.

```cpp
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
스플리터 창의 공유 스크롤 막대 지원에 대한 새 스크롤 스타일은 다음 값 중 하나가 될 수 있습니다.

- WS_HSCROLL 가로 공유 스크롤 막대 만들기/표시합니다.

- WS_VSCROLL 세로 공유 스크롤 막대 만들기/표시합니다.

### <a name="remarks"></a>설명

스크롤 막대가 만들어지면 해당 스타일없이 호출되더라도 `SetScrollStyle` 소멸되지 않습니다. 대신 스크롤 막대가 숨김이 있습니다. 이렇게 하면 스크롤 막대가 숨겨져 있더라도 상태를 유지할 수 있습니다. 호출 `SetScrollStyle` 후 모든 변경 내용을 적용 하려면 [RecalcLayout호출](#recalclayout) 해야 합니다.

## <a name="csplitterwndsplitcolumn"></a><a name="splitcolumn"></a>C스플리터Wnd::분할열

프레임 창이 세로로 분할되는 위치를 나타냅니다.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>매개 변수

*cx이전*<br/>
분할이 발생하기 전에 픽셀 단위로 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 수직 분할자 창이 만들어질 때 호출됩니다. `SplitColumn`은 분할이 발생하는 기본 위치를 나타냅니다.

`SplitColumn`동적 분할자 창의 논리를 구현 하기 위해 프레임 워크에 의해 호출 됩니다 (즉, 분할자 창SPLS_DYNAMIC_SPLIT 스타일). 그것은 가상 기능 [CreateView와](#createview)함께, 사용자 정의 할 수 있습니다, 더 고급 동적 스플리터를 구현합니다.

## <a name="csplitterwndsplitrow"></a><a name="splitrow"></a>C스플리터Wnd::스플리트로우

프레임 창이 가로로 분할되는 위치를 나타냅니다.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>매개 변수

*사이 전에*<br/>
분할이 발생하기 전에 픽셀 단위로 위치입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 수평 분할자 창이 만들어질 때 호출됩니다. `SplitRow`은 분할이 발생하는 기본 위치를 나타냅니다.

`SplitRow`동적 분할자 창의 논리를 구현 하기 위해 프레임 워크에 의해 호출 됩니다 (즉, 분할자 창SPLS_DYNAMIC_SPLIT 스타일). 그것은 가상 기능 [CreateView와](#createview)함께, 사용자 정의 할 수 있습니다, 더 고급 동적 스플리터를 구현합니다.

## <a name="csplitterwndondraw"></a><a name="ondraw"></a>C스플리터Wnd::온드로우

스플리터 창을 그리는 프레임 워크에 의해 호출 됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
디바이스 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[MFC 샘플 뷰렉스](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
