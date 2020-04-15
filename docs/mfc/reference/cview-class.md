---
title: CView 클래스
ms.date: 11/04/2016
f1_keywords:
- CView
- AFXWIN/CView
- AFXWIN/CView::CView
- AFXWIN/CView::DoPreparePrinting
- AFXWIN/CView::GetDocument
- AFXWIN/CView::IsSelected
- AFXWIN/CView::OnDragEnter
- AFXWIN/CView::OnDragLeave
- AFXWIN/CView::OnDragOver
- AFXWIN/CView::OnDragScroll
- AFXWIN/CView::OnDrop
- AFXWIN/CView::OnDropEx
- AFXWIN/CView::OnInitialUpdate
- AFXWIN/CView::OnPrepareDC
- AFXWIN/CView::OnScroll
- AFXWIN/CView::OnScrollBy
- AFXWIN/CView::OnActivateFrame
- AFXWIN/CView::OnActivateView
- AFXWIN/CView::OnBeginPrinting
- AFXWIN/CView::OnDraw
- AFXWIN/CView::OnEndPrinting
- AFXWIN/CView::OnEndPrintPreview
- AFXWIN/CView::OnPreparePrinting
- AFXWIN/CView::OnPrint
- AFXWIN/CView::OnUpdate
helpviewer_keywords:
- CView [MFC], CView
- CView [MFC], DoPreparePrinting
- CView [MFC], GetDocument
- CView [MFC], IsSelected
- CView [MFC], OnDragEnter
- CView [MFC], OnDragLeave
- CView [MFC], OnDragOver
- CView [MFC], OnDragScroll
- CView [MFC], OnDrop
- CView [MFC], OnDropEx
- CView [MFC], OnInitialUpdate
- CView [MFC], OnPrepareDC
- CView [MFC], OnScroll
- CView [MFC], OnScrollBy
- CView [MFC], OnActivateFrame
- CView [MFC], OnActivateView
- CView [MFC], OnBeginPrinting
- CView [MFC], OnDraw
- CView [MFC], OnEndPrinting
- CView [MFC], OnEndPrintPreview
- CView [MFC], OnPreparePrinting
- CView [MFC], OnPrint
- CView [MFC], OnUpdate
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
ms.openlocfilehash: 763e36b0736ce588e7e2aded25e50347f9e0ca70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373197"
---
# <a name="cview-class"></a>CView 클래스

사용자 정의 뷰 클래스에 대한 기본 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CView : public CWnd
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[C보기::C보기](#cview)|`CView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CView::Doprepareprinting](#doprepareprinting)|[복사상자] 인쇄 를 표시하고 프린터 장치 컨텍스트를 만듭니다. 멤버 함수를 `OnPreparePrinting` 재정의할 때 호출합니다.|
|[C보기::GetDocument](#getdocument)|뷰와 연결된 문서를 반환합니다.|
|[C보기::선택됨](#isselected)|문서 항목이 선택되었는지 여부를 테스트합니다. OLE 지원에 필요합니다.|
|[C보기::에 드래그 엔터](#ondragenter)|항목이 뷰의 끌어서 놓기 영역으로 처음 드래그될 때 호출됩니다.|
|[C보기::에 드래그 리브](#ondragleave)|드래그된 항목이 뷰의 끌어서 놓기 영역을 떠날 때 호출됩니다.|
|[C보기::에 드래그 오버](#ondragover)|뷰의 끌어서 놓기 영역 위로 항목을 드래그할 때 호출됩니다.|
|[C보기::온드래그스크롤](#ondragscroll)|커서가 창의 스크롤 영역으로 드래그되는지 여부를 결정하기 위해 호출됩니다.|
|[C보기::드롭](#ondrop)|항목이 뷰의 끌어서 놓기 영역인 기본 처리기에 놓아도 호출됩니다.|
|[C보기::온드롭엑스](#ondropex)|항목이 뷰의 끌어서 놓기 영역에 삭제된 경우 호출됩니다.|
|[C보기::초기 업데이트](#oninitialupdate)|뷰가 문서에 먼저 첨부된 후에 호출됩니다.|
|[C보기::온준비DC](#onpreparedc)|화면 표시를 `OnDraw` 위해 멤버 함수가 `OnPrint` 호출되기 전에 호출하거나 멤버 함수가 인쇄 또는 인쇄 미리 보기를 위해 호출됩니다.|
|[C보기::온스크롤](#onscroll)|OLE 항목이 뷰의 테두리를 넘어 드래그될 때 호출됩니다.|
|[C보기::온스크롤비](#onscrollby)|활성 내부 OLE 항목이 포함된 뷰가 스크롤될 때 호출됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C보기::온인스로이스프레임](#onactivateframe)|뷰를 포함하는 프레임 창이 활성화되거나 비활성화될 때 호출됩니다.|
|[C보기::온인스로뷰](#onactivateview)|뷰가 활성화될 때 호출됩니다.|
|[CView::OnBeginPrinting](#onbeginprinting)|인쇄 작업이 시작될 때 호출됩니다. 재정의하여 GDI(그래픽 장치 인터페이스) 리소스를 할당합니다.|
|[C보기::에 그리기](#ondraw)|화면 표시, 인쇄 또는 인쇄 미리 보기를 위해 문서 이미지를 렌더링하기 위해 호출됩니다. 구현이 필요합니다.|
|[C보기::온엔드 프린팅](#onendprinting)|인쇄 작업이 끝날 때 호출됩니다. 재정의하여 GDI 리소스를 할당 할 수 있습니다.|
|[C보기::온엔드프린트프리뷰](#onendprintpreview)|미리 보기 모드가 종료될 때 호출됩니다.|
|[C보기::온준비 인쇄](#onprepareprinting)|문서를 인쇄하거나 미리 보기 전에 호출됩니다. 재정의하여 인쇄 대화 상자를 초기화합니다.|
|[C보기::온프린트](#onprint)|문서 페이지를 인쇄하거나 미리 보기 위해 호출됩니다.|
|[C보기::에 업데이트](#onupdate)|해당 문서가 수정되었음을 뷰에 알리기 위해 호출됩니다.|

## <a name="remarks"></a>설명

뷰는 문서에 첨부되고 문서와 사용자 간의 중개자 역할을 합니다: 뷰는 화면 또는 프린터에서 문서의 이미지를 렌더링하고 사용자 입력을 문서의 작업으로 해석합니다.

뷰는 프레임 창의 자식입니다. 스플리터 창의 경우와 같이 두 개 이상의 뷰가 프레임 창을 공유할 수 있습니다. 뷰 클래스, 프레임 창 클래스 및 문서 클래스 간의 관계는 `CDocTemplate` 개체에 의해 설정됩니다. 사용자가 새 창을 열거나 기존 창을 분할하면 프레임워크는 새 뷰를 구성하고 문서에 연결합니다.

뷰는 하나의 문서에만 첨부할 수 있지만 문서가 분할 창또는 여러 MDI(문서 인터페이스) 응용 프로그램의 여러 하위 창에 표시되는 경우와 같은 여러 뷰를 한 번에 여러 뷰가 첨부할 수 있습니다. 응용 프로그램은 지정된 문서 유형에 대해 다양한 유형의 보기를 지원할 수 있습니다. 예를 들어 워드 프로세싱 프로그램은 문서의 전체 텍스트 보기와 단면 머리글만 표시하는 개요 보기를 모두 제공할 수 있습니다. 스플리터 창을 사용하는 경우 이러한 다양한 유형의 뷰를 별도의 프레임 창이나 단일 프레임 창의 별도 창에 배치할 수 있습니다.

뷰는 키보드 입력, 마우스 입력 또는 드래그 앤 드롭을 통한 입력과 같은 여러 가지 유형의 입력과 메뉴, 도구 모음 또는 스크롤 막대의 명령을 처리하는 역할을 할 수 있습니다. 뷰는 프레임 창으로 전달된 명령을 수신합니다. 뷰에서 지정된 명령을 처리하지 않으면 해당 명령이 연결된 문서로 전달됩니다. 모든 명령 대상과 마찬가지로 뷰는 메시지 맵을 통해 메시지를 처리합니다.

뷰는 문서의 데이터를 표시하고 수정할 책임이 있지만 문서 의 데이터를 저장하는 것은 담당하지 않습니다. 문서는 뷰에 데이터에 대한 필요한 세부 정보를 제공합니다. 뷰가 문서의 데이터 멤버에 직접 액세스하도록 허용하거나 뷰 클래스가 호출할 문서 클래스의 멤버 함수를 제공할 수 있습니다.

문서의 데이터가 변경되면 변경 을 담당하는 뷰는 일반적으로 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews) 함수를 호출하며, 이 함수는 각 `OnUpdate` 문서에 대해 멤버 함수를 호출하여 다른 모든 뷰에 알부릅니다. 기본 구현은 `OnUpdate` 뷰의 전체 클라이언트 영역을 무효화합니다. 재정의를 사용하여 문서의 수정된 부분에 매핑되는 클라이언트 영역의 해당 영역만 무효화할 수 있습니다.

을 `CView`사용하려면 클래스를 파생시키고 `OnDraw` 멤버 함수를 구현하여 화면 표시를 수행합니다. 인쇄 및 `OnDraw` 인쇄 미리 보기를 수행하는 데 사용할 수도 있습니다. 프레임워크는 문서를 인쇄하고 미리 보기 위한 인쇄 루프를 처리합니다.

뷰는 [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수를 통해 스크롤 막대 메시지를 처리합니다. 이러한 함수에서 스크롤 막대 메시지 처리를 구현하거나 파생 `CView` 클래스 [CScrollView를](../../mfc/reference/cscrollview-class.md) 사용하여 스크롤을 처리할 수 있습니다.

게다가 `CScrollView`Microsoft 재단 클래스 라이브러리는 다음에서 `CView`파생된 9개의 다른 클래스를 제공합니다.

- [CCtrlView](../../mfc/reference/cctrlview-class.md)- 트리, 목록 및 풍부한 편집 컨트롤이 있는 보기 아키텍처 - 문서 사용을 허용하는 보기입니다.

- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 보기입니다.

- [CEditView](../../mfc/reference/ceditview-class.md): 간단한 다중 줄 텍스트 편집기제공 보기입니다. 개체를 `CEditView` 대화 상자의 컨트롤과 문서의 보기로 사용할 수 있습니다.

- [CFormView](../../mfc/reference/cformview-class.md)- 대화 상자 컨트롤을 포함하 고 대화 상자 템플릿 리소스를 기반으로 하는 스크롤 가능한 보기입니다.

- [CListView](../../mfc/reference/clistview-class.md)- 문서 사용을 허용하는 보기 - 목록 컨트롤이 있는 보기 아키텍처입니다.

- [CRecordView](../../mfc/reference/crecordview-class.md)대화 상자 컨트롤에 데이터베이스 레코드를 표시 하는 보기입니다.

- [CRichEditView](../../mfc/reference/cricheditview-class.md)- 풍부한 편집 컨트롤이 있는 뷰 아키텍처 - 문서 사용을 허용하는 보기입니다.

- [CScrollView](../../mfc/reference/cscrollview-class.md)- 스크롤 지원을 자동으로 제공하는 보기입니다.

- [CTreeView](../../mfc/reference/ctreeview-class.md)- 트리 컨트롤이 있는 뷰 아키텍처 - 문서 사용을 허용하는 보기입니다.

`CView` 클래스에는 인쇄 미리 보기를 수행하는 `CPreviewView`데 프레임워크에서 사용되는 파생 구현 클래스도 있습니다. 이 클래스는 도구 모음, 단일 또는 이중 페이지 미리 보기 및 확대/축소, 즉 미리 보기 이미지를 확대하는 등 인쇄 미리 보기 창에 고유한 기능을 지원합니다. 인쇄 미리 보기(예: 인쇄 미리 `CPreviewView`보기 모드에서 편집을 지원하려는 경우)를 위해 고유한 인터페이스를 구현하려는 경우가 아니면 멤버 함수를 호출하거나 재정의할 필요가 없습니다. 사용에 `CView`대한 자세한 내용은 [문서/아키텍처 보기](../../mfc/document-view-architecture.md) 및 [인쇄](../../mfc/printing.md)를 참조하십시오. 또한 인쇄 미리 보기 사용자 지정에 대한 자세한 내용은 [기술 참고 30을](../../mfc/tn030-customizing-printing-and-print-preview.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cviewcview"></a><a name="cview"></a>C보기::C보기

`CView` 개체를 생성합니다.

```
CView();
```

### <a name="remarks"></a>설명

프레임워크는 새 프레임 창이 만들어지거나 창이 분할될 때 생성자입니다. 문서가 연결된 후 뷰를 초기화하려면 [OnInitialUpdate](#oninitialupdate) 멤버 함수를 재정의합니다.

## <a name="cviewdoprepareprinting"></a><a name="doprepareprinting"></a>CView::Doprepareprinting

[OnPreparePrinting](#onprepareprinting) 의 재정의에서 이 함수를 호출하여 인쇄 대화 상자를 호출하고 프린터 장치 컨텍스트를 만듭니다.

```
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="return-value"></a>Return Value

인쇄 또는 인쇄 미리 보기를 시작할 수 있는 경우 0이 아닙니다. 작업이 취소된 경우 0입니다.

### <a name="remarks"></a>설명

이 함수의 동작은 인쇄 또는 인쇄 미리 보기(pInfo `m_bPreview` 매개 변수의 멤버에 의해 지정됨)에 대해 호출되는지 여부에 따라 달라집니다. *pInfo* 파일이 인쇄되는 경우 이 함수는 *pInfo가* 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조의 값을 사용하여 인쇄 대화 상자를 호출합니다. 사용자가 대화 상자를 닫은 후 함수는 대화 상자에 지정된 설정에 따라 프린터 장치 컨텍스트를 만들고 *pInfo* 매개 변수를 통해 이 장치 컨텍스트를 반환합니다. 이 장치 컨텍스트는 문서를 인쇄하는 데 사용됩니다.

파일을 미리 보고 있는 경우 이 함수는 현재 프린터 설정을 사용하여 프린터 장치 컨텍스트를 만듭니다. 이 장치 컨텍스트는 미리 보기 중에 프린터를 시뮬레이션하는 데 사용됩니다.

## <a name="cviewgetdocument"></a><a name="getdocument"></a>C보기::GetDocument

이 함수를 호출하여 뷰의 문서에 대한 포인터를 가져옵니다.

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>Return Value

뷰와 연결된 [CDocument](../../mfc/reference/cdocument-class.md) 개체에 대한 포인터입니다. 뷰가 문서에 첨부되지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

이렇게 하면 문서의 멤버 함수를 호출할 수 있습니다.

## <a name="cviewisselected"></a><a name="isselected"></a>C보기::선택됨

프레임워크에서 호출하여 지정된 문서 항목이 선택되었는지 여부를 확인합니다.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>매개 변수

*pDoc항목*<br/>
테스트 중인 문서 항목을 가리킵니다.

### <a name="return-value"></a>Return Value

지정된 문서 항목을 선택한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 FALSE를 반환합니다. [CDocItem 개체를](../../mfc/reference/cdocitem-class.md) 사용하여 선택을 구현하는 경우 이 함수를 재정의합니다. 보기에 OLE 항목이 포함된 경우 이 함수를 재정의해야 합니다.

## <a name="cviewonactivateframe"></a><a name="onactivateframe"></a>C보기::온인스로이스프레임

뷰를 포함하는 프레임 창이 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.

```
virtual void OnActivateFrame(
    UINT nState,
    CFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
프레임 창이 활성화 또는 비활성화되는지 여부를 지정합니다. 다음 값 중 하나일 수 있습니다.

- WA_INACTIVE 프레임 창이 비활성화되고 있습니다.

- WA_ACTIVE 프레임 창은 마우스 클릭 이외의 일부 방법을 통해 활성화되고 있습니다(예: 키보드 인터페이스를 사용하여 창을 선택).

- WA_CLICKACTIVE 프레임 창이 마우스 클릭으로 활성화됨

*pFrameWnd*<br/>
활성화할 프레임 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

뷰와 연결된 프레임 창이 활성화되거나 비활성화될 때 특별한 처리를 수행하려는 경우 이 멤버 함수를 재정의합니다. 예를 들어 [CFormView는](../../mfc/reference/cformview-class.md) 포커스가 있는 컨트롤을 저장하고 복원할 때 이 재정의를 수행합니다.

## <a name="cviewonactivateview"></a><a name="onactivateview"></a>C보기::온인스로뷰

뷰가 활성화되거나 비활성화될 때 프레임워크에서 호출됩니다.

```
virtual void OnActivateView(
    BOOL bActivate,
    CView* pActivateView,
    CView* pDeactiveView);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
뷰가 활성화 또는 비활성화되고 있는지 여부를 나타냅니다.

*p활성화보기*<br/>
활성화 중인 뷰 오브젝트를 가리킵니다.

*p데액티브뷰*<br/>
비활성화되는 뷰 객체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 활성화되는 뷰에 포커스를 설정합니다. 뷰가 활성화되거나 비활성화될 때 특수 처리를 수행하려는 경우 이 함수를 재정의합니다. 예를 들어 활성 뷰와 비활성 뷰를 구분하는 특수 시각적 신호를 제공하려는 경우 *bActivate* 매개 변수를 검사하고 그에 따라 뷰의 모양을 업데이트합니다.

*pActivateView* 및 *pDeactiveView* 매개 변수는 응용 프로그램의 주 프레임 창이 활성 보기의 변경 없이 활성화되는 경우(예: 포커스가 응용 프로그램 내의 한 보기에서 다른 보기로 전송되는 경우 또는 MDI 자식 창 간에 전환할 때)를 가리킵니다. 이렇게 하면 필요한 경우 뷰에서 해당 팔레트를 다시 실현할 수 있습니다.

이러한 매개 변수는 [CFrameWnd::GetActiveView반환하는](../../mfc/reference/cframewnd-class.md#setactiveview) 것과 다른 뷰로 호출될 때 다릅니다. [CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview) 이 작업은 스플리터 창에서 가장 자주 발생합니다.

## <a name="cviewonbeginprinting"></a><a name="onbeginprinting"></a>C보기::시작 인쇄

`OnPreparePrinting` 이 호출된 후 인쇄 또는 인쇄 미리 보기 작업을 시작할 때 프레임워크에서 호출됩니다.

```
virtual void OnBeginPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 인쇄용으로 특별히 필요한 GDI 리소스(예: 펜 또는 글꼴)를 할당하려면 이 함수를 재정의합니다. GDI 개체를 사용하는 각 페이지에 대한 [OnPrint](#onprint) 멤버 함수 내에서 디바이스 컨텍스트로 GDI 개체를 선택합니다. 동일한 view 개체를 사용하여 화면 표시와 인쇄를 모두 수행하는 경우 각 화면 표시에 필요한 GDI 리소스에 별도의 변수를 사용합니다. 이렇게 하면 인쇄하는 동안 화면을 업데이트할 수 있습니다.

또한 이 함수를 사용하여 프린터 디바이스 컨텍스트의 속성에 따라 초기화를 수행할 수 있습니다. 예를 들어 문서를 인쇄하는 데 필요한 페이지 수는 사용자가 인쇄 대화 상자에서 지정한 설정(예: 페이지 길이)에 따라 다를 수 있습니다. 이러한 상황에서는 일반적인 경우와 달리 [OnPreparePrinting](#onprepareprinting) 멤버 함수에서 문서 길이를 지정할 수 없습니다. 대화 상자 설정에 따라 프린터 디바이스 컨텍스트가 만들어질 때까지 기다려야 합니다. [OnBeginPrinting](#onbeginprinting) 은 프린터 디바이스 컨텍스트를 나타내는 [CDC](../../mfc/reference/cdc-class.md) 개체에 대한 액세스를 제공하는 첫 번째 재정의 가능 함수이므로 이 함수에서 문서 길이를 설정할 수 있습니다. 이때까지 문서 길이를 지정하지 않으면 인쇄 미리 보기 중에 스크롤 막대가 표시되지 않습니다.

## <a name="cviewondragenter"></a><a name="ondragenter"></a>C보기::에 드래그 엔터

마우스가 먼저 놓기 대상 창의 비 스크롤 영역을 입력할 때 프레임워크에서 호출됩니다.

```
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
뷰의 놓기 영역으로 드래그되는 [COleDataObject를](../../mfc/reference/coledataobject-class.md) 가리킵니다.

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
뷰의 클라이언트 영역을 기준으로 한 현재 마우스 위치입니다.

### <a name="return-value"></a>Return Value

사용자가 이 위치에서 개체를 삭제한 경우 발생할 수 있는 드롭 유형을 나타내는 DROPEFFECT 지정 형식의 값입니다. 드롭 유형은 일반적으로 *dwKeyState*로 표시된 현재 키 상태에 따라 달라집니다. DROPEFFECT 값에 대한 키 상태의 표준 매핑은 다음과 입니다.

- DROPEFFECT_NONE 이 창에서 데이터 개체를 삭제할 수 없습니다.

- MK_CONTROL &#124; MK_SHIFT DROPEFFECT_LINK 개체와 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL 삭제된 개체의 복사본을 만듭니다.

- MK_ALT DROPEFFECT_MOVE 삭제된 개체의 복사본을 만들고 원래 개체를 삭제합니다. 이는 일반적으로 뷰에서 이 데이터 개체를 허용할 수 있는 기본 놓기 효과입니다.

자세한 내용은 MFC 고급 개념 샘플 [OCLIENT를](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="remarks"></a>설명

기본 구현은 아무 것도 하지 않으며 DROPEFFECT_NONE 반환하는 것입니다.

[OnDragOver](#ondragover) 멤버 함수에 대한 향후 호출을 준비하려면 이 함수를 재정의합니다. `OnDragOver` 나중에 멤버 함수에서 사용할 수 있는 데이터 개체에서 필요한 모든 데이터를 이 시점에서 검색해야 합니다. 이 때 사용자에게 시각적 피드백을 제공하기 위해 보기도 업데이트해야 합니다. 자세한 내용은 [OLE 끌어 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)문서를 참조하십시오.

## <a name="cviewondragleave"></a><a name="ondragleave"></a>C보기::에 드래그 리브

마우스가 해당 창의 유효한 놓기 영역 밖으로 이동될 때 끌기 작업 중에 프레임워크에서 호출됩니다.

```
virtual void OnDragLeave();
```

### <a name="remarks"></a>설명

현재 뷰가 [OnDragEnter](#ondragenter) 또는 [OnDragOver](#ondragover) 호출 중에 수행된 작업을 정리해야 하는 경우 개체를 드래그앤드롭하는 동안 시각적 사용자 피드백을 제거하는 등 이 함수를 재정의합니다.

## <a name="cviewondragover"></a><a name="ondragover"></a>C보기::에 드래그 오버

마우스가 놓기 대상 창 위로 이동될 때 끌기 작업 중에 프레임워크에서 호출됩니다.

```
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
드롭 대상 위로 드래그되는 [COleDataObject를](../../mfc/reference/coledataobject-class.md) 가리킵니다.

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
뷰 클라이언트 영역을 기준으로 한 현재 마우스 위치입니다.

### <a name="return-value"></a>Return Value

사용자가 이 위치에서 개체를 삭제한 경우 발생할 수 있는 드롭 유형을 나타내는 DROPEFFECT 지정 형식의 값입니다. 드롭 유형은 *dwKeyState*에 표시된 현재 키 상태에 따라 달라지는 경우가 많습니다. DROPEFFECT 값에 대한 키 상태의 표준 매핑은 다음과 입니다.

- DROPEFFECT_NONE 이 창에서 데이터 개체를 삭제할 수 없습니다.

- MK_CONTROL &#124; MK_SHIFT DROPEFFECT_LINK 개체와 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL 삭제된 개체의 복사본을 만듭니다.

- MK_ALT DROPEFFECT_MOVE 삭제된 개체의 복사본을 만들고 원래 개체를 삭제합니다. 이는 일반적으로 뷰가 데이터 개체를 수락할 수 있는 기본 놓기 효과입니다.

자세한 내용은 MFC 고급 개념 샘플 [OCLIENT를](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="remarks"></a>설명

기본 구현은 아무 것도 하지 않으며 DROPEFFECT_NONE 반환하는 것입니다.

끌기 작업 중에 사용자에게 시각적 피드백을 제공하려면 이 함수를 재정의합니다. 이 함수는 지속적으로 호출되므로 이 함수에 포함된 모든 코드를 가능한 한 최적화해야 합니다. 자세한 내용은 [OLE 끌어 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)문서를 참조하십시오.

## <a name="cviewondragscroll"></a><a name="ondragscroll"></a>C보기::온드래그스크롤

지점이 스크롤 영역에 있는지 여부를 결정하기 위해 [OnDragEnter](#ondragenter) 또는 [OnDragOver를](#ondragover) 호출하기 전에 프레임 워크에 의해 호출됩니다.

```
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*dwKeyState*<br/>
수정자 키의 상태를 포함합니다. 이는 MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON 및 MK_RBUTTON 여러 가지 조합입니다.

*지점*<br/>
화면을 기준으로 커서의 위치를 픽셀 단위로 포함합니다.

### <a name="return-value"></a>Return Value

사용자가 이 위치에서 개체를 삭제한 경우 발생할 수 있는 드롭 유형을 나타내는 DROPEFFECT 지정 형식의 값입니다. 드롭 유형은 일반적으로 *dwKeyState*로 표시된 현재 키 상태에 따라 달라집니다. DROPEFFECT 값에 대한 키 상태의 표준 매핑은 다음과 입니다.

- DROPEFFECT_NONE 이 창에서 데이터 개체를 삭제할 수 없습니다.

- MK_CONTROL &#124; MK_SHIFT DROPEFFECT_LINK 개체와 해당 서버 간의 연결을 만듭니다.

- DROPEFFECT_COPY MK_CONTROL 삭제된 개체의 복사본을 만듭니다.

- MK_ALT DROPEFFECT_MOVE 삭제된 개체의 복사본을 만들고 원래 개체를 삭제합니다.

- DROPEFFECT_SCROLL 끌기 스크롤 작업이 발생하려고 하거나 대상 보기에서 발생 중임을 나타냅니다.

자세한 내용은 MFC 고급 개념 샘플 [OCLIENT를](../../overview/visual-cpp-samples.md)참조하십시오.

### <a name="remarks"></a>설명

이 이벤트에 대한 특수 동작을 제공하려는 경우 이 함수를 재정의합니다. 기본 구현은 커서를 각 창의 테두리 내부의 기본 스크롤 영역으로 드래그하면 창을 자동으로 스크롤합니다. 자세한 내용은 [OLE 끌어 놓기: 놓기 대상 구현](../../mfc/drag-and-drop-ole.md#implement-a-drop-target)문서를 참조하십시오.

## <a name="cviewondraw"></a><a name="ondraw"></a>C보기::에 그리기

문서의 이미지를 렌더링하기 위해 프레임워크에서 호출합니다.

```
virtual void OnDraw(CDC* pDC) = 0;
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
문서 이미지를 렌더링하는 데 사용할 장치 컨텍스트를 가리킵니다.

### <a name="remarks"></a>설명

프레임워크는 화면 표시, 인쇄 및 인쇄 미리 보기를 수행하기 위해 이 함수를 호출하고 각 경우에 다른 장치 컨텍스트를 전달합니다. 기본 구현은 없습니다.

문서 보기를 표시하려면 이 함수를 재정의해야 합니다. *pDC* 매개 변수를 가리키는 [CDC](../../mfc/reference/cdc-class.md) 개체를 사용하여 그래픽 장치 인터페이스(GDI) 호출을 만들 수 있습니다. 그리기 전에 장치 컨텍스트에 펜이나 글꼴과 같은 GDI 리소스를 선택한 다음 나중에 선택을 취소할 수 있습니다. 드로잉 코드는 장치 독립적일 수 있는 경우가 많습니다. 즉, 이미지를 표시하는 장치 유형에 대한 정보가 필요하지 않습니다.

도면을 최적화하려면 장치 컨텍스트의 [RectVisible](../../mfc/reference/cdc-class.md#rectvisible) 멤버 함수를 호출하여 지정된 사각형이 그려질지 여부를 확인합니다. 일반 화면 표시와 인쇄를 구분해야 하는 경우 장치 컨텍스트의 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting) 멤버 함수를 호출합니다.

## <a name="cviewondrop"></a><a name="ondrop"></a>C보기::드롭

사용자가 유효한 삭제 대상을 통해 데이터 개체를 해제할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnDrop(
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

'pDataObject* 드롭 대상에 드롭된 [COleDataObject를](../../mfc/reference/coledataobject-class.md) 가리킵니다.

*드롭 이펙트*<br/>
사용자가 요청한 삭제 효과입니다.

- DROPEFFECT_COPY 삭제되는 데이터 개체의 복사본을 만듭니다.

- DROPEFFECT_MOVE 데이터 개체를 현재 마우스 위치로 이동합니다.

- DROPEFFECT_LINK 데이터 개체와 해당 서버 간의 링크를 만듭니다.

*지점*<br/>
뷰 클라이언트 영역을 기준으로 한 현재 마우스 위치입니다.

### <a name="return-value"></a>Return Value

투하가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

기본 구현은 아무 것도 수행하지 않으며 FALSE를 반환합니다.

이 함수를 재정의하여 OLE 드롭이 뷰의 클라이언트 영역에 미치는 영향을 구현합니다. 데이터 개체는 클립보드 데이터 형식및 지정된 지점에 삭제된 데이터에 대한 *pDataObject를* 통해 검사할 수 있습니다.

> [!NOTE]
> 이 뷰 클래스에서 [OnDropEx에](#ondropex) 대한 재정의가 있는 경우 프레임워크는 이 함수를 호출하지 않습니다.

## <a name="cviewondropex"></a><a name="ondropex"></a>C보기::온드롭엑스

사용자가 유효한 삭제 대상을 통해 데이터 개체를 해제할 때 프레임워크에서 호출됩니다.

```
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

*pDataObject*<br/>
드롭 대상에 드롭된 [COleDataObject를](../../mfc/reference/coledataobject-class.md) 가리킵니다.

*dropDefault*<br/>
사용자가 현재 키 상태에 따라 기본 놓기 작업에 대해 선택한 효과입니다. 그것은 DROPEFFECT_NONE 수 있습니다. 삭제 효과는 비고 섹션에서 설명합니다.

*드롭리스트*<br/>
드롭 소스가 지원하는 삭제 효과의 목록입니다. 낙하 효과 값은 비트별 **OR(&#124;) **연산을 사용하여 결합될 수 있다. 삭제 효과는 비고 섹션에서 설명합니다.

*지점*<br/>
뷰 클라이언트 영역을 기준으로 한 현재 마우스 위치입니다.

### <a name="return-value"></a>Return Value

*점에*의해 지정된 위치에서 놓기 시도에서 발생한 놓기 효과입니다. 이 값은 *dropEffectList*로 표시된 값 중 하나여야 합니다. 삭제 효과는 비고 섹션에서 설명합니다.

### <a name="remarks"></a>설명

기본 구현은 아무 것도 하지 않으며 프레임워크가 [OnDrop](#ondrop) 처리기를 호출해야 함을 나타내기 위해 더미 값(-1)을 반환하는 것입니다.

오른쪽 마우스 단추 드래그 앤 드롭의 효과를 구현하려면 이 함수를 재정의합니다. 오른쪽 마우스 단추 드래그 앤 드롭은 일반적으로 오른쪽 마우스 버튼이 해제될 때 선택 메뉴가 표시됩니다.

`OnDropEx` 재정의는 오른쪽 마우스 버튼을 쿼리해야합니다. [GetKeyState를](/windows/win32/api/winuser/nf-winuser-getkeystate) 호출하거나 [OnDragEnter](#ondragenter) 처리기에서 오른쪽 마우스 단추 상태를 저장할 수 있습니다.

- 오른쪽 마우스 버튼이 다운되면 재정의가 드롭 소스에 의한 낙하 효과 지원을 제공하는 팝업 메뉴를 표시해야 합니다.

  - *dropList를* 검사하여 놓기 소스에서 지원하는 삭제 효과를 확인합니다. 팝업 메뉴에서 이러한 작업만 사용하도록 설정합니다.

  - [SetMenuDefault항목을](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) 사용하여 *dropDefault*에 따라 기본 작업을 설정합니다.

  - 마지막으로 팝업 메뉴에서 사용자 선택으로 표시된 작업을 수행합니다.

- 오른쪽 마우스 버튼이 다운되지 않으면 재정의가 표준 드롭 요청으로 처리해야 합니다. *dropDefault*에 지정된 놓기 효과를 사용합니다. 또는 재정의가 더미 값(-1)을 반환하여 이 `OnDrop` 드롭 작업을 처리할 것임을 나타낼 수 있습니다.

*pDataObject를* 사용하여 `COleDataObject` 지정된 지점에서 삭제된 클립보드 데이터 형식 및 데이터를 검사합니다.

놓기 효과는 놓기 작업과 관련된 작업을 설명합니다. 드롭 효과의 다음 목록을 참조하십시오.

- DROPEFFECT_NONE 한 방울은 허용되지 않습니다.

- DROPEFFECT_COPY 복사 작업이 수행됩니다.

- DROPEFFECT_MOVE 이동 작업이 수행됩니다.

- DROPEFFECT_LINK 삭제된 데이터에서 원본 데이터에 대한 링크가 설정됩니다.

- DROPEFFECT_SCROLL 드래그 스크롤 작업이 발생하려고 하거나 대상에서 발생 중임을 나타냅니다.

기본 메뉴 명령 설정에 대한 자세한 내용은 이 볼륨의 Windows SDK 및 [CMenu::GetSafeHmenu의](../../mfc/reference/cmenu-class.md#getsafehmenu) [SetMenuDefaultItem을](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem) 참조하십시오.

## <a name="cviewonendprinting"></a><a name="onendprinting"></a>C보기::온엔드 프린팅

문서를 인쇄하거나 미리 작업한 후 프레임워크에서 호출합니다.

```
virtual void OnEndPrinting(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. [OnBeginPrinting](#onbeginprinting) 멤버 함수에 할당된 GDI 리소스를 해제하려면 이 함수를 재정의합니다.

## <a name="cviewonendprintpreview"></a><a name="onendprintpreview"></a>C보기::온엔드프린트프리뷰

사용자가 인쇄 미리 보기 모드를 종료할 때 프레임워크에서 호출됩니다.

```
virtual void OnEndPrintPreview(
    CDC* pDC,
    CPrintInfo* pInfo,
    POINT point,
    CPreviewView* pView);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

*지점*<br/>
미리 보기 모드에서 마지막으로 표시된 페이지의 점을 지정합니다.

*pView*<br/>
미리 보기에 사용되는 뷰 객체를 가리킵니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 [OnEndPrinting](#onendprinting) 멤버 함수를 호출하고 인쇄 미리 보기가 시작되기 전에 있던 상태로 주 프레임 창을 복원합니다. 미리 보기 모드가 종료될 때 이 기능을 재정의하여 특수 처리를 수행합니다. 예를 들어 미리 보기 모드에서 일반 표시 모드로 전환할 때 문서에서 사용자의 위치를 유지하려는 경우 *pInfo* 매개 변수가 `m_nCurPage` 가리키는 `CPrintInfo` *점* 매개 변수 및 구조의 멤버에 의해 설명된 위치로 스크롤할 수 있습니다.

항상 재정의를 통해 `OnEndPrintPreview` 기본 클래스 버전을 호출합니다(일반적으로 함수의 끝에).

## <a name="cviewoninitialupdate"></a><a name="oninitialupdate"></a>C보기::초기 업데이트

뷰가 문서에 처음 연결되지만 뷰가 처음 표시되기 전에 프레임워크에서 호출됩니다.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 힌트 정보가 없는 [OnUpdate](#onupdate) 멤버 함수를 호출합니다(즉, *lHint* 매개 변수에 대해 0의 기본값을 사용하고 *pHint* 매개 변수에 NULL을 사용함). 이 함수를 재정의하여 문서에 대한 정보가 필요한 일회성 초기화를 수행합니다. 예를 들어 응용 프로그램에 고정 크기의 문서가 있는 경우 이 함수를 사용하여 문서 크기에 따라 뷰의 스크롤 제한을 초기화할 수 있습니다. 응용 프로그램에서 가변 크기의 문서를 지원하는 경우 [OnUpdate를](#onupdate) 사용하여 문서가 변경될 때마다 스크롤 제한을 업데이트합니다.

## <a name="cviewonpreparedc"></a><a name="onpreparedc"></a>C보기::온준비DC

[OnDraw](#ondraw) 멤버 함수가 화면 표시를 위해 호출되기 전과 인쇄 또는 인쇄 미리 보기 중에 각 페이지에 [대해 OnPrint](#onprint) 멤버 함수가 호출되기 전에 프레임워크에서 호출됩니다.

```
virtual void OnPrepareDC(
    CDC* pDC,
    CPrintInfo* pInfo = NULL);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
문서 이미지를 렌더링하는 데 사용할 장치 컨텍스트를 가리킵니다.

*pInfo*<br/>
인쇄 또는 인쇄 미리 보기를 위해 호출되는 `OnPrepareDC` 경우 현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조를 가리킵니다. 멤버는 `m_nCurPage` 인쇄할 페이지를 지정합니다. 이 매개 변수는 화면 표시를 위해 호출되는 경우 `OnPrepareDC` NULL입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 화면 표시를 위해 함수가 호출되는 경우 아무 것도 수행하지 않습니다. 그러나 이 함수는 [CScrollView와](../../mfc/reference/cscrollview-class.md)같은 파생 클래스에서 재정의되어 장치 컨텍스트의 특성을 조정합니다. 따라서 재정의를 시작할 때 항상 기본 클래스 구현을 호출해야 합니다.

함수가 인쇄를 위해 호출되는 경우 기본 구현에서는 *pInfo* 매개 변수에 저장된 페이지 정보를 검사합니다. 문서 길이를 지정하지 않은 경우 `OnPrepareDC` 문서가 한 페이지 길이로 가정하고 한 페이지가 인쇄된 후 인쇄 루프를 중지합니다. 이 함수는 구조의 `m_bContinuePrinting` 멤버를 FALSE로 설정하여 인쇄 루프를 중지합니다.

다음 `OnPrepareDC` 이유 중 한 가지 이유로 재정의하십시오.

- 지정된 페이지에 필요에 따라 장치 컨텍스트의 속성을 조정합니다. 예를 들어 매핑 모드 또는 장치 컨텍스트의 다른 특성을 설정해야 하는 경우 이 함수에서 설정합니다.

- 인쇄 시간 페이지 이동을 수행합니다. 일반적으로 OnPreparePrinting 멤버 함수를 사용하여 인쇄를 시작할 때 문서의 길이를 [지정합니다.](#onprepareprinting) 그러나 문서가 얼마나 오래 지속되는지 미리 모르는 경우(예: 데이터베이스에서 불특정 수의 레코드를 인쇄하는 경우) 문서의 인쇄 기간 동안 문서의 끝을 테스트하기 위해 재정의합니다. `OnPrepareDC` 인쇄할 문서가 더 이상 없는 경우 구조의 멤버를 `m_bContinuePrinting` `CPrintInfo` FALSE로 설정합니다.

- 페이지 단위로 프린터로 이스케이프 코드를 전송합니다. 에서 `OnPrepareDC`이스케이프 코드를 `Escape` 보내려면 *pDC* 매개 변수의 멤버 함수를 호출합니다.

재정의 의 시작 `OnPrepareDC` 부분에 기본 클래스 버전을 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#183](../../mfc/codesnippet/cpp/cview-class_1.cpp)]

## <a name="cviewonprepareprinting"></a><a name="onprepareprinting"></a>C보기::온준비 인쇄

문서를 인쇄하거나 미리 보기 전에 프레임워크에서 호출합니다.

```
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
현재 인쇄 작업을 설명하는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조체를 가리킵니다.

### <a name="return-value"></a>Return Value

인쇄를 시작하는 영하지 않은 점; 인쇄 작업이 취소된 경우 0입니다.

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다.

인쇄 및 인쇄 미리 보기를 사용하려면 이 함수를 재정의해야 합니다. [DoPreparePrinting](#doprepareprinting) 멤버 함수를 호출하여 *pInfo* 매개 변수를 전달한 다음 반환 값을 반환합니다. `DoPreparePrinting` 프린터 장치 컨텍스트를 만듭니다. 기본값이 아닌 값으로 인쇄 대화 상자를 초기화하려면 *pInfo*의 멤버에 값을 할당합니다. 예를 들어 문서의 길이를 알고 있는 경우 호출하기 `DoPreparePrinting`전에 값을 *pInfo의* [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage) 멤버 함수에 전달합니다. 이 값은 [인쇄 대화 상자의 범위 부분]에 있는 상자: 상자에 표시됩니다.

`DoPreparePrinting`미리 보기 작업에 대한 [인쇄] 대화 상자가 표시되지 않습니다. 인쇄 작업에 대한 인쇄 대화 상자를 우회하려면 *pInfo의* `m_bPreview` 멤버가 FALSE인지 확인한 다음 을 전달하기 전에 `DoPreparePrinting`TRUE로 설정합니다. 나중에 FALSE로 재설정합니다.

프린터 장치 컨텍스트를 나타내는 `CDC` 개체에 대한 액세스가 필요한 초기화를 수행해야 하는 경우(예: 문서 길이를 지정하기 전에 페이지 `OnBeginPrinting` 크기를 알아야 하는 경우) 멤버 함수를 재정의합니다.

*pInfo* 매개 변수의 `DoPreparePrinting` `m_nNumPreviewPages` 또는 `m_strPageDesc` 멤버값을 설정하려면 을 호출한 후 이렇게 합니다. 멤버 `DoPreparePrinting` 함수는 `m_nNumPreviewPages` 응용 프로그램의 에 있는 값으로 설정합니다. INI 파일을 `m_strPageDesc` 설정하고 기본값으로 설정합니다.

### <a name="example"></a>예제

  프레임워크에 `OnPreparePrinting` 인쇄 `DoPreparePrinting` 대화 상자가 표시되고 프린터 DC를 만들 수 있도록 재정의및 재정의를 호출합니다.

[!code-cpp[NVC_MFCDocView#184](../../mfc/codesnippet/cpp/cview-class_2.cpp)]

문서에 포함된 페이지 수를 알고 있는 경우 호출하기 `OnPreparePrinting` `DoPreparePrinting`전에 최대 페이지를 설정합니다. 프레임워크는 인쇄 대화 상자의 "받는" 상자에 최대 페이지 번호를 표시합니다.

[!code-cpp[NVC_MFCDocView#185](../../mfc/codesnippet/cpp/cview-class_3.cpp)]

## <a name="cviewonprint"></a><a name="onprint"></a>C보기::온프린트

문서의 페이지를 인쇄하거나 미리 보기 위해 프레임워크에서 호출합니다.

```
virtual void OnPrint(
    CDC* pDC,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
프린터 디바이스 컨텍스트를 가리킵니다.

*pInfo*<br/>
현재 인쇄 `CPrintInfo` 작업을 설명하는 구조를 가리킵니다.

### <a name="remarks"></a>설명

인쇄되는 각 페이지에 대해 프레임워크는 [OnPrepareDC](#onpreparedc) 멤버 함수를 호출한 직후에 이 함수를 호출합니다. 인쇄되는 페이지는 `m_nCurPage` *pInfo가* 가리키는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 구조의 구성원에 의해 지정됩니다. 기본 구현은 [OnDraw](#ondraw) 멤버 함수를 호출하고 프린터 장치 컨텍스트를 전달합니다.

다음 이유로 이 함수를 재정의합니다.

- 다중 페이지 문서의 인쇄를 허용합니다. 현재 인쇄 중인 페이지에 해당하는 문서 부분만 렌더링합니다. 렌더링을 수행하는 `OnDraw` 데 사용하는 경우 문서의 적절한 부분만 인쇄되도록 뷰포트 원점을 조정할 수 있습니다.

- 인쇄된 이미지를 화면 이미지와 다르게 보이게 하려면(즉, 응용 프로그램이 WYSIWYG가 아닌 경우). 프린터 장치 컨텍스트를 `OnDraw`에 전달하는 대신 장치에 대한 컨텍스트를 사용하여 화면에 표시되지 않는 특성을 사용하여 이미지를 렌더링합니다.

   화면 표시에 사용하지 않는 인쇄에 GDI 리소스가 필요한 경우 그리기 전에 장치 컨텍스트에 GDI 리소스를 선택하고 나중에 선택을 취소합니다. 이러한 GDI 리소스는 [OnBeginPrinting에](#onbeginprinting) 할당되고 [OnEndPrinting](#onendprinting)에서 릴리스되어야 합니다.

- 헤더 또는 바닥글을 구현합니다. 인쇄할 수 `OnDraw` 있는 영역을 제한하여 렌더링을 수행하는 데 계속 사용할 수 있습니다.

*pInfo* `m_rectDraw` 매개 변수의 멤버는 논리 단위로 페이지의 인쇄 가능 영역을 설명합니다.

재정의에 `OnPrepareDC` 전화하지 `OnPrint`마십시오; 를 호출하기 `OnPrepareDC` `OnPrint`전에 프레임워크가 자동으로 호출됩니다.

### <a name="example"></a>예제

다음은 재정의된 `OnPrint` 함수에 대한 골격입니다.

[!code-cpp[NVC_MFCDocView#186](../../mfc/codesnippet/cpp/cview-class_4.cpp)]

또 다른 예는 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)을 참조하십시오.

## <a name="cviewonscroll"></a><a name="onscroll"></a>C보기::온스크롤

스크롤이 가능한지 여부를 결정하기 위해 프레임워크에서 호출합니다.

```
virtual BOOL OnScroll(
    UINT nScrollCode,
    UINT nPos,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*n스크롤 코드*<br/>
사용자의 스크롤 요청을 나타내는 스크롤 바로 표시 줄 코드입니다. 이 매개 변수는 가로로 발생하는 스크롤 유형을 결정하는 낮은 순서바이트와 세로로 발생하는 스크롤 유형을 결정하는 고차 바이트의 두 부분으로 구성됩니다.

- SB_BOTTOM 아래로 스크롤합니다.

- SB_LINEDOWN 한 줄 아래로 스크롤합니다.

- SB_LINEUP 한 줄을 스크롤합니다.

- SB_PAGEDOWN 한 페이지 아래로 스크롤합니다.

- SB_PAGEUP 한 페이지 위로 스크롤합니다.

- SB_THUMBTRACK 스크롤 상자를 지정된 위치로 드래그합니다. 현재 위치는 *nPos에*지정됩니다.

- SB_TOP 스크롤합니다.

*Npos*<br/>
스크롤 바코드SB_THUMBTRACK 경우 현재 스크롤 상자 위치를 포함합니다. 그렇지 않으면 사용되지 않습니다. 초기 스크롤 범위에 따라 *nPos는* 음수일 수 있으며 필요한 경우 **int로** 캐스팅해야 합니다.

*b도스크롤*<br/>
지정된 스크롤 작업을 실제로 수행해야 하는지 여부를 결정합니다. TRUE이면 스크롤이 수행되어야 합니다. FALSE인 경우 스크롤이 발생하지 않아야 합니다.

### <a name="return-value"></a>Return Value

*bDoScroll이* TRUE이고 뷰가 실제로 스크롤된 경우 0이 아닌 것을 반환합니다. 그렇지 않으면 0. *bDoScroll이* FALSE이면 실제로 스크롤을 수행하지 않더라도 *bDoScroll이* TRUE인 경우 반환한 값을 반환합니다.

### <a name="remarks"></a>설명

뷰가 스크롤 막대 메시지를 수신할 때 *bDoScroll이* TRUE로 설정된 프레임워크에서 이 함수를 호출하는 경우도 있습니다. 이 경우 실제로 뷰를 스크롤해야 합니다. 다른 경우에는 이 함수가 실제로 스크롤이 발생하기 전에 OLE 항목이 처음 드롭 대상의 자동 스크롤 영역으로 드래그될 때 *false로 설정된 bDoScroll을* 사용하여 호출됩니다. 이 경우 실제로 뷰를 스크롤해서는 안 됩니다.

## <a name="cviewonscrollby"></a><a name="onscrollby"></a>C보기::온스크롤비

사용자가 뷰의 현재 테두리에 대해 OLE 항목을 드래그하거나 세로 또는 가로 스크롤 막대를 조작하여 문서의 현재 보기 를 벗어난 영역을 볼 때 프레임워크에서 호출합니다.

```
virtual BOOL OnScrollBy(
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*크기스크롤*<br/>
가로 및 세로로 스크롤된 픽셀 수입니다.

*b도스크롤*<br/>
뷰 스크롤이 발생하는지 여부를 결정합니다. TRUE이면 스크롤이 수행됩니다. FALSE인 경우 스크롤이 발생하지 않습니다.

### <a name="return-value"></a>Return Value

뷰를 스크롤할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드는 사용자가 요청한 방향으로 뷰를 스크롤할 수 있는지 확인한 다음 필요한 경우 새 영역을 업데이트합니다. 이 함수는 [CWnd::OnH스크롤](../../mfc/reference/cwnd-class.md#onhscroll) 및 [CWnd::OnVScroll에서](../../mfc/reference/cwnd-class.md#onvscroll) 자동으로 호출되어 실제 스크롤 요청을 수행합니다.

이 메서드의 기본 구현은 뷰를 변경하지 않지만 호출되지 않으면 뷰가 `CScrollView`-derived 클래스에서 스크롤되지 않습니다.

문서 너비 또는 높이가 32767 픽셀을 초과하면 잘못된 *sizeScroll* 인수를 `OnScrollBy` 사용하면 32767을 지나서 스크롤하는 데 실패합니다.

## <a name="cviewonupdate"></a><a name="onupdate"></a>C보기::에 업데이트

뷰의 문서가 수정된 후 프레임워크에서 호출됩니다. 이 함수는 [CDocument::UpdateAllViews에서](../../mfc/reference/cdocument-class.md#updateallviews) 호출되며 뷰에서 해당 수정 사항을 반영하도록 해당 디스플레이를 업데이트할 수 있습니다.

```
virtual void OnUpdate(
    CView* pSender,
    LPARAM lHint,
    CObject* pHint);
```

### <a name="parameters"></a>매개 변수

*pSender*<br/>
모든 뷰를 업데이트할 경우 문서를 수정한 뷰 또는 NULL을 가리킵니다.

*lHint*<br/>
수정 사항에 대한 정보가 들어 있습니다.

*pHint*<br/>
수정에 대한 정보를 저장하는 객체를 가리킵니다.

### <a name="remarks"></a>설명

[또한 OnInitialUpdate](#oninitialupdate)의 기본 구현에 의해 호출됩니다. 기본 구현은 전체 클라이언트 영역을 무효화하여 다음 WM_PAINT 메시지가 수신될 때 페인팅을 위해 표시합니다. 문서의 수정된 부분에 매핑되는 지역만 업데이트하려면 이 함수를 재정의합니다. 이렇게 하려면 힌트 매개 변수를 사용하여 수정 사항에 대한 정보를 전달해야 합니다.

*lHint를*사용하려면 특수 힌트 값, 일반적으로 비트 마스크 또는 열거된 형식을 정의하고 문서가 이러한 값 중 하나를 전달하도록 합니다. *pHint를*사용하려면 [CObject에서](../../mfc/reference/cobject-class.md) 힌트 클래스를 파생시키고 문서가 힌트 개체에 대한 포인터를 전달하도록 합니다. 재정의 `OnUpdate`할 때 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 멤버 함수를 사용하여 힌트 개체의 런타임 유형을 결정합니다.

일반적으로 에서 `OnUpdate`직접 그리기를 수행하면 안 됩니다. 대신 장치 좌표에서 업데이트가 필요한 영역을 설명하는 사각형을 결정합니다. 이 사각형을 [CWnd::무효화에 전달합니다.](../../mfc/reference/cwnd-class.md#invalidaterect) 이렇게 하면 다음에 [WM_PAINT](/windows/win32/gdi/wm-paint) 메시지가 수신될 때 페인팅이 발생합니다.

*lHint가* 0이고 *pHint이* NULL이면 문서에 제네릭 업데이트 알림이 전송되었습니다. 뷰에서 제네릭 업데이트 알림을 받거나 힌트를 디코딩할 수 없는 경우 전체 클라이언트 영역을 무효화해야 합니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[C스플리터Wnd 클래스](../../mfc/reference/csplitterwnd-class.md)<br/>
[CDC 클래스](../../mfc/reference/cdc-class.md)<br/>
[CDoc템플릿 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[C문서 클래스](../../mfc/reference/cdocument-class.md)
