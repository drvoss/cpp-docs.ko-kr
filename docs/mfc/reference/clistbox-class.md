---
title: 클리스박스 클래스
description: MFC CListBox 클래스 및 해당 멤버 함수에 대한 설명입니다.
ms.date: 01/22/2020
f1_keywords:
- CListBox
- AFXWIN/CListBox
- AFXWIN/CListBox::CListBox
- AFXWIN/CListBox::AddString
- AFXWIN/CListBox::CharToItem
- AFXWIN/CListBox::CompareItem
- AFXWIN/CListBox::Create
- AFXWIN/CListBox::DeleteItem
- AFXWIN/CListBox::DeleteString
- AFXWIN/CListBox::Dir
- AFXWIN/CListBox::DrawItem
- AFXWIN/CListBox::FindString
- AFXWIN/CListBox::FindStringExact
- AFXWIN/CListBox::GetAnchorIndex
- AFXWIN/CListBox::GetCaretIndex
- AFXWIN/CListBox::GetCount
- AFXWIN/CListBox::GetCurSel
- AFXWIN/CListBox::GetHorizontalExtent
- AFXWIN/CListBox::GetItemData
- AFXWIN/CListBox::GetItemDataPtr
- AFXWIN/CListBox::GetItemHeight
- AFXWIN/CListBox::GetItemRect
- AFXWIN/CListBox::GetListBoxInfo
- AFXWIN/CListBox::GetLocale
- AFXWIN/CListBox::GetSel
- AFXWIN/CListBox::GetSelCount
- AFXWIN/CListBox::GetSelItems
- AFXWIN/CListBox::GetText
- AFXWIN/CListBox::GetTextLen
- AFXWIN/CListBox::GetTopIndex
- AFXWIN/CListBox::InitStorage
- AFXWIN/CListBox::InsertString
- AFXWIN/CListBox::ItemFromPoint
- AFXWIN/CListBox::MeasureItem
- AFXWIN/CListBox::ResetContent
- AFXWIN/CListBox::SelectString
- AFXWIN/CListBox::SelItemRange
- AFXWIN/CListBox::SetAnchorIndex
- AFXWIN/CListBox::SetCaretIndex
- AFXWIN/CListBox::SetColumnWidth
- AFXWIN/CListBox::SetCurSel
- AFXWIN/CListBox::SetHorizontalExtent
- AFXWIN/CListBox::SetItemData
- AFXWIN/CListBox::SetItemDataPtr
- AFXWIN/CListBox::SetItemHeight
- AFXWIN/CListBox::SetLocale
- AFXWIN/CListBox::SetSel
- AFXWIN/CListBox::SetTabStops
- AFXWIN/CListBox::SetTopIndex
- AFXWIN/CListBox::VKeyToItem
helpviewer_keywords:
- CListBox [MFC], CListBox
- CListBox [MFC], AddString
- CListBox [MFC], CharToItem
- CListBox [MFC], CompareItem
- CListBox [MFC], Create
- CListBox [MFC], DeleteItem
- CListBox [MFC], DeleteString
- CListBox [MFC], Dir
- CListBox [MFC], DrawItem
- CListBox [MFC], FindString
- CListBox [MFC], FindStringExact
- CListBox [MFC], GetAnchorIndex
- CListBox [MFC], GetCaretIndex
- CListBox [MFC], GetCount
- CListBox [MFC], GetCurSel
- CListBox [MFC], GetHorizontalExtent
- CListBox [MFC], GetItemData
- CListBox [MFC], GetItemDataPtr
- CListBox [MFC], GetItemHeight
- CListBox [MFC], GetItemRect
- CListBox [MFC], GetListBoxInfo
- CListBox [MFC], GetLocale
- CListBox [MFC], GetSel
- CListBox [MFC], GetSelCount
- CListBox [MFC], GetSelItems
- CListBox [MFC], GetText
- CListBox [MFC], GetTextLen
- CListBox [MFC], GetTopIndex
- CListBox [MFC], InitStorage
- CListBox [MFC], InsertString
- CListBox [MFC], ItemFromPoint
- CListBox [MFC], MeasureItem
- CListBox [MFC], ResetContent
- CListBox [MFC], SelectString
- CListBox [MFC], SelItemRange
- CListBox [MFC], SetAnchorIndex
- CListBox [MFC], SetCaretIndex
- CListBox [MFC], SetColumnWidth
- CListBox [MFC], SetCurSel
- CListBox [MFC], SetHorizontalExtent
- CListBox [MFC], SetItemData
- CListBox [MFC], SetItemDataPtr
- CListBox [MFC], SetItemHeight
- CListBox [MFC], SetLocale
- CListBox [MFC], SetSel
- CListBox [MFC], SetTabStops
- CListBox [MFC], SetTopIndex
- CListBox [MFC], VKeyToItem
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
ms.openlocfilehash: 171038ebaaed815aa687c200fe3210bde8000be3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753584"
---
# <a name="clistbox-class"></a>클리스박스 클래스

Windows 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CListBox : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|`CListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CListBox::AddString](#addstring)|목록 상자에 문자열을 추가합니다.|
|[CListBox::CharToItem](#chartoitem)|문자열이 없는 소유자 그리기 목록 상자에 대한 사용자 지정 WM_CHAR 처리를 제공하기 위해 재정의합니다.|
|[CListBox::CompareItem](#compareitem)|정렬된 소유자-그리기 목록 상자에서 새 항목의 위치를 결정 하기 위해 프레임 워크에 의해 호출 됩니다.|
|[CListBox::Create](#create)|Windows 목록 상자를 만들고 개체에 `CListBox` 연결합니다.|
|[CListBox::DeleteItem](#deleteitem)|사용자가 소유자-그리기 목록 상자에서 항목을 삭제할 때 프레임워크에서 호출됩니다.|
|[CListBox::DeleteString](#deletestring)|목록 상자에서 문자열을 삭제합니다.|
|[CListBox::Dir](#dir)|현재 디렉터리에서 파일 이름, 드라이브 또는 둘 다를 목록 상자에 추가합니다.|
|[CListBox::DrawItem](#drawitem)|소유자-그리기 목록 상자의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.|
|[CListBox::FindString](#findstring)|목록 상자에서 문자열을 검색합니다.|
|[CListBox::FindStringExact](#findstringexact)|지정된 문자열과 일치하는 첫 번째 목록 상자 문자열을 찾습니다.|
|[CListBox::GetAnchorIndex](#getanchorindex)|목록 상자에서 현재 앵커 항목의 0기반 인덱스를 검색합니다.|
|[CListBox::GetCaretIndex](#getcaretindex)|다중 선택 목록 상자에 포커스 사각형이 있는 항목의 인덱스를 결정합니다.|
|[CListBox::GetCount](#getcount)|목록 상자에 문자열 수를 반환합니다.|
|[CListBox::GetCurSel](#getcursel)|목록 상자에서 현재 선택된 문자열의 0기반 인덱스를 반환합니다.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|목록 상자를 가로로 스크롤할 수 있는 너비를 픽셀단위로 반환합니다.|
|[CListBox::GetItemData](#getitemdata)|목록 상자 항목과 연결된 값을 반환합니다.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|목록 상자 항목에 대한 포인터를 반환합니다.|
|[CListBox::GetItemHeight](#getitemheight)|목록 상자에서 항목의 높이를 결정합니다.|
|[CListBox::GetItemRect](#getitemrect)|현재 표시되는 목록 상자 항목의 경계 사각형을 반환합니다.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|열당 항목 수를 검색합니다.|
|[CListBox:::GetLocale](#getlocale)|목록 상자에 대한 로캘 식별자를 검색합니다.|
|[CListBox::GetSel](#getsel)|목록 상자 항목의 선택 상태를 반환합니다.|
|[CListBox::GetSelCount](#getselcount)|다중 선택 목록 상자에서 현재 선택한 문자열 수를 반환합니다.|
|[CListBox::GetSelItems](#getselitems)|목록 상자에서 현재 선택한 문자열의 인덱스를 반환합니다.|
|[CListBox::GetText](#gettext)|목록 상자 항목을 버퍼에 복사합니다.|
|[CListBox:::GetTextLen](#gettextlen)|목록 상자 항목의 길이를 바이트로 반환합니다.|
|[CListBox::GetTopIndex](#gettopindex)|목록 상자에서 표시되는 첫 번째 문자열의 인덱스를 반환합니다.|
|[CListBox::InitStorage](#initstorage)|목록 상자 항목 및 문자열에 대한 메모리 블록을 Preallocates합니다.|
|[CListBox::InsertString](#insertstring)|목록 상자의 특정 위치에 문자열을 삽입합니다.|
|[CListBox::ItemFromPoint](#itemfrompoint)|점에 가장 가까운 목록 상자 항목의 인덱스를 반환합니다.|
|[CListBox::측정 항목](#measureitem)|목록 상자 차원을 결정하기 위해 소유자-그리기 목록 상자를 만들 때 프레임워크에서 호출됩니다.|
|[CListBox::ResetContent](#resetcontent)|목록 상자에서 모든 항목을 지웁습니다.|
|[CListBox::선택 문자열](#selectstring)|단일 선택 목록 상자에서 문자열을 검색하고 선택합니다.|
|[CListBox::SelItemRange](#selitemrange)|다중 선택 목록 상자에서 문자열 범위를 선택하거나 선택 취소합니다.|
|[CListBox::세트앵커인덱스](#setanchorindex)|확장 된 선택을 시작 하려면 여러 선택 목록 상자에 앵커를 설정 합니다.|
|[CListBox::셋케어인덱스](#setcaretindex)|포커스 사각형을 여러 선택 목록 상자의 지정된 인덱스에서 항목으로 설정합니다.|
|[CListBox::설정열 폭](#setcolumnwidth)|다중 열 목록 상자의 열 너비를 설정합니다.|
|[CListBox::세트커셀](#setcursel)|목록 상자 문자열을 선택합니다.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|목록 상자를 가로로 스크롤할 수 있는 너비를 픽셀단위로 설정합니다.|
|[CListBox:::세트항목데이터](#setitemdata)|목록 상자 항목과 연결된 값을 설정합니다.|
|[CListBox::셋아이템데이터Ptr](#setitemdataptr)|목록 상자 항목에 대한 포인터를 설정합니다.|
|[CListBox::SetItemHeight](#setitemheight)|목록 상자에 있는 항목의 높이를 설정합니다.|
|[CListBox::설정 로컬](#setlocale)|목록 상자에 대한 로캘 식별자를 설정합니다.|
|[CListBox::Setsel](#setsel)|다중 선택 목록 상자에서 목록 상자 항목을 선택하거나 선택 취소합니다.|
|[CListBox::SetTabStops](#settabstops)|목록 상자에서 탭 중지 위치를 설정합니다.|
|[CListBox::셋탑인덱스](#settopindex)|목록 상자에서 표시되는 첫 번째 문자열의 0기반 인덱스를 설정합니다.|
|[CListBox::VKeyToItem](#vkeytoitem)|LBS_WANTKEYBOARDINPUT 스타일 집합을 사용하여 목록 상자에 대한 사용자 지정 WM_KEYDOWN 처리를 제공하기 위해 재정의합니다.|

## <a name="remarks"></a>설명

목록 상자에는 사용자가 보고 선택할 수 있는 파일 이름과 같은 항목 목록이 표시됩니다.

단일 선택 목록 상자에서 사용자는 하나의 항목만 선택할 수 있습니다. 다중 선택 목록 상자에서 항목 범위를 선택할 수 있습니다. 사용자가 항목을 선택하면 항목이 강조 표시되고 목록 상자가 부모 창에 알림 메시지를 보냅니다.

대화 상자 템플릿에서 또는 코드에서 직접 목록 상자를 만들 수 있습니다. 직접 만들려면 개체를 `CListBox` 생성한 다음 멤버 [만들기](#create) 함수를 호출하여 Windows 목록 상자 `CListBox` 컨트롤을 만들고 개체에 연결합니다. 대화 상자 템플릿에서 목록 상자를 사용하려면 대화 상자 클래스에서 목록 상자 변수를 선언한 다음 대화 `DoDataExchange` 상자 클래스의 `DDX_Control` 함수에서 멤버 변수를 컨트롤에 연결합니다. 이 작업은 대화 상자 클래스에 컨트롤 변수를 추가할 때 자동으로 수행됩니다.

구성은 에서 파생된 클래스의 한 단계 `CListBox`프로세스일 수 있습니다. 파생 클래스에 대한 생성자 및 `Create` 생성자 내에서 호출합니다.

목록 상자에서 부모에게 보낸 Windows 알림 메시지(일반적으로 [CDialog에서](../../mfc/reference/cdialog-class.md)파생된 클래스)를 처리하려면 각 메시지에 대한 부모 클래스에 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가합니다.

각 메시지 맵 항목은 다음과 같은 형식을 취합니다.

`ON_Notification( id, memberFxn )`

여기서 `id` 알림을 보내는 목록 상자 컨트롤의 자식 창 `memberFxn` ID를 지정하고 알림을 처리하기 위해 작성한 부모 구성원 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

`afx_msg void memberFxn( );`

다음은 잠재적인 메시지 맵 항목 목록과 상위 사용자에게 전송될 사례에 대한 설명입니다.

- ON_LBN_DBLCLK 사용자가 목록 상자에서 문자열을 두 번 클릭합니다. [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 목록 상자만 이 알림 메시지를 보냅니다.

- ON_LBN_ERRSPACE 목록 상자는 요청을 충족하기에 충분한 메모리를 할당할 수 없습니다.

- ON_LBN_KILLFOCUS 목록 상자가 입력 포커스를 잃고 있습니다.

- ON_LBN_SELCANCEL 현재 목록 상자 선택이 취소됩니다. 이 메시지는 목록 상자에 LBS_NOTIFY 스타일이 있는 경우에만 전송됩니다.

- ON_LBN_SELCHANGE 목록 상자의 선택 영역이 변경되었습니다. [CListBox:SetCurSel](#setcursel) 멤버 함수에서 선택 영역을 변경하면 이 알림이 전송되지 않습니다. 이 알림은 LBS_NOTIFY 스타일이 있는 목록 상자에만 적용됩니다. LBN_SELCHANGE 알림 메시지는 사용자가 화살표 키를 누를 때마다 선택 영역이 변경되지 않더라도 다중 선택 목록 상자에 대해 전송됩니다.

- ON_LBN_SETFOCUS 목록 상자가 입력 포커스를 받고 있습니다.

- ON_WM_CHARTOITEM 문자열이 없는 소유자-그리기 목록 상자에 WM_CHAR 메시지가 수신 됩니다.

- ON_WM_VKEYTOITEM LBS_WANTKEYBOARDINPUT 스타일이 있는 목록 상자는 WM_KEYDOWN 메시지를 수신합니다.

대화 상자 `CListBox` 내에서(대화 상자 리소스를 통해) 개체를 `CListBox` 만들면 사용자가 대화 상자를 닫을 때 개체가 자동으로 소멸됩니다.

창 내에서 `CListBox` 객체를 만드는 경우 객체를 `CListBox` 삭제해야 할 수 있습니다. 스택에서 객체를 `CListBox` 만들면 자동으로 소멸됩니다. 새 함수를 `CListBox` 사용하여 힙에 개체를 **new** 만드는 경우 사용자가 부모 창을 닫을 때 개체에 **삭제를** 호출하여 개체를 삭제해야 합니다.

개체에 메모리를 `CListBox` 할당하는 경우 `CListBox` 소멸자 재정의하여 할당을 삭제합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>CListBox::추가 문자열

목록 상자에 문자열을 추가합니다.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
추가할 null 종료된 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

목록 상자의 문자열에 대한 0기반 인덱스입니다. 오류가 발생하면 반환 값은 LB_ERR. 새 문자열을 저장할 공간이 부족하면 반환 값이 LB_ERRSPACE.

### <a name="remarks"></a>설명

목록 상자가 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 작성되지 않은 경우 문자열이 목록의 끝에 추가됩니다. 그렇지 않으면 문자열이 목록에 삽입되고 목록이 정렬됩니다. 목록 상자가 LBS_SORT 스타일로 만들어졌지만 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 아닌 경우 프레임워크는 `CompareItem` 멤버 함수에 대한 하나 이상의 호출로 목록을 정렬합니다.

[InsertString을](#insertstring) 사용하여 목록 상자 내의 특정 위치에 문자열을 삽입합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>CListBox::ChartoItem

목록 상자의 부모 창 목록 상자에서 WM_CHARTOITEM 메시지를 받을 때 프레임 워크에 의해 호출 됩니다.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 입력한 문자의 ANSI 코드입니다.

*nIndex*<br/>
목록 상자 카류의 현재 위치입니다.

### <a name="return-value"></a>Return Value

키 입력에 대한 기본 작업을 수행할 목록 상자 항목의 인덱스를 지정하기 위해 추가 작업또는 음수가 아닌 경우 -1 또는 -2를 반환합니다. 기본 구현반환 - 1.

### <a name="remarks"></a>설명

WM_CHARTOITEM 메시지는 WM_CHAR 메시지를 받을 때 목록 상자에서 보내지만 목록 상자가 다음 조건을 모두 충족하는 경우에만 전송됩니다.

- 소유자-그리기 목록 상자입니다.

- [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 집합이 없습니다.

- 항목이 하나 이상 있습니다.

이 함수를 직접 호출해서는 안 됩니다. 이 함수를 재정의하여 키보드 메시지를 사용자 지정처리합니다.

재정의에서 값을 반환하여 프레임워크에 수행한 작업을 알려야 합니다. 반환 값 -1 또는 - 2는 항목을 선택하는 모든 측면을 처리했음을 나타내며 목록 상자에서 추가 작업이 필요하지 않음을 나타냅니다. 반환하기 전에 - 1 또는 - 2, 당신은 선택을 설정하거나 캐리트 또는 둘 다 를 이동할 수 있습니다. 선택 항목을 설정하려면 [SetCursel](#setcursel) 또는 [SetSel을](#setsel)사용합니다. 카를트 이동하려면 [SetCaretIndex](#setcaretindex)를 사용합니다.

반환 값이 0 이상이면 목록 상자에 있는 항목의 인덱스를 지정하고 목록 상자에서 지정된 항목의 키 입력에 대한 기본 작업을 수행해야 함을 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>리스트 박스 ::CListBox

`CListBox` 개체를 생성합니다.

```
CListBox();
```

### <a name="remarks"></a>설명

두 단계로 `CListBox` 객체를 생성합니다. 먼저 생성자 `ClistBox` 호출한 다음 `Create`을 호출하여 Windows 목록 상자를 초기화하고 `CListBox`에 연결합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>CListBox::비교항목

정렬된 소유자-그리기 목록 상자에서 새 항목의 상대위치를 결정하기 위해 프레임워크에서 호출합니다.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpCompareItemStruct*<br/>
구조에 대한 `COMPAREITEMSTRUCT` 긴 포인터입니다.

### <a name="return-value"></a>Return Value

[비교항목truct](/windows/win32/api/winuser/ns-winuser-compareitemstruct) 구조에 설명된 두 항목의 상대적 위치를 나타냅니다. 다음 값 중 어느 값일 수도 있습니다.

|값|의미|
|-----------|-------------|
|-1|항목 1 항목 2 전에 정렬합니다.|
|0|항목 1과 항목 2는 동일하게 정렬됩니다.|
|1|항목 1 항목 2 후 정렬 합니다.|

구조에 대한 설명은 [CWnd::OnCompareItem을](../../mfc/reference/cwnd-class.md#oncompareitem) `COMPAREITEMSTRUCT` 참조하십시오.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. LBS_SORT 스타일로 소유자-그리기 목록 상자를 만드는 경우 목록 상자에 추가된 새 항목을 정렬하는 데 프레임워크를 지원하려면 이 멤버 함수를 재정의해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>CListBox::만들기

Windows 목록 상자를 만들고 개체에 `CListBox` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
목록 상자의 스타일을 지정합니다. 목록 상자 [스타일의](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 조합을 상자에 적용합니다.

*rect*<br/>
목록 상자 크기와 위치를 지정합니다. 개체 또는 `CRect` 구조체일 `RECT` 수 있습니다.

*pParentWnd*<br/>
목록 상자의 상위 창(일반적으로 개체)을 지정합니다. `CDialog` NULL이 아니어야 합니다.

*nID*<br/>
목록 상자의 컨트롤 ID를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CListBox` 객체를 생성합니다. 먼저 생성자 호출 한 `Create`다음 호출 `CListBox` 합니다 .

실행되면 `Create` Windows는 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 메시지를 목록 상자 컨트롤로 보냅니다.

이러한 메시지는 기본적으로 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 `CWnd` 함수에 의해 기본 클래스에서 처리됩니다. 기본 메시지 처리를 확장하려면 에서 `CListBox`클래스를 파생 합니다 . 예를 `OnCreate`들어 새 클래스에 필요한 초기화를 수행하려면 을 재정의합니다.

다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 목록 상자 컨트롤에 적용합니다.

- 항상 WS_CHILD

- WS_VISIBLE 보통

- WS_DISABLED 드물게

- WS_VSCROLL 세로 스크롤 막대를 추가하려면

- WS_HSCROLL 가로 스크롤 막대를 추가하려면

- WS_GROUP 컨트롤그룹

- WS_TABSTOP 이 컨트롤에 대한 탭 을 허용하려면

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::DeleteItem

사용자가 소유자-draw `CListBox` 개체에서 항목을 삭제하거나 목록 상자를 삭제할 때 프레임워크에서 호출됩니다.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDeleteItemStruct*<br/>
삭제된 항목에 대한 정보가 포함된 Windows [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 필요에 따라 소유자-그리기 목록 상자를 다시 그리려면 이 함수를 재정의합니다.

구조에 대한 설명은 [CWnd::OnDeleteItem을](../../mfc/reference/cwnd-class.md#ondeleteitem) `DELETEITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>CListBox::DeleteString

목록 상자에서 위치 *nIndex에서* 항목을 삭제합니다.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
삭제할 문자열의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

목록에 남아 있는 문자열의 개수입니다. 반환 값은 *nIndex* 목록의 항목 수보다 큰 인덱스를 지정하는 경우 LB_ERR.

### <a name="remarks"></a>설명

*이제 nIndex* 다음의 모든 항목이 한 위치로 이동합니다. 예를 들어 목록 상자에 두 개의 항목이 포함된 경우 첫 번째 항목을 삭제하면 나머지 항목이 첫 번째 위치에 있게 됩니다. *nIndex*=0을 첫 번째 위치에 있는 항목에 대해

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>CListBox::Dir

파일 이름, 드라이브 또는 둘 다 목록을 목록 상자에 추가합니다.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>매개 변수

*Attr*<br/>
`CFile::GetStatu` [s에](../../mfc/reference/cfile-class.md#getstatus)설명된 **열거형** 값의 조합 또는 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|0x0000|파일을 읽거나 쓸 수 있습니다.|
|0x0001|파일은 읽을 수 있지만 쓸 수 없습니다.|
|0x0002|파일이 숨겨져 있으며 디렉터리 목록에 나타나지 않습니다.|
|0x0004|파일은 시스템 파일입니다.|
|0x0010|*lpszWildCard에서* 지정한 이름은 디렉터리를 지정합니다.|
|0x0020|파일이 보관되었습니다.|
|0x4000|*lpszWildCard에서*지정한 이름과 일치하는 모든 드라이브를 포함합니다.|
|0x8000|배타적 플래그입니다. 단독 플래그가 설정된 경우 지정된 형식의 파일만 나열됩니다. 그렇지 않으면 지정된 형식의 파일이 "일반" 파일 외에 나열됩니다.|

*lpszWildCard*<br/>
파일 사양 문자열을 가리킵니다. 문자열에는 와일드카드(예: *. )가\*포함될 수 있습니다.

### <a name="return-value"></a>Return Value

목록에 추가된 성 파일 이름의 0기반 인덱스입니다. 오류가 발생하면 반환 값은 LB_ERR. 새 문자열을 저장할 공간이 부족한 경우 반환 값은 LB_ERRSPACE.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>CListBox::D원시아이템

소유자-그리기 목록 상자의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

`itemAction` `itemState` 및 구조의 멤버는 수행할 드로잉 작업을 `DRAWITEMSTRUCT` 정의합니다.

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CListBox` 응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에서* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

구조에 대한 설명은 [CWnd::OnDrawItem을](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>CListBox::찾기 스트링

목록 상자 선택을 변경하지 않고 지정된 접두사가 포함된 목록 상자에서 첫 번째 문자열을 찾습니다.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞에 항목의 0기반 인덱스를 포함합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nStartAfter에*의해 지정된 항목으로 다시 계속됩니다. *nStartAfter가* -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszItem*<br/>
검색할 접두사가 포함된 null 종료 된 문자열을 가리킵니다. 검색은 대/소문자독립적이므로 이 문자열에는 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

일치하는 항목의 0기준 인덱스 또는 검색에 실패한 경우 LB_ERR.

### <a name="remarks"></a>설명

[SelectString](#selectstring) 멤버 함수를 사용하여 문자열을 찾고 선택합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox::찾기스트링Exact

*lpszFind에*지정된 문자열과 일치하는 첫 번째 목록 상자 문자열을 찾습니다.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>매개 변수

*nIndexStart*<br/>
검색할 첫 번째 항목 전에 항목의 0기반 인덱스를 지정합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nIndexStart에서*지정한 항목으로 다시 계속됩니다. *nIndexStart가* -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszFind*<br/>
검색할 null 종료된 문자열을 가리킵니다. 이 문자열에는 확장을 포함하여 전체 파일 이름이 포함될 수 있습니다. 검색은 대/소문자를 구분하지 않으므로 문자열에 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

일치하는 항목의 인덱스 또는 검색에 실패한 경우 LB_ERR.

### <a name="remarks"></a>설명

목록 상자가 소유자-그리기 스타일로 만들어졌지만 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 `FindStringExact` 없는 경우 멤버 함수는 *lpszFind*의 값과 doubleword 값을 일치시키려고 시도합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox::겟앵커인덱스

목록 상자에서 현재 앵커 항목의 0기반 인덱스를 검색합니다.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Return Value

성공하면 현재 앵커 항목의 인덱스입니다. 그렇지 않으면 LB_ERR.

### <a name="remarks"></a>설명

다중 선택 목록 상자에서 앵커 항목은 연속선택 항목 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

  [CListBox::SetAnchorIndex](#setanchorindex)에 대한 예제를 참조하십시오.

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox::겟케어트인덱스

다중 선택 목록 상자에 포커스 사각형이 있는 항목의 인덱스를 결정합니다.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Return Value

목록 상자에 포커스 사각형이 있는 항목의 0기준 인덱스입니다. 목록 상자가 단일 선택 목록 상자인 경우 반환 값은 선택된 항목의 인덱스(있는 경우)입니다.

### <a name="remarks"></a>설명

항목을 선택할 수도 또는 선택하지 않을 수도 있습니다.

### <a name="example"></a>예제

  [CListBox::SetCaretIndex에](#setcaretindex)대한 예제를 참조하십시오.

## <a name="clistboxgetcount"></a><a name="getcount"></a>CListBox::GetCount

목록 상자의 항목 수를 검색합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 항목 수 또는 오류가 발생하는 경우 LB_ERR.

### <a name="remarks"></a>설명

반환된 개수는 마지막 항목의 인덱스 값보다 큰 값입니다(인덱스는 0을 기반으로 합니다).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>CListBox::GetCursel

단일 선택 목록 상자에서 현재 선택한 항목(있는 경우)의 0기준 인덱스를 검색합니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

단일 선택 목록 상자인 경우 현재 선택한 항목의 0기준 인덱스입니다. 현재 선택된 항목이 없는 경우 LB_ERR.

다중 선택 목록 상자에서 포커스가 있는 항목의 인덱스입니다.

### <a name="remarks"></a>설명

다중 `GetCurSel` 선택 목록 상자를 호출하지 마십시오. [CListBox::GetSelItems](#getselitems) 대신 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox::get수평범위

목록 상자에서 가로로 스크롤할 수 있는 픽셀의 너비를 검색합니다.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 스크롤 가능한 너비(픽셀)입니다.

### <a name="remarks"></a>설명

목록 상자에 가로 스크롤 막대가 있는 경우에만 적용됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox:::겟아이템데이터

지정된 목록 상자 항목과 연결된 응용 프로그램에서 제공한 doubleword 값을 검색합니다.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

항목과 연결된 값 또는 오류가 발생하는 경우 LB_ERR.

### <a name="remarks"></a>설명

이중 단어 값은 [SetItemData](#setitemdata) 호출의 *dwItemData* 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox::겟아이템데이터Ptr

지정된 목록 상자 항목과 연결된 응용 프로그램에서 제공한 32비트 값을**포인터(void)로** <strong>\*</strong>검색합니다.

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 포인터 또는 -1을 검색합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox::GetItemHeight

목록 상자에서 항목의 높이를 결정합니다.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 항목의 0기반 인덱스를 지정합니다. 이 매개 변수는 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이 있는 경우에만 사용됩니다. 그렇지 않으면 0으로 설정해야 합니다.

### <a name="return-value"></a>Return Value

목록 상자에 있는 항목의 높이(픽셀 단위)입니다. 목록 상자에 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 경우 반환 값은 *nIndex*. 오류가 발생하면 반환 값이 LB_ERR.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox::GetItemRect

목록 상자 창에 현재 표시되는 목록 상자 항목의 경계를 묶는 사각형의 치수를 검색합니다.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0기반 인덱스를 지정합니다.

*Lprect*<br/>
항목의 목록 상자 클라이언트 좌표를 받는 [RECT 구조에](/windows/win32/api/windef/ns-windef-rect) 대한 긴 포인터를 지정합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox:::GetListBoxInfo

열당 항목 수를 검색합니다.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Return Value

개체의 열당 항목 `CListBox` 수입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo) 메시지의 기능을 에뮬레이트합니다.

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>CListBox:::GetLocale

목록 상자에서 사용하는 로캘을 검색합니다.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 문자열에 대한 로캘 식별자(LCID) 값입니다.

### <a name="remarks"></a>설명

예를 들어 로캘은 정렬된 목록 상자에서 문자열의 정렬 순서를 결정하는 데 사용됩니다.

### <a name="example"></a>예제

  [CListBox::SetLocale에](#setlocale)대한 예제를 참조하십시오.

## <a name="clistboxgetsel"></a><a name="getsel"></a>CListBox::GetSel

항목의 선택 상태를 검색합니다.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

지정된 항목이 선택된 경우 양수입니다. 그렇지 않으면 0입니다. 오류가 발생하면 반환 값이 LB_ERR.

### <a name="remarks"></a>설명

이 멤버 함수는 단일 및 다중 선택 목록 상자에서 모두 작동합니다.

현재 선택한 목록 상자 항목의 인덱스를 검색하려면 [CListBox::GetCurSel](#getcursel)을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>CListBox:::겟셀카운트

다중 선택 목록 상자에서 선택한 항목의 총 수를 검색합니다.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자에서 선택한 항목의 개수입니다. 목록 상자가 단일 선택 목록 상자인 경우 반환 값은 LB_ERR.

### <a name="example"></a>예제

  [CListBox::GetSelItems에](#getselitems)대한 예제를 참조하십시오.

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>CListBox::getselItems

복수 선택 목록 상자에서 선택한 항목의 항목 번호를 지정하는 정수 배열로 버퍼를 채웁니다.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>매개 변수

*nMaxItems*<br/>
버퍼에 배치할 항목 번호가 선택된 항목의 최대 수를 지정합니다.

*rgIndex*<br/>
*nMaxItems에서*지정한 정수 수에 충분히 큰 버퍼에 대한 포인터를 지정합니다.

### <a name="return-value"></a>Return Value

버퍼에 배치된 실제 항목 수입니다. 목록 상자가 단일 선택 목록 상자인 경우 `LB_ERR`반환 값은 입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>CListBox::GetText

목록 상자에서 문자열을 가져옵니다.

```
int GetText(
    int nIndex,
    LPTSTR lpszBuffer) const;

void GetText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 문자열의 0기반 인덱스를 지정합니다.

*lpszBuffer*<br/>
문자열을 받는 버퍼를 가리킵니다. 버퍼에는 문자열과 null 문자를 종료할 수 있는 충분한 공간이 있어야 합니다. 문자열의 크기는 `GetTextLen` 멤버 함수를 호출하여 미리 결정할 수 있습니다.

*rString*<br/>
`CString` 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

종료 null 문자를 제외한 문자열의 길이(바이트)입니다. *nIndex가* 유효한 인덱스를 지정하지 않으면 반환 값이 LB_ERR.

### <a name="remarks"></a>설명

이 멤버 함수의 두 번째 `CString` 양식은 개체를 문자열 텍스트로 채웁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>CListBox:::GetTextLen

목록 상자 항목에서 문자열의 길이를 가져옵니다.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

종단 null 문자를 제외한 문자열의 문자열 길이입니다. *nIndex가* 유효한 인덱스를 지정하지 않으면 반환 값이 LB_ERR.

### <a name="example"></a>예제

  [CListBox::GetText](#gettext)에 대한 예제를 참조하십시오.

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>CListBox::GetTopIndex

목록 상자에 표시되는 첫 번째 항목의 0기반 인덱스를 검색합니다.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Return Value

그렇지 않으면 LB_ERR 경우 목록 상자에 표시되는 첫 번째 항목의 0기반 인덱스입니다.

### <a name="remarks"></a>설명

처음에는 항목 0이 목록 상자의 맨 위에 있지만 목록 상자를 스크롤하면 다른 항목이 맨 위에 있을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>CListBox:::InitStorage

목록 상자 항목을 저장하기 위해 메모리를 할당합니다.

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

성공하면 메모리 재할당이 필요하기 전에 목록 상자에서 저장할 수 있는 최대 항목 수가 LB_ERRSPACE 메모리가 충분하지 않음을 의미합니다.

### <a name="remarks"></a>설명

`CListBox`에 많은 수의 항목을 추가하기 전에 이 함수를 호출합니다.

이 함수는 많은 수의 항목(100개 이상)이 있는 목록 상자의 초기화 속도를 높이는 데 도움이 됩니다. 후속 [AddString,](#addstring) [InsertString](#insertstring)및 [Dir](#dir) 함수가 가능한 가장 짧은 시간을 할애할 수 있도록 지정된 양의 메모리를 할당합니다. 매개 변수에 대 한 추정을 사용할 수 있습니다. 과대 평가하는 경우 일부 추가 메모리가 할당됩니다. 과소평가하는 경우, 일반 할당은 preallocated 양을 초과하는 항목에 사용됩니다.

Windows 95/98전용: *nItems* 매개 변수는 16비트 값으로 제한됩니다. 즉, 목록 상자에 32,767개 이상의 항목을 포함할 수 없습니다. 항목 수는 제한되어 있지만 목록 상자에 있는 항목의 총 크기는 사용 가능한 메모리에 의해서만 제한됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>CListBox::삽입 스트링

목록 상자에 문자열을 삽입합니다.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열을 삽입할 위치의 0기반 인덱스를 지정합니다. 이 매개 변수가 -1이면 문자열이 목록의 끝에 추가됩니다.

*lpszItem*<br/>
삽입할 null 종료 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

문자열이 삽입된 위치의 0부터 시작하는 인덱스입니다. 오류가 발생하면 반환 값은 LB_ERR. 새 문자열을 저장할 공간이 부족하면 반환 값이 LB_ERRSPACE.

### <a name="remarks"></a>설명

[AddString](#addstring) 멤버 함수와 `InsertString` 달리 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 목록이 정렬되지 는 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>CListBox::항목에서부터 포인트

*pt에*지정된 점에 가장 가까운 목록 상자 항목을 결정합니다.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
목록 상자의 클라이언트 영역왼쪽 위 모서리를 기준으로 가장 가까운 항목을 찾을 수 있는 점을 지정합니다.

*bOutside*<br/>
*PT가* 목록 상자의 클라이언트 영역 외부에 있는 경우 TRUE로 설정되는 BOOL 변수에 대한 참조, *pt가* 목록 상자의 클라이언트 영역 내에 있는 경우 FALSE입니다.

### <a name="return-value"></a>Return Value

*pt에*지정된 점에 가장 가까운 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 마우스 커서가 이동하는 목록 상자 항목을 확인할 수 있습니다.

### <a name="example"></a>예제

  [CListBox::SetAnchorIndex](#setanchorindex)에 대한 예제를 참조하십시오.

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>CListBox::측정 항목

소유자-그리기 스타일이 있는 목록 상자를 만들 때 프레임워크에서 호출됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) 구조에 대한 긴 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 `MEASUREITEMSTRUCT` 재정의하고 구조를 입력하여 Windows에 목록 상자 차원을 알립니다. 목록 상자가 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 만들어지면 프레임워크는 목록 상자의 각 항목에 대해 이 멤버 함수를 호출합니다. 그렇지 않으면 이 멤버는 한 번만 호출됩니다.

`CWnd`의 멤버 함수 `SubclassDlgItem`를 사용하여 만든 소유자 그리기 목록 상자에서 [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용하는 방법에 대한 자세한 내용은 [기술 참고 사항 14](../../mfc/tn014-custom-controls.md)의 설명을 참조하십시오.

구조에 대한 설명은 [CWnd::OnMeasureItem을](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>CListBox::콘텐츠 재설정

목록 상자에서 모든 항목을 제거합니다.

```cpp
void ResetContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>CListBox::선택 문자열

지정된 문자열과 일치하는 목록 상자 항목을 검색하고 일치하는 항목이 발견되면 항목을 선택합니다.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞에 항목의 0기반 인덱스를 포함합니다. 검색이 목록 상자의 맨 아래에 도달하면 목록 상자 의 맨 위에서 *nStartAfter에*의해 지정된 항목으로 다시 계속됩니다. *nStartAfter가* -1이면 전체 목록 상자가 처음부터 검색됩니다.

*lpszItem*<br/>
검색할 접두사가 포함된 null 종료 된 문자열을 가리킵니다. 검색은 대/소문자독립적이므로 이 문자열에는 대문자와 소문자의 조합이 포함될 수 있습니다.

### <a name="return-value"></a>Return Value

검색에 성공한 경우 선택한 항목의 인덱스입니다. 검색에 실패한 경우 반환 값이 LB_ERR 현재 선택 영역은 변경되지 않습니다.

### <a name="remarks"></a>설명

필요한 경우 목록 상자가 스크롤되어 선택한 항목을 볼 수 있습니다.

이 멤버 함수는 [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 목록 상자와 함께 사용할 수 없습니다.

항목의 초기 문자(시작 점에서)가 *lpszItem*에서 지정한 문자열의 문자와 일치하는 경우에만 항목이 선택됩니다.

멤버 `FindString` 함수를 사용하여 항목을 선택하지 않고 문자열을 찾습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>CListBox::셀아이템레인지

다중 선택 목록 상자에서 여러 연속 항목을 선택합니다.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>매개 변수

*bSelect*<br/>
선택 영역을 설정하는 방법을 지정합니다. *bSelect가* TRUE이면 문자열이 선택되고 강조 표시됩니다. FALSE이면 강조 표시가 제거되고 문자열이 더 이상 선택되지 않습니다.

*nFirstItem*<br/>
설정할 첫 번째 항목의 0기반 인덱스를 지정합니다.

*nLastItem*<br/>
설정할 마지막 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

이 멤버 함수는 여러 선택 목록 상자에서만 사용합니다. 여러 선택 목록 상자에서 하나의 항목만 선택해야 하는 경우(즉, *nFirstItem이* *nLastItem과* 동일한 경우) [대신 SetSel](#setsel) 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox::세트앵커인덱스

확장 된 선택을 시작 하려면 여러 선택 목록 상자에 앵커를 설정 합니다.

```cpp
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
앵커가 될 목록 상자 항목의 0기반 인덱스를 지정합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에서 앵커 항목은 연속선택 항목 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox::셋케어인덱스

포커스 사각형을 여러 선택 목록 상자의 지정된 인덱스에서 항목으로 설정합니다.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 포커스 사각형을 수신하도록 항목의 0기반 인덱스를 지정합니다.

*bScroll*<br/>
이 값이 0이면 항목이 완전히 표시될 때까지 스크롤됩니다. 이 값이 0이 아닌 경우 항목이 적어도 부분적으로 표시될 때까지 스크롤됩니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

항목이 표시되지 않으면 보기로 스크롤됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox::설정열 폭

다중 열 목록 [상자(LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 작성됨)에서 모든 열의 픽셀로 너비를 설정합니다.

```cpp
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>매개 변수

*cxWidth*<br/>
모든 열의 너비를 픽셀로 지정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>CListBox::세트커셀

필요한 경우 문자열을 선택하고 보기로 스크롤합니다.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>매개 변수

*nSelect*<br/>
선택할 문자열의 0기반 인덱스를 지정합니다. *nSelect가* -1이면 목록 상자에 선택 항목이 없는 것으로 설정됩니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

새 문자열을 선택하면 목록 상자에서 이전에 선택한 문자열에서 강조 표시가 제거됩니다.

단일 선택 목록 상자에서만 이 멤버 함수를 사용합니다.

여러 선택 목록 상자에서 선택 영역을 설정하거나 제거하려면 [CListBox::SetSel](#setsel)을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox::설정수평익

목록 상자를 가로로 스크롤할 수 있는 너비를 픽셀 단위로 설정합니다.

```cpp
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>매개 변수

*cxExtent*<br/>
목록 상자를 가로로 스크롤할 수 있는 픽셀 수를 지정합니다.

### <a name="remarks"></a>설명

목록 상자의 크기가 이 값보다 작으면 가로 스크롤 막대가 목록 상자의 항목을 가로로 스크롤합니다. 목록 상자가 이 값보다 크거나 크면 가로 스크롤 막대가 숨김으로 표시됩니다.

호출에 `SetHorizontalExtent`응답하려면 목록 상자가 [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) 스타일로 정의되어 있어야 합니다.

이 멤버 함수는 다중 열 목록 상자에 유용하지 않습니다. 다중 열 목록 상자의 `SetColumnWidth` 경우 멤버 함수를 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox:::세트항목데이터

목록 상자에서 지정된 항목과 연결된 값을 설정합니다.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0기반 인덱스를 지정합니다.

*dwItemData*<br/>
항목과 연결할 값을 지정합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox::셋아이템데이터Ptr

목록 상자의 지정된 항목과 연결된 32비트 값을 지정된 포인터(void)로 **void** <strong>\*</strong>설정합니다.

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 0기반 인덱스를 지정합니다.

*Pdata*<br/>
항목과 연결될 포인터를 지정합니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

이 포인터는 항목이 추가되거나 제거될 때 목록 상자 내의 항목의 상대적인 위치가 변경될 수 있더라도 목록 상자의 수명 동안 유효합니다. 따라서 상자 내의 항목 인덱스가 변경될 수 있지만 포인터는 안정적으로 유지됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox::세트항목높이

목록 상자에 있는 항목의 높이를 설정합니다.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에 항목의 0기반 인덱스를 지정합니다. 이 매개 변수는 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이 있는 경우에만 사용됩니다. 그렇지 않으면 0으로 설정해야 합니다.

*cyItemHeight*<br/>
항목의 높이(픽셀)를 지정합니다.

### <a name="return-value"></a>Return Value

인덱스 또는 높이가 잘못된 지 LB_ERR.

### <a name="remarks"></a>설명

목록 상자에 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 경우 이 함수는 *nIndex*로 지정된 항목의 높이를 설정합니다. 그렇지 않으면 이 함수는 목록 상자에 있는 모든 항목의 높이를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>CListBox::설정 로컬

이 목록 상자에 대한 로캘 식별자를 설정합니다.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>매개 변수

*nNewLocale*<br/>
목록 상자에 대해 설정할 새 로캘 식별자(LCID) 값입니다.

### <a name="return-value"></a>Return Value

이 목록 상자에 대한 이전 로캘 식별자(LCID) 값입니다.

### <a name="remarks"></a>설명

호출되지 않으면 `SetLocale` 기본 로캘이 시스템에서 가져옵니다. 이 시스템 기본 로캘은 제어판의 지역(또는 국제) 응용 프로그램을 사용하여 수정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>CListBox::Setsel

다중 선택 목록 상자에서 문자열을 선택합니다.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
설정할 문자열의 0기반 인덱스를 포함합니다. -1이면 *bSelect*값에 따라 선택 영역이 모든 문자열에 추가되거나 제거됩니다.

*bSelect*<br/>
선택 영역을 설정하는 방법을 지정합니다. *bSelect가* TRUE이면 문자열이 선택되고 강조 표시됩니다. FALSE이면 강조 표시가 제거되고 문자열이 더 이상 선택되지 않습니다. 지정된 문자열이 선택되고 기본적으로 강조 표시됩니다.

### <a name="return-value"></a>Return Value

오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

이 멤버 함수는 여러 선택 목록 상자에서만 사용합니다.

단일 선택 목록 상자에서 항목을 선택하려면 [CListBox::SetCurSel](#setcursel)을 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>CListBox::SetTabstops

목록 상자에서 탭 중지 위치를 설정합니다.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>매개 변수

*cxEachStop*<br/>
탭 중지는 모든 *cxEachStop* 대화 상자 단위에서 설정됩니다. 대화 상자 장치에 대한 설명은 *rgTabStops를* 참조하십시오.

*nTabStops*<br/>
목록 상자에 있을 탭 중지 수를 지정합니다.

*rgTabStops*<br/>
대화 상자 단위의 탭 중지 위치를 포함하는 정수 배열의 첫 번째 멤버를 가리킵니다. 대화 상자는 수평 또는 수직 거리입니다. 하나의 가로 대화 상자 단위는 현재 대화 상자 기본 너비 단위의 1/4과 같으며 한 수직 대화 상자 단위는 현재 대화 상자 기본 높이 단위의 1/8과 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 높이와 너비를 기준으로 계산됩니다. Windows `GetDialogBaseUnits` 함수는 현재 대화 상자 기본 단위를 픽셀 단위로 반환합니다. 탭 중지는 증가 순서로 정렬되어야 합니다. 뒤로 탭은 허용되지 않습니다.

### <a name="return-value"></a>Return Value

모든 탭이 설정된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

탭 중지를 2개의 대화 상자 단위의 기본 크기로 설정하려면 이 멤버 함수의 매개 변수 없는 버전을 호출합니다. 탭 중지를 2가 아닌 다른 크기로 설정하려면 *cxEachStop* 인수가 있는 버전을 호출합니다.

탭 중지를 크기 배열로 설정하려면 *rgTabStops* 및 *nTabStops* 인수가 있는 버전을 사용합니다. 탭 중지는 *nTabStops에*의해 지정된 숫자까지 *rgTabStops의*각 값에 대해 설정됩니다.

`SetTabStops` 멤버 함수호출에 응답하려면 목록 상자가 [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 만들어졌어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>CListBox::셋탑인덱스

특정 목록 상자 항목이 표시되는지 확인합니다.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

성공하면 0이거나 오류가 발생하면 LB_ERR.

### <a name="remarks"></a>설명

*nIndex로* 지정된 항목이 목록 상자 의 맨 위에 나타나거나 최대 스크롤 범위에 도달할 때까지 시스템은 목록 상자를 스크롤합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>CListBox::VKeyToItem

목록 상자의 부모 창 목록 상자에서 WM_VKEYTOITEM 메시지를 받을 때 프레임 워크에 의해 호출 됩니다.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 누른 키의 가상 키 코드입니다. 표준 가상 키 코드 목록은 Winuser.h를 참조하십시오.

*nIndex*<br/>
목록 상자 카류의 현재 위치입니다.

### <a name="return-value"></a>Return Value

추가 동작에 대해 2, 기본 동작에 대해 1 또는 음수가 아닌 값을 반환하여 키 입력에 대한 기본 작업을 수행할 목록 상자 항목의 인덱스를 지정합니다.

### <a name="remarks"></a>설명

WM_VKEYTOITEM 메시지는 WM_KEYDOWN 메시지를 받을 때 목록 상자에서 전송되지만 목록 상자가 다음 두 가지 모두를 충족하는 경우에만 전송됩니다.

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일 세트가 있습니다.

- 항목이 하나 이상 있습니다.

이 함수를 직접 호출해서는 안 됩니다. 이 함수를 재정의하여 키보드 메시지를 사용자 지정처리합니다.

재정의가 수행한 작업을 프레임워크에 알리기 위해 값을 반환해야 합니다. 반환 값 - 2는 응용 프로그램이 항목을 선택하는 모든 측면을 처리했음을 나타내며 목록 상자에서 추가 작업이 필요하지 않음을 나타냅니다. 반환하기 전에 - 2, 당신은 선택을 설정하거나 캐리트 또는 둘 다 를 이동할 수 있습니다. 선택 항목을 설정하려면 [SetCursel](#setcursel) 또는 [SetSel을](#setsel)사용합니다. 카를트 이동하려면 [SetCaretIndex](#setcaretindex)를 사용합니다.

반환 값 -1은 목록 상자가 키 입력에 대한 응답으로 기본 작업을 수행해야 함을 나타냅니다. 기본 구현반환 - 1.

반환 값이 0 이상이면 목록 상자에 있는 항목의 인덱스를 지정하고 목록 상자에서 지정된 항목의 키 입력에 대한 기본 작업을 수행해야 함을 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[C스크롤바 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[정적 클래스](../../mfc/reference/cstatic-class.md)
