---
title: CButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
ms.openlocfilehash: 74b07dc8144e853714ea73c8235f1259538a0c12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752760"
---
# <a name="cbutton-class"></a>CButton 클래스

Windows 단추 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CButton : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C 버튼::CButton](#cbutton)|`CButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CButton::만들기](#create)|Windows 단추 컨트롤을 만들고 개체에 `CButton` 연결합니다.|
|[C버튼::D로상품](#drawitem)|소유자가 그린 `CButton` 오브젝트를 그리려면 재정의합니다.|
|[C버튼::겟비트맵](#getbitmap)|SetBitmap을 사용하여 이전에 설정한 [비트맵](#setbitmap)의 핸들을 검색합니다.|
|[CButton::GetButtonStyle](#getbuttonstyle)|단추 제어 스타일에 대한 정보를 검색합니다.|
|[C버튼::GetCheck](#getcheck)|단추 컨트롤의 확인 상태를 검색합니다.|
|[C버튼::겟커서](#getcursor)|[SetCursor로](#setcursor)이전에 설정한 커서 이미지의 핸들을 검색합니다.|
|[CButton::GetIcon](#geticon)|[SetIcon으로](#seticon)이전에 설정한 아이콘의 핸들을 검색합니다.|
|[CButton::GetIdealSize](#getidealsize)|단추 컨트롤의 이상적인 크기를 검색합니다.|
|[CButton::GetImageList](#getimagelist)|단추 컨트롤의 이미지 목록을 검색합니다.|
|[C버튼::겟노트](#getnote)|현재 명령 링크 컨트롤의 메모 구성 요소를 검색합니다.|
|[CButton::GetNoteLength](#getnotelength)|현재 명령 링크 컨트롤에 대 한 메모 텍스트의 길이 검색합니다.|
|[CButton::GetSplitGlyph](#getsplitglyph)|현재 분할 단추 컨트롤과 연결된 글리프를 검색합니다.|
|[C버튼::겟스플릿이미지리스트](#getsplitimagelist)|현재 분할 단추 컨트롤에 대한 이미지 목록을 검색합니다.|
|[C버튼::겟스플릿정보](#getsplitinfo)|현재 분할 단추 컨트롤을 정의하는 정보를 검색합니다.|
|[CButton::GetSplitSize](#getsplitsize)|현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 검색합니다.|
|[CButton::GetSplitStyle](#getsplitstyle)|현재 분할 단추 컨트롤을 정의하는 분할 단추 스타일을 검색합니다.|
|[C버튼::겟스테이트](#getstate)|단추 컨트롤의 확인 상태, 강조 표시 상태 및 초점 상태를 검색합니다.|
|[CButton::GetTextMargin](#gettextmargin)|단추 컨트롤의 텍스트 여백을 검색합니다.|
|[CButton::SetBitmap](#setbitmap)|단추에 표시할 비트맵을 지정합니다.|
|[C버튼::설정버튼 스타일](#setbuttonstyle)|단추의 스타일을 변경합니다.|
|[C버튼::세트체크](#setcheck)|단추 컨트롤의 확인 상태를 설정합니다.|
|[C버튼::세트커서](#setcursor)|단추에 표시할 커서 이미지를 지정합니다.|
|[C버튼::세트드롭다운상태](#setdropdownstate)|현재 분할 단추 컨트롤의 드롭다운 상태를 설정합니다.|
|[C버튼::세티콘](#seticon)|단추에 표시할 아이콘을 지정합니다.|
|[C버튼::세트이미지리스트](#setimagelist)|단추 컨트롤의 이미지 목록을 설정합니다.|
|[C버튼::세트노트](#setnote)|현재 명령 링크 컨트롤에 메모를 설정합니다.|
|[C버튼::세트스플릿글리프](#setsplitglyph)|지정된 글리프를 현재 분할 단추 컨트롤과 연결합니다.|
|[C버튼::세트스플릿이미지리스트](#setsplitimagelist)|이미지 목록을 현재 분할 단추 컨트롤과 연결합니다.|
|[C버튼::세트스플릿정보](#setsplitinfo)|현재 분할 단추 컨트롤을 정의하는 정보를 지정합니다.|
|[C버튼::세트스플릿크기](#setsplitsize)|현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 설정합니다.|
|[C버튼::세트스플릿스타일](#setsplitstyle)|현재 분할 단추 컨트롤의 스타일을 설정합니다.|
|[CButton::설정 상태](#setstate)|단추 컨트롤의 강조 표시 상태를 설정합니다.|
|[C버튼::세트텍스트마진](#settextmargin)|단추 컨트롤의 텍스트 여백을 설정합니다.|

## <a name="remarks"></a>설명

단추 컨트롤은 클릭할 수 있는 작은 직사각형 자식 창입니다. 단추는 단독으로 또는 그룹으로 사용할 수 있으며 레이블을 지정하거나 텍스트 없이 표시할 수 있습니다. 단추는 일반적으로 사용자가 단추를 클릭할 때 모양을 변경합니다.

일반적인 버튼은 확인란, 라디오 버튼 및 푸시 버튼입니다. 개체는 `CButton` 멤버 [만들기](#create) 함수에 의해 초기화될 때 지정된 [단추 스타일에](../../mfc/reference/styles-used-by-mfc.md#button-styles) 따라 이러한 개체가 될 수 있습니다.

또한 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) 클래스에서 `CButton` 파생 된 텍스트 대신 비트 맵 이미지로 레이블이 지정 된 단추 컨트롤의 생성을 지원 합니다. A는 `CBitmapButton` 단추의 위, 아래, 포커스 및 비활성화된 상태에 대해 별도의 비트맵을 가질 수 있습니다.

대화 상자 템플릿에서 또는 코드에서 직접 단추 컨트롤을 만들 수 있습니다. 두 경우 모두 먼저 생성자 `CButton` 호출하여 개체를 생성합니다. `CButton` 그런 다음 `Create` 멤버 함수를 호출하여 Windows 단추 `CButton` 컨트롤을 만들고 개체에 연결합니다.

구성은 에서 파생된 클래스의 한 단계 `CButton`프로세스일 수 있습니다. 파생 클래스에 대한 생성자 및 `Create` 생성자 내에서 호출합니다.

단추 컨트롤에서 부모(일반적으로 [CDialog에서](../../mfc/reference/cdialog-class.md)파생된 클래스)로 보낸 Windows 알림 메시지를 처리하려면 각 메시지에 대한 메시지 맵 항목 및 메시지 처리기 멤버 함수를 부모 클래스에 추가합니다.

각 메시지 맵 항목은 다음과 같은 형식을 취합니다.

**ON\_**_알림_ _(ID,_ _멤버Fxn)_ **)** **(**

*ID는* 알림을 보내는 컨트롤의 자식 창 ID를 지정하고 *memberFxn은* 알림을 처리하기 위해 작성한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

`afx_msg void memberFxn();`

잠재적인 메시지 맵 항목은 다음과 같습니다.

|맵 항목|부모에게 전송될 때...|
|---------------|----------------------------|
|ON_BN_CLICKED|사용자가 단추를 클릭합니다.|
|ON_BN_DOUBLECLICKED|사용자가 단추를 두 번 클릭합니다.|

대화 상자 `CButton` 리소스에서 개체를 만들면 `CButton` 사용자가 대화 상자를 닫을 때 개체가 자동으로 소멸됩니다.

창 내에서 `CButton` 객체를 만드는 경우 객체를 삭제해야 할 수 있습니다. 새 함수를 `CButton` 사용하여 힙에 개체를 **new** 만드는 경우 사용자가 Windows 단추 컨트롤을 닫을 때 개체에서 **삭제를** 호출하여 개체를 삭제해야 합니다. 스택에서 개체를 `CButton` 만들거나 상위 대화 상자 개체에 포함된 경우 자동으로 소멸됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cbuttoncbutton"></a><a name="cbutton"></a>C 버튼::CButton

`CButton` 개체를 생성합니다.

```
CButton();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

## <a name="cbuttoncreate"></a><a name="create"></a>CButton::만들기

Windows 단추 컨트롤을 만들고 개체에 `CButton` 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszCaption*<br/>
단추 컨트롤의 텍스트를 지정합니다.

*dwStyle*<br/>
단추 컨트롤의 스타일을 지정합니다. [단추 스타일에](../../mfc/reference/styles-used-by-mfc.md#button-styles) 임의의 조합을 적용합니다.

*rect*<br/>
단추 컨트롤의 크기와 위치를 지정합니다. 개체 또는 `CRect` `RECT` 구조체일 수 있습니다.

*pParentWnd*<br/>
단추 컨트롤의 부모 창(일반적으로)을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
단추 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CButton` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 합니다 . `CButton`

WS_VISIBLE 스타일이 지정되면 Windows는 단추를 활성화하고 표시하는 데 필요한 모든 메시지를 단추 컨트롤로 보냅니다.

단추 컨트롤에 다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_GROUP 컨트롤그룹

- WS_TABSTOP 탭 순서에 단추를 포함하려면

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

## <a name="cbuttondrawitem"></a><a name="drawitem"></a>C버튼::D로상품

소유자가 그린 단추의 시각적 측면이 변경된 경우 프레임워크에서 호출합니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 긴 포인터입니다. 구조에는 그릴 항목과 필요한 도면 유형에 대한 정보가 포함되어 있습니다.

### <a name="remarks"></a>설명

소유자가 그린 버튼에는 BS_OWNERDRAW 스타일 세트가 있습니다. 소유자가 그린 `CButton` 객체에 대한 도면을 구현하려면 이 멤버 함수를 재정의합니다. 응용 프로그램은 멤버 함수가 종료되기 전에 *lpDrawItemStruct에* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

또한 [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) 스타일 값을 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

## <a name="cbuttongetbitmap"></a><a name="getbitmap"></a>C버튼::겟비트맵

이 멤버 함수를 호출하여 단추와 연결된 [SetBitmap으로](#setbitmap)이전에 설정한 비트맵의 핸들을 가져옵니다.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Return Value

비트맵에 대한 핸들입니다. 비트맵이 이전에 지정되지 않은 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>C버튼::겟버튼 스타일

단추 제어 스타일에 대한 정보를 검색합니다.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Return Value

이 `CButton` 개체의 단추 스타일을 반환합니다. 이 함수는 다른 창 스타일이 아닌 [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) 스타일 값만 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttongetcheck"></a><a name="getcheck"></a>C버튼::GetCheck

라디오 단추 또는 확인란의 확인 상태를 검색합니다.

```
int GetCheck() const;
```

### <a name="return-value"></a>Return Value

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON 또는 BS_3STATE 스타일로 만든 단추 컨트롤의 반환 값은 다음 값 중 하나입니다.

|값|의미|
|-----------|-------------|
|BST_UNCHECKED|단추 상태가 선택되지 않았습니다.|
|BST_CHECKED|단추 상태가 선택됩니다.|
|BST_INDETERMINATE|단추 상태는 확정되지 않습니다(단추에 BS_3STATE 또는 BS_AUTO3STATE 스타일이 있는 경우에만 적용됩니다).|

단추에 다른 스타일이 있는 경우 반환 값은 BST_UNCHECKED.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttongetcursor"></a><a name="getcursor"></a>C버튼::겟커서

이 멤버 함수를 호출하여 단추와 연결된 [SetCursor로](#setcursor)이전에 설정한 커서의 핸들을 가져옵니다.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Return Value

커서 이미지에 대한 핸들입니다. 커서가 이전에 지정되지 않은 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttongeticon"></a><a name="geticon"></a>C버튼::게아이콘

이 멤버 함수를 호출하여 단추와 연결된 [SetIcon으로](#seticon)이전에 설정한 아이콘의 핸들을 가져옵니다.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Return Value

아이콘에 대한 핸들입니다. 아이콘이 이전에 지정되지 않은 경우 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttongetidealsize"></a><a name="getidealsize"></a>버튼::이상적 크기

단추 컨트롤에 이상적인 크기를 검색합니다.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>매개 변수

*크기 조정*<br/>
단추의 현재 크기에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK의 [단추](/windows/win32/controls/buttons) 섹션에 설명된 대로 BCM_GETIDEALSIZE 메시지의 기능을 에뮬레이트합니다.

## <a name="cbuttongetimagelist"></a><a name="getimagelist"></a>C버튼::이미지리스트

단추 컨트롤에서 이미지 목록을 얻으려면이 메서드를 호출 합니다.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>매개 변수

*pbuttonImagelist*<br/>
개체의 이미지 목록에 대한 `CButton` 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK의 [단추](/windows/win32/controls/buttons) 섹션에 설명된 대로 BCM_GETIMAGELIST 메시지의 기능을 에뮬레이트합니다.

## <a name="cbuttongetnote"></a><a name="getnote"></a>C버튼::겟노트

현재 명령 링크 컨트롤과 연결된 메모 텍스트를 검색합니다.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpszNote*|【아웃】 호출자는 할당 및 할당 지정을 담당하는 버퍼에 대한 포인터입니다. 반환 값이 TRUE이면 버퍼에는 현재 명령 링크 컨트롤과 연결된 메모 텍스트가 포함됩니다. 그렇지 않으면 버퍼가 변경되지 않습니다.|
|*cchNote*|【인, 아웃】 서명되지 않은 정수 변수에 대한 포인터입니다.<br /><br /> 이 메서드가 호출될 때 변수에는 *lpszNote* 매개 변수가 지정한 버퍼의 크기가 포함됩니다.<br /><br /> 이 메서드가 반환 하는 경우 반환 값이 TRUE 경우 변수는 현재 명령 링크 컨트롤과 관련 된 메모의 크기를 포함 합니다. 반환 값이 FALSE인 경우 변수에는 메모를 포함하는 데 필요한 버퍼 크기가 포함됩니다.|

### <a name="return-value"></a>Return Value

첫 번째 오버로드에서 현재 명령 링크 컨트롤과 연결된 메모 텍스트를 포함하는 [CString](../../atl-mfc-shared/using-cstring.md) 개체입니다.

또는

두 번째 오버로드에서 이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_COMMANDLINK BS_DEFCOMMANDLINK 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [BCM_GETNOTE](/windows/win32/Controls/bcm-getnote) 메시지를 보냅니다.

## <a name="cbuttongetnotelength"></a><a name="getnotelength"></a>C버튼::겟노트길이

현재 명령 링크 컨트롤에 대 한 메모 텍스트의 길이 검색합니다.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Return Value

현재 명령 링크 컨트롤에 대한 16비트 유니코드 문자의 메모 텍스트 길이입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_COMMANDLINK BS_DEFCOMMANDLINK 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [BCM_GETNOTELENGTH](/windows/win32/Controls/bcm-getnotelength) 메시지를 보냅니다.

## <a name="cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>C버튼::겟스플릿글리프

현재 분할 단추 컨트롤과 연결된 글리프를 검색합니다.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Return Value

현재 분할 단추 컨트롤과 연결된 문자 입니다.

### <a name="remarks"></a>설명

글리프는 특정 글꼴에 있는 문자를 물리적으로 표현하는 것입니다. 예를 들어 분할 단추 컨트롤은 유니코드 확인 표시 문자(U+2713)의 문자로 장식될 수 있습니다.

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 `mask` [BCSIF_GLYPH](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 플래그를 사용 하 고 windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에 해당 구조를 보냅니다 BUTTON_SPLITINFO 구조의 멤버를 초기화 합니다. 메시지 함수가 반환되면 이 메서드는 구조체의 `himlGlyph` 멤버에서 문자 메시지를 검색합니다.

## <a name="cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>C버튼::겟스플릿이미지리스트

현재 분할 단추 컨트롤에 대한 [이미지 목록을](../../mfc/reference/cimagelist-class.md) 검색합니다.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Return Value

[CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 BCSIF_IMAGE `mask` 플래그를 사용 하 고 windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에 해당 구조를 보냅니다 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 구조의 멤버를 초기화 합니다. 메시지 함수가 반환되면 이 메서드는 구조체의 `himlGlyph` 멤버에서 이미지 목록을 검색합니다.

## <a name="cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>C버튼::겟스플릿정보

Windows에서 현재 분할 단추 컨트롤을 그리는 방법을 결정하는 매개 변수를 검색합니다.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pInfo*|【아웃】 현재 분할 단추 컨트롤에 대한 정보를 수신하는 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 구조에 대한 포인터입니다. 호출자는 구조를 할당할 책임이 있습니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지를 보냅니다.

## <a name="cbuttongetsplitsize"></a><a name="getsplitsize"></a>C버튼::겟스플릿사이즈

현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 검색합니다.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pSize*|【아웃】 사각형에 대한 설명을 받는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

분할 단추 컨트롤이 확장되면 목록 컨트롤 또는 호출기 컨트롤과 같은 드롭다운 구성 요소를 표시할 수 있습니다. 이 메서드는 드롭다운 구성 요소를 포함 하는 경계 사각형을 검색합니다.

이 메서드는 `mask` [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 구조체의 멤버를 BCSIF_SIZE 플래그로 초기화한 다음 Windows SDK에 설명된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에서 해당 구조를 보냅니다. 메시지 함수가 반환되면 이 메서드는 구조체의 멤버에서 경계 사각형을 `size` 검색합니다.

## <a name="cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>C버튼::겟스플리트스타일

현재 분할 단추 컨트롤을 정의하는 분할 단추 스타일을 검색합니다.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Return Value

분할 단추 스타일의 비트 조합입니다. 자세한 내용은 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) `uSplitStyle` 구조의 멤버를 참조하십시오.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

분할 단추 스타일은 Windows에서 분할 단추 아이콘을 그리는 정렬, 종횡비 및 그래픽 형식을 지정합니다.

이 메서드는 BCSIF_STYLE `mask` 플래그를 사용 하 고 windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에 해당 구조를 보냅니다 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 구조의 멤버를 초기화 합니다. 메시지 함수가 반환되면 이 메서드는 구조체의 `uSplitStyle` 멤버에서 분할 단추 스타일을 검색합니다.

## <a name="cbuttongetstate"></a><a name="getstate"></a>C버튼::겟스테이트

단추 컨트롤의 상태를 검색합니다.

```
UINT GetState() const;
```

### <a name="return-value"></a>Return Value

단추 컨트롤의 현재 상태를 나타내는 값의 조합을 포함하는 비트 필드입니다. 다음 표에는 가능한 값이 나열되어 있습니다.

|단추 상태|값|Description|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|초기 상태입니다.|
|BST_CHECKED|0x0001|단추 컨트롤이 선택됩니다.|
|BST_INDETERMINATE|0x0002|상태는 확정되지 않습니다(단추 컨트롤에 세 가지 상태가 있는 경우에만 가능).|
|BST_PUSHED|0x0004|버튼 컨트롤을 누른 다.|
|BST_FOCUS|0x0008|버튼 컨트롤에 포커스가 있습니다.|

### <a name="remarks"></a>설명

BS_3STATE 또는 BS_AUTO3STATE 단추 스타일이 있는 단추 컨트롤은 확정되지 않은 상태라는 세 번째 상태가 있는 확인란을 만듭니다. 확정되지 않은 상태는 확인란이 선택되거나 선택취소되지 않음을 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttongettextmargin"></a><a name="gettextmargin"></a>C버튼::GetText마진

개체의 텍스트 여백을 얻으려면이 `CButton` 메서드를 호출 합니다.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>매개 변수

*pmargin*<br/>
개체의 텍스트 여백에 `CButton` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

텍스트 여백을 반환합니다.

### <a name="remarks"></a>설명

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK의 [단추](/windows/win32/controls/buttons) 섹션에 설명된 대로 BCM_GETTEXTMARGIN 메시지의 기능을 에뮬레이트합니다.

## <a name="cbuttonsetbitmap"></a><a name="setbitmap"></a>C버튼::세트비트맵

이 멤버 함수를 호출하여 새 비트맵을 단추와 연결합니다.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>매개 변수

*hBitmap*<br/>
비트맵의 핸들입니다.

### <a name="return-value"></a>Return Value

단추와 이전에 연결된 비트맵의 핸들입니다.

### <a name="remarks"></a>설명

비트맵은 기본적으로 중앙에 있는 단추의 얼굴에 자동으로 배치됩니다. 비트맵이 단추에 대해 너무 크면 양쪽에서 잘립니다. 다음을 포함하여 다른 정렬 옵션을 선택할 수 있습니다.

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

단추 당 4 개의 비트맵을 사용하는 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)와 달리 `SetBitmap`에서는 단추 당 하나의 비트맵만 사용합니다. 단추를 누르면 비트맵이 아래와 오른쪽으로 이동하는 것처럼 보입니다.

비트맵을 완료하면 비트맵을 해제할 책임이 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>C버튼::설정버튼 스타일

단추의 스타일을 변경합니다.

```cpp
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
[단추 스타일을](../../mfc/reference/styles-used-by-mfc.md#button-styles)지정합니다.

*bRedraw*<br/>
단추를 다시 그릴지 여부를 지정합니다. 영하지 않은 값은 단추를 다시 그립니다. 0 값은 단추를 다시 그리지 않습니다. 버튼은 기본적으로 다시 그려집니다.

### <a name="remarks"></a>설명

멤버 `GetButtonStyle` 함수를 사용하여 단추 스타일을 검색합니다. 전체 단추 스타일의 낮은 순서 단어는 단추 특정 스타일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttonsetcheck"></a><a name="setcheck"></a>C버튼::세트체크

라디오 단추 또는 확인란의 확인 상태를 설정하거나 재설정합니다.

```cpp
void SetCheck(int nCheck);
```

### <a name="parameters"></a>매개 변수

*nCheck*<br/>
검사 상태를 지정합니다. 이 매개 변수는 다음 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|BST_UNCHECKED|단추 상태를 선택 취소로 설정합니다.|
|BST_CHECKED|단추 상태를 선택하도록 설정합니다.|
|BST_INDETERMINATE|단추 상태를 확정되지 않은 상태로 설정합니다. 이 값은 단추에 BS_3STATE 또는 BS_AUTO3STATE 스타일이 있는 경우에만 사용할 수 있습니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 푸시 버튼에 영향을 주지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttonsetcursor"></a><a name="setcursor"></a>C버튼::세트커서

이 멤버 함수를 호출하여 새 커서를 단추와 연결합니다.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>매개 변수

*hCursor*<br/>
커서의 핸들입니다.

### <a name="return-value"></a>Return Value

단추와 이전에 연결된 커서의 핸들입니다.

### <a name="remarks"></a>설명

커서는 기본적으로 중앙에 있는 단추의 면에 자동으로 배치됩니다. 커서가 단추에 너무 크면 양쪽에서 잘립니다. 다음을 포함하여 다른 정렬 옵션을 선택할 수 있습니다.

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

단추 당 4 개의 비트맵을 사용하는 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)와 달리 `SetCursor`는 단추 마다 하나의 커서만 사용합니다. 단추를 누르면 커서가 아래와 오른쪽으로 이동하는 것처럼 보입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>C버튼::세트드롭다운상태

현재 분할 단추 컨트롤의 드롭다운 상태를 설정합니다.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*fDropDown*|【인】 true는 BST_DROPDOWNPUSHED 상태를 설정합니다. 그렇지 않으면 false입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

분할 단추 컨트롤은 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 스타일로 되어 있으며 버튼과 오른쪽의 드롭다운 화살표로 구성됩니다. 자세한 내용은 [단추 스타일을](/windows/win32/Controls/button-styles)참조하십시오. 일반적으로 사용자가 드롭다운 화살표를 클릭할 때 드롭다운 상태가 설정됩니다. 이 메서드를 사용하여 컨트롤의 드롭다운 상태를 프로그래밍 방식으로 설정합니다. 드롭다운 화살표가 그려져 상태를 나타냅니다.

이 메서드는 Windows SDK에 설명 된 [BCM_SETDROPDOWNSTATE](/windows/win32/Controls/bcm-setdropdownstate) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 분할 단추 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_splitButton*정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>예제

다음 코드 예제는 분할 단추 컨트롤의 상태를 설정하여 드롭다운 화살표가 푸시되었음을 나타냅니다.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

## <a name="cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>C버튼::설정고도필요

현재 단추 컨트롤의 상태를 `elevation required`높은 보안 아이콘을 표시 하는 데 필요한 으로 설정 합니다.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*fElevationRequired*|【인】 TRUE 는 `elevation required` 상태를 설정합니다. 그렇지 않으면 false입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 또는 명령 링크 컨트롤에서 작업을 수행하기 위해 높은 보안 `elevation required` 권한이 필요한 경우 컨트롤을 상태로 설정합니다. 그런 다음 Windows는 컨트롤에 UAC(사용자 계정 컨트롤) 쉴드 아이콘을 표시합니다. 자세한 내용은 [MSDN의](https://go.microsoft.com/fwlink/p/?linkid=18507)"사용자 계정 제어"를 참조하십시오.

이 메서드는 Windows SDK에 설명 된 [BCM_SETSHIELD](/windows/win32/Controls/bcm-setshield) 메시지를 보냅니다.

## <a name="cbuttonseticon"></a><a name="seticon"></a>C버튼::세티콘

이 멤버 함수를 호출하여 새 아이콘을 단추와 연결합니다.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
아이콘의 핸들입니다.

### <a name="return-value"></a>Return Value

단추와 이전에 연결된 아이콘의 핸들입니다.

### <a name="remarks"></a>설명

아이콘은 기본적으로 중앙에 있는 단추의 얼굴에 자동으로 배치됩니다. 아이콘이 단추에 대해 너무 크면 양쪽에서 잘립니다. 다음을 포함하여 다른 정렬 옵션을 선택할 수 있습니다.

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

단추 당 4 개의 비트맵을 사용하는 [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)와 달리 `SetIcon`에서는 단추 당 하나의 아이콘만 사용합니다. 버튼을 누르면 아이콘이 아래와 오른쪽으로 이동하는 것처럼 보입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttonsetimagelist"></a><a name="setimagelist"></a>C버튼::세트이미지리스트

이 메서드를 호출하여 개체의 `CButton` 이미지 목록을 설정합니다.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>매개 변수

*pbuttonImagelist*<br/>
새 이미지 목록에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK의 [단추](/windows/win32/controls/buttons) 섹션에 설명된 대로 BCM_SETIMAGELIST 메시지의 기능을 에뮬레이트합니다.

## <a name="cbuttonsetnote"></a><a name="setnote"></a>C버튼::세트노트

현재 명령 링크 컨트롤에 대한 메모 텍스트를 설정합니다.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpszNote*|【인】 명령 링크 컨트롤의 메모 텍스트로 설정된 유니코드 문자열에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_COMMANDLINK BS_DEFCOMMANDLINK 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [BCM_SETNOTE](/windows/win32/Controls/bcm-setnote) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 명령 링크 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_cmdLink*정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>예제

다음 코드 예제는 명령 링크 컨트롤에 대한 메모 텍스트를 설정합니다.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

## <a name="cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>C버튼::세트스플릿글리프

지정된 글리프를 현재 분할 단추 컨트롤과 연결합니다.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*chGlyph*|【인】 분할 단추 드롭다운 화살표로 사용할 문자를 지정하는 문자입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

글리프는 특정 글꼴에 있는 문자를 물리적으로 표현하는 것입니다. *chGlyph* 매개 변수는 글리프로 사용되지 않고 대신 시스템 정의 글리프 집합에서 글리프를 선택하는 데 사용됩니다. 기본 드롭다운 화살표 문자 모양은 문자 '6'으로 지정되며 유니코드 문자인 BLACK DOWN-POINTING 삼각형(U+25BC)과 유사합니다.

이 `mask` 메서드는 [BUTTON_SPLITINFO BCSIF_GLYPH](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 플래그와 `himlGlyph` *chGlyph* 매개 변수를 사용 하 고 해당 구조를 Windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에서 해당 구조를 보냅니다.

## <a name="cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>C버튼::세트스플릿이미지리스트

이미지 [목록을](../../mfc/reference/cimagelist-class.md) 현재 분할 단추 컨트롤과 연결합니다.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pSplitImageList*|【인】 현재 분할 단추 컨트롤에 할당할 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 [BCSIF_IMAGE](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 플래그와 BCSIF_IMAGE `himlGlyph` 멤버를 사용 하 고 *pSplitImageList* 매개 변수를 사용 하 고 Windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에 해당 구조를 보냅니다 BUTTON_SPLITINFO 구조의 `mask` 멤버를 초기화 합니다.

## <a name="cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>C버튼::세트스플릿정보

Windows에서 현재 분할 단추 컨트롤을 그리는 방법을 결정하는 매개 변수를 지정합니다.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pInfo*|【인】 현재 분할 단추 컨트롤을 정의하는 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

이 메서드는 Windows SDK에 설명 된 [BCM_SETSPLITINFO](/windows/win32/Controls/bcm-setsplitinfo) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 분할 `m_splitButton`단추 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수를 정의합니다.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>예제

다음 코드 예제는 분할 단추 드롭다운 화살표에 사용되는 문자 를 변경합니다. 이 예제는 기본 하향-가리키는 삼각형 글리프에 대해 위쪽 을 가리키는 삼각형 글리프를 대체합니다. 표시되는 문자 모양은 구조의 `himlGlyph` 멤버에서 지정한 문자에 `BUTTON_SPLITINFO` 따라 다릅니다. 아래쪽 을 가리키는 삼각형 문자는 문자 '6'으로 지정되고 위쪽 을 가리키는 삼각형 문자는 문자 '5'로 지정됩니다. 비교를 위해 편의 [방법, CButton::SetSplitGlyph](#setsplitglyph)를 참조하십시오.

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

## <a name="cbuttonsetsplitsize"></a><a name="setsplitsize"></a>C버튼::세트스플릿크기

현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 설정합니다.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pSize*|【인】 경계 사각형을 설명하는 [SIZE](/windows/win32/api/windef/ns-windef-size) 구조에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

분할 단추 컨트롤이 확장되면 목록 컨트롤 또는 호출기 컨트롤과 같은 드롭다운 구성 요소를 표시할 수 있습니다. 이 메서드는 드롭다운 구성 요소를 포함하는 경계 사각형의 크기를 지정합니다.

이 메서드는 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) `size` 구조체의 `mask` 멤버를 BCSIF_SIZE 플래그와 *pSize* 매개 변수를 사용 하 고 Windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에서 해당 구조를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 분할 `m_splitButton`단추 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수를 정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>예제

다음 코드 예제는 분할 단추 드롭다운 화살표의 크기를 두 배로 늘렸습니다.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

## <a name="cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>C버튼::세트스플릿스타일

현재 분할 단추 컨트롤의 스타일을 설정합니다.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*uSplitStyle*|【인】 분할 단추 스타일의 비트 조합입니다. 자세한 내용은 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) `uSplitStyle` 구조의 멤버를 참조하십시오.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

단추 스타일이 BS_SPLITBUTTON 또는 BS_DEFSPLITBUTTON 컨트롤에서만 이 메서드를 사용합니다.

분할 단추 스타일은 Windows에서 분할 단추 아이콘을 그리는 정렬, 종횡비 및 그래픽 형식을 지정합니다. 자세한 내용은 [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) `uSplitStyle` 구조의 멤버를 참조하십시오.

이 메서드는 [BCSIF_STYLE](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) 플래그와 `uSplitStyle` *uSplitStyle* 매개 변수를 사용 하 고 멤버를 BUTTON_SPLITINFO 구조체의 `mask` 멤버를 초기화 하 고 Windows SDK에 설명 된 [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) 메시지에 해당 구조를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 분할 `m_splitButton`단추 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수를 정의합니다.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>예제

다음 코드 예제는 분할 단추 드롭다운 화살표의 스타일을 설정합니다. BCSS_ALIGNLEFT 스타일은 단추의 왼쪽에 화살표를 표시하고 BCSS_STRETCH 스타일은 단추 크기를 조정할 때 드롭다운 화살표의 비율을 유지합니다.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

## <a name="cbuttonsetstate"></a><a name="setstate"></a>CButton::설정 상태

단추 컨트롤이 강조 표시될지 여부를 설정합니다.

```cpp
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
단추를 강조 표시할지 여부를 지정합니다. 영하지 않은 값은 단추를 강조 표시됩니다. 0 값은 강조 표시를 제거합니다.

### <a name="remarks"></a>설명

강조 표시는 단추 컨트롤의 외부에 영향을 줍니다. 라디오 단추 또는 확인란의 확인 상태에는 영향을 주지 않습니다.

사용자가 왼쪽 마우스 버튼을 클릭하고 누를 때 단추 컨트롤이 자동으로 강조 표시됩니다. 사용자가 마우스 단추를 해제하면 강조 표시가 제거됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttonsettextmargin"></a><a name="settextmargin"></a>C버튼::세트텍스트마진

이 메서드를 호출하여 개체의 `CButton` 텍스트 여백을 설정합니다.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>매개 변수

*pmargin*<br/>
새 텍스트 여백에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK의 [단추](/windows/win32/controls/buttons) 섹션에 설명된 대로 BCM_SETTEXTMARGIN 메시지의 기능을 에뮬레이트합니다.

## <a name="see-also"></a>참조

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[C스크롤바 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[정적 클래스](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton 클래스](../../mfc/reference/cbitmapbutton-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
