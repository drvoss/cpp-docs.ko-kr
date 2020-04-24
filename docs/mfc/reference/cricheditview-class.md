---
title: 리치에이트뷰 클래스
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: b72daac576411b45908d1e91bd86bbd9aeacf738
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754459"
---
# <a name="cricheditview-class"></a>리치에이트뷰 클래스

[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 및 [CRichEditCntrItem을](../../mfc/reference/cricheditcntritem-class.md)사용하면 MFC의 문서 보기 아키텍처의 컨텍스트 내에서 풍부한 편집 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[리치에이트 뷰::CRichEditView](#cricheditview)|`CRichEditView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CRichEditView::조정대화 위치](#adjustdialogposition)|현재 선택 영역이 가려지지 않도록 대화 상자를 이동합니다.|
|[CRichEditView::캔페이스트](#canpaste)|클립보드에 리치 편집 보기에 붙여넣을 수 있는 데이터가 포함되어 있는지 여부를 알려줍니다.|
|[CRichEditView::DoPaste](#dopaste)|OLE 항목을 이 풍부한 편집 뷰에 붙여넣습니다.|
|[CRichEditView::찾기 텍스트](#findtext)|대기 커서를 호출하여 지정된 텍스트를 찾습니다.|
|[CRichEditView::찾기 텍스트 단순](#findtextsimple)|지정된 텍스트를 찾습니다.|
|[CrichEditView::GetCharFormat선택](#getcharformatselection)|현재 선택 영역에 대한 문자 서식 지정 특성을 검색합니다.|
|[CRichEditView::GetDocument](#getdocument)|관련 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)에 대한 포인터를 검색합니다.|
|[CrichEditView::GetInPlace액티브항목](#getinplaceactiveitem)|리치 편집 보기에서 현재 활성 상태인 OLE 항목을 검색합니다.|
|[CRichEditView::GetMargins](#getmargins)|이 풍부한 편집 뷰의 여백을 검색합니다.|
|[CRichEditView::GetPageRect](#getpagerect)|이 풍부한 편집 뷰에 대한 페이지 사각형을 검색합니다.|
|[CrichEdit뷰::겟페이퍼사이즈](#getpapersize)|이 풍부한 편집 뷰의 용지 크기를 검색합니다.|
|[CrichEditView::GetPara형식 선택](#getparaformatselection)|현재 선택 영역에 대한 단락 서식 지정 특성을 검색합니다.|
|[CRichEdit뷰::겟프린트렉트](#getprintrect)|이 풍부한 편집 뷰에 대한 인쇄 사각형을 검색합니다.|
|[CRichEditView::GetPrint폭](#getprintwidth)|이 풍부한 편집 뷰의 인쇄 너비를 검색합니다.|
|[CRichEditView::GetRichEditCtrl](#getricheditctrl)|리치 편집 컨트롤을 검색합니다.|
|[CRichEditView::Getselected항목](#getselecteditem)|리치 편집 뷰에서 선택한 항목을 검색합니다.|
|[CRichEditView::GetText길이](#gettextlength)|풍부한 편집 뷰에서 텍스트 길이를 검색합니다.|
|[CRichEditView::GetText길이Ex](#gettextlengthex)|리치 편집 뷰에서 문자 또는 바이트 수를 검색합니다. 길이를 결정하는 방법에 대한 확장플래그 목록입니다.|
|[CRichEditView::삽입파일오브젝트오브젝트](#insertfileasobject)|파일을 OLE 항목으로 삽입합니다.|
|[CRichEditView::삽입항목](#insertitem)|새 항목을 OLE 항목으로 삽입합니다.|
|[CRichEditView::리치편집 형식](#isricheditformat)|클립보드에 풍부한 편집 또는 텍스트 형식의 데이터가 포함되어 있는지 여부를 알려줍니다.|
|[리치에이트 뷰::온차 효과](#onchareffect)|현재 선택 영역에 대한 문자 서식을 전환합니다.|
|[리치에이트 뷰::온파라정렬](#onparaalign)|단락의 정렬을 변경합니다.|
|[CrichEdit뷰::온업데이트차효과](#onupdatechareffect)|문자 공용 멤버 함수에 대한 명령 UI를 업데이트합니다.|
|[CrichEdit뷰::OnUpdateParaAlign](#onupdateparaalign)|단락 공용 멤버 함수에 대한 명령 UI를 업데이트합니다.|
|[CRichEditView::P린트인사이드렉트](#printinsiderect)|지정된 사각형 내에서 지정된 텍스트의 서식을 지정합니다.|
|[CRichEditView::P린트페이지](#printpage)|지정된 페이지 내에서 지정된 텍스트의 서식을 지정합니다.|
|[CRichEditView::세트차형식](#setcharformat)|현재 선택 영역에 대한 문자 서식 지정 특성을 설정합니다.|
|[CRichEditView::세트 마진](#setmargins)|이 풍부한 편집 뷰의 여백을 설정합니다.|
|[리치에이트 뷰::세트페이퍼크기](#setpapersize)|이 풍부한 편집 뷰의 용지 크기를 설정합니다.|
|[CRichEditView::SetParaFormat](#setparaformat)|현재 선택 영역에 대한 단락 서식 지정 특성을 설정합니다.|
|[CRichEditView::텍스트찾을 수 없습니다](#textnotfound)|컨트롤의 내부 검색 상태를 재설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CRichEdit보기::GetClipboard데이터](#getclipboarddata)|이 풍부한 편집 뷰에서 범위에 대한 클립보드 개체를 검색합니다.|
|[CRichEditView::GetContextMenu](#getcontextmenu)|오른쪽 마우스 단추 아래로 사용할 컨텍스트 메뉴를 검색합니다.|
|[리치편집뷰::선택됨](#isselected)|지정된 OLE 항목이 선택되었는지 여부입니다.|
|[리치에이트 뷰::온파인트넥스트](#onfindnext)|하위 문자열의 다음 발생을 찾습니다.|
|[CRichEditView::초기 업데이트](#oninitialupdate)|뷰가 문서에 처음 첨부될 때 뷰를 새로 고칩니다.|
|[CRichEditView::온페이스트네이티브 오브젝트](#onpastenativeobject)|OLE 항목에서 기본 데이터를 검색합니다.|
|[CRichEditView::온프린터 변경](#onprinterchanged)|지정된 장치에 인쇄 특성을 설정합니다.|
|[리치에이트 뷰::에대체 모두](#onreplaceall)|지정된 문자열의 모든 발생을 새 문자열로 바꿉습니다.|
|[리치에이트 뷰::에대체셀](#onreplacesel)|현재 선택 영역을 바꿉습니다.|
|[CrichEdit뷰::온텍스트Not](#ontextnotfound)|요청된 텍스트를 찾을 수 없다는 사용자 알림을 처리합니다.|
|[CRichEditView::쿼리 수락데이터](#queryacceptdata)|의 데이터에 대해 볼 수 `IDataObject`있는 쿼리입니다.|
|[CRichEditView::랩 변경](#wrapchanged)|`m_nWordWrap`의 값에 따라 이 풍부한 편집 뷰의 대상 출력 장치를 조정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CRichEdit뷰::m_nBulletIndent](#m_nbulletindent)|글머리 기호 목록에 대한 들여쓰기 의 양을 나타냅니다.|
|[CRichEdit뷰::m_nWordWrap](#m_nwordwrap)|단어 wrap 제약 조건을 나타냅니다.|

## <a name="remarks"></a>설명

"풍부한 편집 컨트롤"은 사용자가 텍스트를 입력하고 편집할 수 있는 창입니다. 텍스트에 문자 및 단락 서식을 할당할 수 있으며 포함된 OLE 개체를 포함할 수 있습니다. 풍부한 편집 컨트롤은 텍스트 서식을 지정하기 위한 프로그래밍 인터페이스를 제공합니다. 그러나 응용 프로그램은 사용자가 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 모든 사용자 인터페이스 구성 요소를 구현 해야 합니다.

`CRichEditView`은 텍스트의 텍스트 및 서식 특성을 유지합니다. `CRichEditDoc`은 보기에 있는 OLE 클라이언트 항목 의 목록을 유지 관리합니다. `CRichEditCntrItem`은 OLE 클라이언트 항목에 대한 컨테이너 측 액세스를 제공합니다.

이 Windows 공통 제어(따라서 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스)는 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

MFC 응용 프로그램에서 리치 편집 뷰를 사용하는 예는 [WORDPAD](../../overview/visual-cpp-samples.md) 샘플 응용 프로그램을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>요구 사항

**헤더:** afxrich.h

## <a name="cricheditviewadjustdialogposition"></a><a name="adjustdialogposition"></a>CRichEditView::조정대화 위치

이 함수를 호출하여 현재 선택 영역을 가리지 않도록 지정된 대화 상자를 이동합니다.

```cpp
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>매개 변수

*pDlg*<br/>
`CDialog` 개체에 대한 포인터입니다.

## <a name="cricheditviewcanpaste"></a><a name="canpaste"></a>CRichEditView::캔페이스트

이 함수를 호출하여 클립보드에 이 풍부한 편집 보기에 붙여넣을 수 있는 정보가 포함되어 있는지 확인합니다.

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>Return Value

클립보드에 이 풍부한 편집 뷰가 허용할 수 있는 형식의 데이터가 포함된 경우 비영입니다. 그렇지 않으면 0입니다.

## <a name="cricheditviewcricheditview"></a><a name="cricheditview"></a>리치에이트 뷰::CRichEditView

이 함수를 호출하여 개체를 `CRichEditView` 만듭니다.

```
CRichEditView();
```

## <a name="cricheditviewdopaste"></a><a name="dopaste"></a>CRichEditView::DoPaste

이 함수를 호출하여 *dataobj의* OLE 항목을 이 풍부한 편집 문서/보기에 붙여넣습니다.

```cpp
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>매개 변수

*dataobj*<br/>
붙여넣기 데이터를 포함하는 [COleDataObject입니다.](../../mfc/reference/coledataobject-class.md)

*Cf*<br/>
원하는 클립보드 형식입니다.

*hMetaPict*<br/>
붙여넣기 항목을 나타내는 메타파일입니다.

### <a name="remarks"></a>설명

프레임워크는 이 함수를 [QueryAcceptData](#queryacceptdata)의 기본 구현의 일부로 호출합니다.

이 함수는 붙여넣기 스페셜에 대한 처리기의 결과에 따라 붙여넣기 유형을 결정합니다. *cf가* 0이면 새 항목은 현재 의 상징적 표현을 사용합니다. *cf가* 영하지 않고 *hMetaPict가* NULL이 아닌 경우 새 항목은 *표현에 hMetaPict를* 사용합니다.

## <a name="cricheditviewfindtext"></a><a name="findtext"></a>CRichEditView::찾기 텍스트

이 함수를 호출하여 지정된 텍스트를 찾고 현재 선택 영역으로 설정합니다.

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
검색할 문자열을 포함합니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 나타냅니다.

*bWord*<br/>
검색이 단어의 일부가 아닌 전체 단어만 일치해야 하는지 를 나타냅니다.

*b다음*<br/>
검색 방향을 나타냅니다. TRUE이면 검색 방향이 버퍼의 끝을 향합니다. FALSE인 경우 검색 방향이 버퍼의 시작 부분을 향합니다.

### <a name="return-value"></a>Return Value

*lpszFind* 텍스트가 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수는 찾기 작업 중에 대기 커서를 표시합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

## <a name="cricheditviewfindtextsimple"></a><a name="findtextsimple"></a>CRichEditView::찾기 텍스트 단순

이 함수를 호출하여 지정된 텍스트를 찾고 현재 선택 영역으로 설정합니다.

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
검색할 문자열을 포함합니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 나타냅니다.

*bWord*<br/>
검색이 단어의 일부가 아닌 전체 단어만 일치해야 하는지 를 나타냅니다.

*b다음*<br/>
검색 방향을 나타냅니다. TRUE이면 검색 방향이 버퍼의 끝을 향합니다. FALSE인 경우 검색 방향이 버퍼의 시작 부분을 향합니다.

### <a name="return-value"></a>Return Value

*lpszFind* 텍스트가 발견되면 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

  [CRichEditView::FindText](#findtext)에 대한 예제를 참조하십시오.

## <a name="cricheditviewgetcharformatselection"></a><a name="getcharformatselection"></a>CrichEditView::GetCharFormat선택

이 함수를 호출하여 현재 선택 영역의 문자 서식 지정 특성을 가져옵니다.

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>Return Value

현재 선택 영역의 문자 서식 지정 특성을 포함하는 [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) 구조입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat) 메시지 및 [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) 구조를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewgetclipboarddata"></a><a name="getclipboarddata"></a>CRichEdit보기::GetClipboard데이터

프레임워크는 [IRichEditOleCallback::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)의 처리의 일부로 이 함수를 호출합니다.

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>매개 변수

*lpchrg*<br/>
*lplpdataobj에*의해 지정된 데이터 개체에 복사할 문자(및 OLE 항목)의 범위를 지정하는 [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) 구조에 대한 포인터 .

*dwReco*<br/>
클립보드 작업 플래그입니다. 이러한 값 중 하나가 될 수 있습니다.

- RECO_COPY 클립보드에 복사합니다.

- RECO_CUT 클립보드로 잘라냅니다.

- 드래그 작업(드래그 앤 드롭)RECO_DRAG.

- RECO_DROP 놓기 작업(끌어서 놓기).

- 클립보드에서 붙여넣기를 RECO_PASTE.

*lpRichDataObj*<br/>
리치 편집 컨트롤의 클립보드 데이터가 포함된 [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject) 개체에 대한 [포인터(IRichEditOle::GetClipboardData).](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)

*lplpdataobj*<br/>
*lpchrg* 매개 변수에 지정된 `IDataObject` 범위를 나타내는 개체의 주소를 수신하는 포인터 변수에 대한 포인터입니다. 오류가 반환되면 *lplpdataobj* 의 값은 무시됩니다.

### <a name="return-value"></a>Return Value

작업의 성공을 보고하는 HRESULT 값입니다. HRESULT에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

### <a name="remarks"></a>설명

반환 값이 성공을 나타내는 `IRichEditOleCallback::GetClipboardData` 경우 `IDataObject` *lplpdataobj에*의해 액세스된 액세스를 반환합니다. 그렇지 않으면 *lpRichDataObj에*의해 액세스 된 것을 반환합니다. 이 함수를 재정의하여 자체 클립보드 데이터를 제공합니다. 이 함수의 기본 구현은 E_NOTIMPL 반환합니다.

이 고급 재정의 할 수 있습니다.

자세한 내용은 [IRichEditOle::GetClipboardData,](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata) [IRichEditOleCallback::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)및 WINDOWS SDK의 [CHARRANGE를](/windows/win32/api/richedit/ns-richedit-charrange) 참조하고 Windows SDK에서 [IDataObject를](/windows/win32/api/objidl/nn-objidl-idataobject) 참조하십시오.

## <a name="cricheditviewgetcontextmenu"></a><a name="getcontextmenu"></a>CRichEditView::GetContextMenu

프레임워크는 [IRichEditOleCallback::GetContextMenu](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu).

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>매개 변수

*셀티그 (것)스내*<br/>
선택 유형입니다. 선택 유형 값은 설명 섹션에 설명되어 있습니다.

*로폴레오비*<br/>
선택 영역에 `OLEOBJECT` 하나 이상의 OLE 항목이 포함된 경우 첫 번째 선택된 OLE 개체를 지정하는 구조에 대한 포인터입니다. 선택 영역에 항목이 없는 경우 *lpoleobj는* NULL입니다. 구조는 `OLEOBJECT` OLE 개체 v-테이블에 대 한 포인터를 보유 합니다.

*lpchrg*<br/>
현재 선택 영역을 포함하는 [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

컨텍스트 메뉴를 처리합니다.

### <a name="remarks"></a>설명

이 기능은 오른쪽 마우스 버튼 다운 처리의 일반적인 부분입니다.

선택 유형은 다음 플래그의 조합일 수 있습니다.

- SEL_EMPTY 현재 선택 영역이 없음을 나타냅니다.

- SEL_TEXT 현재 선택 영역에 텍스트가 포함되어 있음을 나타냅니다.

- SEL_OBJECT 현재 선택 영역에 하나 이상의 OLE 항목이 포함되어 있음을 나타냅니다.

- SEL_MULTICHAR 현재 선택 영역에 두 개 이상의 텍스트 문자가 포함되어 있음을 나타냅니다.

- SEL_MULTIOBJECT 현재 선택 영역에 두 개 이상의 OLE 개체가 포함되어 있음을 나타냅니다.

기본 구현은 NULL을 반환합니다. 이 고급 재정의 할 수 있습니다.

자세한 내용은 [IRichEditOleCallback::GetContextMenu메뉴](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu) 및 WINDOWS SDK의 [CHARRANGE를](/windows/win32/api/richedit/ns-richedit-charrange) 참조하십시오.

## <a name="cricheditviewgetdocument"></a><a name="getdocument"></a>CRichEditView::GetDocument

이 함수를 호출하여 이 `CRichEditDoc` 뷰와 연결된 포인터를 가져옵니다.

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>Return Value

`CRichEditView` 개체와 연결된 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 개체에 대한 포인터입니다.

## <a name="cricheditviewgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>CrichEditView::GetInPlace액티브항목

이 함수를 호출하여 이 `CRichEditView` 개체에서 현재 활성화된 OLE 항목을 가져옵니다.

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>Return Value

이 풍부한 편집 뷰에서 단일 활성 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체에 대한 포인터입니다. 현재 현재 현재 활성 상태에 있는 OLE 항목이 없는 경우 NULL입니다.

## <a name="cricheditviewgetmargins"></a><a name="getmargins"></a>CRichEditView::GetMargins

이 함수를 호출하여 인쇄에 사용되는 현재 여백을 검색합니다.

```
CRect GetMargins() const;
```

### <a name="return-value"></a>Return Value

MM_TWIPS 측정된 인쇄에 사용되는 여백입니다.

## <a name="cricheditviewgetpagerect"></a><a name="getpagerect"></a>CRichEditView::GetPageRect

인쇄에 사용되는 페이지의 크기를 얻으려면 이 함수를 호출합니다.

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>Return Value

MM_TWIPS 측정된 인쇄에 사용되는 페이지의 경계입니다.

### <a name="remarks"></a>설명

이 값은 용지 크기를 기준으로 합니다.

## <a name="cricheditviewgetpapersize"></a><a name="getpapersize"></a>CrichEdit뷰::겟페이퍼사이즈

이 함수를 호출하여 현재 용지 크기를 검색합니다.

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>Return Value

MM_TWIPS 측정된 인쇄에 사용되는 용지의 크기입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

## <a name="cricheditviewgetparaformatselection"></a><a name="getparaformatselection"></a>CrichEditView::GetPara형식 선택

이 함수를 호출하여 현재 선택 영역의 단락 서식 지정 특성을 가져옵니다.

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>Return Value

현재 선택 영역의 단락 서식 지정 특성을 포함하는 [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) 구조입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat) 메시지 및 [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) 구조를 참조하십시오.

## <a name="cricheditviewgetprintrect"></a><a name="getprintrect"></a>CRichEdit뷰::겟프린트렉트

이 함수를 호출하여 페이지 사각형 내의 인쇄 영역 경계를 검색합니다.

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>Return Value

인쇄에 사용되는 이미지 영역의 경계는 MM_TWIPS 측정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

## <a name="cricheditviewgetprintwidth"></a><a name="getprintwidth"></a>CRichEditView::GetPrint폭

이 함수를 호출하여 인쇄 영역의 너비를 확인합니다.

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>Return Value

MM_TWIPS 측정된 인쇄 영역의 너비입니다.

## <a name="cricheditviewgetricheditctrl"></a><a name="getricheditctrl"></a>CRichEditView::GetRichEditCtrl

이 함수를 호출하여 개체와 연결된 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 개체를 검색합니다. `CRichEditView`

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>Return Value

이 `CRichEditCtrl` 뷰의 개체입니다.

### <a name="example"></a>예제

  [CRichEditView::FindText](#findtext)에 대한 예제를 참조하십시오.

## <a name="cricheditviewgetselecteditem"></a><a name="getselecteditem"></a>CRichEditView::Getselected항목

이 함수를 호출하여 현재 `CRichEditCntrItem` 이 `CRichEditView` 개체에서 선택된 OLE 항목(개체)을 검색합니다.

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>Return Value

개체에서 선택된 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) `CRichEditView` 개체에 대한 포인터; 이 보기에서 항목이 선택되지 않은 경우 NULL입니다.

## <a name="cricheditviewgettextlength"></a><a name="gettextlength"></a>CRichEditView::GetText길이

이 함수를 호출하여 이 `CRichEditView` 개체의 텍스트 길이를 검색합니다.

```
long GetTextLength() const;
```

### <a name="return-value"></a>Return Value

이 `CRichEditView` 개체의 텍스트 길이입니다.

## <a name="cricheditviewgettextlengthex"></a><a name="gettextlengthex"></a>CRichEditView::GetText길이Ex

이 개체의 텍스트 길이를 계산하려면 `CRichEditView` 이 멤버 함수를 호출합니다.

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
텍스트 길이를 결정하는 데 사용할 메서드를 지정하는 값입니다. 이 멤버는 Windows SDK에 설명된 [GETTEXTLENGTHEX의](/windows/win32/api/richedit/ns-richedit-gettextlengthex) 플래그 멤버에 나열된 값 중 하나 이상일 수 있습니다.

*uCodePage*<br/>
번역을 위한 코드 페이지(ANSI 코드 페이지의 경우 CP_ACP, 유니코드의 경우 1200).

### <a name="return-value"></a>Return Value

편집 컨트롤의 문자 또는 바이트 수입니다. 호환되지 않는 플래그가 *dwFlags에*설정된 경우 이 멤버 함수는 E_INVALIDARG 반환합니다.

### <a name="remarks"></a>설명

`GetTextLengthEx`에서는 텍스트 길이를 결정하는 추가 방법을 제공합니다. 리치 편집 2.0 기능을 지원합니다. 자세한 내용은 Windows SDK의 [리치 편집 컨트롤 정보를](/windows/win32/Controls/about-rich-edit-controls) 참조하십시오.

## <a name="cricheditviewinsertfileasobject"></a><a name="insertfileasobject"></a>CRichEditView::삽입파일오브젝트오브젝트

이 함수를 호출하여 지정된 [파일(CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체)을 풍부한 편집 뷰에 삽입합니다.

```cpp
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>매개 변수

*lpsz파일이름*<br/>
삽입할 파일의 이름이 포함된 문자열입니다.

## <a name="cricheditviewinsertitem"></a><a name="insertitem"></a>CRichEditView::삽입항목

이 함수를 호출하여 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) 개체를 리치 편집 뷰에 삽입합니다.

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>매개 변수

*pItem*<br/>
삽입할 항목에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

삽입의 성공을 나타내는 HRESULT 값입니다.

### <a name="remarks"></a>설명

HRESULT에 대한 자세한 내용은 Windows SDK의 [COM 오류 코드 구조를](/windows/win32/com/structure-of-com-error-codes) 참조하십시오.

## <a name="cricheditviewisricheditformat"></a><a name="isricheditformat"></a>CRichEditView::리치편집 형식

이 함수를 호출하여 *cf가* 텍스트, 진부한 텍스트 또는 OLE 항목이 있는 진부한 텍스트인 클립보드 형식인지 확인합니다.

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
관심 있는 클립보드 형식입니다.

### <a name="return-value"></a>Return Value

*cf가* 풍부한 편집 또는 텍스트 클립보드 형식인 경우 영하지 않습니다.

## <a name="cricheditviewisselected"></a><a name="isselected"></a>리치편집뷰::선택됨

이 함수를 호출하여 지정된 OLE 항목이 현재 이 보기에서 선택되어 있는지 확인합니다.

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>매개 변수

*pDoc항목*<br/>
뷰의 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

개체가 선택된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

파생 뷰 클래스에 OLE 항목 선택을 처리하기 위한 다른 방법이 있는 경우 이 함수를 재정의합니다.

## <a name="cricheditviewm_nbulletindent"></a><a name="m_nbulletindent"></a>CRichEdit뷰::m_nBulletIndent

목록의 글머리 기호 항목에 대한 들여쓰기; 기본적으로 720 단위이며 1/2 인치입니다.

```
int m_nBulletIndent;
```

## <a name="cricheditviewm_nwordwrap"></a><a name="m_nwordwrap"></a>CRichEdit뷰::m_nWordWrap

이 풍부한 편집 뷰에 대한 단어 줄 바꿈 유형을 나타냅니다.

```
int m_nWordWrap;
```

### <a name="remarks"></a>설명

해당 값은

- `WrapNone`자동 단어 래핑이 없음을 나타냅니다.

- `WrapToWindow`창 너비를 기준으로 단어 줄 바꿈을 나타냅니다.

- `WrapToTargetDevice`대상 장치의 특성에 따라 단어 래핑을 나타냅니다.

### <a name="example"></a>예제

  [CRichEditView::WrapChanged](#wrapchanged)에 대한 예제를 참조하십시오.

## <a name="cricheditviewonchareffect"></a><a name="onchareffect"></a>리치에이트 뷰::온차 효과

이 함수를 호출하여 현재 선택 영역에 대한 문자 서식 지정 효과를 토글합니다.

```cpp
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>매개 변수

*dwMask*<br/>
현재 선택 에서 수정할 문자 서식 지정 효과입니다.

*dw 이펙트*<br/>
토글할 문자 서식 지정 효과의 원하는 목록입니다.

### <a name="remarks"></a>설명

이 함수에 대한 각 호출은 현재 선택 영역에 대해 지정된 서식 지정 효과를 전환합니다.

*dwMask* 및 *dwEffect* 매개 변수 및 해당 잠재적 값에 대한 자세한 내용은 Windows SDK에서 [CHARFORMAT의](/windows/win32/api/richedit/ns-richedit-charformata) 해당 데이터 멤버를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

## <a name="cricheditviewonfindnext"></a><a name="onfindnext"></a>리치에이트 뷰::온파인트넥스트

찾기/바꾸기 대화 상자에서 명령을 처리할 때 프레임워크에서 호출됩니다.

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 문자열입니다.

*b다음*<br/>
검색 방향: TRUE는 아래로 나타냅니다. 거짓, 최대.

*b 케이스*<br/>
검색이 대/소문자를 구분할 지 여부를 나타냅니다.

*bWord*<br/>
검색이 전체 단어만 일치하는지 여부를 나타냅니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 `CRichEditView`에서 텍스트를 찾습니다. 파생 뷰 클래스의 검색 특성을 변경하려면 이 함수를 재정의합니다.

## <a name="cricheditviewoninitialupdate"></a><a name="oninitialupdate"></a>CRichEditView::초기 업데이트

뷰가 문서에 처음 연결되지만 뷰가 처음 표시되기 전에 프레임워크에서 호출됩니다.

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>설명

이 함수의 기본 구현은 힌트 정보가 없는 [CView:OnUpdate](../../mfc/reference/cview-class.md#onupdate) 멤버 함수를 호출합니다(즉, *lHint* 매개 변수에 대해 0의 기본값을 사용하고 *pHint* 매개 변수에 NULL을 사용함). 이 함수를 재정의하여 문서에 대한 정보가 필요한 일회성 초기화를 수행합니다. 예를 들어 응용 프로그램에 고정 크기의 문서가 있는 경우 이 함수를 사용하여 문서 크기에 따라 뷰의 스크롤 제한을 초기화할 수 있습니다. 응용 프로그램에서 가변 크기의 문서를 `OnUpdate` 지원하는 경우 문서가 변경될 때마다 스크롤 제한을 업데이트하는 데 사용합니다.

### <a name="example"></a>예제

  [CRichEditView::m_nWordWrap](#m_nwordwrap)에 대한 예제를 참조하십시오.

## <a name="cricheditviewonpastenativeobject"></a><a name="onpastenativeobject"></a>CRichEditView::온페이스트네이티브 오브젝트

이 함수를 사용하여 포함된 항목에서 기본 데이터를 로드합니다.

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>매개 변수

*lpStg*<br/>
[IStorage](/windows/win32/api/objidl/nn-objidl-istorage) 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 0;

### <a name="remarks"></a>설명

일반적으로 `IStorage`을 중심으로 [COleStreamFile을](../../mfc/reference/colestreamfile-class.md) 만들어 이 작업을 수행합니다. 는 `COleStreamFile` 아카이브 및 [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) 데이터를 로드 하기 위해 호출에 연결할 수 있습니다.

이 고급 재정의 할 수 있습니다.

자세한 내용은 Windows SDK의 [IStorage를](/windows/win32/api/objidl/nn-objidl-istorage) 참조하십시오.

## <a name="cricheditviewonparaalign"></a><a name="onparaalign"></a>리치에이트 뷰::온파라정렬

선택한 단락의 단락 정렬을 변경하려면 이 함수를 호출합니다.

```cpp
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>매개 변수

*wAlign*<br/>
원하는 단락 정렬. 해당 값은

- PFA_LEFT 단락을 왼쪽 여백과 정렬합니다.

- PFA_RIGHT 단락을 오른쪽 여백에 정렬합니다.

- PFA_CENTER 여백 사이에 단락을 가운데로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

## <a name="cricheditviewonprinterchanged"></a><a name="onprinterchanged"></a>CRichEditView::온프린터 변경

프린터가 변경될 때 이 풍부한 편집 뷰의 특성을 변경하려면 이 함수를 재정의합니다.

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>매개 변수

*dc프린터*<br/>
새 프린터의 [CDC](../../mfc/reference/cdc-class.md) 개체입니다.

### <a name="remarks"></a>설명

기본 구현에서는 용지 크기를 출력 장치(프린터)의 실제 높이 및 너비로 설정합니다. *dcPrinter와*연결된 장치 컨텍스트가 없는 경우 기본 구현에서 용지 크기를 8.5 x 11인치로 설정합니다.

## <a name="cricheditviewonreplaceall"></a><a name="onreplaceall"></a>리치에이트 뷰::에대체 모두

처리 할 때 프레임 워크에 의해 호출 대체 대화 상자에서 모든 명령 바꾸기.

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
대체할 텍스트입니다.

*lpszReplace*<br/>
대체 텍스트입니다.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 나타냅니다.

*bWord*<br/>
검색에서 전체 단어를 선택해야 하는지 여부가 나타냅니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 지정된 일부 텍스트의 모든 발생을 다른 문자열로 바꿉습니다. 이 함수를 재정의하여 이 뷰의 검색 특성을 변경합니다.

### <a name="example"></a>예제

  [CRichEditView::FindText](#findtext)에 대한 예제를 참조하십시오.

## <a name="cricheditviewonreplacesel"></a><a name="onreplacesel"></a>리치에이트 뷰::에대체셀

대체 대화 상자에서 Replace 명령을 처리할 때 프레임워크에서 호출합니다.

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
대체할 텍스트입니다.

*b다음*<br/>
검색 방향을 나타냅니다: TRUE가 다운되었습니다. 거짓, 최대.

*b 케이스*<br/>
검색이 대/소문자를 구분하는지 나타냅니다.

*bWord*<br/>
검색에서 전체 단어를 선택해야 하는지 여부가 나타냅니다.

*lpszReplace*<br/>
대체 텍스트입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 지정된 텍스트의 한 번의 발생을 다른 문자열로 바꿉습니다. 이 함수를 재정의하여 이 뷰의 검색 특성을 변경합니다.

## <a name="cricheditviewontextnotfound"></a><a name="ontextnotfound"></a>CrichEdit뷰::온텍스트Not

검색에 실패할 때마다 프레임워크에서 호출됩니다.

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 없는 텍스트입니다.

### <a name="remarks"></a>설명

이 함수를 재정의하여 [MessageBeep](/windows/win32/api/winuser/nf-winuser-messagebeep)에서 출력 알림을 변경합니다.

자세한 내용은 Windows SDK의 [MessageBeep를](/windows/win32/api/winuser/nf-winuser-messagebeep) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

## <a name="cricheditviewonupdatechareffect"></a><a name="onupdatechareffect"></a>CrichEdit뷰::온업데이트차효과

프레임워크는 이 함수를 호출하여 문자 효과 명령에 대한 명령 UI를 업데이트합니다.

```cpp
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) 개체에 대한 포인터입니다.

*dwMask*<br/>
문자 서식 지정 마스크를 나타냅니다.

*dw 이펙트*<br/>
문자 서식 지정 효과를 나타냅니다.

### <a name="remarks"></a>설명

마스크 *dwMask는* 확인할 문자 서식 지정 특성을 지정합니다. 플래그 *dwEffect* 설정/지우기 문자 서식 특성을 나열 합니다.

*dwMask* 및 *dwEffect* 매개 변수 및 해당 잠재적 값에 대한 자세한 내용은 Windows SDK에서 [CHARFORMAT의](/windows/win32/api/richedit/ns-richedit-charformata) 해당 데이터 멤버를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

## <a name="cricheditviewonupdateparaalign"></a><a name="onupdateparaalign"></a>CrichEdit뷰::OnUpdateParaAlign

프레임워크는 이 함수를 호출하여 단락 효과 명령에 대한 명령 UI를 업데이트합니다.

```cpp
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>매개 변수

*pCmdUI*<br/>
[CCmdUI](../../mfc/reference/ccmdui-class.md) 개체에 대한 포인터입니다.

*wAlign*<br/>
확인할 단락 정렬입니다. 해당 값은

- PFA_LEFT 단락을 왼쪽 여백과 정렬합니다.

- PFA_RIGHT 단락을 오른쪽 여백에 정렬합니다.

- PFA_CENTER 여백 사이에 단락을 가운데로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

## <a name="cricheditviewprintinsiderect"></a><a name="printinsiderect"></a>CRichEditView::P린트인사이드렉트

*pDC에서*지정한 장치의 *rectLayout* 내에 맞게 리치 편집 컨트롤의 텍스트 범위를 포맷하려면 이 함수를 호출합니다.

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
출력 영역에 대한 장치 컨텍스트에 대한 포인터입니다.

*정류 레이아웃*<br/>
출력 영역을 정의하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 또는 [CRect입니다.](../../atl-mfc-shared/reference/crect-class.md)

*nIndexStart*<br/>
서식을 지정할 첫 번째 문자의 0기반 인덱스입니다.

*n인덱스 스탑*<br/>
서식을 지정할 마지막 문자의 0기반 인덱스입니다.

*b출력*<br/>
텍스트를 렌더링해야 하는지 를 나타냅니다. FALSE인 경우 텍스트는 측정됩니다.

### <a name="return-value"></a>Return Value

출력 영역에 맞는 마지막 문자의 인덱스와 1을 더한 인덱스입니다.

### <a name="remarks"></a>설명

일반적으로 이 호출 다음에는 출력을 생성하는 [CRichEditCtrl::DisplayBand를](../../mfc/reference/cricheditctrl-class.md#displayband) 호출합니다.

### <a name="example"></a>예제

  [CRichEditView::GetPaperSize에](#getpapersize)대한 예제를 참조하십시오.

## <a name="cricheditviewprintpage"></a><a name="printpage"></a>CRichEditView::P린트페이지

*pDC에서*지정한 출력 장치에 대한 풍부한 편집 컨트롤에서 텍스트 범위를 포맷하려면 이 함수를 호출합니다.

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
페이지 출력을 위한 장치 컨텍스트에 대한 포인터입니다.

*nIndexStart*<br/>
서식을 지정할 첫 번째 문자의 0기반 인덱스입니다.

*n인덱스 스탑*<br/>
서식을 지정할 마지막 문자의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

페이지에 맞는 마지막 문자의 인덱스와 1을 더한 인덱스입니다.

### <a name="remarks"></a>설명

각 페이지의 레이아웃은 [GetPageRect](#getpagerect) 및 [GetPrintRect에 의해 제어됩니다.](#getprintrect) 일반적으로 이 호출 다음에는 출력을 생성하는 [CRichEditCtrl::DisplayBand를](../../mfc/reference/cricheditctrl-class.md#displayband) 호출합니다.

여백은 논리 페이지가 아니라 실제 페이지를 기준으로 합니다. 따라서 많은 프린터에 인쇄할 수 없는 영역이 페이지에 있으므로 여백이 0인 경우가 많습니다. 텍스트가 클리핑되지 않도록 하려면 [SetMargins를](#setmargins) 호출하고 인쇄하기 전에 적절한 여백을 설정해야 합니다.

## <a name="cricheditviewqueryacceptdata"></a><a name="queryacceptdata"></a>CRichEditView::쿼리 수락데이터

리치 편집에 개체를 붙여 넣기 위해 프레임워크에서 호출합니다.

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>매개 변수

*lpdataobj*<br/>
쿼리할 [IDataObject에](/windows/win32/api/objidl/nn-objidl-idataobject) 대한 포인터입니다.

*lpcfFormat*<br/>
허용되는 데이터 형식에 대한 포인터입니다.

*dwReco*<br/>
사용되지 않습니다.

*b정말*<br/>
붙여넣기 작업이 계속되어야 하는지 여부입니다.

*h메타파일*<br/>
항목아이콘을 그리는 데 사용되는 메타파일의 핸들입니다.

### <a name="return-value"></a>Return Value

작업의 성공을 보고하는 HRESULT 값입니다.

### <a name="remarks"></a>설명

파생 문서 클래스에서 COM 항목의 다른 조직을 처리 하려면이 기능을 재정의 합니다. 이 고급 재정의 할 수 있습니다.

HRESULT 및 `IDataObject`에 대한 자세한 내용은 Windows SDK에서 COM 오류 코드 및 [IDataObject의](/windows/win32/api/objidl/nn-objidl-idataobject) [구조를](/windows/win32/com/structure-of-com-error-codes) 각각 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

## <a name="cricheditviewsetcharformat"></a><a name="setcharformat"></a>CRichEditView::세트차형식

이 함수를 호출하여 이 `CRichEditView` 개체의 새 텍스트에 대한 문자 서식 지정 특성을 설정합니다.

```cpp
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
새 기본 문자 서식 지정 특성을 포함하는 [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) 구조입니다.

### <a name="remarks"></a>설명

`dwMask` *cf의* 멤버가 지정한 특성만 이 함수에 의해 변경됩니다.

자세한 내용은 Windows SDK의 [EM_SETCHARFORMAT](/windows/win32/Controls/em-setcharformat) 메시지 및 [CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w) 구조를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewsetmargins"></a><a name="setmargins"></a>CRichEditView::세트 마진

이 함수를 호출하여 이 풍부한 편집 뷰의 인쇄 여백을 설정합니다.

```cpp
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>매개 변수

*정사각형 여백*<br/>
MM_TWIPS 측정된 인쇄의 새 여백 값입니다.

### <a name="remarks"></a>설명

[m_nWordWrap](#m_nwordwrap) `WrapToTargetDevice`경우 이 함수를 사용하여 인쇄 특성을 조정한 후 [WrapChanged를](#wrapchanged) 호출해야 합니다.

[PrintPage에서](#printpage) 사용하는 여백은 논리 페이지가 아니라 실제 페이지를 기준으로 합니다. 따라서 많은 프린터에 인쇄할 수 없는 영역이 페이지에 있으므로 여백이 0인 경우가 많습니다. 텍스트가 클리핑되지 않도록 하려면 `SetMargins` 인쇄하기 전에 적절한 프린터 여백을 설정하기 위해 전화를 걸어야 합니다.

### <a name="example"></a>예제

  [CRichEditView::GetPaperSize에](#getpapersize)대한 예제를 참조하십시오.

## <a name="cricheditviewsetpapersize"></a><a name="setpapersize"></a>리치에이트 뷰::세트페이퍼크기

이 함수를 호출하여 이 풍부한 편집 뷰를 인쇄하기 위한 용지 크기를 설정합니다.

```cpp
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>매개 변수

*크기용지*<br/>
MM_TWIPS 측정된 인쇄를 위한 새 용지 크기 값입니다.

### <a name="remarks"></a>설명

[m_nWordWrap](#m_nwordwrap) `WrapToTargetDevice`경우 이 함수를 사용하여 인쇄 특성을 조정한 후 [WrapChanged를](#wrapchanged) 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

## <a name="cricheditviewsetparaformat"></a><a name="setparaformat"></a>CRichEditView::SetParaFormat

이 함수를 호출하여 이 `CRichEditView` 개체의 현재 선택 영역에 대한 단락 서식 지정 특성을 설정합니다.

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>매개 변수

*Pf*<br/>
새 기본 단락 서식 지정 특성을 포함하는 [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) 구조체입니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`dwMask` *pf의* 멤버에 의해 지정 된 특성만이 함수에 의해 변경 됩니다.

자세한 내용은 Windows SDK의 [EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat) 메시지 및 [PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2) 구조를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

## <a name="cricheditviewtextnotfound"></a><a name="textnotfound"></a>CRichEditView::텍스트찾을 수 없습니다

FindText 에 대한 호출이 실패한 후 [CRichEditView](../../mfc/reference/cricheditview-class.md) 컨트롤의 내부 검색 상태를 재설정하려면 이 함수를 [호출합니다.](#findtext)

```cpp
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>매개 변수

*lpszFind*<br/>
찾을 수 없는 텍스트 문자열을 포함합니다.

### <a name="remarks"></a>설명

컨트롤의 내부 검색 상태가 제대로 재설정되도록 [FindText에](#findtext) 대한 호출에 실패한 직후에 이 메서드를 호출하는 것이 좋습니다.

*lpszFind* 매개 변수는 [FindText](#findtext)에 제공된 문자열과 동일한 내용을 포함해야 합니다. 내부 검색 상태를 재설정한 후 이 메서드는 제공된 검색 문자열을 사용하여 [OnTextNotFound](#ontextnotfound) 메서드를 호출합니다.

### <a name="example"></a>예제

  [CRichEditView::FindText](#findtext)에 대한 예제를 참조하십시오.

## <a name="cricheditviewwrapchanged"></a><a name="wrapchanged"></a>CRichEditView::랩 변경

인쇄 특성이 변경되면 이 함수를 [호출합니다(SetMargins](#setmargins) 또는 [SetPaperSize).](#setpapersize)

```
virtual void WrapChanged();
```

### <a name="remarks"></a>설명

이 함수를 재정의하여 m_nWordWrap [변경](#m_nwordwrap) 또는 인쇄 [특성(OnPrinterChanged)의](#onprinterchanged)변경 사항에 리치 편집 뷰가 응답하는 방식을 수정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 워드패드](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView 클래스](../../mfc/reference/cctrlview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[리치에이트닥 클래스](../../mfc/reference/cricheditdoc-class.md)<br/>
[리치에이트Cntr항목 클래스](../../mfc/reference/cricheditcntritem-class.md)
