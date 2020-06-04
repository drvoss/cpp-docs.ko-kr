---
title: C헤더Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: de1705d47c5692d3563bc7d9cb2646531819197a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750925"
---
# <a name="cheaderctrl-class"></a>C헤더Ctrl 클래스

Windows의 공용 헤더 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C헤더Ctrl:::C헤더Ctrl](#cheaderctrl)|`CHeaderCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C헤더Ctrl::클리어올필터](#clearallfilters)|헤더 컨트롤에 대한 모든 필터를 지웁습니다.|
|[C헤더Ctrl::클리어 필터](#clearfilter)|헤더 컨트롤에 대한 필터를 지웁습니다.|
|[C헤더Ctrl::만들기](#create)|헤더 컨트롤을 만들고 개체에 `CHeaderCtrl` 연결합니다.|
|[C헤더Ctrl::드래그 이미지 만들기](#createdragimage)|헤더 컨트롤 내에서 항목 이미지의 투명한 버전을 만듭니다.|
|[C헤더Ctrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 헤더 컨트롤을 만들고 `CListCtrl` 개체에 연결합니다.|
|[C헤더Ctrl::Delete항목](#deleteitem)|헤더 컨트롤에서 항목을 삭제합니다.|
|[C헤더Ctrl::D원시아이템](#drawitem)|헤더 컨트롤의 지정된 항목을 그립니다.|
|[C헤더Ctrl::편집 필터](#editfilter)|헤더 컨트롤의 지정된 필터 편집을 시작합니다.|
|[C헤더Ctrl::GetBitmap마진](#getbitmapmargin)|헤더 컨트롤에서 비트맵 여백의 너비를 검색합니다.|
|[C헤더Ctrl::GetFocusedItem](#getfocuseditem)|포커스가 있는 현재 헤더 컨트롤에서 항목의 식별자를 가져옵니다.|
|[C헤더Ctrl::GetImageList](#getimagelist)|헤더 컨트롤에서 헤더 항목을 그리는 데 사용되는 이미지 목록의 핸들을 검색합니다.|
|[C헤더Ctrl::GetItem](#getitem)|헤더 컨트롤의 항목에 대한 정보를 검색합니다.|
|[C헤더Ctrl::겟아이템카운트](#getitemcount)|헤더 컨트롤의 항목 수를 검색합니다.|
|[CHeaderCtrl:::GetItem드롭다운렉트](#getitemdropdownrect)|헤더 컨트롤에서 지정된 드롭다운 단추에 대한 경계 사각형 정보를 가져옵니다.|
|[C헤더Ctrl::겟아이템렉트](#getitemrect)|헤더 컨트롤에서 지정된 항목에 대한 경계 사각형을 검색합니다.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 검색합니다.|
|[C헤더Ctrl::오버플로우렉트](#getoverflowrect)|현재 헤더 컨트롤에 대한 오버플로 단추의 경계 사각형을 가져옵니다.|
|[C헤더Ctrl::히트테스트](#hittest)|지정된 지점에 있는 헤더 항목(있는 경우)을 결정합니다.|
|[C헤더Ctrl::삽입항목](#insertitem)|새 항목을 헤더 컨트롤에 삽입합니다.|
|[C헤더Ctrl::레이아웃](#layout)|지정된 사각형 내에서 헤더 컨트롤의 크기와 위치를 검색합니다.|
|[C헤더Ctrl::주문토인덱스](#ordertoindex)|헤더 컨트롤의 순서에 따라 항목에 대한 인덱스 값을 검색합니다.|
|[C헤더Ctrl::세트비트맵마진](#setbitmapmargin)|헤더 컨트롤에서 비트맵 여백의 너비를 설정합니다.|
|[C헤더Ctrl::세트필터변경시간](#setfilterchangetimeout)|필터 특성에서 변경이 발생하는 시간과 알림 게시 사이의 시간 시간 `HDN_FILTERCHANGE` 간격을 설정합니다.|
|[C헤더Ctrl::세트포커스항목](#setfocuseditem)|포커스를 현재 헤더 컨트롤의 지정된 헤더 항목으로 설정합니다.|
|[C헤더Ctrl:::세트핫디바이더](#sethotdivider)|헤더 항목 간의 구분을 변경하여 헤더 항목의 수동 드래그 앤 드롭을 나타냅니다.|
|[C헤더Ctrl::세트이미지리스트](#setimagelist)|헤더 컨트롤에 이미지 목록을 할당합니다.|
|[C헤더Ctrl::세트아이템](#setitem)|헤더 컨트롤에서 지정된 항목의 특성을 설정합니다.|
|[C헤더Ctrl::세트순서 배열](#setorderarray)|헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 설정합니다.|

## <a name="remarks"></a>설명

헤더 컨트롤은 일반적으로 텍스트 또는 숫자 열 집합 위에 배치되는 창입니다. 각 열에 대한 제목이 포함되어 있으며 부분으로 나눌 수 있습니다. 사용자는 부품을 분리하는 칸막이를 드래그하여 각 열의 너비를 설정할 수 있습니다. 헤더 컨트롤의 그림은 헤더 [컨트롤](/windows/win32/Controls/header-controls)을 참조하십시오.

이 컨트롤(및 `CHeaderCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

Windows 95/Internet Explorer 4.0 일반 컨트롤에 추가된 기능에는 다음이 포함됩니다.

- 헤더 항목 사용자 정의 순서입니다.

- 헤더 항목의 순서를 조정하기 위해 헤더 항목을 드래그 앤 드롭합니다. `CHeaderCtrl` 객체를 만들 때 HDS_DRAGDROP 스타일을 사용합니다.

- 열 크기를 조정하는 동안 헤더 열 텍스트를 계속 볼 수 있습니다. `CHeaderCtrl` 객체를 작성할 때 HDS_FULLDRAG 스타일을 사용합니다.

- 포인터가 가리키는 경우 헤더 항목을 강조 표시됩니다. `CHeaderCtrl` 객체를 작성할 때 HDS_HOTTRACK 스타일을 사용합니다.

- 이미지 목록 지원. 헤더 항목에는 개체 또는 `CImageList` 텍스트에 저장된 이미지가 포함될 수 있습니다.

사용에 `CHeaderCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CHeaderCtrl 사용](../../mfc/using-cheaderctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>C헤더Ctrl:::C헤더Ctrl

`CHeaderCtrl` 개체를 생성합니다.

```
CHeaderCtrl();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>C헤더Ctrl::클리어올필터

헤더 컨트롤에 대한 모든 필터를 지웁습니다.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) 설명된 대로 열 값 -1을 사용 하 HDM_CLEARFILTER Win32 메시지의 동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a>C헤더Ctrl::클리어 필터

헤더 컨트롤에 대한 필터를 지웁습니다.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>매개 변수

*n열*<br/>
지울 필터를 나타내는 열 값입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명된 대로 HDM_CLEARFILTER Win32 [메시지의](/windows/win32/Controls/hdm-clearfilter)동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a>C헤더Ctrl::만들기

헤더 컨트롤을 만들고 개체에 `CHeaderCtrl` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
헤더 컨트롤의 스타일을 지정합니다. 헤더 제어 스타일에 대한 설명은 Windows SDK의 [헤더 제어 스타일을](/windows/win32/Controls/header-control-styles) 참조하십시오.

*rect*<br/>
헤더 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
헤더 컨트롤의 부모 창(일반적으로 )을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
헤더 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CHeaderCtrl` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 합니다 . `CHeaderCtrl`

헤더 제어 스타일 외에도 다음 공통 제어 스타일을 사용하여 헤더 제어 위치 및 크기 조정 방법을 확인할 수 있습니다(자세한 내용은 [공용 제어 스타일](/windows/win32/Controls/common-control-styles) 참조).

- CCS_BOTTOM 컨트롤이 부모 창의 클라이언트 영역 의 맨 아래에 배치되고 너비가 부모 창의 너비와 같도록 설정합니다.

- CCS_NODIVIDER 컨트롤의 맨 위에 2픽셀 강조 표시가 그려지지 않도록 합니다.

- CCS_NOMOVEY WM_SIZE 메시지에 대한 응답으로 컨트롤의 크기를 조정하고 세로로 이동하지 않고 세로로 이동합니다. CCS_NORESIZE 스타일을 사용하는 경우 이 스타일은 적용되지 않습니다. 헤더 컨트롤에는 기본적으로 이 스타일이 있습니다.

- CCS_NOPARENTALIGN 컨트롤이 부모 창의 위쪽 또는 아래쪽으로 자동으로 이동하지 못하게 합니다. 대신 컨트롤은 부모 창의 크기가 변경에도 불구하고 부모 창 내에서 위치를 유지합니다. CCS_TOP 또는 CCS_BOTTOM 스타일도 사용되는 경우 높이는 기본값으로 조정되지만 위치와 너비는 변경되지 않습니다.

- CCS_NORESIZE 컨트롤의 초기 크기 또는 새 크기를 설정할 때 기본 너비와 높이를 사용하지 못하게 합니다. 대신 컨트롤은 만들기 또는 크기 조정 요청에 지정된 너비와 높이를 사용합니다.

- CCS_TOP 컨트롤이 부모 창의 클라이언트 영역 의 맨 위에 배치되고 너비가 부모 창의 너비와 같도록 설정합니다.

다음 창 스타일을 헤더 컨트롤에 적용할 수도 있습니다(자세한 내용은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 참조).

- WS_CHILD 하위 창을 만듭니다. WS_POPUP 스타일과 함께 사용할 수 없습니다.

- WS_VISIBLE 처음에 표시되는 창을 만듭니다.

- WS_DISABLED 처음에 사용하지 않도록 설정한 창을 만듭니다.

- WS_GROUP 사용자가 화살표 키를 사용하여 한 컨트롤에서 다음 컨트롤로 이동할 수 있는 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다. 첫 번째 컨트롤 이후에 WS_GROUP 스타일로 정의된 모든 컨트롤은 동일한 그룹에 속합니다. WS_GROUP 스타일로 다음 컨트롤은 스타일 그룹을 종료하고 다음 그룹을 시작합니다(즉, 한 그룹은 다음 그룹이 시작되는 지점).

- WS_TABSTOP 사용자가 TAB 키를 사용하여 이동할 수 있는 여러 컨트롤 중 하나를 지정합니다. TAB 키는 사용자를 WS_TABSTOP 스타일로 지정된 다음 컨트롤로 이동합니다.

컨트롤과 함께 확장 된 창 스타일을 사용 하려면 `Create`호출 [CreateEx](#createex) 대신 .

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a>C헤더Ctrl::만들기

컨트롤(하위 창)을 만들고 개체와 `CHeaderCtrl` 연결합니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
생성되는 컨트롤의 확장 스타일을 지정합니다. 확장 된 Windows 스타일 목록은 Windows SDK에서 [CreateWindowEx에](/windows/win32/api/winuser/nf-winuser-createwindowexw) 대한 *dwExStyle* 매개 변수를 참조하십시오.

*dwStyle*<br/>
헤더 컨트롤의 스타일입니다. 헤더 제어 스타일에 대한 설명은 Windows SDK의 [헤더 제어 스타일을](/windows/win32/Controls/header-control-styles) 참조하십시오. 추가 스타일 목록은 [만들기를](#create) 참조하십시오.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 생성할 창의 크기와 위치를 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows `CreateEx` 확장 `Create` 스타일 **서문 WS_EX_** 지정된 확장 된 Windows 스타일을 적용하는 대신 사용합니다.

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>C헤더Ctrl::드래그 이미지 만들기

헤더 컨트롤 내에서 항목 이미지의 투명한 버전을 만듭니다.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
헤더 컨트롤 내의 항목의 0기반 인덱스입니다. 이 항목에 할당된 이미지는 투명 이미지의 기초입니다.

### <a name="return-value"></a>Return Value

성공하면 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터; 그렇지 않으면 NULL. 반환된 목록에는 이미지가 하나만 들어 있습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_CREATEDRAGIMAGE Win32 [메시지의](/windows/win32/Controls/hdm-createdragimage)동작을 구현합니다. 헤더 항목 드래그 앤 드롭을 지원하기 위해 제공됩니다.

반환된 포인터 가리키는 `CImageList` 개체는 임시 개체이며 다음 유휴 시간 처리에서 삭제됩니다.

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a>C헤더Ctrl::Delete항목

헤더 컨트롤에서 항목을 삭제합니다.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
삭제할 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a>C헤더Ctrl::D원시아이템

소유자-draw 헤더 컨트롤의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
페인팅할 항목을 설명하는 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다.

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CHeaderCtrl`

응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에서* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a>C헤더Ctrl::편집 필터

헤더 컨트롤의 지정된 필터를 편집하기 시작합니다.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>매개 변수

*n열*<br/>
편집할 열입니다.

*b변경변경사항 삭제*<br/>
[HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter) 메시지가 전송될 때 사용자가 필터를 편집하는 중일 때 사용자의 편집 변경 내용을 처리하는 방법을 지정하는 값입니다.

TRUE를 지정하여 사용자가 변경한 내용을 취소하거나 FALSE를 사용하여 사용자가 변경한 내용을 수락하도록 지정합니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명된 대로 HDM_EDITFILTER Win32 [메시지의](/windows/win32/Controls/hdm-editfilter)동작을 구현 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>C헤더Ctrl::GetBitmap마진

헤더 컨트롤에서 비트맵 여백의 너비를 검색합니다.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>Return Value

비트맵 여백의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin)Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>C헤더Ctrl::GetFocusedItem

현재 헤더 컨트롤에 포커스가 있는 항목의 인덱스를 가져옵니다.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>Return Value

포커스가 있는 헤더 항목의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_headerCtrl`헤더 컨트롤에 액세스하는 데 사용되는 변수, 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 `SetFocusedItem` 및 `GetFocusedItem` 메서드를 보여 줍니다. 코드의 이전 섹션에서는 5개의 열이 있는 헤더 컨트롤을 만들었습니다. 그러나 열 구분 기호를 드래그하여 열이 표시되지 않도록 할 수 있습니다. 다음 예제는 마지막 열 헤더를 포커스 항목으로 설정한 다음 확인합니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a>C헤더Ctrl::GetImageList

헤더 컨트롤에서 헤더 항목을 그리는 데 사용되는 이미지 목록의 핸들을 검색합니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Return Value

[CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_GETIMAGELIST Win32 [메시지의](/windows/win32/Controls/hdm-getimagelist)동작을 구현합니다. 반환된 포인터 가리키는 `CImageList` 개체는 임시 개체이며 다음 유휴 시간 처리에서 삭제됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a>C헤더Ctrl::GetItem

헤더 제어 항목에 대한 정보를 검색합니다.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
검색할 항목의 0기반 인덱스를 지정합니다.

*p헤더아이템*<br/>
새 항목을 받는 [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 구조에 대한 포인터입니다. 이 구조는 `InsertItem` 및 `SetItem` 멤버 함수와 함께 사용됩니다. `mask` 요소에 설정된 모든 플래그는 반환 시 해당 요소의 값이 제대로 채워지도록 합니다. `mask` 요소가 0으로 설정된 경우 다른 구조 요소의 값은 의미가 없습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a>C헤더Ctrl::겟아이템카운트

헤더 컨트롤의 항목 수를 검색합니다.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 헤더 제어 항목 수입니다. 그렇지 않은 경우 - 1.

### <a name="example"></a>예제

  [CHeaderCtrl::DeleteItem](#deleteitem)에 대한 예제를 참조하십시오.

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>CHeaderCtrl:::GetItem드롭다운렉트

현재 헤더 컨트롤에서 헤더 항목에 대한 드롭다운 단추의 경계 사각형을 가져옵니다.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iItem*|【인】 스타일이 HDF_SPLITBUTTON 헤더 항목의 0기준 인덱스입니다. 자세한 내용은 `fmt` [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 구조의 멤버를 참조하십시오.|
|*Lprect*|【아웃】 경계 사각형 정보를 수신하려면 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 함수가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_headerCtrl`헤더 컨트롤에 액세스하는 데 사용되는 변수, 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetItemDropDownRect` 메서드. 코드의 이전 섹션에서는 5개의 열이 있는 헤더 컨트롤을 만들었습니다. 다음 코드 예제는 헤더 드롭다운 단추에 대해 예약된 첫 번째 열의 위치 주위에 3D 사각형을 그립니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a>C헤더Ctrl::겟아이템렉트

헤더 컨트롤에서 지정된 항목에 대한 경계 사각형을 검색합니다.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
헤더 제어 항목의 0기반 인덱스입니다.

*Lprect*<br/>
경계 사각형 정보를 수신하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조의 주소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명된 대로 HDM_GETITEMRECT Win32 [메시지의](/windows/win32/Controls/hdm-getitemrect)동작을 구현 합니다.

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a>CHeaderCtrl::GetOrderArray

헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 검색합니다.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>매개 변수

*piArray*<br/>
헤더 컨트롤에서 항목의 인덱스 값을 왼쪽에서 오른쪽으로 표시하는 순서대로 받는 버퍼의 주소에 대한 포인터입니다.

*iCount*<br/>
헤더 제어 항목의 수입니다. 음수가 아닌 여야 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_GETORDERARRAY Win32 [메시지의](/windows/win32/Controls/hdm-getorderarray)동작을 구현합니다. 헤더 항목 순서를 지원하기 위해 제공됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>C헤더Ctrl::오버플로우렉트

현재 헤더 컨트롤의 오버플로 단추의 경계 사각형을 가져옵니다.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*Lprect*|【아웃】 경계 사각형 정보를 받는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 함수가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

헤더 컨트롤에 동시에 표시할 수 있는 항목보다 많은 항목이 포함된 경우 컨트롤에 표시되지 않는 항목으로 스크롤되는 오버플로 단추를 표시할 수 있습니다. 헤더 컨트롤에는 오버플로 단추를 표시할 HDS_OVERFLOW 및 HDF_SPLITBUTTON 스타일이 있어야 합니다. 경계 사각형은 오버플로 단추를 둘러싸고 오버플로 버튼이 표시될 때만 존재합니다. 자세한 내용은 [헤더 제어 스타일을](/windows/win32/Controls/header-control-styles)참조하십시오.

이 메서드는 Windows SDK에 설명 된 [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_headerCtrl`헤더 컨트롤에 액세스하는 데 사용되는 변수, 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetOverflowRect` 메서드. 코드의 이전 섹션에서는 5개의 열이 있는 헤더 컨트롤을 만들었습니다. 그러나 열 구분 기호를 드래그하여 열이 표시되지 않도록 할 수 있습니다. 일부 열이 표시되지 않으면 헤더 컨트롤에 오버플로 버튼이 그려져 있습니다. 다음 코드 예제는 오버플로 단추의 위치 주위에 3D 사각형을 그립니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a>C헤더Ctrl::히트테스트

지정된 지점에 있는 헤더 항목(있는 경우)을 결정합니다.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*phdhti*|【인, 아웃】 테스트 할 지점을 지정하고 테스트 결과를 받는 [HDHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

지정된 위치에서 헤더 항목의 0기반 인덱스(있는 경우)입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_headerCtrl`헤더 컨트롤에 액세스하는 데 사용되는 변수, 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `HitTest` 메서드. 이 코드 예제의 이전 섹션에서는 5개의 열이 있는 헤더 컨트롤을 만들었습니다. 그러나 열 구분 기호를 드래그하여 열이 표시되지 않도록 할 수 있습니다. 이 예제는 열이 표시되는 경우 열의 인덱스를 보고하고 열이 표시되지 않으면 -1을 보고합니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a>C헤더Ctrl::삽입항목

지정된 인덱스에서 헤더 컨트롤에 새 항목을 삽입합니다.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
삽입할 항목의 인덱스(0부터 시작)입니다. 값이 0이면 항목이 헤더 컨트롤의 시작 부분에 삽입됩니다. 값이 최대값보다 크면 항목이 헤더 컨트롤의 끝에 삽입됩니다.

*phdi*<br/>
삽입할 항목에 대한 정보가 포함된 [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 새 항목의 인덱스; 그렇지 않은 경우 - 1.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a>C헤더Ctrl::레이아웃

지정된 사각형 내에서 헤더 컨트롤의 크기와 위치를 검색합니다.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>매개 변수

*p헤더레이아웃*<br/>
헤더 컨트롤의 크기와 위치를 설정하는 데 사용되는 정보가 포함된 [HDLAYOUT](/windows/win32/api/commctrl/ns-commctrl-hdlayout) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 지정된 사각형을 차지하는 새 헤더 컨트롤에 적합한 차원을 결정하는 데 사용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a>C헤더Ctrl::주문토인덱스

헤더 컨트롤의 순서에 따라 항목에 대한 인덱스 값을 검색합니다.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>매개 변수

*n순서*<br/>
항목이 헤더 컨트롤에 왼쪽에서 오른쪽으로 표시되는 0기반 순서입니다.

### <a name="return-value"></a>Return Value

헤더 컨트롤의 순서에 따라 항목의 인덱스입니다. 인덱스는 0부터 시작하여 왼쪽에서 오른쪽으로 계산됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_ORDERTOINDEX Win32 [매크로의](/windows/win32/controls/hdm-ordertoindex)동작을 구현합니다. 헤더 항목 순서를 지원하기 위해 제공됩니다.

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>C헤더Ctrl::세트비트맵마진

헤더 컨트롤에서 비트맵 여백의 너비를 설정합니다.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
기존 헤더 컨트롤 내에서 비트맵을 둘러싸는 여백의 픽셀로 지정된 너비입니다.

### <a name="return-value"></a>Return Value

비트맵 여백의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_SETBITMAPMARGIN Win32 [메시지의](/windows/win32/Controls/hdm-setbitmapmargin)동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>C헤더Ctrl::세트필터변경시간

필터 특성에서 변경이 발생하는 시간과 [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) 알림 게시 사이의 시간 시간 간격을 설정합니다.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>매개 변수

*dw타임아웃*<br/>
시간 시간(밀리초)입니다.

### <a name="return-value"></a>Return Value

수정중인 필터 컨트롤의 인덱스입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout)Win32 메시지의 동작을 구현합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>C헤더Ctrl::세트포커스항목

포커스를 현재 헤더 컨트롤의 지정된 헤더 항목으로 설정합니다.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iItem*|【인】 헤더 항목의 0기반 인덱스입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_headerCtrl`헤더 컨트롤에 액세스하는 데 사용되는 변수, 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 `SetFocusedItem` 및 `GetFocusedItem` 메서드를 보여 줍니다. 코드의 이전 섹션에서는 5개의 열이 있는 헤더 컨트롤을 만들었습니다. 그러나 열 구분 기호를 드래그하여 열이 표시되지 않도록 할 수 있습니다. 다음 예제는 마지막 열 헤더를 포커스 항목으로 설정한 다음 확인합니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>C헤더Ctrl:::세트핫디바이더

헤더 항목 간의 구분을 변경하여 헤더 항목의 수동 드래그 앤 드롭을 나타냅니다.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
포인터의 위치입니다. 헤더 컨트롤은 포인터의 위치에 따라 적절한 구분을 강조 표시됩니다.

*nIndex*<br/>
강조 표시된 구분사이의 인덱스입니다.

### <a name="return-value"></a>Return Value

강조 표시된 구분사이의 인덱스입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 HDM_SETHOTDIVIDER Win32 [메시지의](/windows/win32/Controls/hdm-sethotdivider)동작을 구현합니다. 헤더 항목 드래그 앤 드롭을 지원하기 위해 제공됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a>C헤더Ctrl::세트이미지리스트

헤더 컨트롤에 이미지 목록을 할당합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
헤더 컨트롤에 `CImageList` 할당할 이미지 목록을 포함하는 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

헤더 컨트롤에 이전에 할당된 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist)Win32 메시지의 동작을 구현합니다. 반환된 포인터 가리키는 `CImageList` 개체는 임시 개체이며 다음 유휴 시간 처리에서 삭제됩니다.

### <a name="example"></a>예제

  [CHeaderCtrl::GetImageList에](#getimagelist)대한 예제를 참조하십시오.

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a>C헤더Ctrl::세트아이템

헤더 컨트롤에서 지정된 항목의 특성을 설정합니다.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
조작할 항목의 0기반 인덱스입니다.

*p헤더아이템*<br/>
새 항목에 대한 정보가 포함된 [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CHeaderCtrl::GetItem](#getitem)에 대한 예제를 참조하십시오.

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a>C헤더Ctrl::세트순서 배열

헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 설정합니다.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>매개 변수

*iCount*<br/>
헤더 제어 항목의 수입니다.

*piArray*<br/>
헤더 컨트롤에서 항목의 인덱스 값을 왼쪽에서 오른쪽으로 표시하는 순서대로 받는 버퍼의 주소에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 매크로 [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)동작을 구현합니다. 헤더 항목 순서를 지원하기 위해 제공됩니다.

### <a name="example"></a>예제

  [CHeaderCtrl::GetOrderArray에](#getorderarray)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[크탭터클래스](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList 클래스](../../mfc/reference/cimagelist-class.md)
