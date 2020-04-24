---
title: 크탭터클래스
ms.date: 11/04/2016
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
ms.openlocfilehash: 42d4b24222b1760bc418e904881edb2bb0e5a1f4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752315"
---
# <a name="ctabctrl-class"></a>크탭터클래스

Windows의 공용 탭 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CTabCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CTabCtrl:::CTabCtrl](#ctabctrl)|`CTabCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CTabCtrl::adjustRect](#adjustrect)|창 사각형이 지정된 탭 컨트롤의 표시 영역을 계산하거나 지정된 표시 영역에 해당하는 창 사각형을 계산합니다.|
|[CTabCtrl::만들기](#create)|탭 컨트롤을 만들고 `CTabCtrl` 개체의 인스턴스에 연결합니다.|
|[CTabCtrl::만들기](#createex)|지정된 Windows 확장 스타일을 사용하여 탭 컨트롤을 만들고 `CTabCtrl` 개체의 인스턴스에 연결합니다.|
|[CTabCtrl::D모든 항목](#deleteallitems)|탭 컨트롤에서 모든 항목을 제거합니다.|
|[CTabCtrl::Deleteitem](#deleteitem)|탭 컨트롤에서 항목을 제거합니다.|
|[CTabCtrl::D모두 선택](#deselectall)|탭 컨트롤에서 항목을 재설정하여 누른 항목을 지운 다.|
|[CTabCtrl::D원시아이템](#drawitem)|탭 컨트롤의 지정된 항목을 그립니다.|
|[CTabCtrl::GetCurFocus](#getcurfocus)|탭 컨트롤의 현재 포커스가 있는 탭을 검색합니다.|
|[CTabCtrl::GetCursel](#getcursel)|탭 컨트롤에서 현재 선택한 탭을 결정합니다.|
|[CTabCtrl::GetExtended스타일](#getextendedstyle)|탭 컨트롤에 현재 사용 중인 확장 스타일을 검색합니다.|
|[CTabCtrl::GetImageList](#getimagelist)|탭 컨트롤과 연결된 이미지 목록을 검색합니다.|
|[CTabCtrl::GetItem](#getitem)|탭 컨트롤에서 탭에 대한 정보를 검색합니다.|
|[CTabCtrl:::겟아이템카운트](#getitemcount)|탭 컨트롤에서 탭 수를 검색합니다.|
|[CTabCtrl::GetItemRect](#getitemrect)|탭 컨트롤에서 탭에 대한 경계 사각형을 검색합니다.|
|[CTabCtrl::겟아이템스테이트](#getitemstate)|표시된 탭 컨트롤 항목의 상태를 검색합니다.|
|[크탭트롤::겟로우카운트](#getrowcount)|탭 컨트롤에서 현재 탭 행 수를 검색합니다.|
|[CTabCtrl::getToolTips](#gettooltips)|탭 컨트롤과 연결된 도구 팁 컨트롤의 핸들을 검색합니다.|
|[CTabCtrl::하이라이트항목](#highlightitem)|탭 항목의 강조 표시 상태를 설정합니다.|
|[CTabCtrl::히트 테스트](#hittest)|지정된 화면 위치에 있는 탭(있는 경우)을 결정합니다.|
|[CTabCtrl::삽입항목](#insertitem)|탭 컨트롤에 새 탭을 삽입합니다.|
|[CTabCtrl::이미지 제거](#removeimage)|탭 컨트롤의 이미지 목록에서 이미지를 제거합니다.|
|[CTabCtrl::세트큐포커스](#setcurfocus)|탭 컨트롤에서 지정된 탭으로 포커스를 설정합니다.|
|[CTabCtrl::세트커셀](#setcursel)|탭 컨트롤에서 탭을 선택합니다.|
|[CTabCtrl::세트확장스타일](#setextendedstyle)|탭 컨트롤에 대한 확장 스타일을 설정합니다.|
|[CTabCtrl::세트 이미지 목록](#setimagelist)|탭 컨트롤에 이미지 목록을 할당합니다.|
|[CTabCtrl::세트 항목](#setitem)|탭 속성의 일부 또는 전부를 설정합니다.|
|[CTabCtrl::세트항목추가](#setitemextra)|탭 컨트롤에서 응용 프로그램 정의 데이터에 대해 예약된 탭당 바이트 수를 설정합니다.|
|[CTabCtrl::세트항목 크기](#setitemsize)|항목의 너비와 높이를 설정합니다.|
|[CTabCtrl::세트항목 상태](#setitemstate)|표시된 탭 컨트롤 항목의 상태를 설정합니다.|
|[CTabCtrl::설정민탭폭](#setmintabwidth)|탭 컨트롤에서 항목의 최소 너비를 설정합니다.|
|[CTabCtrl::세트 패딩](#setpadding)|각 탭의 아이콘 주위에 공간(패딩)의 양을 설정하고 탭 컨트롤에서 레이블을 지정합니다.|
|[CTabCtrl::설정 도구 팁](#settooltips)|탭 컨트롤에 도구 설명 컨트롤을 할당합니다.|

## <a name="remarks"></a>설명

"탭 컨트롤"은 전자 필기장의 칸막이 또는 파일 캐비닛의 레이블과 유사합니다. 애플리케이션은 탭 컨트롤을 사용하여 창 또는 대화 상자의 동일한 영역에 대해 여러 페이지를 정의할 수 있습니다. 각 페이지는 사용자가 해당 탭을 선택할 때 응용 프로그램이 표시하는 정보 집합 또는 컨트롤 그룹으로 구성됩니다. 특별한 유형의 탭 컨트롤은 단추처럼 보이는 탭을 표시합니다. 단추를 클릭하면 페이지를 표시하는 대신 즉시 명령을 수행해야 합니다.

이 컨트롤(및 `CTabCtrl` 따라서 클래스)은 Windows 95/98 및 Windows NT 버전 3.51 이상에서 실행되는 프로그램에서만 사용할 수 있습니다.

사용에 `CTabCtrl`대한 자세한 내용은 [컨트롤](../../mfc/controls-mfc.md) 및 [CTabCtrl 사용](../../mfc/using-ctabctrl.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CTabCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl::adjustRect

창 사각형이 지정된 탭 컨트롤의 표시 영역을 계산하거나 지정된 표시 영역에 해당하는 창 사각형을 계산합니다.

```cpp
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*bLarger*<br/>
수행할 작업을 나타냅니다. 이 매개변수가 TRUE이면 *lpRect는* 표시 사각형을 지정하고 해당 창 사각형을 수신합니다. 이 매개변수가 FALSE인 경우 *lpRect는* 창 사각형을 지정하고 해당 표시 사각형을 수신합니다.

*Lprect*<br/>
지정된 사각형을 지정하고 계산된 사각형을 받는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]

## <a name="ctabctrlcreate"></a><a name="create"></a>CTabCtrl::만들기

탭 컨트롤을 만들고 `CTabCtrl` 개체의 인스턴스에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
탭 컨트롤의 스타일을 지정합니다. Windows SDK에 설명된 [탭 컨트롤 스타일의](/windows/win32/Controls/tab-control-styles)조합을 적용합니다. 컨트롤에 적용할 수 있는 창 스타일 목록은 **비고를** 참조하십시오.

*rect*<br/>
탭 컨트롤의 크기와 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
탭 컨트롤의 부모 창(일반적으로 )을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
탭 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 개체의 초기화가 성공한 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

두 단계로 `CTabCtrl` 객체를 생성합니다. 먼저 생성자 호출 한 다음 `Create`탭 컨트롤을 만들고 `CTabCtrl` 개체에 연결 하는 호출 합니다.

탭 컨트롤 스타일 외에도 다음 창 스타일을 탭 컨트롤에 적용할 수 있습니다.

- WS_CHILD 탭 컨트롤을 나타내는 자식 창을 만듭니다. WS_POPUP 스타일과 함께 사용할 수 없습니다.

- WS_VISIBLE 처음에 표시되는 탭 컨트롤을 만듭니다.

- WS_DISABLED 처음에 사용하지 않도록 설정한 창을 만듭니다.

- WS_GROUP 사용자가 화살표 키를 사용하여 한 컨트롤에서 다음 컨트롤로 이동할 수 있는 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다. 첫 번째 컨트롤 이후에 WS_GROUP 스타일로 정의된 모든 컨트롤은 동일한 그룹에 속합니다. WS_GROUP 스타일로 다음 컨트롤은 스타일 그룹을 종료하고 다음 그룹을 시작합니다(즉, 한 그룹은 다음 그룹이 시작되는 지점).

- WS_TABSTOP 사용자가 TAB 키를 사용하여 이동할 수 있는 여러 컨트롤 중 하나를 지정합니다. TAB 키는 사용자를 WS_TABSTOP 스타일로 지정된 다음 컨트롤로 이동합니다.

확장 된 창 스타일을 사용하여 탭 컨트롤을 만들려면 [대신 CTabCtrl::CreateEx를](#createex) `Create`호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]

## <a name="ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::만들기

컨트롤(하위 창)을 만들고 `CTabCtrl` 개체와 연결합니다.

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
탭 컨트롤의 스타일을 지정합니다. Windows SDK에 설명된 [탭 컨트롤 스타일의](/windows/win32/Controls/tab-control-styles)조합을 적용합니다. 컨트롤에 [Create](#create) 적용할 수 있는 창 스타일 목록은 **만들기에서 발언을** 참조하십시오.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 생성할 창의 크기와 위치를 설명하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모인 창에 대한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 성공하면 0이 아닙니다.

### <a name="remarks"></a>설명

만들기 `CreateEx` 대신 [Create](#create) Windows 확장 스타일 **서문 WS_EX_** 지정된 확장 된 Windows 스타일을 적용합니다.

`CreateEx`*dwExStyle에*의해 지정된 확장 된 Windows 스타일로 컨트롤을 만듭니다. [SetExtendedStyle을](#setextendedstyle)사용하여 컨트롤에 특정확장 스타일을 설정합니다. 예를 들어 `CreateEx` WS_EX_CONTEXTHELP 같은 스타일을 설정하지만 `SetExtendedStyle` TCS_EX_FLATSEPARATORS 같은 스타일을 설정하는 데 사용합니다. 자세한 내용은 Windows SDK의 [탭 제어 확장 스타일에](/windows/win32/Controls/tab-control-extended-styles) 설명된 스타일을 참조하십시오.

## <a name="ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl:::CTabCtrl

`CTabCtrl` 개체를 생성합니다.

```
CTabCtrl();
```

## <a name="ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::D모든 항목

탭 컨트롤에서 모든 항목을 제거합니다.

```
BOOL DeleteAllItems();
```

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::Deleteitem

탭 컨트롤에서 지정된 항목을 제거합니다.

```
BOOL DeleteItem(int nItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
삭제할 항목의 0기준 값입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]

## <a name="ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::D모두 선택

탭 컨트롤에서 항목을 재설정하여 누른 항목을 지운 다.

```cpp
void DeselectAll(BOOL fExcludeFocus);
```

### <a name="parameters"></a>매개 변수

*f제외포커스*<br/>
항목 선택 해제 범위를 지정하는 플래그입니다. 이 매개 변수가 FALSE로 설정되면 모든 탭 버튼이 재설정됩니다. TRUE로 설정된 경우 현재 선택한 탭항목을 제외한 모든 탭 항목이 재설정됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 [TCM_DESELECTALL](/windows/win32/Controls/tcm-deselectall)설명된 대로 TCM_DESELECTALL Win32 메시지의 동작을 구현합니다.

## <a name="ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::D원시아이템

소유자-그리기 탭 컨트롤의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
페인팅할 항목을 설명하는 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다.

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CTabCtrl`

응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에서* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

## <a name="ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl::GetCurFocus

현재 포커스가 있는 탭의 인덱스를 검색합니다.

```
int GetCurFocus() const;
```

### <a name="return-value"></a>Return Value

현재 포커스가 있는 탭의 0기반 인덱스입니다.

## <a name="ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl::GetCursel

탭 컨트롤에서 현재 선택한 탭을 검색합니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

탭이 선택되지 않은 경우 선택한 탭의 0기반 인덱스 또는 -1.

## <a name="ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtended스타일

탭 컨트롤에 현재 사용 중인 확장 스타일을 검색합니다.

```
DWORD GetExtendedStyle();
```

### <a name="return-value"></a>Return Value

탭 컨트롤에 현재 사용 중인 확장 스타일을 나타냅니다. 이 값은 Windows SDK에 설명된 [대로 탭 컨트롤 확장 스타일](/windows/win32/Controls/tab-control-extended-styles)조합입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TCM_GETEXTENDEDSTYLE Win32 [메시지의](/windows/win32/Controls/tcm-getextendedstyle)동작을 구현합니다.

## <a name="ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl::GetImageList

탭 컨트롤에 연관된 이미지 목록을 검색합니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Return Value

성공할 경우 탭 컨트롤의 이미지 목록에 대한 포인터이고 그렇지 않으면 NULL입니다.

## <a name="ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl::GetItem

탭 컨트롤에서 탭에 대한 정보를 검색합니다.

```
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
탭의 0기반 인덱스입니다.

*pTabCtrl항목*<br/>
검색할 정보를 지정하는 데 사용되는 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조에 대한 포인터입니다. 또한 탭에 대한 정보를 수신하는 데 사용됩니다. 이 구조는 `InsertItem`에서 `GetItem`및 `SetItem` 멤버 함수와 함께 사용됩니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

메시지가 전송되면 멤버는 `mask` 반환할 특성을 지정합니다. 멤버가 `mask` TCIF_TEXT 값을 지정하는 경우 `pszText` 멤버는 항목 텍스트를 수신하는 버퍼의 주소를 `cchTextMax` 포함해야 하며 멤버는 버퍼 크기를 지정해야 합니다.

- `mask`

   검색하거나 설정할 `TCITEM` 구조멤버를 지정하는 값입니다. 이 멤버는 0이거나 다음 값의 조합일 수 있습니다.

  - TCIF_TEXT `pszText` 멤버가 유효합니다.

  - TCIF_IMAGE `iImage` 멤버가 유효합니다.

  - TCIF_PARAM `lParam` 멤버가 유효합니다.

  - TCIF_RTLREADING `pszText` 텍스트는 히브리어 또는 아랍어 시스템에서 오른쪽에서 왼쪽 읽기 순서를 사용하여 표시됩니다.

  - TCIF_STATE `dwState` 멤버가 유효합니다.

- `pszText`

   구조에 탭에 대한 정보가 포함된 경우 탭 텍스트를 포함하는 null 종료 된 문자열에 대한 포인터입니다. 구조체가 정보를 수신하는 경우 이 멤버는 탭 텍스트를 수신하는 버퍼의 주소를 지정합니다.

- `cchTextMax`

   을 가리키는 버퍼의 `pszText`크기입니다. 구조가 정보를 받지 못하는 경우 이 멤버는 무시됩니다.

- `iImage`탭 컨트롤의 이미지 목록에 인덱싱하거나 탭에 대한 이미지가 없는 경우 -1입니다.

- `lParam`

   탭과 연결된 응용 프로그램 정의 데이터입니다. 탭당 응용 프로그램 정의 데이터가 4바이트 이상인 경우 응용 프로그램은 구조를 정의하고 `TCITEM` 구조 대신 사용해야 합니다. 응용 프로그램 정의 구조의 첫 번째 멤버는 [TCITEMHEADER](/windows/win32/api/commctrl/ns-commctrl-tcitemheaderw)구조여야 합니다. 구조는 `TCITEMHEADER` 구조와 `TCITEM` 동일하지만 멤버가 `lParam` 없습니다. 구조의 크기와 `TCITEMHEADER` 구조의 크기 간의 차이는 탭당 추가 바이트 수와 같아야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]

## <a name="ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl:::겟아이템카운트

탭 컨트롤에서 탭 수를 검색합니다.

```
int GetItemCount() const;
```

### <a name="return-value"></a>Return Value

탭 컨트롤의 항목 수입니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl::GetItemRect

탭 컨트롤에서 지정된 탭에 대한 경계 사각형을 검색합니다.

```
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
탭 항목의 0기반 인덱스입니다.

*Lprect*<br/>
탭의 경계 사각형을 받는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 포인터입니다. 이러한 좌표는 뷰포트의 현재 매핑 모드를 사용합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl::겟아이템스테이트

*nItem*로 식별된 탭 컨트롤 항목의 상태를 검색합니다.

```
DWORD GetItemState(
    int nItem,
    DWORD dwMask) const;
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
상태 정보를 검색할 항목의 0기반 인덱스 번호입니다.

*dwMask*<br/>
반환할 항목의 상태 플래그를 지정하는 마스크입니다. 값 목록은 Windows SDK에 설명된 대로 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조의 마스크 멤버를 참조하십시오.

### <a name="return-value"></a>Return Value

상태 정보를 수신하는 DWORD 값에 대한 참조입니다. 다음 값 중 하나를 사용할 수 있습니다.

|값|Description|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|탭 컨트롤 항목이 선택됩니다.|
|TCIS_HIGHLIGHTED|탭 컨트롤 항목이 강조 표시되고 현재 강조 표시 색상을 사용하여 탭과 텍스트가 그려집니다. 강조 표시 색상을 사용하는 경우 디더된 색상이 아닌 실제 보간이 됩니다.|

### <a name="remarks"></a>설명

항목의 상태는 구조의 멤버에 `dwState` 의해 지정됩니다. `TCITEM`

## <a name="ctabctrlgetrowcount"></a><a name="getrowcount"></a>크탭트롤::겟로우카운트

탭 컨트롤에서 현재 행 수를 검색합니다.

```
int GetRowCount() const;
```

### <a name="return-value"></a>Return Value

탭 컨트롤의 탭 행 수입니다.

### <a name="remarks"></a>설명

TCS_MULTILINE 스타일이 있는 탭 컨트롤만 여러 행의 탭을 가질 수 있습니다.

## <a name="ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::getToolTips

탭 컨트롤과 연결된 도구 팁 컨트롤의 핸들을 검색합니다.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Return Value

성공하면 공구 팁 컨트롤의 핸들; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

탭 컨트롤은 TCS_TOOLTIPS 스타일이 있는 경우 도구 설명 컨트롤을 만듭니다. 멤버 함수를 사용하여 탭 컨트롤에 도구 설명 `SetToolTips` 컨트롤을 할당할 수도 있습니다.

## <a name="ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::하이라이트항목

탭 항목의 강조 표시 상태를 설정합니다.

```
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```

### <a name="parameters"></a>매개 변수

*id항목*<br/>
탭 컨트롤 항목의 0기반 인덱스입니다.

*fHighlight*<br/>
설정할 강조 표시 상태를 지정하는 값입니다. 이 값이 TRUE이면 탭이 강조 표시됩니다. FALSE이면 탭이 기본 상태로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TCM_HIGHLIGHTITEM Win32 [메시지를](/windows/win32/Controls/tcm-highlightitem)구현합니다.

## <a name="ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::히트 테스트

지정된 화면 위치에 있는 탭(있는 경우)을 결정합니다.

```
int HitTest(TCHITTESTINFO* pHitTestInfo) const;
```

### <a name="parameters"></a>매개 변수

*pHitTestInfo*<br/>
테스트할 화면 위치를 지정하는 Windows SDK에 설명된 대로 [TCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tchittestinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

지정된 위치에 탭이 없는 경우 탭의 0기반 인덱스 또는 1을 반환합니다.

## <a name="ctabctrlinsertitem"></a><a name="insertitem"></a>CTabCtrl::삽입항목

기존 탭 컨트롤에 새 탭을 삽입합니다.

```
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam,
    DWORD dwState,
    DWORD dwStateMask);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
새 탭의 0기반 인덱스입니다.

*pTabCtrl항목*<br/>
탭의 속성을 지정하는 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조에 대한 포인터입니다.

*lpszItem*<br/>
탭의 텍스트를 포함 하는 null 종료 된 문자열의 주소입니다.

*nImage*<br/>
이미지 목록에서 삽입할 이미지의 0기반 인덱스입니다.

*nMask*<br/>
설정할 `TCITEM` 구조 특성을 지정합니다. 0 또는 다음 값의 조합일 수 있습니다.

- TCIF_TEXT `pszText` 멤버가 유효합니다.

- TCIF_IMAGE `iImage` 멤버가 유효합니다.

- TCIF_PARAM *lParam* 멤버가 유효합니다.

- TCIF_RTLREADING `pszText` 텍스트는 히브리어 또는 아랍어 시스템에서 오른쪽에서 왼쪽 읽기 순서를 사용하여 표시됩니다.

- TCIF_STATE *dwState* 멤버가 유효합니다.

*lParam*<br/>
탭과 연결된 응용 프로그램 정의 데이터입니다.

*dwState*<br/>
항목의 상태에 대한 값을 지정합니다. 자세한 내용은 Windows SDK의 [TCITEM를](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 참조하십시오.

*dw스테이트 마스크*<br/>
설정할 상태를 지정합니다. 자세한 내용은 Windows SDK의 [TCITEM를](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 참조하십시오.

### <a name="return-value"></a>Return Value

성공하면 새 탭의 제로 기반 인덱스; 그렇지 않은 경우 - 1.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]

## <a name="ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::이미지 제거

탭 컨트롤의 이미지 목록에서 지정된 이미지를 제거합니다.

```cpp
void RemoveImage(int nImage);
```

### <a name="parameters"></a>매개 변수

*nImage*<br/>
제거할 이미지의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

탭 컨트롤은 각 탭의 이미지 인덱스를 업데이트하여 각 탭이 동일한 이미지와 연결된 상태로 유지됩니다.

## <a name="ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::세트큐포커스

탭 컨트롤에서 지정된 탭으로 포커스를 설정합니다.

```cpp
void SetCurFocus(int nItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
포커스를 얻는 탭의 인덱스를 지정합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TCM_SETCURFOCUS Win32 [메시지의](/windows/win32/Controls/tcm-setcurfocus)동작을 구현합니다.

## <a name="ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::세트커셀

탭 컨트롤에서 탭을 선택합니다.

```
int SetCurSel(int nItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
선택할 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

그렇지 않으면 성공한 경우 이전에 선택한 탭의 0기반 인덱스 - 1.

### <a name="remarks"></a>설명

이 기능을 사용하여 탭을 선택하면 탭 컨트롤이 TCN_SELCHANGING 또는 TCN_SELCHANGE 알림 메시지를 보내지 않습니다. 이러한 알림은 사용자가 키보드를 클릭하거나 탭을 변경할 때 WM_NOTIFY 사용하여 전송됩니다.

## <a name="ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::세트확장스타일

탭 컨트롤에 대한 확장 스타일을 설정합니다.

```
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```

### <a name="parameters"></a>매개 변수

*dwNewStyle*<br/>
탭 컨트롤 확장 스타일 조합을 지정하는 값입니다.

*dwExMask*<br/>
*dwNewStyle에서* 영향을 받을 스타일을 나타내는 DWORD 값입니다. *dwExMask의* 확장 된 스타일만 변경됩니다. 다른 모든 스타일은 있는 것처럼 유지됩니다. 이 매개변수가 0이면 *dwNewStyle의* 모든 스타일이 영향을 받습니다.

### <a name="return-value"></a>Return Value

Windows SDK에 설명된 대로 이전 [탭 컨트롤 확장 스타일을](/windows/win32/Controls/tab-control-extended-styles)포함하는 DWORD 값입니다.

### <a name="return-value"></a>Return Value

이 멤버 함수는 Windows SDK에 설명된 대로 [TCM_SETEXTENDEDSTYLE](/windows/win32/Controls/tcm-setextendedstyle)Win32 메시지의 동작을 구현합니다.

## <a name="ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl::세트 이미지 목록

탭 컨트롤에 이미지 목록을 할당합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
탭 컨트롤에 할당할 이미지 목록에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

이전 이미지 목록이 없는 경우 이전 이미지 목록 또는 NULL에 대한 포인터를 반환합니다.

## <a name="ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl::세트 항목

탭 속성의 일부 또는 전부를 설정합니다.

```
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
항목의 0 기반 인덱스입니다.

*pTabCtrl항목*<br/>
새 항목 특성을 포함하는 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조에 대한 포인터입니다. 멤버는 `mask` 설정할 특성을 지정합니다. 멤버가 `mask` TCIF_TEXT 값을 지정하면 멤버는 `pszText` null 종료된 문자열의 주소이며 `cchTextMax` 멤버는 무시됩니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [GetItem](#getitem)에 대한 예제를 참조하십시오.

## <a name="ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::세트항목추가

탭 컨트롤에서 응용 프로그램 정의 데이터에 대해 예약된 탭당 바이트 수를 설정합니다.

```
BOOL SetItemExtra(int nBytes);
```

### <a name="parameters"></a>매개 변수

*n바이트*<br/>
설정할 추가 바이트 수입니다.

### <a name="return-value"></a>Return Value

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 TCM_SETITEMEXTRA Win32 [메시지의](/windows/win32/Controls/tcm-setitemextra)동작을 구현합니다.

## <a name="ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl::세트항목 크기

탭 컨트롤 항목의 높이 및 너비를 설정합니다.

```
CSize SetItemSize(CSize size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
탭 제어 항목의 새로운 너비 및 높이입니다(픽셀).

### <a name="return-value"></a>Return Value

탭 제어 항목의 이전 높이 및 너비를 반환합니다.

## <a name="ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl::세트항목 상태

*nItem로*식별된 탭 컨트롤 항목의 상태를 설정합니다.

```
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
상태 정보를 설정할 항목의 0기반 인덱스 번호입니다.

*dwMask*<br/>
설정할 항목의 상태 플래그를 지정하는 마스크입니다. 값 목록은 Windows SDK에 설명된 대로 [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조의 마스크 멤버를 참조하십시오.

*dwState*<br/>
상태 정보를 포함하는 DWORD 값에 대한 참조입니다. 다음 값 중 하나를 사용할 수 있습니다.

|값|Description|
|-----------|-----------------|
|TCIS_BUTTONPRESSED|탭 컨트롤 항목이 선택됩니다.|
|TCIS_HIGHLIGHTED|탭 컨트롤 항목이 강조 표시되고 현재 강조 표시 색상을 사용하여 탭과 텍스트가 그려집니다. 강조 표시 색상을 사용하는 경우 디더된 색상이 아닌 실제 보간이 됩니다.|

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

## <a name="ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl::설정민탭폭

탭 컨트롤에서 항목의 최소 너비를 설정합니다.

```
int SetMinTabWidth(int cx);
```

### <a name="parameters"></a>매개 변수

*Cx*<br/>
탭 컨트롤 항목에 대해 설정할 최소 너비입니다. 이 매개 변수가 -1로 설정된 경우 컨트롤은 기본 탭 너비를 사용합니다.

### <a name="return-value"></a>Return Value

이전 최소 탭 너비입니다.

### <a name="return-value"></a>Return Value

이 멤버 함수는 Windows SDK에 설명된 대로 TCM_SETMINTABWIDTH Win32 [메시지의](/windows/win32/Controls/tcm-setmintabwidth)동작을 구현합니다.

## <a name="ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl::세트 패딩

각 탭의 아이콘 주위에 공간(패딩)의 양을 설정하고 탭 컨트롤에서 레이블을 지정합니다.

```cpp
void SetPadding(CSize size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
각 탭의 아이콘 주위에 공간(패딩)의 양을 설정하고 탭 컨트롤에서 레이블을 지정합니다.

## <a name="ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::설정 도구 팁

탭 컨트롤에 도구 설명 컨트롤을 할당합니다.

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>매개 변수

*pWndTip*<br/>
공구 팁 컨트롤의 핸들입니다.

### <a name="remarks"></a>설명

을 호출하여 탭 컨트롤과 연결된 도구 설명 컨트롤을 `GetToolTips`얻을 수 있습니다.

### <a name="example"></a>예제

  [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C헤더Ctrl 클래스](../../mfc/reference/cheaderctrl-class.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)
