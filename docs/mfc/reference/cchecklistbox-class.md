---
title: C체크리스트박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: dc0e80e80d61104a4d8cb5f1cfd4e26a64c42249
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752735"
---
# <a name="cchecklistbox-class"></a>C체크리스트박스 클래스

Windows 검사 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C체크리스트박스::C체크리스트박스](#cchecklistbox)|`CCheckListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C체크리스트상자::만들기](#create)|Windows 확인란을 만들고 개체에 `CCheckListBox` 연결합니다.|
|[C체크리스트박스::D원시아이템](#drawitem)|소유자-그리기 목록 상자의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.|
|[C체크리스트박스::사용](#enable)|확인란 확인란 항목을 사용 하거나 비활성화합니다.|
|[C체크리스트박스::GetCheck](#getcheck)|항목의 확인란의 상태를 가져옵니다.|
|[C체크리스트박스::겟체크스타일](#getcheckstyle)|컨트롤의 확인란 의 스타일을 가져옵니다.|
|[C체크리스트박스::사용 안 함](#isenabled)|항목이 활성화되어 있는지 여부를 결정합니다.|
|[C체크리스트상자::측정항목](#measureitem)|소유자-그리기 스타일이 있는 목록 상자를 만들 때 프레임워크에서 호출됩니다.|
|[C체크리스트박스::온겟체크포지션](#ongetcheckposition)|항목의 확인란의 위치를 얻기 위해 프레임 워크에 의해 호출됩니다.|
|[C체크리스트박스::세트체크](#setcheck)|항목의 확인란의 상태를 설정합니다.|
|[C체크리스트박스::세트체크스타일](#setcheckstyle)|컨트롤의 확인란 의 스타일을 설정합니다.|

## <a name="remarks"></a>설명

"확인란"에는 파일 이름과 같은 항목 목록이 표시됩니다. 목록의 각 항목에는 사용자가 확인하거나 지울 수 있는 확인란이 옆에 있습니다.

`CCheckListBox`목록에 텍스트 문자열 이상이 포함되어 있기 때문에 소유자가 그린 컨트롤에만 사용할 수 있습니다. 가장 간단하게 체크리스트 상자에는 텍스트 문자열과 확인란이 포함되어 있지만 텍스트가 전혀 필요하지는 않습니다. 예를 들어 각 항목 옆에 확인란이 있는 작은 비트맵 목록이 있을 수 있습니다.

사용자 고유의 확인목록 확인란을 만들려면 `CCheckListBox`에서 고유한 클래스를 파생해야 합니다. 사용자 고유의 클래스를 파생하려면 파생 클래스에 대한 `Create`생성자 작성을 한 다음 을 호출합니다.

목록 상자에서 부모에게 보낸 Windows 알림 메시지(일반적으로 [CDialog에서](../../mfc/reference/cdialog-class.md)파생된 클래스)를 처리하려면 각 메시지에 대한 부모 클래스에 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가합니다.

각 메시지 맵 항목은 다음과 같은 형식을 취합니다.

**ON\_**_알림_ _(ID,_ _멤버Fxn)_ **)** **(**

여기서 `id` 알림을 보내는 컨트롤의 자식 창 ID를 지정하고 `memberFxn` 알림을 처리하기 위해 작성한 부모 구성원 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

`afx_msg void memberFxn();`

특별히 관련된 메시지 맵 항목은 `CCheckListBox` 하나뿐입니다(CListBox의 메시지 맵 항목도 [CListBox](../../mfc/reference/clistbox-class.md)참조).

- ON_CLBN_CHKCHANGE 사용자가 항목의 확인란의 상태를 변경했습니다.

확인목록 확인란이 기본 확인란인 경우(각각의 왼쪽에 기본 크기의 확인란이 있는 문자열 목록) 기본 [CCheckListBox::DrawItem을](#drawitem) 사용하여 체크리스트 상자를 그릴 수 있습니다. 그렇지 않으면 [CListBox::비교항목](../../mfc/reference/clistbox-class.md#compareitem) 함수와 [CCheckListBox::DrawItem](#drawitem) 및 [CCheckListBox::MeasureItem](#measureitem) 함수를 재정의해야 합니다.

대화 상자 템플릿에서 또는 코드에서 직접 확인란을 만들 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cchecklistboxcchecklistbox"></a><a name="cchecklistbox"></a>C체크리스트박스::C체크리스트박스

`CCheckListBox` 개체를 생성합니다.

```
CCheckListBox();
```

### <a name="remarks"></a>설명

두 단계로 `CCheckListBox` 객체를 생성합니다. 먼저 `CCheckListBox`에서 파생 된 클래스를 `Create`정의 한 다음 Windows 확인 목록 확인란을 `CCheckListBox` 초기화 하 고 개체에 연결 하는 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

## <a name="cchecklistboxcreate"></a><a name="create"></a>C체크리스트상자::만들기

Windows 확인란을 만들고 개체에 `CCheckListBox` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
확인란 확인란의 스타일을 지정합니다. 스타일은 LBS_HASSTRINGS LBS_OWNERDRAWFIXED(목록의 모든 항목은 높이가 같거나) 또는 LBS_OWNERDRAWVARIABLE(목록의 항목은 높이가 다를 수 있음)이어야 합니다. 이 스타일은 LBS_USETABSTOPS 제외한 다른 [목록 상자 스타일과](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 결합할 수 있습니다.

*rect*<br/>
확인란 크기 및 위치를 지정합니다. [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조일 수 있습니다.

*pParentWnd*<br/>
확인란의 상위 창(일반적으로 개체)을 `CDialog` 지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
확인란의 컨트롤 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CCheckListBox` 객체를 생성합니다. 먼저 Windows 확인 목록 `CcheckListBox` 확인란을 `Create`초기화하고 `CCheckListBox`에 연결하는 호출에서 파생된 클래스를 정의합니다. 샘플은 [C체크리스트박스::C체크리스트상자를](#cchecklistbox) 참조하십시오.

실행되면 `Create` Windows는 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), WM_CREATE [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 메시지를 확인란 컨트롤로 보냅니다. [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)

이러한 메시지는 기본적으로 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 `CWnd` 함수에 의해 기본 클래스에서 처리됩니다. 기본 메시지 처리를 확장하려면 파생 클래스에 메시지 맵을 추가하고 앞의 메시지 처리기 멤버 함수를 재정의합니다. 예를 `OnCreate`들어 새 클래스에 필요한 초기화를 수행하려면 을 재정의합니다.

다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 확인란 확인란 컨트롤에 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_VSCROLL 세로 스크롤 막대를 추가하려면

- WS_HSCROLL 가로 스크롤 막대를 추가하려면

- WS_GROUP 컨트롤그룹

- WS_TABSTOP 이 컨트롤에 대한 탭 을 허용하려면

## <a name="cchecklistboxdrawitem"></a><a name="drawitem"></a>C체크리스트박스::D원시아이템

소유자가 그린 확인란 확인란의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

`itemAction` `itemState` 및 구조의 멤버는 수행할 드로잉 작업을 `DRAWITEMSTRUCT` 정의합니다.

기본적으로 이 함수는 기본 크기의 확인란이 있는 문자열 목록으로 구성된 기본 확인란 목록을 왼쪽에 그립니다. 확인란 목록 크기는 [만들기에](#create)지정된 크기입니다.

이 멤버 함수를 재정의하여 기본값이 아닌 소유자-그리기 확인목록 확인란(예: 문자열이 아닌 목록, 가변 높이 항목 또는 왼쪽에 없는 확인란)의 그리기를 구현합니다. 응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

확인목록 확인란 항목이 모두 같은 높이가 아닌 경우 `Create`확인목록 확인스타일(에 지정된)이 **LBS_OWNERVARIABLE**및 [MeasureItem](#measureitem) 함수를 재정의해야 합니다.

## <a name="cchecklistboxenable"></a><a name="enable"></a>C체크리스트박스::사용

이 함수를 호출하여 확인란 확인란 항목을 사용하거나 사용하지 않도록 설정합니다.

```cpp
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
사용할 확인목록 확인란 항목의 인덱스입니다.

*bEnabled*<br/>
항목을 사용 설정하거나 사용하지 않도록 설정할 지 여부를 지정합니다.

## <a name="cchecklistboxgetcheck"></a><a name="getcheck"></a>C체크리스트박스::GetCheck

지정된 확인란의 상태를 검색합니다.

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 확인란에 포함된 확인란의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 확인란의 상태입니다. 다음 표에는 가능한 값이 나열되어 있습니다.

|값|Description|
|-----------|-----------------|
|BST_CHECKED|확인란이 선택되었습니다.|
|BST_UNCHECKED|확인란이 선택되어 있지 않습니다.|
|BST_INDETERMINATE|확인란 상태가 확정되지 않습니다.|

## <a name="cchecklistboxgetcheckstyle"></a><a name="getcheckstyle"></a>C체크리스트박스::겟체크스타일

이 함수를 호출하여 확인란의 스타일을 가져옵니다.

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>Return Value

컨트롤의 확인란 스타일입니다.

### <a name="remarks"></a>설명

가능한 스타일에 대한 자세한 내용은 [SetCheckStyle](#setcheckstyle)을 참조하십시오.

## <a name="cchecklistboxisenabled"></a><a name="isenabled"></a>C체크리스트박스::사용 안 함

이 함수를 호출하여 항목이 활성화되어 있는지 확인합니다.

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스입니다.

### <a name="return-value"></a>Return Value

항목이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

## <a name="cchecklistboxmeasureitem"></a><a name="measureitem"></a>C체크리스트상자::측정항목

기본값이 아닌 스타일이 있는 확인목록 상자가 만들어지면 프레임워크에서 호출됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 `MEASUREITEMSTRUCT` 재정의하고 구조를 입력하여 Windows에 확인란 항목의 크기를 알립니다. [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 확인란을 만든 경우 프레임워크는 목록 상자의 각 항목에 대해 이 멤버 함수를 호출합니다. 그렇지 않으면 이 멤버는 한 번만 호출됩니다.

## <a name="cchecklistboxongetcheckposition"></a><a name="ongetcheckposition"></a>C체크리스트박스::온겟체크포지션

프레임워크는 이 함수를 호출하여 항목에서 확인란의 위치와 크기를 가져옵니다.

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>매개 변수

*정류 항목*<br/>
목록 항목의 위치와 크기입니다.

*정류확인란*<br/>
항목의 기본 위치 및 크기 확인란입니다.

### <a name="return-value"></a>Return Value

항목의 위치 및 크기 확인란입니다.

### <a name="remarks"></a>설명

기본 구현은 확인란()의`rectCheckBox`기본 위치와 크기만 반환합니다. 기본적으로 확인란은 항목의 왼쪽 위 모서리에 정렬되며 표준 확인란 크기입니다. 오른쪽에 있는 확인란을 원하거나 더 크거나 작은 확인란을 원하는 경우가 있을 수 있습니다. 이러한 경우 재정의를 `OnGetCheckPosition` 사용하여 항목 내의 확인란 위치와 크기를 변경합니다.

## <a name="cchecklistboxsetcheck"></a><a name="setcheck"></a>C체크리스트박스::세트체크

지정된 확인란의 상태를 설정합니다.

```cpp
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 확인란에 포함된 확인란의 0기준 인덱스입니다.

*nCheck*<br/>
지정된 확인란의 단추 상태입니다. 가능한 값은 비고 섹션을 참조하십시오.

### <a name="remarks"></a>설명

다음 표에는 *nCheck* 매개 변수에 대한 가능한 값이 나열됩니다.

|값|Description|
|-----------|-----------------|
|BST_CHECKED|지정된 확인란을 선택합니다.|
|BST_UNCHECKED|지정된 확인란을 선택 취소합니다.|
|BST_INDETERMINATE|지정된 확인란 상태를 확정되지 않은 상태로 설정합니다.<br /><br /> 이 상태는 확인란 스타일이 BS_AUTO3STATE 또는 BS_3STATE 경우에만 사용할 수 있습니다. 자세한 내용은 [단추 스타일을](../../mfc/reference/styles-used-by-mfc.md#button-styles)참조하십시오.|

## <a name="cchecklistboxsetcheckstyle"></a><a name="setcheckstyle"></a>C체크리스트박스::세트체크스타일

이 함수를 호출하여 확인란의 확인란 스타일을 설정합니다.

```cpp
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
확인란 확인란에서 확인란의 스타일을 결정합니다.

### <a name="remarks"></a>설명

유효한 스타일은 다음과 같습니다.

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

이러한 스타일에 대한 자세한 내용은 [단추 스타일을](../../mfc/reference/styles-used-by-mfc.md#button-styles)참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 TSTCON](../../overview/visual-cpp-samples.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)
