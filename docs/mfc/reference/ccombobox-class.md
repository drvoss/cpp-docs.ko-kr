---
title: CComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
ms.openlocfilehash: dc803fb4ce137b256f4197afaec7bc3327e1e85a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754839"
---
# <a name="ccombobox-class"></a>CComboBox 클래스

Windows 콤보 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CComboBox : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComboBox::CComboBox](#ccombobox)|`CComboBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComboBox::AddString](#addstring)|콤보 상자의 목록 상자의 목록 상자 또는 CBS_SORT 스타일이 있는 목록 상자의 정렬된 위치에 문자열을 추가합니다.|
|[CComboBox::지우기](#clear)|편집 컨트롤에서 현재 선택 영역(있는 경우)을 삭제(지우기)합니다.|
|[CComboBox::비교항목](#compareitem)|정렬된 소유자가 그린 콤보 상자에서 새 목록 항목의 상대적 위치를 결정하기 위해 프레임워크에서 호출됩니다.|
|[CComboBox::Copy](#copy)|현재 선택 영역(있는 경우)을 클립보드에 CF_TEXT 형식으로 복사합니다.|
|[CComboBox::Create](#create)|콤보 상자를 만들고 오브젝트에 `CComboBox` 연결합니다.|
|[CComboBox::Cut](#cut)|편집 컨트롤에서 현재 선택 영역(있는 경우)을 삭제(잘라내며)를 삭제하고 삭제된 텍스트를 CF_TEXT 형식으로 클립보드에 복사합니다.|
|[CComboBox::DeleteItem](#deleteitem)|소유자가 그린 콤보 상자에서 목록 항목이 삭제될 때 프레임워크에서 호출됩니다.|
|[CComboBox::DeleteString](#deletestring)|콤보 상자의 목록 상자에서 문자열을 삭제합니다.|
|[CComboBox::Dir](#dir)|콤보 상자의 목록 상자에 파일 이름 목록을 추가합니다.|
|[CComboBox::D로아이템](#drawitem)|소유자가 그린 콤보 상자의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.|
|[CComboBox::찾기 스트링](#findstring)|콤보 상자의 목록 상자에 지정된 접두사가 포함된 첫 번째 문자열을 찾습니다.|
|[CComboBox::찾기스트링Exact](#findstringexact)|지정된 문자열과 일치하는 첫 번째 목록 상자 문자열(콤보 상자)을 찾습니다.|
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|개체에 대한 `CComboBox` 정보를 검색합니다.|
|[CComboBox::GetCount](#getcount)|콤보 상자의 목록 상자에 있는 항목 수를 검색합니다.|
|[CComboBox::GetCueBanner](#getcuebanner)|콤보 상자 컨트롤에 대해 표시되는 큐 텍스트를 가져옵니다.|
|[CComboBox::GetCursel](#getcursel)|콤보 상자의 목록 상자에서 현재 선택된 항목의 인덱스(있는 경우)를 검색합니다.|
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|드롭다운 콤보 상자의 표시되는(드롭다운) 목록 상자의 화면 좌표를 검색합니다.|
|[CComboBox::GetDroppedState](#getdroppedstate)|드롭다운 콤보 상자의 목록 상자가 표시되는지 여부를 결정합니다(삭제).|
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|콤보 상자의 드롭다운 목록 상자 부분에 대해 허용되는 최소 너비를 검색합니다.|
|[CComboBox::GetEditsel](#geteditsel)|콤보 상자의 편집 컨트롤에서 현재 선택 영역의 시작 및 종료 문자 위치를 가져옵니다.|
|[CComboBox::GetExtendedUI](#getextendedui)|콤보 상자에 기본 사용자 인터페이스 또는 확장된 사용자 인터페이스가 있는지 여부를 결정합니다.|
|[CComboBox::Get수평범위](#gethorizontalextent)|콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 있는 픽셀의 너비를 반환합니다.|
|[CComboBox::GetItemData](#getitemdata)|지정된 콤보 상자 항목과 연결된 응용 프로그램에서 제공한 32비트 값을 검색합니다.|
|[CComboBox::겟아이템데이터Ptr](#getitemdataptr)|지정된 콤보 상자 항목과 연결된 응용 프로그램에서 제공한 32비트 포인터를 검색합니다.|
|[CComboBox::GetItemHeight](#getitemheight)|콤보 상자에서 목록 항목의 높이를 검색합니다.|
|[CComboBox::GetLBText](#getlbtext)|콤보 상자의 목록 상자에서 문자열을 가져옵니다.|
|[CComboBox:::GetLBTextLen](#getlbtextlen)|콤보 상자의 목록 상자에 문자열의 길이를 가져옵니다.|
|[CComboBox::GetLocale](#getlocale)|콤보 상자에 대한 로캘 식별자를 검색합니다.|
|[CComboBox::GetMinVisible](#getminvisible)|현재 콤보 상자의 드롭다운 목록에서 표시되는 항목의 최소 수를 가져옵니다.|
|[CComboBox::GetTopIndex](#gettopindex)|콤보 상자의 목록 상자 부분에 있는 첫 번째 표시되는 항목의 인덱스를 반환합니다.|
|[CComboBox::InitStorage](#initstorage)|콤보 상자의 목록 상자 부분에 있는 항목 및 문자열에 대한 메모리 블록을 Preallocates합니다.|
|[CComboBox::InsertString](#insertstring)|콤보 상자의 목록 상자에 문자열을 삽입합니다.|
|[CComboBox::LimitText](#limittext)|사용자가 콤보 상자의 편집 컨트롤에 입력할 수 있는 텍스트의 길이를 제한합니다.|
|[CComboBox::MeasureItem](#measureitem)|소유자가 그린 콤보 상자를 만들 때 콤보 상자 차원을 결정하기 위해 프레임 워크에서 호출됩니다.|
|[CComboBox::P아스트](#paste)|현재 커서 위치에서 편집 컨트롤에 클립보드의 데이터를 삽입합니다. 클립보드에 CF_TEXT 형식의 데이터가 포함된 경우에만 데이터가 삽입됩니다.|
|[CComboBox::ResetContent](#resetcontent)|목록 상자에서 모든 항목을 제거하고 콤보 상자의 컨트롤을 편집합니다.|
|[CComboBox::SelectString](#selectstring)|콤보 상자의 목록 상자에서 문자열을 검색하고 문자열이 발견되면 목록 상자에서 문자열을 선택하고 문자열을 편집 컨트롤에 복사합니다.|
|[CComboBox::SetCueBanner](#setcuebanner)|콤보 상자 컨트롤에 대해 표시되는 큐 텍스트를 설정합니다.|
|[CComboBox::SetCurSel](#setcursel)|콤보 상자의 목록 상자에서 문자열을 선택합니다.|
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|콤보 상자의 드롭다운 목록 상자 부분에 대해 허용되는 최소 너비를 설정합니다.|
|[CComboBox::SetEditsel](#seteditsel)|콤보 상자의 편집 컨트롤에서 문자를 선택합니다.|
|[CComboBox::SetExtendedUI](#setextendedui)|CBS_DROPDOWN 또는 CBS_DROPDOWNLIST 스타일이 있는 콤보 상자에 대한 기본 사용자 인터페이스 또는 확장된 사용자 인터페이스를 선택합니다.|
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 있는 너비를 픽셀단위로 설정합니다.|
|[CComboBox::SetItemData](#setitemdata)|콤보 상자에서 지정된 항목과 연결된 32비트 값을 설정합니다.|
|[CComboBox::세트아이템데이터Ptr](#setitemdataptr)|콤보 상자에서 지정된 항목과 연결된 32비트 포인터를 설정합니다.|
|[CComboBox::SetItemHeight](#setitemheight)|콤보 상자의 목록 항목 높이 또는 콤보 상자의 편집 제어(또는 정적 텍스트) 부분의 높이를 설정합니다.|
|[CComboBox::SetLocale](#setlocale)|콤보 상자에 대한 로캘 식별자를 설정합니다.|
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|현재 콤보 상자의 드롭다운 목록에서 표시되는 항목의 최소 수를 설정합니다.|
|[CComboBox::셋탑인덱스](#settopindex)|콤보 상자의 목록 상자 부분을 지정한 인덱스가 맨 위에 있는 항목을 표시하도록 지시합니다.|
|[CComboBox::ShowDropDown](#showdropdown)|CBS_DROPDOWN 또는 CBS_DROPDOWNLIST 스타일이 있는 콤보 상자의 목록 상자를 표시하거나 숨깁니다.|

## <a name="remarks"></a>설명

콤보 상자는 정적 컨트롤 또는 편집 컨트롤과 결합된 목록 상자로 구성됩니다. 컨트롤의 목록 상자 부분은 항상 표시되거나 사용자가 컨트롤 옆에 있는 드롭다운 화살표를 선택할 때만 드롭다운할 수 있습니다.

목록 상자에서 현재 선택된 항목(있는 경우)이 정적 또는 편집 컨트롤에 표시됩니다. 또한 콤보 상자에 드롭다운 목록 스타일이 있는 경우 사용자는 목록의 항목 중 하나의 초기 문자를 입력할 수 있으며 목록 상자가 표시되는 경우 해당 초기 문자가 있는 다음 항목을 강조 표시합니다.

다음 표는 세 가지 콤보 상자 [스타일을](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)비교합니다.

|스타일|목록 상자가 표시되는 경우|정적 또는 편집 컨트롤|
|-----------|-------------------------------|-----------------------------|
|간단한|항상|편집|
|Drop-down|떨어졌을 때|편집|
|드롭다운 목록|떨어졌을 때|정적|

대화 상자 `CComboBox` 템플릿에서 또는 코드에서 직접 개체를 만들 수 있습니다. 두 경우 모두 먼저 생성자 `CComboBox` 호출하여 개체를 생성합니다. `CComboBox` 그런 다음 멤버 [만들기](#create) 함수를 호출하여 컨트롤을 만들고 개체에 `CComboBox` 연결합니다.

콤보 상자에서 부모(일반적으로 파생된 `CDialog`클래스)에 보낸 Windows 알림 메시지를 처리하려면 각 메시지에 대한 부모 클래스에 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가합니다.

각 메시지 맵 항목은 다음과 같은 형식을 취합니다.

**ON\_**_알림_ _(ID,_ _멤버Fxn)_ **)** **(**

여기서 `id` 알림을 보내는 콤보 박스 컨트롤의 자식 창 ID를 지정하고 `memberFxn` 알림을 처리하기 위해 작성한 부모 구성원 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

**afx_msg** `void` `memberFxn` **( );**

특정 알림이 전송되는 순서는 예측할 수 없습니다. 특히 CBN_SELCHANGE 알림은 CBN_CLOSEUP 통지 전후에 발생할 수 있습니다.

잠재적인 메시지 맵 항목은 다음과 같습니다.

- ON_CBN_CLOSEUP (윈도우 3.1 이상.) 콤보 상자의 목록 상자가 닫혔습니다. 이 알림 메시지는 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자에 대해 전송되지 않습니다.

- ON_CBN_DBLCLK 사용자는 콤보 상자의 목록 상자에서 문자열을 두 번 클릭합니다. 이 알림 메시지는 CBS_SIMPLE 스타일이 있는 콤보 상자에 대해서만 전송됩니다. [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자의 경우 한 번의 클릭으로 목록 상자를 숨기기 때문에 두 번 클릭이 발생할 수 없습니다.

- ON_CBN_DROPDOWN 콤보 상자의 목록 상자가 드롭다운하려고 합니다(표시). 이 알림 메시지는 CBS_DROPDOWN 또는 CBS_DROPDOWNLIST 스타일이 있는 콤보 상자에대해서만 발생할 수 있습니다.

- ON_CBN_EDITCHANGE 사용자가 콤보 상자의 편집 제어 부분에서 텍스트를 변경했을 수 있는 작업을 수행했습니다. CBN_EDITUPDATE 메시지와 달리 이 메시지는 Windows에서 화면을 업데이트한 후 전송됩니다. 콤보 상자에 CBS_DROPDOWNLIST 스타일이 있는 경우 전송되지 않습니다.

- ON_CBN_EDITUPDATE 콤보 상자의 편집 제어 부분이 변경된 텍스트를 표시하려고 합니다. 이 알림 메시지는 컨트롤이 텍스트의 서식을 지정한 후 텍스트를 표시하기 전에 전송됩니다. 콤보 상자에 CBS_DROPDOWNLIST 스타일이 있는 경우 전송되지 않습니다.

- ON_CBN_ERRSPACE 콤보 상자는 특정 요청을 충족하기에 충분한 메모리를 할당할 수 없습니다.

- ON_CBN_SELENDCANCEL (윈도우 3.1 이상.) 사용자의 선택을 취소해야 했음을 나타냅니다. 사용자가 항목을 클릭한 다음 다른 창 또는 컨트롤을 클릭하여 콤보 상자의 목록 상자를 숨깁니다. 이 알림 메시지는 사용자의 선택을 무시해야 함을 나타내기 위해 CBN_CLOSEUP 알림 메시지 앞에 전송됩니다. CBN_CLOSEUP 알림 메시지가 전송되지 않은 경우에도 CBN_SELENDCANCEL 또는 CBN_SELENDOK 알림 메시지가 전송됩니다(CBS_SIMPLE 스타일이 있는 콤보 상자의 경우와 같이).

- ON_CBN_SELENDOK 사용자가 항목을 선택한 다음 ENTER 키를 누르거나 DOWN ARROW 키를 클릭하여 콤보 상자의 목록 상자를 숨깁니다. 이 알림 메시지는 사용자의 선택이 유효한 것으로 간주되어야 함을 나타내기 위해 CBN_CLOSEUP 메시지 앞에 전송됩니다. CBN_CLOSEUP 알림 메시지가 전송되지 않은 경우에도 CBN_SELENDCANCEL 또는 CBN_SELENDOK 알림 메시지가 전송됩니다(CBS_SIMPLE 스타일이 있는 콤보 상자의 경우와 같이).

- ON_CBN_KILLFOCUS 콤보 상자가 입력 포커스를 잃고 있습니다.

- ON_CBN_SELCHANGE 사용자가 목록 상자를 클릭하거나 화살표 키를 사용하여 선택 항목을 변경한 결과로 콤보 상자의 목록 상자의 선택 영역이 변경됩니다. 이 메시지를 처리할 때 콤보 상자의 편집 컨트롤의 텍스트는 또는 `GetLBText` 다른 유사한 함수를 통해서만 검색할 수 있습니다. `GetWindowText` 사용할 수 없습니다.

- ON_CBN_SETFOCUS 콤보 상자는 입력 포커스를 수신합니다.

대화 상자 `CComboBox` 내에서(대화 상자 리소스를 통해) 개체를 `CComboBox` 만들면 사용자가 대화 상자를 닫을 때 개체가 자동으로 소멸됩니다.

다른 창 개체 `CComboBox` 내에 객체를 포함하면 객체를 삭제할 필요가 없습니다. 스택에서 객체를 `CComboBox` 만들면 자동으로 소멸됩니다. 새 함수를 `CComboBox` 사용하여 힙에 개체를 **new** 만드는 경우 Windows 콤보 상자가 소멸될 때 개체에서 **삭제를** 호출하여 개체를 삭제해야 합니다.

**참고 사항** WM_KEYDOWN 및 WM_CHAR 메시지를 처리하려면 콤보 상자의 편집 및 목록 상자 컨트롤을 하위 클래스로 분류하고, 클래스를 `CEdit` 파생시키고, `CListBox`해당 메시지에 대한 처리기를 파생된 클래스에 추가해야 합니다. 자세한 내용은 [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CComboBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="ccomboboxaddstring"></a><a name="addstring"></a>CComboBox::추가 스트링

콤보 상자의 목록 상자에 문자열을 추가합니다.

```
int AddString(LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*lpszString*<br/>
추가할 null 종료된 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

반환 값이 0보다 크거나 같으면 목록 상자의 문자열에 대한 0 기반 인덱스입니다. 오류가 발생하면 반환 값은 CB_ERR. 새 문자열을 저장할 공간이 부족하면 반환 값이 CB_ERRSPACE.

### <a name="remarks"></a>설명

목록 상자가 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일로 작성되지 않은 경우 문자열이 목록의 끝에 추가됩니다. 그렇지 않으면 문자열이 목록에 삽입되고 목록이 정렬됩니다.

> [!NOTE]
> 이 기능은 Windows `ComboBoxEx` 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 컨트롤을](/windows/win32/Controls/comboboxex-controls) 참조하십시오.

목록 내의 특정 위치에 문자열을 삽입하려면 [InsertString](#insertstring) 멤버 함수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]

## <a name="ccomboboxccombobox"></a><a name="ccombobox"></a>CComboBox::CComboBox

`CComboBox` 개체를 생성합니다.

```
CComboBox();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]

## <a name="ccomboboxclear"></a><a name="clear"></a>CComboBox::지우기

콤보 상자의 편집 컨트롤에서 현재 선택 영역(있는 경우)을 삭제(지우기)합니다.

```cpp
void Clear();
```

### <a name="remarks"></a>설명

현재 선택 영역을 삭제하고 삭제된 내용을 클립보드에 배치하려면 [멤버 잘라내기](#cut) 기능을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]

## <a name="ccomboboxcompareitem"></a><a name="compareitem"></a>CComboBox::비교항목

정렬된 소유자-그리기 콤보 상자의 목록 상자 부분에서 새 항목의 상대적 위치를 결정 하기 위해 프레임 워크에 의해 호출 됩니다.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpCompareItemStruct*<br/>
[비교항목truct](/windows/win32/api/winuser/ns-winuser-compareitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="return-value"></a>Return Value

`COMPAREITEMSTRUCT` 구조에 설명된 두 항목의 상대위치를 나타냅니다. 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|- 1|항목 1 항목 2 전에 정렬합니다.|
|0|항목 1과 항목 2는 동일하게 정렬됩니다.|
|1|항목 1 항목 2 후 정렬 합니다.|

에 대한 설명은 [CWnd::OnCompareItem을](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT`참조하십시오.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. LBS_SORT 스타일로 소유자-그리기 콤보 상자를 만드는 경우 목록 상자에 추가된 새 항목을 정렬하는 데 프레임워크를 지원하려면 이 멤버 함수를 재정의해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]

## <a name="ccomboboxcopy"></a><a name="copy"></a>CComboBox::복사

콤보 상자의 편집 컨트롤에서 현재 선택 영역(있는 경우)을 CF_TEXT 형식으로 클립보드에 복사합니다.

```cpp
void Copy();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]

## <a name="ccomboboxcreate"></a><a name="create"></a>CComboBox:만들기

콤보 상자를 만들고 오브젝트에 `CComboBox` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
콤보 상자의 스타일을 지정합니다. [콤보 박스 스타일의](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 조합을 상자에 적용합니다.

*rect*<br/>
콤보 상자의 위치와 크기를 가리킵니다. [RECT 구조](/windows/win32/api/windef/ns-windef-rect) 또는 개체일 `CRect` 수 있습니다.

*pParentWnd*<br/>
콤보 상자의 상위 창(일반적으로 a)을 `CDialog`지정합니다. NULL이 아니어야 합니다.

*nID*<br/>
콤보 상자의 컨트롤 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CComboBox` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 합니다 . `CComboBox`

실행되면 `Create` Windows는 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 메시지를 콤보 상자로 보냅니다.

이러한 메시지는 기본적으로 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 `CWnd` 함수에 의해 기본 클래스에서 처리됩니다. 기본 메시지 처리를 확장하려면 에서 `CComboBox`클래스를 파생 합니다 . 예를 `OnCreate`들어 새 클래스에 필요한 초기화를 수행하려면 을 재정의합니다.

콤보 상자 컨트롤에 다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 적용합니다. :

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_VSCROLL 콤보 상자의 목록 상자에 대한 세로 스크롤을 추가하려면

- WS_HSCROLL 콤보 상자의 목록 상자에 대한 가로 스크롤을 추가하려면

- WS_GROUP 컨트롤그룹

- WS_TABSTOP 탭 순서에 콤보 상자를 포함하려면

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]

## <a name="ccomboboxcut"></a><a name="cut"></a>CComboBox :: 컷

콤보 상자 편집 컨트롤에서 현재 선택 영역(있는 경우)을 삭제(잘라내며)하고 삭제된 텍스트를 CF_TEXT 형식으로 클립보드에 복사합니다.

```cpp
void Cut();
```

### <a name="remarks"></a>설명

삭제된 텍스트를 클립보드에 배치하지 않고 현재 선택 영역을 삭제하려면 [멤버 지우기](#clear) 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]

## <a name="ccomboboxdeleteitem"></a><a name="deleteitem"></a>CComboBox::DeleteItem

사용자가 소유자-draw `CComboBox` 개체에서 항목을 삭제하거나 콤보 상자를 삭제할 때 프레임워크에서 호출됩니다.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDeleteItemStruct*<br/>
삭제된 항목에 대한 정보가 포함된 Windows [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) 구조에 대한 긴 포인터입니다. 이 구조에 대한 설명은 [CWnd::OnDeleteItem을](../../mfc/reference/cwnd-class.md#ondeleteitem) 참조하십시오.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 필요에 따라 콤보 상자를 다시 그리려면 이 함수를 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]

## <a name="ccomboboxdeletestring"></a><a name="deletestring"></a>CComboBox::DeleteString

콤보 상자에서 위치 *nIndex에서* 항목을 삭제합니다.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
삭제할 문자열에 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

반환 값이 0보다 크거나 같으면 목록에 남아 있는 문자열의 개수입니다. *nIndex가* 목록의 항목 수보다 큰 인덱스를 지정하는 경우 반환 값은 CB_ERR.

### <a name="remarks"></a>설명

*이제 nIndex* 다음의 모든 항목이 한 위치로 이동합니다. 예를 들어 콤보 상자에 두 개의 항목이 포함된 경우 첫 번째 항목을 삭제하면 나머지 항목이 첫 번째 위치에 있게 됩니다. *nIndex*=0을 첫 번째 위치에 있는 항목에 대해

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]

## <a name="ccomboboxdir"></a><a name="dir"></a>CComboBox::Dir

콤보 상자의 목록 상자에 파일 이름 또는 드라이브 목록을 추가합니다.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>매개 변수

*Attr*<br/>
[CFile::GetStatus에](../../mfc/reference/cfile-class.md#getstatus) 설명된 **열거형** 값의 조합 또는 다음 값의 조합일 수 있습니다.

- DDL_READWRITE 파일을 읽거나 쓸 수 있습니다.

- DDL_READONLY 파일에서 읽을 수 있지만 쓸 수 없습니다.

- DDL_HIDDEN 파일이 숨겨져 있으며 디렉터리 목록에 나타나지 않습니다.

- DDL_SYSTEM 파일은 시스템 파일입니다.

- DDL_DIRECTORY *lpszWildCard에서* 지정한 이름은 디렉터리를 지정합니다.

- DDL_ARCHIVE 파일이 보관되었습니다.

- DDL_DRIVES *lpszWildCard에서*지정한 이름과 일치하는 모든 드라이브를 포함합니다.

- DDL_EXCLUSIVE 배타적 플래그입니다. 단독 플래그가 설정된 경우 지정된 형식의 파일만 나열됩니다. 그렇지 않으면 지정된 형식의 파일이 "일반" 파일 외에 나열됩니다.

*lpszWildCard*<br/>
파일 사양 문자열을 가리킵니다. 문자열에는 와일드카드(예: *. )가\*포함될 수 있습니다.

### <a name="return-value"></a>Return Value

반환 값이 0보다 크거나 같으면 목록에 추가된 마지막 파일 이름의 0기반 인덱스입니다. 오류가 발생하면 반환 값은 CB_ERR. 새 문자열을 저장할 공간이 부족하면 반환 값이 CB_ERRSPACE.

### <a name="remarks"></a>설명

이 기능은 Windows `ComboBoxEx` 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 컨트롤을](/windows/win32/Controls/comboboxex-controls) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]

## <a name="ccomboboxdrawitem"></a><a name="drawitem"></a>CComboBox::D로아이템

소유자-그리기 콤보 상자의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다. 이 구조에 대한 설명은 [CWnd::OnDrawItem을](../../mfc/reference/cwnd-class.md#ondrawitem) 참조하십시오.

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CComboBox` 이 멤버 함수가 종료되기 전에 응용 프로그램은 *lpDrawItemStruct에서*제공된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 인터페이스(GDI) 개체를 복원해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]

## <a name="ccomboboxfindstring"></a><a name="findstring"></a>CComboBox::찾기 스트링

콤보 상자의 목록 상자에 지정된 접두사가 포함된 첫 번째 문자열을 찾지만 선택하지 않습니다.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszString) const;
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞에 항목의 0기반 인덱스를 포함합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nStartAfter에*의해 지정된 항목으로 다시 계속됩니다. -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszString*<br/>
검색할 접두사가 포함된 null 종료 된 문자열을 가리킵니다. 검색은 대/소문자에 독립적이므로 이 문자열에는 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

반환 값이 0보다 크거나 같으면 일치하는 항목의 0기반 인덱스입니다. 검색에 실패한 경우 CB_ERR.

### <a name="remarks"></a>설명

이 기능은 Windows `ComboBoxEx` 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 컨트롤을](/windows/win32/Controls/comboboxex-controls) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]

## <a name="ccomboboxfindstringexact"></a><a name="findstringexact"></a>CComboBox::찾기스트링Exact

멤버 `FindStringExact` 함수를 호출하여 *lpszFind*에 지정된 문자열과 일치하는 첫 번째 목록 상자 문자열(콤보 상자)을 찾습니다.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>매개 변수

*nIndexStart*<br/>
검색할 첫 번째 항목 전에 항목의 0기반 인덱스를 지정합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nIndexStart에서*지정한 항목으로 다시 계속됩니다. *nIndexStart가* -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszFind*<br/>
검색할 null 종료된 문자열을 가리킵니다. 이 문자열에는 확장을 포함하여 전체 파일 이름이 포함될 수 있습니다. 검색은 대/소문자를 구분하지 않으므로 이 문자열에는 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

일치하는 항목의 0기준 인덱스 또는 검색에 실패한 경우 CB_ERR.

### <a name="remarks"></a>설명

콤보 상자가 소유자-그리기 스타일로 만들어졌지만 [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 `FindStringExact` 없는 경우 *lpszFind*의 값과 doubleword 값을 일치시키려고 시도합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]

## <a name="ccomboboxgetcomboboxinfo"></a><a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo

개체에 대한 `CComboBox` 정보를 검색합니다.

```
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;
```

### <a name="parameters"></a>매개 변수

*pcbi*<br/>
[콤보박스INFO](/windows/win32/api/winuser/ns-winuser-comboboxinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CB_GETCOMBOBOXINFO](/windows/win32/Controls/cb-getcomboboxinfo) 메시지의 기능을 에뮬레이트합니다.

## <a name="ccomboboxgetcount"></a><a name="getcount"></a>CComboBox::GetCount

이 멤버 함수를 호출하여 콤보 상자의 목록 상자 부분에 있는 항목 수를 검색합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

항목의 수입니다. 반환된 개수는 마지막 항목의 인덱스 값보다 큰 값입니다(인덱스는 0을 기반으로 합니다). 오류가 발생하면 CB_ERR.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]

## <a name="ccomboboxgetcuebanner"></a><a name="getcuebanner"></a>CComboBox::GetCue배너

콤보 상자 컨트롤에 대해 표시되는 큐 텍스트를 가져옵니다.

```
CString GetCueBanner() const;

BOOL GetCueBanner(
    LPTSTR lpszText,
    int cchText) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpszText*|【아웃】 큐 배너 텍스트를 받는 버퍼에 대한 포인터입니다.|
|*cchText*|【인】 *lpszText* 매개 변수가 가리키는 버퍼의 크기입니다.|

### <a name="return-value"></a>Return Value

첫 번째 오버로드에서 큐 배너 텍스트가 있는 경우 큐 배너 텍스트가 포함된 [CString](../../atl-mfc-shared/using-cstring.md) 개체입니다. 그렇지 않으면 `CString` 길이가 0인 개체입니다.

또는

두 번째 오버로드에서 이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

큐 텍스트는 콤보 상자 컨트롤의 입력 영역에 표시되는 프롬프트입니다. 사용자가 입력을 제공 할 때까지 큐 텍스트가 표시됩니다.

이 메서드는 Windows SDK에 설명 된 [CB_GETCUEBANNER](/windows/win32/Controls/cb-getcuebanner) 메시지를 보냅니다.

## <a name="ccomboboxgetcursel"></a><a name="getcursel"></a>CComboBox::GetCursel

이 멤버 함수를 호출하여 콤보 상자에서 선택된 항목을 확인합니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

콤보 상자의 목록 상자에 있는 현재 선택된 항목의 0기준 인덱스 또는 항목이 선택되지 않은 경우 CB_ERR.

### <a name="remarks"></a>설명

`GetCurSel`인덱스를 목록에 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]

## <a name="ccomboboxgetdroppedcontrolrect"></a><a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect

멤버 `GetDroppedControlRect` 함수를 호출하여 드롭다운 콤보 상자의 표시되는(드롭다운) 목록 상자의 화면 좌표를 검색합니다.

```cpp
void GetDroppedControlRect(LPRECT lprect) const;
```

### <a name="parameters"></a>매개 변수

*lprect*<br/>
좌표를 수신하는 [RECT 구조를](/windows/win32/api/windef/ns-windef-rect) 가리킵니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]

## <a name="ccomboboxgetdroppedstate"></a><a name="getdroppedstate"></a>CComboBox::GetDroppedState

멤버 `GetDroppedState` 함수를 호출하여 드롭다운 콤보 상자의 목록 상자가 표시되는지 확인합니다(삭제).

```
BOOL GetDroppedState() const;
```

### <a name="return-value"></a>Return Value

목록 상자가 표시되는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]

## <a name="ccomboboxgetdroppedwidth"></a><a name="getdroppedwidth"></a>CComboBox::GetDropped폭

이 함수를 호출하여 콤보 상자의 목록 상자의 최소 허용 너비(픽셀)를 검색합니다.

```
int GetDroppedWidth() const;
```

### <a name="return-value"></a>Return Value

성공하면 최소 허용 너비(픽셀)가 표시됩니다. 그렇지 않으면, CB_ERR.

### <a name="remarks"></a>설명

이 함수는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자에만 적용됩니다.

기본적으로 드롭다운 목록 상자의 최소 허용 너비는 0입니다. [SetDroppedWidth를](#setdroppedwidth)호출하여 최소 허용 너비를 설정할 수 있습니다. 콤보 상자의 목록 상자 부분이 표시되면 해당 너비는 허용되는 최소 너비 또는 콤보 상자 너비보다 큽합니다.

### <a name="example"></a>예제

  [SetDropped폭에](#setdroppedwidth)대한 예제를 참조하십시오.

## <a name="ccomboboxgeteditsel"></a><a name="geteditsel"></a>CComboBox::GetEditsel

콤보 상자의 편집 컨트롤에서 현재 선택 영역의 시작 및 종료 문자 위치를 가져옵니다.

```
DWORD GetEditSel() const;
```

### <a name="return-value"></a>Return Value

하위 순서 단어의 시작 위치와 높은 순서 단어에서 선택 종료 후 첫 번째 선택되지 않은 문자의 위치를 포함하는 32비트 값입니다. 이 함수가 편집 컨트롤없이 콤보 상자에서 사용되는 경우 CB_ERR 반환됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]

## <a name="ccomboboxgetextendedui"></a><a name="getextendedui"></a>CComboBox::GetExtendedUI

멤버 `GetExtendedUI` 함수를 호출하여 콤보 상자에 기본 사용자 인터페이스 또는 확장된 사용자 인터페이스가 있는지 확인합니다.

```
BOOL GetExtendedUI() const;
```

### <a name="return-value"></a>Return Value

콤보 박스에 확장된 사용자 인터페이스가 있는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

확장된 사용자 인터페이스는 다음과 같은 방법으로 식별할 수 있습니다.

- 정적 컨트롤을 클릭하면 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자에 대해서만 목록 상자가 표시됩니다.

- 아래쪽 화살표 키를 누르면 목록 상자가 표시됩니다(F4가 비활성화됨).

항목 목록이 표시되지 않으면 정적 컨트롤에서 스크롤이 비활성화됩니다(화살표 키가 비활성화됨).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]

## <a name="ccomboboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CComboBox::Get수평범위

콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 있는 픽셀 단위로 콤보 상자에서 검색합니다.

```
UINT GetHorizontalExtent() const;
```

### <a name="return-value"></a>Return Value

콤보 상자의 목록 상자 부분의 스크롤 가능한 너비(픽셀)입니다.

### <a name="remarks"></a>설명

콤보 상자의 목록 상자 부분에 가로 스크롤 막대가 있는 경우에만 적용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]

## <a name="ccomboboxgetitemdata"></a><a name="getitemdata"></a>CComboBox::GetItemData

지정된 콤보 상자 항목과 연결된 응용 프로그램에서 제공한 32비트 값을 검색합니다.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
콤보 상자의 목록 상자에 항목의 0기반 인덱스를 포함합니다.

### <a name="return-value"></a>Return Value

항목과 연결된 32비트 값 또는 오류가 발생하는 경우 CB_ERR.

### <a name="remarks"></a>설명

32비트 값은 [SetItemData](#setitemdata) 함수 호출의 *dwItemData* 매개 변수로 설정할 수 있습니다. 검색할 `GetItemDataPtr` 32비트 값이 포인터(void)인**void** <strong>\*</strong>경우 멤버 함수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]

## <a name="ccomboboxgetitemdataptr"></a><a name="getitemdataptr"></a>CComboBox::겟아이템데이터Ptr

지정된 콤보 상자 항목과 연결된 응용 프로그램에서 제공한 32비트 값을**포인터(void)로** <strong>\*</strong>검색합니다.

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
콤보 상자의 목록 상자에 항목의 0기반 인덱스를 포함합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 포인터 또는 -1을 검색합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]

## <a name="ccomboboxgetitemheight"></a><a name="getitemheight"></a>CComboBox::GetItemHeight

멤버 `GetItemHeight` 함수를 호출하여 콤보 상자에서 목록 항목의 높이를 검색합니다.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
높이를 검색할 콤보 상자의 구성 요소를 지정합니다. *nIndex* 매개 변수가 -1이면 콤보 상자의 편집 제어(또는 정적 텍스트) 부분의 높이가 검색됩니다. 콤보 상자에 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 경우 *nIndex는* 높이를 검색할 목록 항목의 0기반 인덱스를 지정합니다. 그렇지 않으면 *nIndex를* 0으로 설정해야 합니다.

### <a name="return-value"></a>Return Value

콤보 상자에 지정된 항목의 높이(픽셀 단위)입니다. 오류가 발생할 경우 반환 값은 CB_ERR입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]

## <a name="ccomboboxgetlbtext"></a><a name="getlbtext"></a>CComboBox::GetLBText

콤보 상자의 목록 상자에서 문자열을 가져옵니다.

```
int GetLBText(
    int nIndex,
    LPTSTR lpszText) const;

void GetLBText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
복사할 목록 상자 문자열의 0기반 인덱스를 포함합니다.

*lpszText*<br/>
문자열을 수신할 버퍼를 가리킵니다. 버퍼에는 문자열과 null 문자를 종료할 수 있는 충분한 공간이 있어야 합니다.

*rString*<br/>
에 대 한 참조를 `CString`입니다.

### <a name="return-value"></a>Return Value

종료 null 문자를 제외한 문자열의 길이(바이트)입니다. *nIndex가* 유효한 인덱스를 지정하지 않으면 반환 값이 CB_ERR.

### <a name="remarks"></a>설명

이 멤버 함수의 두 번째 `CString` 양식은 개체에 항목의 텍스트를 채웁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]

## <a name="ccomboboxgetlbtextlen"></a><a name="getlbtextlen"></a>CComboBox:::GetLBTextLen

콤보 상자의 목록 상자에 문자열의 길이를 가져옵니다.

```
int GetLBTextLen(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자 문자열의 0기반 인덱스를 포함합니다.

### <a name="return-value"></a>Return Value

종단 null 문자를 제외한 바이트의 문자열 길이입니다. *nIndex가* 유효한 인덱스를 지정하지 않으면 반환 값이 CB_ERR.

### <a name="example"></a>예제

  [CComboBox::GetLBText에](#getlbtext)대한 예제를 참조하십시오.

## <a name="ccomboboxgetlocale"></a><a name="getlocale"></a>CComboBox::GetLocale

콤보 상자에서 사용하는 로캘을 검색합니다.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Return Value

콤보 상자의 문자열에 대한 로캘 식별자(LCID) 값입니다.

### <a name="remarks"></a>설명

예를 들어 로캘은 정렬된 콤보 상자에서 문자열의 정렬 순서를 결정하는 데 사용됩니다.

### <a name="example"></a>예제

  [CComboBox::SetLocale에](#setlocale)대 한 예제를 참조 하십시오.

## <a name="ccomboboxgetminvisible"></a><a name="getminvisible"></a>CComboBox::GetMinvisible

현재 콤보 상자 컨트롤의 드롭다운 목록에서 표시되는 항목의 최소 수를 가져옵니다.

```
int GetMinVisible() const;
```

### <a name="return-value"></a>Return Value

현재 드롭다운 목록에 표시되는 최소 항목 수입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [CB_GETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) 메시지를 보냅니다.

## <a name="ccomboboxgettopindex"></a><a name="gettopindex"></a>CComboBox::GetTopIndex

콤보 상자의 목록 상자 부분에서 첫 번째 표시되는 항목의 0기반 인덱스를 검색합니다.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Return Value

성공한 경우 콤보 상자의 목록 상자 부분에 표시되는 첫 번째 항목의 0기반 인덱스가 CB_ERR.

### <a name="remarks"></a>설명

처음에는 항목 0이 목록 상자의 맨 위에 있지만 목록 상자를 스크롤하면 다른 항목이 맨 위에 있을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]

## <a name="ccomboboxinitstorage"></a><a name="initstorage"></a>CComboBox::InitStorage

콤보 상자의 목록 상자 부분에 목록 상자 항목을 저장하기 위한 메모리를 할당합니다.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>매개 변수

*nItems*<br/>
추가할 항목 수를 지정합니다.

*n바이트*<br/>
항목 문자열에 할당할 메모리 양을 바이트별로 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 메모리 재할당이 필요하기 전에 콤보 상자의 목록 상자 부분이 저장할 수 있는 최대 항목 수가 CB_ERRSPACE 메모리가 충분하지 않음을 의미합니다.

### <a name="remarks"></a>설명

의 목록 상자 부분에 많은 수의 항목을 추가하기 `CComboBox`전에 이 함수를 호출합니다.

Windows 95/98 전용: *wParam* 매개 변수는 16비트 값으로 제한됩니다. 즉, 목록 상자에 32,767개 이상의 항목을 포함할 수 없습니다. 항목 수는 제한되어 있지만 목록 상자에 있는 항목의 총 크기는 사용 가능한 메모리에 의해서만 제한됩니다.

이 함수는 많은 수의 항목(100개 이상)이 있는 목록 상자의 초기화 속도를 높이는 데 도움이 됩니다. 후속 [AddString,](#addstring) [InsertString](#insertstring)및 [Dir](#dir) 함수가 가능한 가장 짧은 시간을 할애할 수 있도록 지정된 양의 메모리를 할당합니다. 매개 변수에 대 한 추정을 사용할 수 있습니다. 과대 평가하는 경우 일부 추가 메모리가 할당됩니다. 과소평가하는 경우, 일반 할당은 preallocated 양을 초과하는 항목에 사용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]

## <a name="ccomboboxinsertstring"></a><a name="insertstring"></a>CComboBox::삽입 스트링

콤보 상자의 목록 상자에 문자열을 삽입합니다.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열을 받을 목록 상자의 위치에 대한 0부터 시작하는 인덱스를 포함합니다. 이 매개 변수가 -1이면 문자열이 목록의 끝에 추가됩니다.

*lpszString*<br/>
삽입할 null 종료 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

문자열이 삽입된 위치의 0부터 시작하는 인덱스입니다. 오류가 발생할 경우 반환 값은 CB_ERR입니다. 공간이 부족하여 새 문자열을 저장할 수 없는 경우 반환 값은 CB_ERRSPACE입니다.

### <a name="remarks"></a>설명

[AddString](#addstring) 멤버 함수와 달리 `InsertString` 멤버 함수에서는 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일의 목록이 정렬되지 않습니다.

> [!NOTE]
> 이 기능은 Windows `ComboBoxEx` 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 컨트롤을](/windows/win32/Controls/comboboxex-controls) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]

## <a name="ccomboboxlimittext"></a><a name="limittext"></a>CComboBox::제한 텍스트

사용자가 콤보 상자의 편집 컨트롤에 입력할 수 있는 텍스트의 바이트 길이를 제한합니다.

```
BOOL LimitText(int nMaxChars);
```

### <a name="parameters"></a>매개 변수

*nMaxChars*<br/>
사용자가 입력할 수 있는 텍스트의 길이(바이트)를 지정합니다. 이 매개변수가 0이면 텍스트 길이가 65,535바이트로 설정됩니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않습니다. 스타일 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 콤보 상자를 호출하거나 편집 컨트롤이 없는 콤보 상자에 대해 호출하면 반환 값이 CB_ERR.

### <a name="remarks"></a>설명

콤보 상자에 [스타일 CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)없는 경우 텍스트 제한을 편집 컨트롤의 크기보다 크게 설정하면 아무런 효과가 없습니다.

`LimitText`사용자가 입력할 수 있는 텍스트만 제한됩니다. 메시지를 보낼 때 편집 컨트롤에 이미 있는 텍스트에는 영향을 주지 않으며 목록 상자의 문자열을 선택할 때 편집 컨트롤에 복사된 텍스트의 길이에도 영향을 주지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]

## <a name="ccomboboxmeasureitem"></a><a name="measureitem"></a>CComboBox::측정 항목

소유자-그리기 스타일이 있는 콤보 상자가 생성될 때 프레임워크에서 호출됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 `MEASUREITEMSTRUCT` 재정의하고 구조를 입력하여 콤보 상자에 목록 상자의 크기를 Windows에 알립니다. 콤보 상자가 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일로 만들어지면 프레임워크는 목록 상자의 각 항목에 대해 이 멤버 함수를 호출합니다. 그렇지 않으면 이 멤버는 한 번만 호출됩니다.

[SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) 멤버 함수로 만든 소유자-그리기 콤보 상자에서 `CWnd` CBS_OWNERDRAWFIXED 스타일을 사용 하 여 추가 프로그래밍 고려 사항을 포함 합니다. 기술 노트 [14에서](../../mfc/tn014-custom-controls.md)토론을 참조하십시오.

구조에 대한 설명은 [CWnd::OnMeasureItem을](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]

## <a name="ccomboboxpaste"></a><a name="paste"></a>CComboBox::P아스트

현재 커서 위치에서 콤보 상자의 편집 컨트롤에 클립보드의 데이터를 삽입합니다.

```cpp
void Paste();
```

### <a name="remarks"></a>설명

클립보드에 CF_TEXT 형식의 데이터가 포함된 경우에만 데이터가 삽입됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]

## <a name="ccomboboxresetcontent"></a><a name="resetcontent"></a>CComboBox::리셋콘텐츠

목록 상자에서 모든 항목을 제거하고 콤보 상자의 컨트롤을 편집합니다.

```cpp
void ResetContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]

## <a name="ccomboboxselectstring"></a><a name="selectstring"></a>CComboBox::선택 문자열

콤보 상자의 목록 상자에서 문자열을 검색하고 문자열이 발견되면 목록 상자에서 문자열을 선택하고 편집 컨트롤에 복사합니다.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞에 항목의 0기반 인덱스를 포함합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nStartAfter에*의해 지정된 항목으로 다시 계속됩니다. -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszString*<br/>
검색할 접두사가 포함된 null 종료 된 문자열을 가리킵니다. 검색은 대/소문자에 독립적이므로 이 문자열에는 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

문자열이 발견된 경우 선택한 항목의 0기준 인덱스입니다. 검색에 실패한 경우 반환 값이 CB_ERR 현재 선택 영역은 변경되지 않습니다.

### <a name="remarks"></a>설명

문자열은 초기 문자(시작 점에서)가 접두사 문자열의 문자와 일치하는 경우에만 선택됩니다.

및 `SelectString` `FindString` 멤버 함수는 모두 문자열을 찾지만 `SelectString` 멤버 함수는 문자열도 선택합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]

## <a name="ccomboboxsetcuebanner"></a><a name="setcuebanner"></a>CComboBox::SetCue배너

콤보 상자 컨트롤에 대해 표시되는 큐 텍스트를 설정합니다.

```
BOOL SetCueBanner(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*lpszText*|【인】 큐 텍스트를 포함하는 null 종료 버퍼에 대한 포인터입니다.|

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

큐 텍스트는 콤보 상자 컨트롤의 입력 영역에 표시되는 프롬프트입니다. 사용자가 입력을 제공 할 때까지 큐 텍스트가 표시됩니다.

이 메서드는 Windows SDK에 설명 된 [CB_SETCUEBANNER](/windows/win32/Controls/cb-setcuebanner) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 콤보 상자 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_combobox*정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>예제

다음 코드 예제는 콤보 상자 컨트롤에 대한 큐 배너를 설정합니다.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsetcursel"></a><a name="setcursel"></a>CComboBox::세트컬셀

콤보 상자의 목록 상자에서 문자열을 선택합니다.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>매개 변수

*nSelect*<br/>
선택할 문자열의 0기반 인덱스를 지정합니다. -1이면 목록 상자의 현재 선택 영역이 제거되고 편집 컨트롤이 선택해제됩니다.

### <a name="return-value"></a>Return Value

메시지가 성공하면 선택한 항목의 0기준 인덱스입니다. 반환 값은 *nSelect가* 목록의 항목 수보다 크거나 *nSelect가* -1로 설정되어 있는 경우 선택 영역을 지우는 CB_ERR.

### <a name="remarks"></a>설명

필요한 경우 목록 상자는 문자열을 보기로 스크롤합니다(목록 상자가 표시되는 경우). 콤보 상자의 편집 컨트롤의 텍스트가 새 선택 영역을 반영하도록 변경됩니다. 목록 상자의 이전 선택 영역이 제거됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]

## <a name="ccomboboxsetdroppedwidth"></a><a name="setdroppedwidth"></a>CComboBox::설정된 폭

이 함수를 호출하여 콤보 상자의 목록 상자의 최소 허용 너비(픽셀)를 설정합니다.

```
int SetDroppedWidth(UINT nWidth);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
콤보 상자의 목록 상자 부분의 최소 허용 너비(픽셀)입니다.

### <a name="return-value"></a>Return Value

성공하면 목록 상자의 새 너비가 CB_ERR.

### <a name="remarks"></a>설명

이 함수는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자에만 적용됩니다.

기본적으로 드롭다운 목록 상자의 최소 허용 너비는 0입니다. 콤보 상자의 목록 상자 부분이 표시되면 해당 너비는 허용되는 최소 너비 또는 콤보 상자 너비보다 큽합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]

## <a name="ccomboboxseteditsel"></a><a name="seteditsel"></a>CComboBox::SetEditsel

콤보 상자의 편집 컨트롤에서 문자를 선택합니다.

```
BOOL SetEditSel(
    int nStartChar,
    int nEndChar);
```

### <a name="parameters"></a>매개 변수

*nStartChar*<br/>
시작 위치를 지정합니다. 시작 위치가 -1로 설정되면 기존 선택 영역이 제거됩니다.

*nEndChar*<br/>
끝 위치를 지정합니다. 끝 위치가 -1로 설정된 경우 시작 위치에서 편집 컨트롤의 마지막 문자까지의 모든 텍스트가 선택됩니다.

### <a name="return-value"></a>Return Value

멤버 함수가 성공하면 0이 아닙니다. 그렇지 않으면 0. `CComboBox`이 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있거나 목록 상자가 없는 경우 CB_ERR입니다.

### <a name="remarks"></a>설명

위치는 0 기반입니다. 편집 컨트롤의 첫 번째 문자를 선택하려면 시작 위치를 0으로 지정합니다. 끝 위치는 마지막 문자 바로 다음에 선택할 문자에 대한 것입니다. 예를 들어 편집 컨트롤의 처음 네 문자를 선택하려면 시작 위치0과 끝 위치 4를 사용합니다.

> [!NOTE]
> 이 기능은 Windows `ComboBoxEx` 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 컨트롤을](/windows/win32/Controls/comboboxex-controls) 참조하십시오.

### <a name="example"></a>예제

  [CComboBox::GetEditsel](#geteditsel)에 대한 예제를 참조하십시오.

## <a name="ccomboboxsetextendedui"></a><a name="setextendedui"></a>CComboBox::세트확장UI

`SetExtendedUI` 멤버 함수를 호출하여 기본 사용자 인터페이스 또는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자의 확장 사용자 인터페이스를 선택합니다.

```
int SetExtendedUI(BOOL bExtended = TRUE);
```

### <a name="parameters"></a>매개 변수

*bExtended*<br/>
콤보 상자확장 사용자 인터페이스 또는 기본 사용자 인터페이스를 사용해야 하는지 여부를 지정합니다. TRUE 값은 확장된 사용자 인터페이스를 선택합니다. FALSE 값은 표준 사용자 인터페이스를 선택합니다.

### <a name="return-value"></a>Return Value

작업이 성공했는지 또는 오류가 발생하는 지 CB_ERR CB_OKAY.

### <a name="remarks"></a>설명

확장된 사용자 인터페이스는 다음과 같은 방법으로 식별할 수 있습니다.

- 정적 컨트롤을 클릭하면 CBS_DROPDOWNLIST 스타일이 있는 콤보 상자에 대해서만 목록 상자가 표시됩니다.

- 아래쪽 화살표 키를 누르면 목록 상자가 표시됩니다(F4가 비활성화됨).

항목 목록이 표시되지 않으면 정적 컨트롤에서 스크롤이 비활성화됩니다(화살표 키가 비활성화됨).

### <a name="example"></a>예제

  [CComboBox::GetExtendedUI에](#getextendedui)대한 예제를 참조하십시오.

## <a name="ccomboboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CComboBox::설정수평 범위

콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 있는 너비를 픽셀 단위로 설정합니다.

```cpp
void SetHorizontalExtent(UINT nExtent);
```

### <a name="parameters"></a>매개 변수

*nExtent*<br/>
콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 있는 픽셀 수를 지정합니다.

### <a name="remarks"></a>설명

목록 상자의 너비가 이 값보다 작으면 가로 스크롤 막대가 목록 상자의 항목을 가로로 스크롤합니다. 목록 상자의 너비가 이 값과 같거나 큰 경우 가로 스크롤 막대가 숨기거나 콤보 상자에 [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 경우 사용할 수 없습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]

## <a name="ccomboboxsetitemdata"></a><a name="setitemdata"></a>CComboBox:::세트항목데이터

콤보 상자에서 지정된 항목과 연결된 32비트 값을 설정합니다.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
설정할 항목에 0기반 인덱스를 포함합니다.

*dwItemData*<br/>
항목과 연결할 새 값을 포함합니다.

### <a name="return-value"></a>Return Value

오류가 발생하는 경우 CB_ERR.

### <a name="remarks"></a>설명

32비트 항목이 `SetItemDataPtr` 포인터인 경우 멤버 함수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]

## <a name="ccomboboxsetitemdataptr"></a><a name="setitemdataptr"></a>CComboBox::세트아이템데이터Ptr

콤보 상자에서 지정된 항목과 연결된 32비트 값을 지정된 포인터(void)로**void** <strong>\*</strong>설정합니다.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목에 0기반 인덱스를 포함합니다.

*Pdata*<br/>
항목과 연결할 포인터를 포함합니다.

### <a name="return-value"></a>Return Value

오류가 발생하는 경우 CB_ERR.

### <a name="remarks"></a>설명

이 포인터는 항목이 추가되거나 제거될 때 콤보 상자 내의 항목의 상대적인 위치가 변경될 수 있더라도 콤보 상자의 수명 동안 유효합니다. 따라서 상자 내의 항목 인덱스가 변경될 수 있지만 포인터는 안정적으로 유지됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]

## <a name="ccomboboxsetitemheight"></a><a name="setitemheight"></a>CComboBox::세트항목높이

멤버 `SetItemHeight` 함수를 호출하여 콤보 상자에서 목록 항목의 높이또는 콤보 상자의 편집 제어(또는 정적 텍스트) 부분의 높이를 설정합니다.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 항목의 높이 또는 콤보 상자의 편집 제어(또는 정적 텍스트) 부분의 높이가 설정되어 있는지 여부를 지정합니다.

콤보 상자에 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 경우 *nIndex는* 높이를 설정할 목록 항목의 0기반 인덱스를 지정합니다. 그렇지 않으면 *nIndex가* 0이어야 하며 모든 목록 항목의 높이가 설정됩니다.

*nIndex가* -1이면 콤보 상자의 편집 제어 또는 정적 텍스트 부분의 높이를 설정합니다.

*cyItemHeight*<br/>
*nIndex로*식별된 콤보 상자 구성 요소의 높이(픽셀)를 지정합니다.

### <a name="return-value"></a>Return Value

인덱스 또는 높이가 잘못된 지 CB_ERR. 그렇지 않으면 0.

### <a name="remarks"></a>설명

콤보 상자의 편집 제어(또는 정적 텍스트) 부분의 높이는 목록 항목의 높이와 독립적으로 설정됩니다. 응용 프로그램은 편집 제어(또는 정적 텍스트) 부분의 높이가 특정 목록 상자 항목의 높이보다 작지 않은지 확인해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]

## <a name="ccomboboxsetlocale"></a><a name="setlocale"></a>CComboBox::세트 로컬

이 콤보 상자에 대한 로캘 식별자를 설정합니다.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>매개 변수

*nNewLocale*<br/>
콤보 상자에 대해 설정할 새 로캘 식별자(LCID) 값입니다.

### <a name="return-value"></a>Return Value

이 콤보 상자에 대한 이전 로캘 식별자(LCID) 값입니다.

### <a name="remarks"></a>설명

호출되지 않으면 `SetLocale` 기본 로캘이 시스템에서 가져옵니다. 이 시스템 기본 로캘은 제어판의 지역(또는 국제) 응용 프로그램을 사용하여 수정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]

## <a name="ccomboboxsetminvisibleitems"></a><a name="setminvisibleitems"></a>CComboBox::설정민가시블아이템

현재 콤보 상자 컨트롤의 드롭다운 목록에서 표시되는 항목의 최소 수를 설정합니다.

```
BOOL SetMinVisibleItems(int iMinVisible);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*iMinVisible*|【인】 표시되는 항목의 최소 수를 지정합니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 Windows SDK에 설명 된 [CB_SETMINVISIBLE](/windows/win32/Controls/cb-setminvisible) 메시지를 보냅니다.

### <a name="example"></a>예제

다음 코드 예제에서는 콤보 상자 컨트롤에 프로그래밍 방식으로 액세스하는 데 사용되는 변수 *m_combobox*정의합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]

### <a name="example"></a>예제

다음 코드 예제는 콤보 상자 컨트롤의 드롭다운 목록에 20개의 항목을 삽입합니다. 그런 다음 사용자가 드롭다운 화살표를 누를 때 최소 10개의 항목이 표시되도록 지정합니다.

[!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]

## <a name="ccomboboxsettopindex"></a><a name="settopindex"></a>CComboBox::셋탑인덱스

콤보 상자의 목록 상자 부분에 특정 항목이 표시되는지 확인합니다.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이거나 오류가 발생하면 CB_ERR.

### <a name="remarks"></a>설명

*nIndex로* 지정된 항목이 목록 상자 의 맨 위에 나타나거나 최대 스크롤 범위에 도달할 때까지 시스템은 목록 상자를 스크롤합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]

## <a name="ccomboboxshowdropdown"></a><a name="showdropdown"></a>CComboBox::쇼드롭다운

[CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일이 있는 콤보 상자의 목록 상자를 표시하거나 숨깁니다.

```cpp
void ShowDropDown(BOOL bShowIt = TRUE);
```

### <a name="parameters"></a>매개 변수

*bShowIt*<br/>
드롭다운 목록 상자를 표시할지 숨길지 여부를 지정합니다. TRUE 값은 목록 상자를 표시합니다. FALSE 값은 목록 상자를 숨깁니다.

### <a name="remarks"></a>설명

기본적으로 이 스타일의 콤보 상자에 목록 상자가 표시됩니다.

이 멤버 함수는 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일로 만든 콤보 상자에는 영향을 주지 않습니다.

### <a name="example"></a>예제

  [CComboBox::GetDroppedState](#getdroppedstate)에 대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[클리스박스 클래스](../../mfc/reference/clistbox-class.md)<br/>
[C스크롤바 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[정적 클래스](../../mfc/reference/cstatic-class.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
