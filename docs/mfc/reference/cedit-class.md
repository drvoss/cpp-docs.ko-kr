---
title: CEdit Class
ms.date: 09/12/2018
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
ms.openlocfilehash: 94769a6fb3c5fceefda96b54cebb35b0533a8afa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753227"
---
# <a name="cedit-class"></a>CEdit Class

Windows 편집 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CEdit : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|컨트롤 개체를 `CEdit` 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CEdit:::CanUndo](#canundo)|편집 제어 작업을 취소할 수 있는지 여부를 결정합니다.|
|[CEdit::CharFrompos](#charfrompos)|지정된 위치에 가장 가까운 문자에 대한 선 및 문자 인덱스를 검색합니다.|
|[CEdit::지우기](#clear)|편집 컨트롤에서 현재 선택 영역(있는 경우)을 삭제(지우기)합니다.|
|[CEdit::복사](#copy)|편집 컨트롤의 현재 선택 영역(있는 경우)을 CF_TEXT 형식으로 클립보드에 복사합니다.|
|[CEdit::만들기](#create)|Windows 편집 컨트롤을 만들고 개체에 `CEdit` 연결합니다.|
|[CEdit::컷](#cut)|편집 컨트롤의 현재 선택 영역(있는 경우)을 삭제(잘라내며)를 삭제하고 삭제된 텍스트를 CF_TEXT 형식으로 클립보드에 복사합니다.|
|[CEdit::빈Undo버퍼](#emptyundobuffer)|편집 컨트롤의 취소 플래그를 재설정(지우기)합니다.|
|[CEdit::FmtLines](#fmtlines)|다중 줄 편집 컨트롤 내에서 소프트 줄 바그 문자의 포함을 설정합니다.|
|[CEdit::GetCue배너](#getcuebanner)|컨트롤이 비어 있고 포커스가 없는 경우 편집 컨트롤에서 텍스트 큐 또는 팁으로 표시되는 텍스트를 검색합니다.|
|[CEdit::GetFirstVisible선](#getfirstvisibleline)|편집 컨트롤에서 가장 맨 위에 표시되는 선을 결정합니다.|
|[CEdit::GetHandle](#gethandle)|다중 줄 편집 컨트롤에 현재 할당된 메모리에 대한 핸들을 검색합니다.|
|[CEdit::Get하이라이트](#gethighlight)|현재 편집 컨트롤에서 강조 표시된 텍스트 범위에서 시작 및 종료 문자의 인덱스를 가져옵니다.|
|[CEdit::GetLimitText](#getlimittext)|포함할 `CEdit` 수 있는 최대 텍스트 양을 가져옵니다.|
|[CEdit::GetLine](#getline)|편집 컨트롤에서 텍스트 줄을 검색합니다.|
|[CEdit::GetLineCount](#getlinecount)|여러 줄 편집 컨트롤에서 줄 수를 검색합니다.|
|[CEdit::getmargins](#getmargins)|이에 `CEdit`대한 왼쪽 및 오른쪽 여백을 가져옵니다.|
|[CEdit::Get수정](#getmodify)|편집 컨트롤의 내용이 수정되었는지 여부를 결정합니다.|
|[CEdit::getPasswordChar](#getpasswordchar)|사용자가 텍스트를 입력할 때 편집 컨트롤에 표시되는 암호 문자를 검색합니다.|
|[CEdit::GetRect](#getrect)|편집 컨트롤의 서식 지정 사각형을 가져옵니다.|
|[CEdit::GetSel](#getsel)|편집 컨트롤에서 현재 선택 영역의 첫 번째 및 마지막 문자 위치를 가져옵니다.|
|[CEdit::숨기기 풍선 팁](#hideballoontip)|현재 편집 컨트롤과 연관된 부품 번호 팁을 숨깁니다.|
|[편집::제한텍스트](#limittext)|사용자가 편집 컨트롤에 입력할 수 있는 텍스트의 길이를 제한합니다.|
|[CEdit::라인에서차](#linefromchar)|지정된 문자 인덱스를 포함하는 줄의 줄 번호를 검색합니다.|
|[CEdit::선 인덱스](#lineindex)|다중 줄 편집 컨트롤 내에서 줄의 문자 인덱스를 검색합니다.|
|[CEdit::선 길이](#linelength)|편집 컨트롤에서 줄의 길이를 검색합니다.|
|[CEdit::라인스크롤](#linescroll)|다중 줄 편집 컨트롤의 텍스트를 스크롤합니다.|
|[CEdit::P아스트](#paste)|현재 커서 위치에서 편집 컨트롤에 클립보드의 데이터를 삽입합니다. 클립보드에 CF_TEXT 형식의 데이터가 포함된 경우에만 데이터가 삽입됩니다.|
|[CEdit::PosFromChar](#posfromchar)|지정된 문자 인덱스의 왼쪽 위 모서리의 좌표를 검색합니다.|
|[CEdit::대체셀](#replacesel)|편집 컨트롤의 현재 선택 영역을 지정된 텍스트로 바꿉습니다.|
|[CEdit::SetCue배너](#setcuebanner)|컨트롤이 비어 있고 포커스가 없는 경우 편집 컨트롤에서 텍스트 큐 또는 팁으로 표시되는 텍스트를 설정합니다.|
|[CEdit::설정 핸들](#sethandle)|핸들을 여러 줄 편집 컨트롤에서 사용할 로컬 메모리로 설정합니다.|
|[편집::설정 강조 표시](#sethighlight)|현재 편집 컨트롤에 표시되는 텍스트 범위를 강조 표시합니다.|
|[편집::설정제한 텍스트](#setlimittext)|포함할 `CEdit` 수 있는 최대 텍스트 양을 설정합니다.|
|[CEdit::세트 마진](#setmargins)|이에 대한 왼쪽 및 `CEdit`오른쪽 여백을 설정합니다.|
|[편집::설정 수정](#setmodify)|편집 컨트롤의 수정 플래그를 설정하거나 지웁습니다.|
|[CEdit::설정암호차르](#setpasswordchar)|사용자가 텍스트를 입력할 때 편집 컨트롤에 표시되는 암호 문자를 설정하거나 제거합니다.|
|[CEdit::설정읽기전용](#setreadonly)|편집 컨트롤의 읽기 전용 상태를 설정합니다.|
|[CEdit::SetRect](#setrect)|다중 줄 편집 컨트롤의 서식 지정 사각형을 설정하고 컨트롤을 업데이트합니다.|
|[CEdit::SetRectNP](#setrectnp)|컨트롤 창을 다시 그리기 않고 다중 줄 편집 컨트롤의 서식 지정 사각형을 설정합니다.|
|[CEdit::SetSel](#setsel)|편집 컨트롤에서 문자 범위를 선택합니다.|
|[CEdit::SetTabstops](#settabstops)|여러 줄 편집 컨트롤에서 탭 중지를 설정합니다.|
|[CEdit::쇼풍선팁](#showballoontip)|현재 편집 컨트롤과 연관된 부품 번호 팁을 표시합니다.|
|[CEdit::: 취소](#undo)|마지막 편집 제어 작업을 반전합니다.|

## <a name="remarks"></a>설명

편집 컨트롤은 사용자가 텍스트를 입력할 수 있는 사각형 자식 창입니다.

대화 상자 템플릿에서 또는 코드에서 직접 편집 컨트롤을 만들 수 있습니다. 두 경우 모두 먼저 `CEdit` 생성자 호출하여 개체를 `CEdit` 생성한 다음 멤버 [만들기](#create) 함수를 호출하여 `CEdit` Windows 편집 컨트롤을 만들고 개체에 연결합니다.

구성은 에서 파생된 클래스의 한 단계 `CEdit`프로세스일 수 있습니다. 파생 클래스에 대한 생성자 및 `Create` 생성자 내에서 호출합니다.

`CEdit`에서 `CWnd`중요한 기능을 상속합니다. `CEdit` 개체에서 `CWnd` 텍스트를 설정하고 검색하려면 다중 라인 컨트롤인 경우에도 편집 컨트롤의 전체 내용을 설정하거나 가져옵니다. [SetWindowText](cwnd-class.md#setwindowtext) [GetWindowText](cwnd-class.md#getwindowtext) 다중 줄 컨트롤의 텍스트 줄은 '\r\n' 문자 시퀀스로 구분됩니다. 또한 편집 컨트롤이 다중 줄인 경우 `CEdit` 멤버 함수 [GetLine,](#getline) [SetSel,](#setsel) [GetSel](#getsel)및 [ReplaceSel을](#replacesel)호출하여 컨트롤 텍스트의 일부를 가져옵니다.

편집 컨트롤에서 부모(일반적으로 파생된 `CDialog`클래스)에 보낸 Windows 알림 메시지를 처리하려면 각 메시지에 대한 부모 클래스에 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가합니다.

각 메시지 맵 항목은 다음과 같은 형식을 취합니다.

  **ON_**_알림_ _(id,_**,** _memberFxn)_ **)** **(**

여기서 `id` 알림을 보내는 편집 컨트롤의 자식 창 ID를 `memberFxn` 지정하고 알림을 처리하기 위해 작성한 부모 구성원 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

**afx_msg** 무효 회원Fxn **();**

다음은 잠재적인 메시지 맵 항목 목록과 상위 사용자에게 전송될 사례에 대한 설명입니다.

- ON_EN_CHANGE 사용자가 편집 컨트롤에서 텍스트를 변경했을 수 있는 작업을 수행했습니다. EN_UPDATE 알림 메시지와 달리 Windows에서 디스플레이를 업데이트한 후 이 알림 메시지가 전송됩니다.

- ON_EN_ERRSPACE 편집 컨트롤은 특정 요청을 충족하기에 충분한 메모리를 할당할 수 없습니다.

- ON_EN_HSCROLL 사용자가 편집 컨트롤의 가로 스크롤 막대를 클릭합니다. 화면이 업데이트되기 전에 부모 창에 알림이 전송됩니다.

- ON_EN_KILLFOCUS 편집 컨트롤이 입력 포커스를 잃습니다.

- ON_EN_MAXTEXT 현재 삽입이 편집 컨트롤의 지정된 문자 수를 초과했으며 잘렸습니다. 또한 편집 컨트롤에 ES_AUTOHSCROLL 스타일이 없고 삽입할 문자 수가 편집 컨트롤의 너비를 초과할 때 전송됩니다. 또한 편집 컨트롤에 ES_AUTOVSCROLL 스타일이 없고 텍스트 삽입으로 인한 총 줄 수가 편집 컨트롤의 높이를 초과할 때 전송됩니다.

- ON_EN_SETFOCUS 편집 컨트롤이 입력 포커스를 수신할 때 전송됩니다.

- ON_EN_UPDATE 편집 컨트롤이 변경된 텍스트를 표시하려고 합니다. 컨트롤이 텍스트의 서식을 지정한 후에 전송되지만 필요한 경우 창 크기를 변경할 수 있도록 텍스트를 검사합니다.

- ON_EN_VSCROLL 사용자가 편집 컨트롤의 세로 스크롤 막대를 클릭합니다. 화면이 업데이트되기 전에 부모 창에 알림이 전송됩니다.

대화 상자 `CEdit` 내에서 개체를 만들면 `CEdit` 사용자가 대화 상자를 닫으면 개체가 자동으로 소멸됩니다.

대화 상자 `CEdit` 편집기에서 대화 상자 리소스에서 개체를 `CEdit` 만들면 사용자가 대화 상자를 닫으면 개체가 자동으로 소멸됩니다.

창 내에서 `CEdit` 객체를 만드는 경우 객체를 삭제해야 할 수도 있습니다. 스택에서 객체를 `CEdit` 만들면 자동으로 소멸됩니다. 새 함수를 `CEdit` 사용하여 힙에 개체를 **new** 만드는 경우 사용자가 Windows 편집 컨트롤을 종료할 때 개체에 **삭제를** 호출하여 개체를 삭제해야 합니다. 개체에 메모리를 `CEdit` 할당하는 경우 `CEdit` 소멸자 재정의하여 할당을 삭제합니다.

편집 컨트롤에서 특정 스타일을 수정하려면(예: ES_READONLY) [수정 스타일](cwnd-class.md#modifystyle)을 사용하는 대신 특정 메시지를 컨트롤에 보내야 합니다. Windows SDK에서 [컨트롤 스타일 편집을](/windows/win32/Controls/edit-control-styles) 참조하십시오.

에 대한 `CEdit`자세한 내용은 [컨트롤](../../mfc/controls-mfc.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="ceditcanundo"></a><a name="canundo"></a>CEdit:::CanUndo

이 함수를 호출하여 마지막 편집 작업을 취소할 수 있는지 확인합니다.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Return Value

멤버 함수에 대한 호출로 `Undo` 마지막 편집 작업을 취소할 수 있는 경우 Nonzero입니다. 취소할 수 없는 경우 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_CANUNDO](/windows/win32/Controls/em-canundo) 참조하세요.

### <a name="example"></a>예제

  [CEdit::Undo에](#undo)대한 예제를 참조하십시오.

## <a name="ceditcedit"></a><a name="cedit"></a>CEdit::CEdit

`CEdit` 개체를 생성합니다.

```
CEdit();
```

### <a name="remarks"></a>설명

[만들기를](#create) 사용하여 Windows 편집 컨트롤을 구성합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

## <a name="ceditcharfrompos"></a><a name="charfrompos"></a>CEdit::CharFrompos

이 함수를 호출하여 이 `CEdit` 컨트롤에서 지정된 지점에 가장 가까운 문자의 0-기반 선 및 문자 인덱스를 검색합니다.

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
이 `CEdit` 개체의 클라이언트 영역에서 점의 좌표입니다.

### <a name="return-value"></a>Return Value

낮은 순서의 WORD의 문자 인덱스와 높은 순서의 WORD의 줄 인덱스입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 이 멤버 기능은 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_CHARFROMPOS](/windows/win32/Controls/em-charfrompos) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

## <a name="ceditclear"></a><a name="clear"></a>CEdit::지우기

편집 컨트롤에서 현재 선택 항목(있는 경우)을 삭제(지우기)하려면 이 함수를 호출합니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

수행 취소 멤버 `Clear` 함수를 호출하여 수행 [Undo](#undo) 취소할 수 있습니다.

현재 선택 영역을 삭제하고 삭제된 내용을 클립보드에 배치하려면 [잘라내기](#cut) 멤버 함수를 호출합니다.

자세한 내용은 Windows SDK의 [WM_CLEAR](/windows/win32/dataxchg/wm-clear) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

## <a name="ceditcopy"></a><a name="copy"></a>CEdit::복사

편집 컨트롤의 현재 선택 영역(있는 경우)을 클립보드 형식으로 CF_TEXT 이 함수를 호출합니다.

```cpp
void Copy();
```

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [WM_COPY](/windows/win32/dataxchg/wm-copy) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

## <a name="ceditcreate"></a><a name="create"></a>CEdit::만들기

Windows 편집 컨트롤을 만들고 개체에 `CEdit` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
편집 컨트롤의 스타일을 지정합니다. [편집 스타일의](styles-used-by-mfc.md#edit-styles) 조합을 컨트롤에 적용합니다.

*rect*<br/>
편집 컨트롤의 크기와 위치를 지정합니다. 개체 또는 `CRect` `RECT` 구조일 수 있습니다.

*pParentWnd*<br/>
편집 컨트롤의 부모 창(일반적으로 a)을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
편집 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

초기화가 성공하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

두 단계로 `CEdit` 객체를 생성합니다. 먼저 생성자 `CEdit` 호출 한 `Create`다음 호출 합니다 . `CEdit`

실행되면 `Create` Windows는 [WM_NCCREATE](/windows/win32/winmsg/wm-nccreate), WM_NCCALCSIZE [WM_CREATE](/windows/win32/winmsg/wm-create)및 [WM_GETMINMAXINFO](/windows/win32/winmsg/wm-getminmaxinfo) 메시지를 편집 컨트롤로 보냅니다. [WM_NCCALCSIZE](/windows/win32/winmsg/wm-nccalcsize)

이러한 메시지는 기본적으로 [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate)및 [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) 멤버 `CWnd` 함수에 의해 기본 클래스에서 처리됩니다. 기본 메시지 처리를 확장하려면 에서 `CEdit`클래스를 파생합니다 . 예를 `OnCreate`들어 새 클래스에 필요한 초기화를 수행하려면 재정의합니다.

다음 [창 스타일을](styles-used-by-mfc.md#window-styles) 편집 컨트롤에 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_GROUP 컨트롤그룹

- WS_TABSTOP 탭 순서에 편집 컨트롤을 포함하려면

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

## <a name="ceditcut"></a><a name="cut"></a>CEdit::컷

편집 컨트롤의 현재 선택 항목(있는 경우)을 삭제(잘라내기)하고 삭제된 텍스트를 클립보드에 CF_TEXT 형식으로 복사하려면 이 함수를 호출합니다.

```cpp
void Cut();
```

### <a name="remarks"></a>설명

수행 취소 멤버 `Cut` 함수를 호출하여 수행 [Undo](#undo) 취소할 수 있습니다.

삭제된 텍스트를 클립보드에 넣지 않고 현재 선택 영역을 삭제하려면 [멤버 지우기](#clear) 함수를 호출합니다.

자세한 내용은 Windows SDK의 [WM_CUT](/windows/win32/dataxchg/wm-cut) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

## <a name="ceditemptyundobuffer"></a><a name="emptyundobuffer"></a>CEdit::빈Undo버퍼

이 함수를 호출하여 편집 컨트롤의 취소 플래그를 재설정(지우기)합니다.

```cpp
void EmptyUndoBuffer();
```

### <a name="remarks"></a>설명

이제 편집 컨트롤이 마지막 작업을 취소할 수 없습니다. 편집 컨트롤 내의 작업을 취소할 수 있을 때마다 완료 취소 플래그가 설정됩니다.

[SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 또는 [SetHandle](#sethandle) `CWnd` 멤버 함수가 호출될 때마다 취소 플래그가 자동으로 지워집니다.

자세한 내용은 Windows SDK의 [EM_EMPTYUNDOBUFFER](/windows/win32/Controls/em-emptyundobuffer) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

## <a name="ceditfmtlines"></a><a name="fmtlines"></a>CEdit::FmtLines

이 함수를 호출하여 다중 줄 편집 컨트롤 내에서 소프트 줄 바그 문자의 포함을 설정하거나 해제합니다.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>매개 변수

*바데올*<br/>
소프트 줄 바그 문자를 삽입할지 여부를 지정합니다. TRUE 값은 문자를 삽입합니다. FALSE 값을 제거합니다.

### <a name="return-value"></a>Return Value

서식이 발생하는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

소프트 라인 나누기는 두 개의 캐리지 리턴과 단어 줄 바꿈으로 인해 끊어진 줄의 끝에 삽입된 줄 바꿈으로 구성됩니다. 하드 라인 브레이크는 하나의 캐리지 리턴과 라인 피드로 구성됩니다. 하드 줄 바단으로 끝나는 선은 `FmtLines`의 영향을 받지 않습니다.

개체가 `CEdit` 다중 줄 편집 컨트롤인 경우에만 Windows가 응답합니다.

`FmtLines`[GetHandle에서](#gethandle) 반환된 버퍼와 [WM_GETTEXT](/windows/win32/winmsg/wm-gettext)반환된 텍스트에만 영향을 줍니다. 편집 컨트롤 내의 텍스트 표시에는 영향을 미치지 않습니다.

자세한 내용은 Windows SDK의 [EM_FMTLINES](/windows/win32/Controls/em-fmtlines) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

## <a name="ceditgetcuebanner"></a><a name="getcuebanner"></a>CEdit::GetCue배너

컨트롤이 비어 있을 때 편집 컨트롤에서 텍스트 큐 또는 팁으로 표시되는 텍스트를 검색합니다.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【아웃】 큐 텍스트가 포함된 문자열에 대한 포인터입니다.

*cchText*<br/>
【인】 수신할 수 있는 문자 수입니다. 이 숫자에는 NULL 문자 종료가 포함됩니다.

### <a name="return-value"></a>Return Value

첫 번째 오버로드의 경우 메서드가 성공하면 TRUE입니다. 그렇지 않으면 거짓.

두 번째 오버로드의 경우 메서드가 성공한 경우 큐 텍스트가 포함된 [CString입니다.](../../atl-mfc-shared/using-cstring.md) 그렇지 않으면 빈 문자열("")이 됩니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [EM_GETCUEBANNER](/windows/win32/Controls/em-getcuebanner) 메시지를 보냅니다. 자세한 내용은 [Edit_GetCueBannerText](/windows/win32/api/commctrl/nf-commctrl-edit_getcuebannertext) 매크로를 참조하세요.

## <a name="ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a>CEdit::GetFirstVisible선

이 함수를 호출하여 편집 컨트롤에서 가장 맨 위에 표시되는 선을 결정합니다.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Return Value

가장 맨 위에 보이는 선의 0기반 인덱스입니다. 한 줄 편집 컨트롤의 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_GETFIRSTVISIBLELINE](/windows/win32/Controls/em-getfirstvisibleline) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

## <a name="ceditgethandle"></a><a name="gethandle"></a>CEdit::GetHandle

이 함수를 호출하여 현재 여러 줄 편집 컨트롤에 할당된 메모리에 대한 핸들을 검색합니다.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Return Value

편집 컨트롤의 내용을 보유 하는 버퍼를 식별 하는 로컬 메모리 핸들입니다. 한 줄 편집 컨트롤에 메시지를 보내는 등의 오류가 발생 하는 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

핸들은 로컬 메모리 핸들이며 로컬 메모리 핸들을 매개 변수로 사용하는 **로컬** Windows 메모리 함수에서 사용할 수 있습니다.

`GetHandle`다중 라인 편집 컨트롤에 의해서만 처리됩니다.

대화 `GetHandle` 상자가 DS_LOCALEDIT 스타일 플래그 집합으로 만들어진 경우에만 대화 상자에서 여러 줄 편집 컨트롤을 호출합니다. DS_LOCALEDIT 스타일이 설정되지 않은 경우에도 0이 아닌 반환 값을 얻지만 반환된 값을 사용할 수 없습니다.

> [!NOTE]
> `GetHandle`윈도우 95/98에서 작동하지 않습니다. Windows 95/98에서 전화를 걸면 `GetHandle` NULL이 반환됩니다. `GetHandle`Windows NT, 버전 3.51 이상에 문서화 된 대로 작동합니다.

자세한 내용은 Windows SDK의 [EM_GETHANDLE](/windows/win32/Controls/em-gethandle) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

## <a name="ceditgethighlight"></a><a name="gethighlight"></a>CEdit::Get하이라이트

현재 편집 컨트롤에서 강조 표시된 텍스트 범위에서 첫 번째 및 마지막 문자의 인덱스를 가져옵니다.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*피치 스타트*|【아웃】 강조 표시된 텍스트 범위의 첫 번째 문자의 0기반 인덱스입니다.|
|*피치 엔드*|【아웃】 강조 표시된 텍스트 범위의 마지막 문자의 0기반 인덱스입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [EM_GETHILITE](/windows/win32/Controls/em-gethilite) 메시지를 보냅니다. 둘 `SetHighlight` `GetHighlight` 다 현재 UNICODE 빌드에 대해서만 사용할 수 있습니다.

## <a name="ceditgetlimittext"></a><a name="getlimittext"></a>CEdit::GetLimitText

이 개체에 대한 텍스트 제한을 `CEdit` 얻으려면 이 멤버 함수를 호출합니다.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Return Value

이 `CEdit` 개체에 대한 TCHAR의 현재 텍스트 제한입니다.

### <a name="remarks"></a>설명

텍스트 제한은 편집 컨트롤이 허용할 수 있는 TCHAR의 최대 텍스트 양입니다.

> [!NOTE]
> 이 멤버 기능은 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_GETLIMITTEXT](/windows/win32/Controls/em-getlimittext) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

## <a name="ceditgetline"></a><a name="getline"></a>CEdit::GetLine

편집 컨트롤에서 텍스트 줄을 검색하 고 *lpszBuffer에*배치 하려면이 함수를 호출 합니다.

```
int GetLine(
    int nIndex,
    LPTSTR lpszBuffer) const;

int GetLine(
    int nIndex,
    LPTSTR lpszBuffer,
    int nMaxLength) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
여러 줄 편집 컨트롤에서 검색할 줄 번호를 지정합니다. 줄 번호는 0을 기준으로 합니다. 값이 0이면 첫 번째 줄을 지정합니다. 이 매개변수는 한 줄 편집 컨트롤에서 무시됩니다.

*lpszBuffer*<br/>
줄의 복사본을 받는 버퍼를 가리킵니다. 버퍼의 첫 번째 단어는 버퍼에 복사할 수 있는 최대 TCHARs 수를 지정해야 합니다.

*nMaxLength*<br/>
버퍼에 복사할 수 있는 최대 TCHAR 문자 수를 지정합니다. `GetLine`Windows를 호출하기 전에 *lpszBuffer의* 첫 번째 단어에 이 값을 배치합니다.

### <a name="return-value"></a>Return Value

실제로 복사된 문자 수입니다. *nIndex에서* 지정한 줄 번호가 편집 컨트롤의 줄 수보다 큰 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

복사된 줄에는 null 종료 문자가 포함되어 있지 않습니다.

자세한 내용은 Windows SDK의 [EM_GETLINE](/windows/win32/Controls/em-getline) 참조하세요.

### <a name="example"></a>예제

  [CEdit::GetLineCount](#getlinecount)에 대한 예제를 참조하십시오.

## <a name="ceditgetlinecount"></a><a name="getlinecount"></a>CEdit::GetLineCount

이 함수를 호출하여 다중 줄 편집 컨트롤에서 줄 수를 검색합니다.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Return Value

다중 줄 편집 컨트롤의 줄 수를 포함하는 정수입니다. 편집 컨트롤에 텍스트를 입력하지 않은 경우 반환 값은 1입니다.

### <a name="remarks"></a>설명

`GetLineCount`다중 라인 편집 컨트롤에서만 처리됩니다.

자세한 내용은 Windows SDK의 [EM_GETLINECOUNT](/windows/win32/Controls/em-getlinecount) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

## <a name="ceditgetmargins"></a><a name="getmargins"></a>CEdit::getmargins

이 멤버 함수를 호출하여 이 편집 컨트롤의 왼쪽 및 오른쪽 여백을 검색합니다.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Return Value

낮은 순서의 WORD에서 왼쪽 여백의 너비와 높은 순서WORD의 오른쪽 여백의 너비입니다.

### <a name="remarks"></a>설명

여백은 픽셀 단위로 측정됩니다.

> [!NOTE]
> 이 멤버 기능은 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_GETMARGINS](/windows/win32/Controls/em-getmargins) 참조하세요.

### <a name="example"></a>예제

  [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)에 대한 예제를 참조하십시오.

## <a name="ceditgetmodify"></a><a name="getmodify"></a>CEdit::Get수정

이 함수를 호출하여 편집 컨트롤의 내용이 수정되었는지 확인합니다.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Return Value

편집 제어 내용이 수정된 경우 0이 아닙니다. 0이 변경되지 않은 상태로 유지된 경우.

### <a name="remarks"></a>설명

Windows는 편집 컨트롤의 내용이 변경되었는지 여부를 나타내는 내부 플래그를 유지 관리합니다. 이 플래그는 편집 컨트롤을 처음 만들 때 지워지며 [SetModify](#setmodify) 멤버 함수를 호출하여 지울 수도 있습니다.

자세한 내용은 Windows SDK의 [EM_GETMODIFY](/windows/win32/Controls/em-getmodify) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

## <a name="ceditgetpasswordchar"></a><a name="getpasswordchar"></a>CEdit::getPasswordChar

사용자가 텍스트를 입력할 때 편집 컨트롤에 표시되는 암호 문자를 검색하려면 이 함수를 호출합니다.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Return Value

사용자가 입력한 문자 대신 표시할 문자를 지정합니다. 암호 문자가 없는 경우 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

ES_PASSWORD 스타일로 편집 컨트롤을 만드는 경우 컨트롤을 지원하는 DLL이 기본 암호 문자를 결정합니다. 매니페스트 또는 [InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex) 메서드는 편집 컨트롤을 지원하는 DLL을 결정합니다. user32.dll이 편집 컨트롤을 지원하는 경우 기본 암호 문자는 ASTERISK('*', U+002A)입니다. comctl32.dll 버전 6이 편집 컨트롤을 지원하는 경우 기본 문자는 BLACK CIRCLE('●', U+25CF)입니다. 공통 컨트롤을 지원하는 DLL 및 버전에 대한 자세한 내용은 [셸 및 일반 컨트롤 버전을](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\))참조하십시오.

이 메서드는 Windows SDK에 설명 된 [EM_GETPASSWORDCHAR](/windows/win32/Controls/em-getpasswordchar) 메시지를 보냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

## <a name="ceditgetrect"></a><a name="getrect"></a>CEdit::GetRect

이 함수를 호출하여 편집 컨트롤의 서식 지정 사각형을 가져옵니다.

```cpp
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
서식 `RECT` 지정 사각형을 받는 구조를 가리킵니다.

### <a name="remarks"></a>설명

서식 지정 사각형은 편집 제어 창의 크기와 는 독립적인 텍스트의 제한 사각형입니다.

[SetRect](#setrect) 및 [SetRectNP](#setrectnp) 멤버 함수에서 다중 라인 편집 컨트롤의 서식 지정 사각형을 수정할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_GETRECT](/windows/win32/Controls/em-getrect) 참조하세요.

### <a name="example"></a>예제

  [CEdit::LimitText](#limittext)에 대한 예제를 참조하십시오.

## <a name="ceditgetsel"></a><a name="getsel"></a>CEdit::GetSel

이 함수를 호출하여 반환 값 또는 매개 변수를 사용하여 편집 컨트롤에서 현재 선택 영역(있는 경우)의 시작 및 종료 문자 위치를 가져옵니다.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>매개 변수

*nStartChar*<br/>
현재 선택 에서 첫 번째 문자의 위치를 받을 정수를 참조 합니다.

*nEndChar*<br/>
현재 선택 영역의 끝을 지나 선택되지 않은 첫 번째 문자의 위치를 받는 정수를 참조합니다.

### <a name="return-value"></a>Return Value

DWORD를 반환하는 버전은 하위 순서 단어의 시작 위치와 높은 순서 단어에서 선택 종료 후 첫 번째 선택되지 않은 문자의 위치를 포함하는 값을 반환합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_GETSEL](/windows/win32/Controls/em-getsel) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

## <a name="cedithideballoontip"></a><a name="hideballoontip"></a>CEdit::숨기기 풍선 팁

현재 편집 컨트롤과 연관된 부품 번호 팁을 숨깁니다.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명된 [EM_HIDEBALLOONTIP](/windows/win32/Controls/em-hideballoontip) 메시지를 보냅니다.

## <a name="ceditlimittext"></a><a name="limittext"></a>편집::제한텍스트

이 함수를 호출하여 사용자가 편집 컨트롤에 입력할 수 있는 텍스트의 길이를 제한합니다.

```cpp
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>매개 변수

*nChars*<br/>
사용자가 입력할 수 있는 텍스트의 길이(TCHAR)를 지정합니다. 이 매개변수가 0이면 텍스트 길이가 UINT_MAX 바이트로 설정됩니다. 기본 동작입니다.

### <a name="remarks"></a>설명

텍스트 제한을 변경하면 사용자가 입력할 수 있는 텍스트만 제한됩니다. 편집 컨트롤에 이미 있는 텍스트에는 영향을 주지 않으며 에서 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수에서 편집 컨트롤에 복사된 텍스트의 길이에도 `CWnd`영향을 주지 않습니다. 응용 프로그램이 이 `SetWindowText` 함수를 사용하여 호출에 `LimitText`지정된 것보다 더 많은 텍스트를 편집 컨트롤에 배치하는 경우 사용자는 편집 컨트롤 내의 텍스트를 삭제할 수 있습니다. 그러나 텍스트 제한은 현재 선택을 삭제하면 텍스트가 텍스트 제한 아래로 떨어지지 않는 한 기존 텍스트를 새 텍스트로 대체하지 못하게 됩니다.

> [!NOTE]
> Win32(Windows NT 및 Windows 95/98)에서 [SetLimitText가](#setlimittext) 이 기능을 대체합니다.

자세한 내용은 Windows SDK의 [EM_LIMITTEXT](/windows/win32/Controls/em-limittext) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

## <a name="ceditlinefromchar"></a><a name="linefromchar"></a>CEdit::라인에서차

이 함수를 호출하여 지정된 문자 인덱스가 포함된 줄의 줄 번호를 검색합니다.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
편집 컨트롤의 텍스트에 원하는 문자에 대한 0기반 인덱스 값을 포함하거나 -1을 포함합니다. *nIndex가* -1이면 현재 줄, 즉 캐릿을 포함하는 줄을 지정합니다.

### <a name="return-value"></a>Return Value

*nIndex에서*지정한 문자 인덱스를 포함하는 줄의 0기반 줄 번호입니다. *nIndex가* -1이면 선택 영역의 첫 번째 문자가 포함된 줄의 수가 반환됩니다. 선택 항목이 없는 경우 현재 줄 번호가 반환됩니다.

### <a name="remarks"></a>설명

문자 인덱스는 편집 컨트롤의 시작 부분에서 문자 수입니다.

이 멤버 함수는 다중 줄 편집 컨트롤에서만 사용됩니다.

자세한 내용은 Windows SDK의 [EM_LINEFROMCHAR](/windows/win32/Controls/em-linefromchar) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

## <a name="ceditlineindex"></a><a name="lineindex"></a>CEdit::선 인덱스

이 함수를 호출하여 다중 줄 편집 컨트롤 내에서 줄의 문자 인덱스를 검색합니다.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>매개 변수

*Nline*<br/>
편집 컨트롤의 텍스트에 원하는 줄에 대한 인덱스 값을 포함하거나 -1을 포함합니다. *nLine이* -1이면 현재 줄, 즉 캐릿을 포함하는 줄을 지정합니다.

### <a name="return-value"></a>Return Value

지정된 줄 번호가 편집 컨트롤의 줄 수보다 큰 경우 *nLine* 또는 -1로 지정된 줄의 문자 인덱스입니다.

### <a name="remarks"></a>설명

문자 인덱스는 편집 컨트롤의 시작부터 지정된 줄까지의 문자 수입니다.

이 멤버 함수는 다중 줄 편집 컨트롤에서만 처리됩니다.

자세한 내용은 Windows SDK의 [EM_LINEINDEX](/windows/win32/controls/em-lineindex) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

## <a name="ceditlinelength"></a><a name="linelength"></a>CEdit::선 길이

편집 컨트롤에서 줄의 길이를 검색합니다.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>매개 변수

*Nline*<br/>
길이를 검색할 줄에 있는 문자의 0기반 인덱스입니다. 기본값은 -1입니다.

### <a name="return-value"></a>Return Value

한 줄 편집 컨트롤의 경우 반환 값은 편집 컨트롤의 텍스트의 길이(TCHARs)입니다.

다중 선 편집 컨트롤의 경우 반환 값은 *nLine* 매개 변수에 의해 지정된 선의 TCHAR의 길이입니다. ANSI 텍스트의 경우 길이는 줄의 바이트 수입니다. 유니코드 텍스트의 경우 길이는 줄의 문자 수입니다. 길이는 줄의 끝에 캐리지 리턴 문자를 포함하지 않습니다.

*nLine* 매개 변수가 컨트롤의 문자 수보다 많으면 반환 값이 0입니다.

*nLine* 매개 변수가 -1이면 반환 값은 선택한 문자를 포함하는 줄의 선택되지 않은 문자 수입니다. 예를 들어 선택이 한 줄의 네 번째 문자에서 다음 줄의 끝에서 8번째 문자까지 확장되는 경우 반환 값은 10입니다. 즉, 첫 번째 줄에는 3자, 다음 줄에는 7자입니다.

TCHAR 형식에 대한 자세한 내용은 [Windows 데이터 형식의](/windows/win32/WinProg/windows-data-types)테이블에서 TCHAR 행을 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [EM_LINELENGTH](/windows/win32/Controls/em-linelength) 메시지에 의해 지원 됩니다.

### <a name="example"></a>예제

  [CEdit::LineIndex](#lineindex)에 대한 예제를 참조하십시오.

## <a name="ceditlinescroll"></a><a name="linescroll"></a>CEdit::라인스크롤

이 함수를 호출하여 여러 줄 편집 컨트롤의 텍스트를 스크롤합니다.

```cpp
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>매개 변수

*n라인*<br/>
세로로 스크롤할 줄 수를 지정합니다.

*nChars*<br/>
가로로 스크롤할 문자 위치 수를 지정합니다. 편집 컨트롤에 ES_RIGHT 또는 ES_CENTER 스타일이 있는 경우 이 값은 무시됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는 다중 줄 편집 컨트롤에서만 처리됩니다.

편집 컨트롤은 편집 컨트롤의 마지막 텍스트 줄을 지나 세로로 스크롤되지 않습니다. 현재 줄과 *nLine으로* 지정된 줄 수가 편집 컨트롤의 총 줄 수를 초과하면 편집 컨트롤의 마지막 줄이 편집 제어 창의 맨 위로 스크롤되도록 값이 조정됩니다.

`LineScroll`이 하면 모든 줄의 마지막 문자를 지나 가로로 스크롤할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_LINESCROLL](/windows/win32/Controls/em-linescroll) 참조하세요.

### <a name="example"></a>예제

  [CEdit::GetFirstVisibleLine](#getfirstvisibleline)에 대한 예제를 참조하십시오.

## <a name="ceditpaste"></a><a name="paste"></a>CEdit::P아스트

이 함수를 호출하여 클립보드의 `CEdit` 데이터를 삽입 지점에 삽입합니다.

```cpp
void Paste();
```

### <a name="remarks"></a>설명

클립보드에 CF_TEXT 형식의 데이터가 포함된 경우에만 데이터가 삽입됩니다.

자세한 내용은 Windows SDK의 [WM_PASTE](/windows/win32/dataxchg/wm-paste) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

## <a name="ceditposfromchar"></a><a name="posfromchar"></a>CEdit::PosFromChar

이 함수를 호출하여 이 `CEdit` 개체 내에서 지정된 문자의 위치(왼쪽 위 모서리)를 가져옵니다.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>매개 변수

*Nchar*<br/>
지정된 문자의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

*nChar로*지정된 문자의 왼쪽 위 모서리의 좌표입니다.

### <a name="remarks"></a>설명

문자는 0기반 인덱스 값을 제공하여 지정됩니다. *nChar가* 이 `CEdit` 개체의 마지막 문자 인덱스보다 큰 경우 반환 값은 이 `CEdit` 개체의 마지막 문자를 지나면 문자 위치의 좌표를 지정합니다.

> [!NOTE]
> 이 멤버 기능은 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_POSFROMCHAR](/windows/win32/Controls/em-posfromchar) 참조하세요.

### <a name="example"></a>예제

  [CEdit::LineFromChar](#linefromchar)에 대한 예제를 참조하십시오.

## <a name="ceditreplacesel"></a><a name="replacesel"></a>CEdit::대체셀

편집 컨트롤의 현재 선택 영역을 *lpszNewText로*지정한 텍스트로 바꾸려면 이 함수를 호출합니다.

```cpp
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszNewText*<br/>
대체 텍스트를 포함하는 null 종료 문자열을 가리킵니다.

*b칸운도*<br/>
이 함수를 취소할 수 있도록 지정하려면 이 매개 변수의 값을 TRUE 로 설정합니다. 기본값은 FALSE입니다.

### <a name="remarks"></a>설명

편집 컨트롤에서 텍스트의 일부만 바꿉입니다. 모든 텍스트를 바꾸려면 [CWnd::SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수를 사용합니다.

현재 선택 영역이 없는 경우 대체 텍스트가 현재 커서 위치에 삽입됩니다.

자세한 내용은 Windows SDK의 [EM_REPLACESEL](/windows/win32/Controls/em-replacesel) 참조하세요.

### <a name="example"></a>예제

  [CEdit::LineIndex](#lineindex)에 대한 예제를 참조하십시오.

## <a name="ceditsetcuebanner"></a><a name="setcuebanner"></a>CEdit::SetCue배너

컨트롤이 비어 있을 때 편집 컨트롤에서 텍스트 큐 또는 팁으로 표시되는 텍스트를 설정합니다.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【인】 편집 컨트롤에 표시할 큐가 포함된 문자열에 대한 포인터입니다.

*f그리기초점*<br/>
【인】 FALSE인 경우 사용자가 편집 컨트롤을 클릭하고 컨트롤에 포커스를 부여할 때 큐 배너가 그려지지 않습니다.

TRUE이면 컨트롤에 포커스가 있는 경우에도 큐 배너가 그려집니다. 사용자가 컨트롤을 입력하기 시작하면 큐 배너가 사라집니다.

기본값은 FALSE입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [EM_SETCUEBANNER](/windows/win32/Controls/em-setcuebanner) 메시지를 보냅니다. 자세한 내용은 [Edit_SetCueBannerTextFocused](/windows/win32/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) 매크로를 참조하세요.

### <a name="example"></a>예제

다음 예제에서는 [CEdit::SetCueBanner](#setcuebanner) 메서드를 보여 줍니다.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

## <a name="ceditsethandle"></a><a name="sethandle"></a>CEdit::설정 핸들

이 함수를 호출하여 핸들을 여러 줄 편집 컨트롤에서 사용할 로컬 메모리로 설정합니다.

```cpp
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>매개 변수

*h버퍼*<br/>
로컬 메모리에 대한 핸들을 포함합니다. 이 핸들은 LMEM_MOVEABLE 플래그를 사용하여 [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) Windows 함수에 대한 이전 호출에 의해 만들어졌어야 합니다. 메모리는 null 종료 된 문자열을 포함 하는 것으로 가정 됩니다. 그렇지 않은 경우 할당된 메모리의 첫 번째 바이트를 0으로 설정해야 합니다.

### <a name="remarks"></a>설명

그런 다음 편집 컨트롤은 이 버퍼를 사용하여 자체 버퍼를 할당하는 대신 현재 표시된 텍스트를 저장합니다.

이 멤버 함수는 다중 줄 편집 컨트롤에서만 처리됩니다.

응용 프로그램이 새 메모리 핸들을 설정하기 전에 [GetHandle](#gethandle) 멤버 함수를 사용하여 현재 메모리 버퍼에 `LocalFree` 대한 핸들을 얻고 Windows 함수를 사용하여 해당 메모리를 해제해야 합니다.

`SetHandle`취소 [버퍼(CanUndo](#canundo) 멤버 함수는 0을 반환) 및 내부 수정 [플래그(GetModify](#getmodify) 멤버 함수는 0을 반환)를 지웁니다. 편집 제어 창이 다시 그려집니다.

DS_LOCALEDIT 스타일 플래그 집합으로 대화 상자를 만든 경우에만 대화 상자의 여러 줄 편집 컨트롤에서 이 멤버 함수를 사용할 수 있습니다.

> [!NOTE]
> `GetHandle`윈도우 95/98에서 작동하지 않습니다. Windows 95/98에서 전화를 걸면 `GetHandle` NULL이 반환됩니다. `GetHandle`Windows NT, 버전 3.51 이상에 문서화 된 대로 작동합니다.

자세한 내용은 [EM_SETHANDLE](/windows/win32/Controls/em-sethandle), [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc)및 [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree) Windows SDK를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

## <a name="ceditsethighlight"></a><a name="sethighlight"></a>편집::설정 강조 표시

현재 편집 컨트롤에 표시되는 텍스트 범위를 강조 표시합니다.

```cpp
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*아이치스타트*|【인】 강조 표시할 텍스트 범위의 첫 번째 문자의 0기반 인덱스입니다.|
|*아이치엔드*|【인】 강조 표시할 텍스트 범위의 마지막 문자의 0기반 인덱스입니다.|

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [EM_SETHILITE](/windows/win32/Controls/em-sethilite) 메시지를 보냅니다.  이 메서드는 Windows SDK에 설명 된 [EM_SETHILITE](/windows/win32/Controls/em-sethilite) 메시지를 보냅니다. 둘 `SetHighlight` `GetHighlight` 다 유니코드 빌드에 대해서만 활성화됩니다.

## <a name="ceditsetlimittext"></a><a name="setlimittext"></a>편집::설정제한 텍스트

이 개체에 대한 텍스트 제한을 `CEdit` 설정하려면 이 멤버 함수를 호출합니다.

```cpp
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
문자의 새 텍스트 제한입니다.

### <a name="remarks"></a>설명

텍스트 제한은 편집 컨트롤이 허용할 수 있는 문자의 최대 텍스트 양입니다.

텍스트 제한을 변경하면 사용자가 입력할 수 있는 텍스트만 제한됩니다. 편집 컨트롤에 이미 있는 텍스트에는 영향을 주지 않으며 에서 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수에서 편집 컨트롤에 복사된 텍스트의 길이에도 `CWnd`영향을 주지 않습니다. 응용 프로그램이 이 `SetWindowText` 함수를 사용하여 호출에 `LimitText`지정된 것보다 더 많은 텍스트를 편집 컨트롤에 배치하는 경우 사용자는 편집 컨트롤 내의 텍스트를 삭제할 수 있습니다. 그러나 텍스트 제한은 현재 선택을 삭제하면 텍스트가 텍스트 제한 아래로 떨어지지 않는 한 기존 텍스트를 새 텍스트로 대체하지 못하게 됩니다.

이 함수는 Win32에서 [LimitText를](#limittext) 대체합니다.

자세한 내용은 Windows SDK의 [EM_SETLIMITTEXT](/windows/win32/Controls/em-setlimittext) 참조하세요.

### <a name="example"></a>예제

  [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)에 대한 예제를 참조하십시오.

## <a name="ceditsetmargins"></a><a name="setmargins"></a>CEdit::세트 마진

이 메서드를 호출하여 이 편집 컨트롤의 왼쪽 및 오른쪽 여백을 설정합니다.

```cpp
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>매개 변수

*n왼쪽*<br/>
새 왼쪽 여백의 너비(픽셀)입니다.

*nRight*<br/>
새 오른쪽 여백의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

> [!NOTE]
> 이 멤버 기능은 Windows 95 및 Windows NT 4.0부터 사용할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_SETMARGINS](/windows/win32/Controls/em-setmargins) 참조하세요.

### <a name="example"></a>예제

  [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)에 대한 예제를 참조하십시오.

## <a name="ceditsetmodify"></a><a name="setmodify"></a>편집::설정 수정

편집 컨트롤에 대해 수정된 플래그를 설정하거나 지우려면 이 함수를 호출합니다.

```cpp
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>매개 변수

*bModified*<br/>
TRUE 값은 텍스트가 수정되었음을 나타내고 FALSE 값은 수정되지 않은 값을 나타냅니다. 기본적으로 수정된 플래그가 설정됩니다.

### <a name="remarks"></a>설명

수정된 플래그는 편집 컨트롤 내의 텍스트가 수정되었는지 여부를 나타냅니다. 사용자가 텍스트를 변경할 때마다 자동으로 설정됩니다. 해당 값은 [GetModify](#getmodify) 멤버 함수를 통해 검색할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_SETMODIFY](/windows/win32/Controls/em-setmodify) 참조하세요.

### <a name="example"></a>예제

  [CEdit::GetModify](#getmodify)에 대한 예제를 참조하십시오.

## <a name="ceditsetpasswordchar"></a><a name="setpasswordchar"></a>CEdit::설정암호차르

사용자가 텍스트를 입력할 때 편집 컨트롤에 표시되는 암호 문자를 설정하거나 제거하려면 이 함수를 호출합니다.

```cpp
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>매개 변수

*채널*<br/>
사용자가 입력한 문자 대신 표시할 문자를 지정합니다. *ch가* 0이면 사용자가 입력한 실제 문자가 표시됩니다.

### <a name="remarks"></a>설명

암호 문자가 설정되면 사용자가 입력하는 각 문자에 대해 해당 문자가 표시됩니다.

이 멤버 함수는 다중 줄 편집 컨트롤에 영향을 주지 않습니다.

멤버 `SetPasswordChar` 함수가 `CEdit` 호출되면 *ch*.

편집 컨트롤이 [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) 스타일로 만들어지면 기본 암호 문자가 별표()로 <strong>\*</strong>설정됩니다. ch가 0으로 `SetPasswordChar` 설정된 경우 *ch* 이 스타일이 제거됩니다.

자세한 내용은 Windows SDK의 [EM_SETPASSWORDCHAR](/windows/win32/Controls/em-setpasswordchar) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

## <a name="ceditsetreadonly"></a><a name="setreadonly"></a>CEdit::설정읽기전용

이 함수를 호출하여 편집 컨트롤의 읽기 전용 상태를 설정합니다.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*bReadOnly*<br/>
편집 컨트롤의 읽기 전용 상태를 설정하거나 제거할지 여부를 지정합니다. TRUE 값은 상태를 읽기 전용으로 설정합니다. FALSE 값은 읽기/쓰기 상태를 설정합니다.

### <a name="return-value"></a>Return Value

작업이 성공하면 0이 아니거나 오류가 발생하는 경우 0입니다.

### <a name="remarks"></a>설명

현재 설정은 [CWnd::GetStyle의](cwnd-class.md#getstyle)반환 값에서 [ES_READONLY](styles-used-by-mfc.md#edit-styles) 플래그를 테스트하여 찾을 수 있습니다.

자세한 내용은 Windows SDK의 [EM_SETREADONLY](/windows/win32/Controls/em-setreadonly) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

## <a name="ceditsetrect"></a><a name="setrect"></a>CEdit::SetRect

지정된 좌표를 사용하여 사각형의 치수를 설정하려면 이 함수를 호출합니다.

```cpp
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
서식 `RECT` 지정 `CRect` 사각형의 새 차원을 지정하는 구조또는 개체를 가리킵니다.

### <a name="remarks"></a>설명

이 멤버는 다중 줄 편집 컨트롤에서만 처리됩니다.

여러 `SetRect` 줄 편집 컨트롤의 서식 지정 사각형을 설정하는 데 사용합니다. 서식 지정 사각형은 편집 제어 창의 크기와 는 독립적인 텍스트의 제한 사각형입니다. 편집 컨트롤을 처음 만들 때 서식 지정 사각형은 편집 제어 창의 클라이언트 영역과 동일합니다. 멤버 함수를 `SetRect` 사용하면 응용 프로그램이 서식 지정 사각형을 편집 제어 창보다 크거나 작게 만들 수 있습니다.

편집 컨트롤에 스크롤 막대가 없는 경우 서식 지정 사각형이 창보다 크게 만들어지면 텍스트가 잘리고 줄이 되지 않습니다. 편집 컨트롤에 테두리가 포함된 경우 서식 지정 사각형은 테두리 크기에 따라 줄어듭니다. `GetRect` 멤버 함수에서 반환되는 사각형을 조정하는 경우 사각형을 `SetRect`로 전달하기 전에 테두리 크기를 제거해야 합니다.

호출될 때 `SetRect` 편집 컨트롤의 텍스트도 다시 포식되고 다시 표시됩니다.

자세한 내용은 Windows SDK의 [EM_SETRECT](/windows/win32/Controls/em-setrect) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

## <a name="ceditsetrectnp"></a><a name="setrectnp"></a>CEdit::SetRectNP

이 함수를 호출하여 다중 줄 편집 컨트롤의 서식 지정 사각형을 설정합니다.

```cpp
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
사각형의 `RECT` 새 `CRect` 차원을 지정하는 구조또는 객체를 가리킵니다.

### <a name="remarks"></a>설명

서식 지정 사각형은 편집 제어 창의 크기와 는 독립적인 텍스트의 제한 사각형입니다.

`SetRectNP`편집 제어 `SetRect` 창이 다시 그려지지 않는다는 점을 제외하면 멤버 함수와 동일합니다.

편집 컨트롤을 처음 만들 때 서식 지정 사각형은 편집 제어 창의 클라이언트 영역과 동일합니다. 멤버 함수를 `SetRectNP` 호출하면 응용 프로그램이 서식 지정 사각형을 편집 제어 창보다 크거나 작게 만들 수 있습니다.

편집 컨트롤에 스크롤 막대가 없는 경우 서식 지정 사각형이 창보다 크게 만들어지면 텍스트가 잘리고 줄이 되지 않습니다.

이 멤버는 다중 줄 편집 컨트롤에서만 처리됩니다.

자세한 내용은 Windows SDK의 [EM_SETRECTNP](/windows/win32/Controls/em-setrectnp) 참조하세요.

### <a name="example"></a>예제

  [CEdit::SetRect](#setrect)에 대한 예제를 참조하십시오.

## <a name="ceditsetsel"></a><a name="setsel"></a>CEdit::SetSel

이 함수를 호출하여 편집 컨트롤에서 문자 범위를 선택합니다.

```cpp
void SetSel(
    DWORD dwSelection,
    BOOL bNoScroll = FALSE);

void SetSel(
    int nStartChar,
    int nEndChar,
    BOOL bNoScroll = FALSE);
```

### <a name="parameters"></a>매개 변수

*dw선택*<br/>
하위 순서 단어의 시작 위치와 높은 순서 단어의 끝 위치를 지정합니다. 하위 순서 단어가 0이고 고차 단어가 -1이면 편집 컨트롤의 모든 텍스트가 선택됩니다. 하위 순서 단어가 -1이면 현재 선택 영역이 제거됩니다.

*bNo스크롤*<br/>
는 카를을 뷰로 스크롤해야 하는지 여부를 나타냅니다. FALSE이면 카를트가 보기로 스크롤됩니다. TRUE이면 카를트가 보기로 스크롤되지 않습니다.

*nStartChar*<br/>
시작 위치를 지정합니다. *nStartChar가* 0이고 *nEndChar가* -1이면 편집 컨트롤의 모든 텍스트가 선택됩니다. *nStartChar가* -1이면 현재 선택 영역이 제거됩니다.

*nEndChar*<br/>
끝 위치를 지정합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EM_SETSEL](/windows/win32/Controls/em-setsel) 참조하세요.

### <a name="example"></a>예제

  [CEdit::GetSel](#getsel)에 대한 예제를 참조하십시오.

## <a name="ceditsettabstops"></a><a name="settabstops"></a>CEdit::SetTabstops

이 함수를 호출하여 여러 줄 편집 컨트롤에서 탭 중지를 설정합니다.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>매개 변수

*cxEachStop*<br/>
모든 *cxEachStop* 대화 상자 단위에서 탭 중지를 설정하도록 지정합니다.

*nTabStops*<br/>
*rgTabStops에*포함된 탭 중지 수를 지정합니다. 이 숫자는 1보다 커야 합니다.

*rgTabStops*<br/>
탭이 대화 상자 단위로 중지됨을 지정하는 서명되지 않은 정수 배열을 가리킵니다. 대화 상자는 수평 또는 수직 거리입니다. 하나의 가로 대화 상자 단위는 현재 대화 상자 기본 너비 단위의 1/4과 같으며 1개의 수직 대화 상자 단위는 현재 대화 상자 기본 높이 단위의 1/8과 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 높이와 너비를 기준으로 계산됩니다. Windows `GetDialogBaseUnits` 함수는 현재 대화 상자 기본 단위를 픽셀 단위로 반환합니다.

### <a name="return-value"></a>Return Value

탭이 설정된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

텍스트가 여러 줄 편집 컨트롤에 복사되면 텍스트의 탭 문자가 있으면 다음 탭 중지까지 공백이 생성됩니다.

탭 중지를 32개의 대화 상자 단위의 기본 크기로 설정하려면 이 멤버 함수의 매개 변수없는 버전을 호출합니다. 탭 중지를 32가 아닌 다른 크기로 설정하려면 *cxEachStop* 매개 변수를 사용하여 버전을 호출합니다. 탭 중지를 크기 배열로 설정하려면 두 개의 매개 변수가 있는 버전을 사용합니다.

이 멤버 함수는 다중 줄 편집 컨트롤에서만 처리됩니다.

`SetTabStops`편집 창이 자동으로 다시 그리지 않습니다. 편집 컨트롤에 이미 있는 텍스트에 대한 탭 중지를 변경하면 [CWnd::무효화를](cwnd-class.md#invalidaterect) 호출하여 편집 창을 다시 그립니다.

자세한 내용은 Windows SDK의 [EM_SETTABSTOPS](/windows/win32/Controls/em-settabstops) 및 [GetDialogBaseUnits를](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) 참조하십시오.

### <a name="example"></a>예제

  [CEditView::SetTabStops](ceditview-class.md#settabstops)에 대한 예제를 참조하십시오.

## <a name="ceditshowballoontip"></a><a name="showballoontip"></a>CEdit::쇼풍선팁

현재 편집 컨트롤과 연관된 부품 번호 팁을 표시합니다.

```
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,
    LPCWSTR lpszText,
    INT ttiIcon = TTI_NONE);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pEdit풍선팁*|【인】 풍선 팁을 설명하는 [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) 구조에 대한 포인터입니다.|
|*lpszTitle*|【인】 풍선 팁의 제목을 포함하는 유니코드 문자열에 대한 포인터입니다.|
|*lpszText*|【인】 풍선 팁 텍스트가 포함된 유니코드 문자열에 대한 포인터입니다.|
|*티아이콘*|【인】 풍선 팁과 연결할 아이콘 유형을 지정하는 **INT입니다.** 기본값은 TTI_NONE. 자세한 내용은 `ttiIcon` [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) 구조의 멤버를 참조하십시오.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명된 [EM_SHOWBALLOONTIP](/windows/win32/Controls/em-showballoontip) 메시지를 보냅니다. 자세한 내용은 [Edit_ShowBalloonTip](/windows/win32/api/commctrl/nf-commctrl-edit_showballoontip) 매크로를 참조하세요.

### <a name="example"></a>예제

다음 코드 예제에서는 현재 `m_cedit`편집 컨트롤에 액세스하는 데 사용되는 변수 를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>예제

다음 코드 예제에는 편집 컨트롤에 대한 부품 번호 팁이 표시됩니다. [CEdit::ShowBalloonTip](#showballoontip) 메서드는 제목 및 풍선 팁 텍스트를 지정합니다.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

## <a name="ceditundo"></a><a name="undo"></a>CEdit::: 취소

이 함수를 호출하여 마지막 편집 제어 작업을 취소합니다.

```
BOOL Undo();
```

### <a name="return-value"></a>Return Value

한 줄 편집 컨트롤의 경우 반환 값은 항상 0이 아닙니다. 다중 줄 편집 컨트롤의 경우 실행 취소 작업이 성공하면 반환 값이 0이 아닌 경우, 실행 취소 작업이 실패하면 0입니다.

### <a name="remarks"></a>설명

취소 작업을 취소할 수도 있습니다. 예를 들어 첫 번째 호출을 사용하여 `Undo`삭제된 텍스트를 복원할 수 있습니다. 중간 편집 작업이 없는 한 `Undo`에 대한 두 번째 호출을 사용하여 텍스트를 다시 제거할 수 있습니다.

자세한 내용은 Windows SDK의 [EM_UNDO](/windows/win32/Controls/em-undo) 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](cwnd-class.md)<br/>
[CButton 클래스](cbutton-class.md)<br/>
[CComboBox 클래스](ccombobox-class.md)<br/>
[클리스박스 클래스](clistbox-class.md)<br/>
[C스크롤바 클래스](cscrollbar-class.md)<br/>
[정적 클래스](cstatic-class.md)<br/>
[클리언로그 클래스](cdialog-class.md)
