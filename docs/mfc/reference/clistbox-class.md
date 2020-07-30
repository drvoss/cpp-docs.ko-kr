---
title: CListBox 클래스
description: MFC CListBox 클래스 및 해당 멤버 함수에 대 한 설명입니다.
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
ms.openlocfilehash: 30f28db746856303e10709417ad7545376fd4812
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231808"
---
# <a name="clistbox-class"></a>CListBox 클래스

Windows 목록 상자의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CListBox : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|Name|설명|
|----------|-----------------|
|[CListBox::CListBox](#clistbox)|`CListBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CListBox::AddString](#addstring)|목록 상자에 문자열을 추가 합니다.|
|[CListBox::CharToItem](#chartoitem)|문자열이 없는 소유자 그리기 목록 상자에 대 한 사용자 지정 WM_CHAR 처리를 제공 하려면를 재정의 합니다.|
|[CListBox::CompareItem](#compareitem)|정렬 된 소유자 그리기 목록 상자에서 새 항목의 위치를 확인 하기 위해 프레임 워크에서 호출 됩니다.|
|[CListBox::Create](#create)|Windows 목록 상자를 만들고 개체에 연결 `CListBox` 합니다.|
|[CListBox::DeleteItem](#deleteitem)|사용자가 소유자 그리기 목록 상자에서 항목을 삭제할 때 프레임 워크에서 호출 됩니다.|
|[CListBox::DeleteString](#deletestring)|목록 상자에서 문자열을 삭제 합니다.|
|[CListBox::Dir](#dir)|현재 디렉터리에 있는 파일 이름, 드라이브 또는 둘 다를 목록 상자에 추가 합니다.|
|[CListBox::DrawItem](#drawitem)|소유자 그리기 목록 상자의 시각적 측면이 변경 될 때 프레임 워크에서 호출 됩니다.|
|[CListBox::FindString](#findstring)|목록 상자에서 문자열을 검색 합니다.|
|[CListBox::FindStringExact](#findstringexact)|지정 된 문자열과 일치 하는 첫 번째 목록 상자 문자열을 찾습니다.|
|[CListBox::GetAnchorIndex](#getanchorindex)|목록 상자에서 현재 앵커 항목의 0부터 시작 하는 인덱스를 검색 합니다.|
|[CListBox::GetCaretIndex](#getcaretindex)|다중 선택 목록 상자에서 포커스 사각형이 있는 항목의 인덱스를 확인 합니다.|
|[CListBox::GetCount](#getcount)|목록 상자에 있는 문자열의 수를 반환 합니다.|
|[CListBox::GetCurSel](#getcursel)|목록 상자에서 현재 선택 된 문자열의 인덱스 (0부터 시작)를 반환 합니다.|
|[CListBox::GetHorizontalExtent](#gethorizontalextent)|목록 상자를 가로로 스크롤할 수 있는 너비 (픽셀)를 반환 합니다.|
|[CListBox::GetItemData](#getitemdata)|목록 상자 항목과 연결 된 값을 반환 합니다.|
|[CListBox::GetItemDataPtr](#getitemdataptr)|목록 상자 항목에 대 한 포인터를 반환 합니다.|
|[CListBox::GetItemHeight](#getitemheight)|목록 상자에 있는 항목의 높이를 결정 합니다.|
|[CListBox::GetItemRect](#getitemrect)|현재 표시 되는 목록 상자 항목의 경계 사각형을 반환 합니다.|
|[CListBox::GetListBoxInfo](#getlistboxinfo)|열당 항목 수를 검색 합니다.|
|[CListBox:: GetLocale](#getlocale)|목록 상자에 대 한 로캘 식별자를 검색 합니다.|
|[CListBox:: GetSel](#getsel)|목록 상자 항목의 선택 상태를 반환 합니다.|
|[CListBox::GetSelCount](#getselcount)|다중 선택 목록 상자에서 현재 선택 된 문자열 수를 반환 합니다.|
|[CListBox::GetSelItems](#getselitems)|목록 상자에서 현재 선택 되어 있는 문자열의 인덱스를 반환 합니다.|
|[CListBox::GetText](#gettext)|목록 상자 항목을 버퍼에 복사 합니다.|
|[CListBox:: GetTextLen](#gettextlen)|목록 상자 항목의 길이 (바이트)를 반환 합니다.|
|[CListBox:: GetTopIndex](#gettopindex)|목록 상자에 표시 되는 첫 번째 문자열의 인덱스를 반환 합니다.|
|[CListBox::InitStorage](#initstorage)|목록 상자 항목 및 문자열에 대 한 메모리 블록을 미리 할당 합니다.|
|[CListBox::InsertString](#insertstring)|목록 상자의 특정 위치에 문자열을 삽입 합니다.|
|[CListBox::ItemFromPoint](#itemfrompoint)|지정 된 지점에 가장 가까운 목록 상자 항목의 인덱스를 반환 합니다.|
|[CListBox:: MeasureItem](#measureitem)|목록 상자 차원을 결정 하기 위해 소유자 그리기 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.|
|[CListBox::ResetContent](#resetcontent)|목록 상자에서 모든 항목을 지웁니다.|
|[CListBox:: SelectString](#selectstring)|단일 선택 목록 상자에서 문자열을 검색 하 고 선택 합니다.|
|[CListBox::SelItemRange](#selitemrange)|다중 선택 목록 상자에서 문자열 범위를 선택 하거나 선택 취소 합니다.|
|[CListBox:: SetAnchorIndex](#setanchorindex)|다중 선택 목록 상자에 앵커를 설정 하 여 확장 된 선택 영역을 시작 합니다.|
|[CListBox:: SetCaretIndex](#setcaretindex)|여러 선택 목록 상자의 지정 된 인덱스에 있는 항목에 포커스 영역을 설정 합니다.|
|[CListBox:: SetColumnWidth](#setcolumnwidth)|여러 열로 된 목록 상자의 열 너비를 설정 합니다.|
|[CListBox:: SetCurSel](#setcursel)|목록 상자 문자열을 선택 합니다.|
|[CListBox::SetHorizontalExtent](#sethorizontalextent)|목록 상자를 가로로 스크롤할 수 있는 너비 (픽셀)를 설정 합니다.|
|[CListBox:: SetItemData](#setitemdata)|목록 상자 항목과 연결 된 값을 설정 합니다.|
|[CListBox:: SetItemDataPtr](#setitemdataptr)|목록 상자 항목에 대 한 포인터를 설정 합니다.|
|[CListBox::SetItemHeight](#setitemheight)|목록 상자에 있는 항목의 높이를 설정 합니다.|
|[CListBox:: SetLocale](#setlocale)|목록 상자에 대 한 로캘 식별자를 설정 합니다.|
|[CListBox:: SetSel](#setsel)|다중 선택 목록 상자에서 목록 상자 항목을 선택 하거나 선택 취소 합니다.|
|[CListBox::SetTabStops](#settabstops)|목록 상자에서 탭 정지 위치를 설정 합니다.|
|[CListBox::SetTopIndex](#settopindex)|목록 상자에 표시 되는 첫 번째 문자열의 인덱스 (0부터 시작)를 설정 합니다.|
|[CListBox::VKeyToItem](#vkeytoitem)|LBS_WANTKEYBOARDINPUT 스타일 집합을 사용 하 여 목록 상자에 대 한 사용자 지정 WM_KEYDOWN 처리를 제공 하도록 재정의 합니다.|

## <a name="remarks"></a>설명

목록 상자에는 사용자가 보고 선택할 수 있는 항목의 목록 (예: 파일 이름)이 표시 됩니다.

단일 선택 목록 상자에서 사용자는 한 항목만 선택할 수 있습니다. 다중 선택 목록 상자에서 항목 범위를 선택할 수 있습니다. 사용자가 항목을 선택 하면 강조 표시 되 고 목록 상자에서 부모 창에 알림 메시지를 보냅니다.

대화 상자 템플릿에서 또는 코드에서 직접 목록 상자를 만들 수 있습니다. 직접 만들려면 개체를 생성 `CListBox` 한 다음 [create](#create) member 함수를 호출 하 여 Windows 목록 상자 컨트롤을 만들고이를 개체에 연결 `CListBox` 합니다. 대화 상자 템플릿에서 목록 상자를 사용 하려면 대화 상자 클래스에서 목록 상자 변수를 선언한 다음 `DDX_Control` 대화 상자 클래스의 함수에서를 사용 `DoDataExchange` 하 여 멤버 변수를 컨트롤에 연결 합니다. 이 작업은 대화 상자 클래스에 컨트롤 변수를 추가할 때 자동으로 수행 됩니다.

생성은에서 파생 된 클래스의 단일 단계 프로세스가 될 수 있습니다 `CListBox` . 파생 클래스에 대 한 생성자를 작성 하 고 `Create` 생성자 내에서를 호출 합니다.

목록 상자에서 부모 (일반적으로 [CDialog](../../mfc/reference/cdialog-class.md)에서 파생 된 클래스)로 보낸 Windows 알림 메시지를 처리 하려면 각 메시지의 부모 클래스에 메시지 매핑 항목과 메시지 처리기 멤버 함수를 추가 합니다.

각 메시지 맵 항목은 다음 형식을 사용 합니다.

`ON_Notification( id, memberFxn )`

여기서는 `id` 알림을 보내는 목록 상자 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 는 알림을 처리 하기 위해 작성 한 부모 멤버 함수의 이름입니다.

부모의 함수 프로토타입은 다음과 같습니다.

`afx_msg void memberFxn( );`

다음은 잠재적 메시지 맵 항목과 부모 항목으로 전송 되는 사례에 대 한 설명 목록입니다.

- ON_LBN_DBLCLK 사용자가 목록 상자에서 문자열을 두 번 클릭 합니다. [LBS_NOTIFY](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 목록 상자 에서만이 알림 메시지를 보냅니다.

- ON_LBN_ERRSPACE 목록 상자에서 요청을 충족 하는 데 충분 한 메모리를 할당할 수 없습니다.

- ON_LBN_KILLFOCUS 목록 상자에서 입력 포커스가 손실 됩니다.

- ON_LBN_SELCANCEL 현재 목록 상자 선택이 취소 됩니다. 이 메시지는 목록 상자에 LBS_NOTIFY 스타일이 있는 경우에만 전송 됩니다.

- 목록 상자에서 선택 항목이 변경 된 ON_LBN_SELCHANGE 합니다. [CListBox:: SetCurSel](#setcursel) 멤버 함수에서 선택을 변경 하는 경우에는이 알림이 전송 되지 않습니다. 이 알림은 LBS_NOTIFY 스타일이 있는 목록 상자에만 적용 됩니다. 선택 영역이 변경 되지 않는 경우에도 사용자가 화살표 키를 누를 때마다 다중 선택 목록 상자에 대 한 LBN_SELCHANGE 알림 메시지가 전송 됩니다.

- 목록 상자에서 입력 포커스를 받고 ON_LBN_SETFOCUS 합니다.

- 문자열이 없는 소유자 그리기 목록 상자 ON_WM_CHARTOITEM WM_CHAR 메시지를 받습니다.

- LBS_WANTKEYBOARDINPUT 스타일을 사용 하 여 목록 상자를 ON_WM_VKEYTOITEM WM_KEYDOWN 메시지가 수신 됩니다.

대화 상자 `CListBox` 내에서 개체를 만드는 경우 (대화 상자 리소스를 통해) `CListBox` 사용자가 대화 상자를 닫으면 개체가 자동으로 소멸 됩니다.

`CListBox`창 내에서 개체를 만드는 경우 개체를 제거 해야 할 수 있습니다 `CListBox` . 스택에서 개체를 만들면 `CListBox` 자동으로 제거 됩니다. `CListBox`함수를 사용 하 여 힙에서 개체를 만드는 경우 **`new`** **`delete`** 사용자가 부모 창을 닫을 때 개체에 대해를 호출 하 여 개체를 제거 해야 합니다.

개체에 메모리를 할당 하는 경우 `CListBox` 소멸자를 재정의 `CListBox` 하 여 할당을 삭제 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CListBox`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="clistboxaddstring"></a><a name="addstring"></a>CListBox:: AddString

목록 상자에 문자열을 추가 합니다.

```
int AddString(LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
추가 될 null로 끝나는 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

목록 상자에 있는 문자열의 인덱스 (0부터 시작)입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR입니다. 새 문자열을 저장 하는 데 사용할 수 있는 공간이 부족 한 경우 반환 값은 LB_ERRSPACE입니다.

### <a name="remarks"></a>설명

[LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일로 목록 상자를 만들지 않은 경우 문자열이 목록의 끝에 추가 됩니다. 그렇지 않으면 문자열이 목록에 삽입 되 고 목록이 정렬 됩니다. 목록 상자가 LBS_SORT 스타일을 사용 하 여 만들어졌지만 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 아닌 경우 프레임 워크는 멤버 함수에 대 한 하나 이상의 호출로 목록을 정렬 합니다 `CompareItem` .

[Insertstring](#insertstring) 을 사용 하 여 목록 상자 내의 특정 위치에 문자열을 삽입 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#3](../../mfc/codesnippet/cpp/clistbox-class_1.cpp)]

## <a name="clistboxchartoitem"></a><a name="chartoitem"></a>CListBox:: CharToItem

목록 상자의 부모 창이 목록 상자에서 WM_CHARTOITEM 메시지를 받을 때 프레임 워크에서 호출 됩니다.

```
virtual int CharToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 입력 한 문자의 ANSI 코드입니다.

*nIndex*<br/>
목록 상자 캐럿의 현재 위치입니다.

### <a name="return-value"></a>Return Value

추가 작업을 수행 하지 않으려면-1 또는-2를 반환 하 고 키 입력에 대 한 기본 작업을 수행할 목록 상자 항목의 인덱스를 지정 하려면 음수를 반환 합니다. 기본 구현에서는-1을 반환 합니다.

### <a name="remarks"></a>설명

WM_CHARTOITEM 메시지는 목록 상자가 다음 조건을 모두 충족 하는 경우에만 목록 상자에서 WM_CHAR 메시지를 받을 때 전송 됩니다.

- 는 소유자 그리기 목록 상자입니다.

- 에 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 설정 되지 않은 경우

- 에 항목이 하나 이상 있습니다.

이 함수는 직접 호출 하면 안 됩니다. 키보드 메시지의 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다.

재정의에서 작업을 수행 하는 작업을 프레임 워크에 알리기 위해 값을 반환 해야 합니다. 반환 값-1 또는-2는 항목을 선택 하는 모든 측면을 처리 하 고 목록 상자에서 추가 작업을 수행 하지 않음을 나타냅니다. -1 또는-2를 반환 하기 전에 선택 항목을 설정 하거나 캐럿 또는 둘 다를 이동할 수 있습니다. 선택 항목을 설정 하려면 [Setcursel](#setcursel) 또는 [setsel](#setsel)을 사용 합니다. 캐럿을 이동 하려면 [SetCaretIndex](#setcaretindex)를 사용 합니다.

반환 값이 0 이상인 경우 목록 상자에 있는 항목의 인덱스를 지정 하 고 목록 상자에서 지정 된 항목의 키 입력에 대 한 기본 작업을 수행 해야 함을 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#4](../../mfc/codesnippet/cpp/clistbox-class_2.cpp)]

## <a name="clistboxclistbox"></a><a name="clistbox"></a>CListBox:: CListBox

`CListBox` 개체를 생성합니다.

```
CListBox();
```

### <a name="remarks"></a>설명

`CListBox`두 단계로 개체를 구성 합니다. 먼저 생성자를 호출한 `ClistBox` 다음 `Create` Windows 목록 상자를 초기화 하 고에 연결 하는를 호출 `CListBox` 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#1](../../mfc/codesnippet/cpp/clistbox-class_3.cpp)]

## <a name="clistboxcompareitem"></a><a name="compareitem"></a>CListBox:: CompareItem

정렬 된 소유자 그리기 목록 상자에서 새 항목의 상대 위치를 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpCompareItemStruct*<br/>
구조체에 대 한 긴 포인터 `COMPAREITEMSTRUCT` 입니다.

### <a name="return-value"></a>Return Value

[Compareitemstruct](/windows/win32/api/winuser/ns-winuser-compareitemstruct) 구조체에 설명 된 두 항목의 상대 위치를 나타냅니다. 다음 값 중 하나일 수 있습니다.

|값|의미|
|-----------|-------------|
|-1|항목 1은 항목 2 앞에 정렬 됩니다.|
|0|항목 1과 항목 2는 동일 하 게 정렬 됩니다.|
|1|항목 1은 항목 2 뒤에 정렬 됩니다.|

구조체에 대 한 설명은 [CWnd:: OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) 을 참조 하십시오 `COMPAREITEMSTRUCT` .

### <a name="remarks"></a>설명

기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. LBS_SORT 스타일을 사용 하 여 소유자 그리기 목록 상자를 만드는 경우 목록 상자에 추가 된 새 항목을 정렬 하는 데 프레임 워크를 지원 하려면이 멤버 함수를 재정의 해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#5](../../mfc/codesnippet/cpp/clistbox-class_4.cpp)]

## <a name="clistboxcreate"></a><a name="create"></a>CListBox:: Create

Windows 목록 상자를 만들고 개체에 연결 `CListBox` 합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
목록 상자의 스타일을 지정 합니다. 상자에 [목록 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 의 조합을 적용 합니다.

*rect*<br/>
목록 상자 크기와 위치를 지정 합니다. 는 `CRect` 개체 또는 구조체 일 수 있습니다 `RECT` .

*pParentWnd*<br/>
목록 상자의 부모 창 (일반적으로 개체)을 지정 합니다 `CDialog` . NULL이 아니어야 합니다.

*nID*<br/>
목록 상자의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`CListBox`두 단계로 개체를 구성 합니다. 먼저 생성자를 호출한 다음 `Create` Windows 목록 상자를 초기화 하 여 개체에 연결 하는를 호출 합니다 `CListBox` .

가 `Create` 실행 되 면 Windows는 목록 상자 컨트롤에 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 메시지를 보냅니다.

이러한 메시지는 기본적으로 기본 클래스의 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 함수에 의해 처리 됩니다 `CWnd` . 기본 메시지 처리를 확장 하려면에서 클래스를 파생 시키고 `CListBox` , 메시지 맵을 새 클래스에 추가 하 고, 앞의 메시지 처리기 멤버 함수를 재정의 합니다. 예를 들어를 재정의 하 `OnCreate` 여 새 클래스에 필요한 초기화를 수행 합니다.

다음 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 을 목록 상자 컨트롤에 적용 합니다.

- 항상 WS_CHILD

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의 없음

- 세로 스크롤 막대를 추가 WS_VSCROLL

- 가로 스크롤 막대를 추가 WS_HSCROLL

- 컨트롤을 그룹화 WS_GROUP

- 이 컨트롤의 탭 이동을 허용 WS_TABSTOP

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#2](../../mfc/codesnippet/cpp/clistbox-class_5.cpp)]

## <a name="clistboxdeleteitem"></a><a name="deleteitem"></a>CListBox::D eleteItem

사용자가 소유자 그리기 개체에서 항목을 삭제 `CListBox` 하거나 목록 상자를 소멸 시키는 경우 프레임 워크에서 호출 됩니다.

```
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDeleteItemStruct*<br/>
삭제 된 항목에 대 한 정보를 포함 하는 Windows [Deleteitemstruct](/windows/win32/api/winuser/ns-winuser-deleteitemstruct) 구조체에 대 한 긴 포인터입니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 필요에 따라 소유자 그리기 목록 상자를 다시 그리려면이 함수를 재정의 합니다.

구조체에 대 한 설명은 [CWnd:: OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) 을 참조 하십시오 `DELETEITEMSTRUCT` .

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#6](../../mfc/codesnippet/cpp/clistbox-class_6.cpp)]

## <a name="clistboxdeletestring"></a><a name="deletestring"></a>CListBox::D eleteString

목록 상자에서 *n 인덱스* 위치에 있는 항목을 삭제 합니다.

```
int DeleteString(UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
삭제할 문자열의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

목록에 남아 있는 문자열의 수입니다. *Nindex* 가 목록의 항목 수보다 많은 인덱스를 지정 하는 경우 반환 값은 LB_ERR입니다.

### <a name="remarks"></a>설명

*N 인덱스* 다음에 나오는 모든 항목은 이제 한 위치 아래로 이동 합니다. 예를 들어 목록 상자에 두 항목이 포함 된 경우 첫 번째 항목을 삭제 하면 나머지 항목이 현재 첫 번째 위치에 있게 됩니다. 첫 번째 위치에 있는 항목의 경우 *n 인덱스*= 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#7](../../mfc/codesnippet/cpp/clistbox-class_7.cpp)]

## <a name="clistboxdir"></a><a name="dir"></a>CListBox: ir:D

목록 상자에 파일 이름, 드라이브 또는 둘 다의 목록을 추가 합니다.

```
int Dir(
    UINT attr,
    LPCTSTR lpszWildCard);
```

### <a name="parameters"></a>매개 변수

*attr*<br/>
는 **`enum`** s에 설명 된 값의 조합 `CFile::GetStatu` [s](../../mfc/reference/cfile-class.md#getstatus)이거나 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|0x0000|파일을 읽거나 쓸 수 있습니다.|
|0x0001|파일은 읽을 수 있지만 쓸 수는 없습니다.|
|0x0002|파일이 숨겨져 있고 디렉터리 목록에 표시 되지 않습니다.|
|0x0004|파일이 시스템 파일입니다.|
|0x0010|*LpszWildCard* 로 지정 된 이름은 디렉터리를 지정 합니다.|
|0x0020|파일이 보관 되었습니다.|
|0x4000|*LpszWildCard*으로 지정 된 이름과 일치 하는 모든 드라이브를 포함 합니다.|
|0x8000|Exclusive 플래그입니다. Exclusive 플래그가 설정 된 경우 지정 된 형식의 파일만 나열 됩니다. 그렇지 않으면 지정 된 형식의 파일이 "normal" 파일 외에 나열 됩니다.|

*lpszWildCard*<br/>
는 파일 사양 문자열을 가리킵니다. 문자열은 와일드 카드를 포함할 수 있습니다 (예: *. \* ).

### <a name="return-value"></a>Return Value

목록에 추가 된 마지막 파일 이름의 인덱스 (0부터 시작)입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR입니다. 새 문자열을 저장 하는 데 사용할 수 있는 공간이 부족 한 경우 반환 값은 LB_ERRSPACE입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#8](../../mfc/codesnippet/cpp/clistbox-class_8.cpp)]

## <a name="clistboxdrawitem"></a><a name="drawitem"></a>CListBox::D rawItem

소유자 그리기 목록 상자의 시각적 측면이 변경 될 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 그리기 형식에 대 한 정보를 포함 하는 [Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조체에 대 한 긴 포인터입니다.

### <a name="remarks"></a>설명

`itemAction` `itemState` 구조체의 및 멤버는 `DRAWITEMSTRUCT` 수행할 그리기 작업을 정의 합니다.

기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기 개체에 대 한 그리기를 구현 하려면이 멤버 함수를 재정의 `CListBox` 합니다. 응용 프로그램은이 멤버 함수가 종료 되기 전에 *Lpdrawitemstruct* 에 제공 된 표시 컨텍스트에 대해 선택한 모든 GDI (그래픽 장치 인터페이스) 개체를 복원 해야 합니다.

구조체에 대 한 설명은 [CWnd:: OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 를 참조 하세요 `DRAWITEMSTRUCT` .

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#9](../../mfc/codesnippet/cpp/clistbox-class_9.cpp)]

## <a name="clistboxfindstring"></a><a name="findstring"></a>CListBox:: FindString

목록 상자 선택을 변경 하지 않고 목록 상자에서 지정 된 접두사를 포함 하는 첫 번째 문자열을 찾습니다.

```
int FindString(
    int nStartAfter,
    LPCTSTR lpszItem) const;
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞의 항목에 대 한 0부터 시작 하는 인덱스를 포함 합니다. 검색은 목록 상자의 아래쪽에 도달 하면 목록 상자의 맨 위에서 *Nstartafter*로 지정 된 항목으로 다시 계속 됩니다. *Nstartafter* 가-1 이면 전체 목록 상자를 처음부터 검색 합니다.

*lpszItem*<br/>
검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색은 대/소문자를 구분 하지 않으므로이 문자열에는 대 문자와 소문자를 조합 하 여 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

일치 하는 항목의 인덱스 (0부터 시작) 이거나, 검색에 실패 한 경우 LB_ERR입니다.

### <a name="remarks"></a>설명

[Selectstring](#selectstring) 멤버 함수를 사용 하 여 문자열을 찾고 선택 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#10](../../mfc/codesnippet/cpp/clistbox-class_10.cpp)]

## <a name="clistboxfindstringexact"></a><a name="findstringexact"></a>CListBox:: FindStringExact

*LpszFind*에 지정 된 문자열과 일치 하는 첫 번째 목록 상자 문자열을 찾습니다.

```
int FindStringExact(
    int nIndexStart,
    LPCTSTR lpszFind) const;
```

### <a name="parameters"></a>매개 변수

*nIndexStart*<br/>
검색할 첫 번째 항목 앞에 있는 항목의 인덱스 (0부터 시작)를 지정 합니다. 검색은 목록 상자의 아래쪽에 도달 하면 목록 상자 맨 위에서 *Nindexstart*로 지정 된 항목으로 다시 계속 됩니다. *Nindexstart* 가-1 인 경우 전체 목록 상자를 처음부터 검색 합니다.

*lpszFind*<br/>
검색할 null로 끝나는 문자열을 가리킵니다. 이 문자열에는 확장명을 포함 하 여 전체 파일 이름이 포함 될 수 있습니다. 검색은 대/소문자를 구분 하지 않으므로 문자열에는 대 문자와 소문자의 모든 조합이 포함 될 수 있습니다.

### <a name="return-value"></a>Return Value

일치 항목의 인덱스 이거나, 검색에 실패 한 경우 LB_ERR입니다.

### <a name="remarks"></a>설명

목록 상자가 소유자 그리기 스타일로 만들어졌지만 [LBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 없으면 `FindStringExact` 멤버 함수는 *lpszFind*의 값과 비교 하 여 더블 워드 값을 찾으려고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#11](../../mfc/codesnippet/cpp/clistbox-class_11.cpp)]

## <a name="clistboxgetanchorindex"></a><a name="getanchorindex"></a>CListBox:: GetAnchorIndex

목록 상자에서 현재 앵커 항목의 0부터 시작 하는 인덱스를 검색 합니다.

```
int GetAnchorIndex() const;
```

### <a name="return-value"></a>Return Value

성공 하는 경우 현재 앵커 항목의 인덱스입니다. 그렇지 않으면 LB_ERR 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에서 앵커 항목은 선택 된 연속 항목 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

  [CListBox:: SetAnchorIndex](#setanchorindex)의 예제를 참조 하세요.

## <a name="clistboxgetcaretindex"></a><a name="getcaretindex"></a>CListBox:: GetCaretIndex

다중 선택 목록 상자에서 포커스 사각형이 있는 항목의 인덱스를 확인 합니다.

```
int GetCaretIndex() const;
```

### <a name="return-value"></a>Return Value

목록 상자에 포커스 사각형이 있는 항목의 인덱스 (0부터 시작)입니다. 목록 상자가 단일 선택 목록 상자 이면 반환 값은 선택 된 항목의 인덱스입니다 (있는 경우).

### <a name="remarks"></a>설명

항목을 선택 하거나 선택할 수 없습니다.

### <a name="example"></a>예제

  [CListBox:: SetCaretIndex](#setcaretindex)의 예제를 참조 하세요.

## <a name="clistboxgetcount"></a><a name="getcount"></a>CListBox:: GetCount

목록 상자의 항목 수를 검색 합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자에 있는 항목 수 또는 오류가 발생 하는 경우 LB_ERR입니다.

### <a name="remarks"></a>설명

반환 된 개수는 마지막 항목의 인덱스 값 보다 하나 큽니다 (인덱스는 0부터 시작).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#12](../../mfc/codesnippet/cpp/clistbox-class_12.cpp)]

## <a name="clistboxgetcursel"></a><a name="getcursel"></a>CListBox:: GetCurSel

단일 선택 목록 상자에서 현재 선택 된 항목 (있는 경우)의 인덱스 (0부터 시작)를 검색 합니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

단일 선택 목록 상자 이면 현재 선택 된 항목의 인덱스 (0부터 시작)입니다. 현재 선택 된 항목이 없는 경우 LB_ERR 됩니다.

다중 선택 목록 상자에서 포커스가 있는 항목의 인덱스입니다.

### <a name="remarks"></a>설명

`GetCurSel`다중 선택 목록 상자에 대해를 호출 하지 마세요. 대신 [CListBox:: GetSelItems](#getselitems) 를 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#13](../../mfc/codesnippet/cpp/clistbox-class_13.cpp)]

## <a name="clistboxgethorizontalextent"></a><a name="gethorizontalextent"></a>CListBox:: GetHorizontalExtent

목록 상자에서 가로로 스크롤할 수 있는 너비 (픽셀)를 검색 합니다.

```
int GetHorizontalExtent() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 스크롤 가능한 너비 (픽셀)입니다.

### <a name="remarks"></a>설명

이는 목록 상자에 가로 스크롤 막대가 있는 경우에만 적용 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#14](../../mfc/codesnippet/cpp/clistbox-class_14.cpp)]

## <a name="clistboxgetitemdata"></a><a name="getitemdata"></a>CListBox:: GetItemData

지정 된 목록 상자 항목과 연결 된 응용 프로그램 제공 더블 워드 값을 검색 합니다.

```
DWORD_PTR GetItemData(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

항목과 연결 된 값 또는 오류가 발생 하는 경우 LB_ERR입니다.

### <a name="remarks"></a>설명

더블 워드 값은 [Setitemdata](#setitemdata) 호출의 *dwItemData* 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#15](../../mfc/codesnippet/cpp/clistbox-class_15.cpp)]

## <a name="clistboxgetitemdataptr"></a><a name="getitemdataptr"></a>CListBox:: GetItemDataPtr

지정 된 목록 상자 항목과 연결 된 응용 프로그램 제공 32 비트 값을 포인터로 검색 합니다 ( **`void`** <strong>\*</strong> ).

```cpp
void* GetItemDataPtr(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

포인터를 검색 하거나, 오류가 발생 하면-1을 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#16](../../mfc/codesnippet/cpp/clistbox-class_16.cpp)]

## <a name="clistboxgetitemheight"></a><a name="getitemheight"></a>CListBox:: GetItemHeight

목록 상자에 있는 항목의 높이를 결정 합니다.

```
int GetItemHeight(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 인덱스 (0부터 시작)를 지정 합니다. 이 매개 변수는 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이 있는 경우에만 사용 됩니다. 그렇지 않으면 0으로 설정 해야 합니다.

### <a name="return-value"></a>Return Value

목록 상자에 있는 항목의 높이 (픽셀)입니다. 목록 상자에 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 경우 반환 값은 *nindex*로 지정 된 항목의 높이입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#17](../../mfc/codesnippet/cpp/clistbox-class_17.cpp)]

## <a name="clistboxgetitemrect"></a><a name="getitemrect"></a>CListBox:: GetItemRect

목록 상자 창에 현재 표시 되는 대로 목록 상자 항목을 제한 하는 사각형의 크기를 검색 합니다.

```
int GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스 (0부터 시작)를 지정 합니다.

*lpRect*<br/>
항목의 목록 상자 클라이언트 좌표를 받는 [RECT 구조체](/windows/win32/api/windef/ns-windef-rect) 에 대 한 긴 포인터를 지정 합니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#18](../../mfc/codesnippet/cpp/clistbox-class_18.cpp)]

## <a name="clistboxgetlistboxinfo"></a><a name="getlistboxinfo"></a>CListBox:: GetListBoxInfo

열당 항목 수를 검색 합니다.

```
DWORD GetListBoxInfo() const;
```

### <a name="return-value"></a>Return Value

개체의 열당 항목 수 `CListBox` 입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [LB_GETLISTBOXINFO](/windows/win32/Controls/lb-getlistboxinfo) 메시지의 기능을 에뮬레이트합니다.

## <a name="clistboxgetlocale"></a><a name="getlocale"></a>CListBox:: GetLocale

목록 상자에 사용 되는 로캘을 검색 합니다.

```
LCID GetLocale() const;
```

### <a name="return-value"></a>Return Value

목록 상자에 있는 문자열의 LCID (로캘 id) 값입니다.

### <a name="remarks"></a>설명

예를 들어, 로캘는 정렬 된 목록 상자에서 문자열의 정렬 순서를 결정 하는 데 사용 됩니다.

### <a name="example"></a>예제

  [CListBox:: SetLocale](#setlocale)의 예제를 참조 하세요.

## <a name="clistboxgetsel"></a><a name="getsel"></a>CListBox:: GetSel

항목의 선택 상태를 검색 합니다.

```
int GetSel(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

지정 된 항목이 선택 된 경우 양수입니다. 그렇지 않으면 0입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 단일 및 다중 선택 목록 상자 둘 다에서 작동 합니다.

현재 선택 된 목록 상자 항목의 인덱스를 검색 하려면 [CListBox:: GetCurSel](#getcursel)을 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#19](../../mfc/codesnippet/cpp/clistbox-class_19.cpp)]

## <a name="clistboxgetselcount"></a><a name="getselcount"></a>CListBox:: GetSelCount

다중 선택 목록 상자에서 선택한 항목의 총 수를 검색 합니다.

```
int GetSelCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자에서 선택한 항목의 수입니다. 목록 상자가 단일 선택 목록 상자 이면 반환 값은 LB_ERR입니다.

### <a name="example"></a>예제

  [CListBox:: GetSelItems](#getselitems)의 예제를 참조 하세요.

## <a name="clistboxgetselitems"></a><a name="getselitems"></a>CListBox:: GetSelItems

다중 선택 목록 상자에서 선택한 항목의 항목 번호를 지정 하는 정수 배열로 버퍼를 채웁니다.

```
int GetSelItems(
    int nMaxItems,
    LPINT rgIndex) const;
```

### <a name="parameters"></a>매개 변수

*nMaxItems*<br/>
항목 번호가 버퍼에 배치 되는 선택 된 항목의 최대 수를 지정 합니다.

*rgIndex*<br/>
*NMaxItems*으로 지정 된 정수 수 만큼 충분히 많은 버퍼에 대 한 포인터를 지정 합니다.

### <a name="return-value"></a>Return Value

버퍼에 배치 된 실제 항목 수입니다. 목록 상자가 단일 선택 목록 상자 이면 반환 값은 `LB_ERR` 입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#20](../../mfc/codesnippet/cpp/clistbox-class_20.cpp)]

## <a name="clistboxgettext"></a><a name="gettext"></a>CListBox:: GetText

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
검색할 문자열의 인덱스 (0부터 시작)를 지정 합니다.

*lpszBuffer*<br/>
는 문자열을 받는 버퍼를 가리킵니다. 버퍼에는 문자열과 종료 null 문자를 위한 충분 한 공간이 있어야 합니다. 멤버 함수를 호출 하 여 문자열 크기를 미리 확인할 수 있습니다 `GetTextLen` .

*rString*<br/>
`CString` 개체에 대한 참조입니다.

### <a name="return-value"></a>Return Value

종료 null 문자를 제외한 문자열의 길이 (바이트)입니다. *Nindex* 가 유효한 인덱스를 지정 하지 않는 경우 반환 값은 LB_ERR입니다.

### <a name="remarks"></a>설명

이 멤버 함수의 두 번째 형태는 개체를 `CString` 문자열 텍스트로 채웁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#21](../../mfc/codesnippet/cpp/clistbox-class_21.cpp)]

## <a name="clistboxgettextlen"></a><a name="gettextlen"></a>CListBox:: GetTextLen

목록 상자 항목의 문자열 길이를 가져옵니다.

```
int GetTextLen(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

종료 null 문자를 제외한 문자열의 길이 (문자)입니다. *Nindex* 가 유효한 인덱스를 지정 하지 않는 경우 반환 값은 LB_ERR입니다.

### <a name="example"></a>예제

  [CListBox:: GetText](#gettext)의 예제를 참조 하세요.

## <a name="clistboxgettopindex"></a><a name="gettopindex"></a>CListBox:: GetTopIndex

목록 상자에 표시 되는 첫 번째 항목의 인덱스 (0부터 시작)를 검색 합니다.

```
int GetTopIndex() const;
```

### <a name="return-value"></a>Return Value

성공 하면 목록 상자에 표시 되는 첫 번째 항목의 0부터 시작 하는 인덱스이 고, 그렇지 않으면 LB_ERR입니다.

### <a name="remarks"></a>설명

처음에는 항목 0이 목록 상자의 맨 위에 있지만 목록 상자를 스크롤하면 다른 항목이 맨 위에 있을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#22](../../mfc/codesnippet/cpp/clistbox-class_22.cpp)]

## <a name="clistboxinitstorage"></a><a name="initstorage"></a>CListBox:: InitStorage

목록 상자 항목을 저장 하기 위한 메모리를 할당 합니다.

```
int InitStorage(
    int nItems,
    UINT nBytes);
```

### <a name="parameters"></a>매개 변수

*nItems*<br/>
추가할 항목 수를 지정 합니다.

*nBytes*<br/>
항목 문자열에 할당할 메모리 크기 (바이트)를 지정 합니다.

### <a name="return-value"></a>Return Value

성공 하는 경우 메모리 재할당이 필요 하기 전에 목록 상자에서 저장할 수 있는 최대 항목 수이 고, 그렇지 않으면 LB_ERRSPACE 사용 가능한 메모리가 부족 하다는 것을 의미 합니다.

### <a name="remarks"></a>설명

에 많은 수의 항목을 추가 하기 전에이 함수를 호출 `CListBox` 합니다.

이 함수는 항목 수가 많은 (100 이상) 목록 상자의 초기화 속도를 높이는 데 도움이 됩니다. 다음 [Addstring](#addstring), [Insertstring](#insertstring)및 [Dir](#dir) 함수에서 가장 짧은 시간을 사용 하도록 지정 된 메모리 양을 사전 할당 합니다. 매개 변수에 대 한 예상 값을 사용할 수 있습니다. 더 많이 추정 하면 몇 가지 추가 메모리가 할당 됩니다. 간과 하면 미리 할당 된 금액을 초과 하는 항목에 일반적인 할당이 사용 됩니다.

Windows 95/98에만 해당: *Nitems* 매개 변수는 16 비트 값으로 제한 됩니다. 즉, 목록 상자에는 32767 개 이상의 항목이 포함 될 수 없습니다. 항목 수가 제한 되지만 목록 상자에 있는 항목의 총 크기는 사용 가능한 메모리에 의해서만 제한 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#23](../../mfc/codesnippet/cpp/clistbox-class_23.cpp)]

## <a name="clistboxinsertstring"></a><a name="insertstring"></a>CListBox:: InsertString

목록 상자에 문자열을 삽입 합니다.

```
int InsertString(
    int nIndex,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
문자열을 삽입할 위치의 인덱스 (0부터 시작)를 지정 합니다. 이 매개 변수가-1 이면 문자열이 목록의 끝에 추가 됩니다.

*lpszItem*<br/>
삽입할 null 종료 문자열을 가리킵니다.

### <a name="return-value"></a>Return Value

문자열이 삽입된 위치의 0부터 시작하는 인덱스입니다. 오류가 발생 하는 경우 반환 값은 LB_ERR입니다. 새 문자열을 저장 하는 데 사용할 수 있는 공간이 부족 한 경우 반환 값은 LB_ERRSPACE입니다.

### <a name="remarks"></a>설명

[Addstring](#addstring) 멤버 함수와 달리를 `InsertString` 사용 하면 [LBS_SORT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일의 목록이 정렬 되지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#24](../../mfc/codesnippet/cpp/clistbox-class_24.cpp)]

## <a name="clistboxitemfrompoint"></a><a name="itemfrompoint"></a>CListBox:: ItemFromPoint

*Pt*에 지정 된 지점에 가장 가까운 목록 상자 항목을 결정 합니다.

```
UINT ItemFromPoint(
    CPoint pt,
    BOOL& bOutside) const;
```

### <a name="parameters"></a>매개 변수

*p t*<br/>
목록 상자 클라이언트 영역의 왼쪽 위 모퉁이를 기준으로 가장 가까운 항목을 찾을 수 있는 지점입니다.

*bOutside*<br/>
*Pt* 가 목록 상자의 클라이언트 영역을 벗어날 경우 TRUE로 설정 되는 BOOL 변수에 대 한 참조이 고,이 목록 상자의 클라이언트 영역에 *있는 경우 FALSE 이면 FALSE입니다.*

### <a name="return-value"></a>Return Value

*Pt*에 지정 된 지점에 가장 가까운 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 마우스 커서가 이동 하는 목록 상자 항목을 확인할 수 있습니다.

### <a name="example"></a>예제

  [CListBox:: SetAnchorIndex](#setanchorindex)의 예제를 참조 하세요.

## <a name="clistboxmeasureitem"></a><a name="measureitem"></a>CListBox:: MeasureItem

소유자 그리기 스타일이 있는 목록 상자를 만들 때 프레임 워크에서 호출 됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
[MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct) 구조체에 대 한 긴 포인터입니다.

### <a name="remarks"></a>설명

기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 이 멤버 함수를 재정의 하 고 구조를 채워서 `MEASUREITEMSTRUCT` 목록 상자 차원의 창을 알립니다. [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용 하 여 목록 상자를 만들 경우 프레임 워크는 목록 상자의 각 항목에 대해이 멤버 함수를 호출 합니다. 그렇지 않으면이 멤버는 한 번만 호출 됩니다.

`CWnd`의 멤버 함수 `SubclassDlgItem`를 사용하여 만든 소유자 그리기 목록 상자에서 [LBS_OWNERDRAWFIXED](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용하는 방법에 대한 자세한 내용은 [기술 참고 사항 14](../../mfc/tn014-custom-controls.md)의 설명을 참조하십시오.

구조체에 대 한 설명은 [CWnd:: OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 를 참조 하세요 `MEASUREITEMSTRUCT` .

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#25](../../mfc/codesnippet/cpp/clistbox-class_25.cpp)]

## <a name="clistboxresetcontent"></a><a name="resetcontent"></a>CListBox:: ResetContent

목록 상자에서 모든 항목을 제거 합니다.

```cpp
void ResetContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#26](../../mfc/codesnippet/cpp/clistbox-class_26.cpp)]

## <a name="clistboxselectstring"></a><a name="selectstring"></a>CListBox:: SelectString

지정 된 문자열과 일치 하는 목록 상자 항목을 검색 하 고, 일치 하는 항목이 있는 경우 해당 항목을 선택 합니다.

```
int SelectString(
    int nStartAfter,
    LPCTSTR lpszItem);
```

### <a name="parameters"></a>매개 변수

*nStartAfter*<br/>
검색할 첫 번째 항목 앞의 항목에 대 한 0부터 시작 하는 인덱스를 포함 합니다. 검색은 목록 상자의 아래쪽에 도달 하면 목록 상자의 맨 위에서 *Nstartafter*로 지정 된 항목으로 다시 계속 됩니다. *Nstartafter* 가-1 이면 전체 목록 상자를 처음부터 검색 합니다.

*lpszItem*<br/>
검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색은 대/소문자를 구분 하지 않으므로이 문자열에는 대 문자와 소문자를 조합 하 여 사용할 수 있습니다.

### <a name="return-value"></a>Return Value

검색에 성공한 경우 선택한 항목의 인덱스입니다. 검색에 실패 한 경우 반환 값은 LB_ERR 되며 현재 선택 항목은 변경 되지 않습니다.

### <a name="remarks"></a>설명

필요한 경우 목록 상자를 스크롤하여 선택한 항목을 뷰로 전환 합니다.

이 멤버 함수는 [LBS_MULTIPLESEL](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있는 목록 상자와 함께 사용할 수 없습니다.

항목은 처음 문자 (시작 지점에서)가 *lpszItem*에 지정 된 문자열의 문자와 일치 하는 경우에만 선택 됩니다.

항목을 `FindString` 선택 하지 않고 멤버 함수를 사용 하 여 문자열을 찾습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#27](../../mfc/codesnippet/cpp/clistbox-class_27.cpp)]

## <a name="clistboxselitemrange"></a><a name="selitemrange"></a>CListBox:: SelItemRange

다중 선택 목록 상자에서 여러 연속 항목을 선택 합니다.

```
int SelItemRange(
    BOOL bSelect,
    int nFirstItem,
    int nLastItem);
```

### <a name="parameters"></a>매개 변수

*bSelect*<br/>
선택 항목을 설정 하는 방법을 지정 합니다. *Bselect* 가 TRUE 이면 문자열이 선택 되 고 강조 표시 됩니다. FALSE 이면 강조 표시가 제거 되 고 문자열이 더 이상 선택 되지 않습니다.

*nFirstItem*<br/>
설정할 첫 번째 항목의 인덱스 (0부터 시작)를 지정 합니다.

*nLastItem*<br/>
설정할 마지막 항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 다중 선택 목록 상자 에서만 사용 합니다. 다중 선택 목록 상자에서 항목을 하나만 선택 해야 하는 경우 즉, *Nfirstitem* 이 *Nfirstitem* 과 같으면 [setsel](#setsel) 멤버 함수를 대신 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#28](../../mfc/codesnippet/cpp/clistbox-class_28.cpp)]

## <a name="clistboxsetanchorindex"></a><a name="setanchorindex"></a>CListBox:: SetAnchorIndex

다중 선택 목록 상자에 앵커를 설정 하 여 확장 된 선택 영역을 시작 합니다.

```cpp
void SetAnchorIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
앵커 되는 목록 상자 항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="remarks"></a>설명

다중 선택 목록 상자에서 앵커 항목은 선택 된 연속 항목 블록의 첫 번째 또는 마지막 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#29](../../mfc/codesnippet/cpp/clistbox-class_29.cpp)]

## <a name="clistboxsetcaretindex"></a><a name="setcaretindex"></a>CListBox:: SetCaretIndex

여러 선택 목록 상자의 지정 된 인덱스에 있는 항목에 포커스 영역을 설정 합니다.

```
int SetCaretIndex(
    int nIndex,
    BOOL bScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 포커스 사각형을 받을 항목의 인덱스 (0부터 시작)를 지정 합니다.

*bScroll*<br/>
이 값이 0 이면 항목이 완전히 표시 될 때까지 항목이 스크롤됩니다. 이 값이 0이 아니면 최소한 부분적으로 표시 될 때까지 항목이 스크롤됩니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="remarks"></a>설명

항목이 표시 되지 않으면 뷰로 스크롤됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#30](../../mfc/codesnippet/cpp/clistbox-class_30.cpp)]

## <a name="clistboxsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListBox:: SetColumnWidth

[LBS_MULTICOLUMN](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용 하 여 만든 여러 열로 된 목록 상자에 있는 모든 열의 너비 (픽셀)를 설정 합니다.

```cpp
void SetColumnWidth(int cxWidth);
```

### <a name="parameters"></a>매개 변수

*cxWidth*<br/>
모든 열의 너비 (픽셀)를 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#31](../../mfc/codesnippet/cpp/clistbox-class_31.cpp)]

## <a name="clistboxsetcursel"></a><a name="setcursel"></a>CListBox:: SetCurSel

문자열을 선택 하 고 필요한 경우 뷰로 스크롤합니다.

```
int SetCurSel(int nSelect);
```

### <a name="parameters"></a>매개 변수

*nSelect*<br/>
선택할 문자열의 인덱스 (0부터 시작)를 지정 합니다. *내보내세요* 가-1 인 경우 목록 상자는 선택 항목 없음으로 설정 됩니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="remarks"></a>설명

새 문자열을 선택한 경우 목록 상자는 이전에 선택한 문자열에서 강조 표시를 제거 합니다.

단일 선택 목록 상자에만이 멤버 함수를 사용 합니다.

다중 선택 목록 상자에서 선택을 설정 하거나 제거 하려면 [CListBox:: SetSel](#setsel)을 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#32](../../mfc/codesnippet/cpp/clistbox-class_32.cpp)]

## <a name="clistboxsethorizontalextent"></a><a name="sethorizontalextent"></a>CListBox:: SetHorizontalExtent

목록 상자를 가로로 스크롤할 수 있는 너비 (픽셀)를 설정 합니다.

```cpp
void SetHorizontalExtent(int cxExtent);
```

### <a name="parameters"></a>매개 변수

*cxExtent*<br/>
목록 상자를 가로로 스크롤할 수 있는 픽셀 수를 지정 합니다.

### <a name="remarks"></a>설명

목록 상자의 크기가이 값 보다 작으면 가로 스크롤 막대가 목록 상자에서 항목을 가로로 스크롤합니다. 목록 상자가이 값 보다 크거나 크면 가로 스크롤 막대가 숨겨집니다.

호출에 응답 하려면 `SetHorizontalExtent` 목록 상자가 [WS_HSCROLL](../../mfc/reference/styles-used-by-mfc.md#window-styles) 스타일로 정의 되어 있어야 합니다.

이 멤버 함수는 여러 열로 된 목록 상자에는 유용 하지 않습니다. 여러 열로 된 목록 상자에 대해 `SetColumnWidth` 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#33](../../mfc/codesnippet/cpp/clistbox-class_33.cpp)]

## <a name="clistboxsetitemdata"></a><a name="setitemdata"></a>CListBox:: SetItemData

목록 상자에서 지정 된 항목과 연결 된 값을 설정 합니다.

```
int SetItemData(
    int nIndex,
    DWORD_PTR dwItemData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스 (0부터 시작)를 지정 합니다.

*dwItemData*<br/>
항목에 연결할 값을 지정 합니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#34](../../mfc/codesnippet/cpp/clistbox-class_34.cpp)]

## <a name="clistboxsetitemdataptr"></a><a name="setitemdataptr"></a>CListBox:: SetItemDataPtr

목록 상자의 지정 된 항목과 연결 된 32 비트 값을 지정 된 포인터 ()로 설정 합니다 **`void`** <strong>\*</strong> .

```
int SetItemDataPtr(
    int nIndex,
    void* pData);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
항목의 인덱스 (0부터 시작)를 지정 합니다.

*pData*<br/>
항목과 연결할 포인터를 지정 합니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="remarks"></a>설명

항목이 추가 되거나 제거 되 면 목록 상자 내에서 항목의 상대 위치가 변경 될 수 있지만이 포인터는 목록 상자의 수명 동안 유효한 상태로 유지 됩니다. 따라서 상자 내의 항목 인덱스는 변경 될 수 있지만 포인터는 안정적으로 유지 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#35](../../mfc/codesnippet/cpp/clistbox-class_35.cpp)]

## <a name="clistboxsetitemheight"></a><a name="setitemheight"></a>CListBox:: SetItemHeight

목록 상자에 있는 항목의 높이를 설정 합니다.

```
int SetItemHeight(
    int nIndex,
    UINT cyItemHeight);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자에서 항목의 인덱스 (0부터 시작)를 지정 합니다. 이 매개 변수는 목록 상자에 LBS_OWNERDRAWVARIABLE 스타일이 있는 경우에만 사용 됩니다. 그렇지 않으면 0으로 설정 해야 합니다.

*cyItemHeight*<br/>
항목의 높이를 픽셀 단위로 지정 합니다.

### <a name="return-value"></a>Return Value

인덱스 또는 높이가 잘못 된 경우를 LB_ERR 합니다.

### <a name="remarks"></a>설명

목록 상자에 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 있으면이 함수는 *nindex*로 지정 된 항목의 높이를 설정 합니다. 그렇지 않으면이 함수는 목록 상자에 있는 모든 항목의 높이를 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#36](../../mfc/codesnippet/cpp/clistbox-class_36.cpp)]

## <a name="clistboxsetlocale"></a><a name="setlocale"></a>CListBox:: SetLocale

이 목록 상자에 대 한 로캘 식별자를 설정 합니다.

```
LCID SetLocale(LCID nNewLocale);
```

### <a name="parameters"></a>매개 변수

*nNewLocale*<br/>
목록 상자에 대해 설정할 새 LCID (로캘 id) 값입니다.

### <a name="return-value"></a>Return Value

이 목록 상자에 대 한 이전 LCID (로캘 id) 값입니다.

### <a name="remarks"></a>설명

`SetLocale`가 호출 되지 않은 경우에는 시스템에서 기본 로캘을 가져옵니다. 이 시스템 기본 로캘은 제어판의 국가별 또는 국가별 응용 프로그램을 사용 하 여 수정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#37](../../mfc/codesnippet/cpp/clistbox-class_37.cpp)]

## <a name="clistboxsetsel"></a><a name="setsel"></a>CListBox:: SetSel

다중 선택 목록 상자에서 문자열을 선택 합니다.

```
int SetSel(
    int nIndex,
    BOOL bSelect = TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
설정할 문자열의 인덱스 (0부터 시작)를 포함 합니다. -1 인 경우 *Bselect*의 값에 따라 모든 문자열에서 선택 항목이 추가 되거나 제거 됩니다.

*bSelect*<br/>
선택 항목을 설정 하는 방법을 지정 합니다. *Bselect* 가 TRUE 이면 문자열이 선택 되 고 강조 표시 됩니다. FALSE 이면 강조 표시가 제거 되 고 문자열이 더 이상 선택 되지 않습니다. 지정 된 문자열이 기본적으로 선택 되 고 강조 표시 됩니다.

### <a name="return-value"></a>Return Value

오류가 발생 하면 LB_ERR 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 다중 선택 목록 상자 에서만 사용 합니다.

단일 선택 목록 상자에서 항목을 선택 하려면 [CListBox:: SetCurSel](#setcursel)을 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#38](../../mfc/codesnippet/cpp/clistbox-class_38.cpp)]

## <a name="clistboxsettabstops"></a><a name="settabstops"></a>CListBox:: SetTabStops

목록 상자에서 탭 정지 위치를 설정 합니다.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>매개 변수

*cxEachStop*<br/>
탭 정지는 모든 *cxEachStop* 대화 상자 단위에서 설정 됩니다. 대화 상자 단위에 대 한 설명은 *rgTabStops* 를 참조 하세요.

*nTabStops*<br/>
목록 상자에 포함할 탭 정지의 수를 지정 합니다.

*rgTabStops*<br/>
대화 상자 단위의 탭 정지 위치를 포함 하는 정수 배열의 첫 번째 멤버를 가리킵니다. 대화 상자 단위는 가로 또는 세로 거리입니다. 하나의 가로 대화 상자 단위는 현재 대화 상자 기본 너비 단위의 4 번째와 같으며, 세로 대화 상자 하나는 현재 대화 상자 기본 높이 단위의 8-8과 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 높이와 너비를 기준으로 계산 됩니다. `GetDialogBaseUnits`Windows 함수는 현재 대화 상자 기본 단위 (픽셀)를 반환 합니다. 탭 정지는 오름차순으로 정렬 되어야 합니다. 뒤로 탭은 허용 되지 않습니다.

### <a name="return-value"></a>Return Value

모든 탭이 설정 된 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

탭 정지를 기본 크기인 2 개 대화 상자 단위로 설정 하려면이 멤버 함수의 매개 변수가 없는 버전을 호출 합니다. 탭 정지를 2 이외의 크기로 설정 하려면 *cxEachStop* 인수를 사용 하 여 버전을 호출 합니다.

탭 정지를 크기 배열로 설정 하려면 *rgTabStops* 및 *ntabstops* 인수를 사용 하 여 버전을 사용 합니다. *RgTabStops*의 각 값에 대해 탭 정지는 *ntabstops*로 지정 된 수까지 설정 됩니다.

멤버 함수에 대 한 호출에 응답 하려면 `SetTabStops` [LBS_USETABSTOPS](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일을 사용 하 여 목록 상자를 만들어야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#39](../../mfc/codesnippet/cpp/clistbox-class_39.cpp)]

## <a name="clistboxsettopindex"></a><a name="settopindex"></a>CListBox:: SetTopIndex

특정 목록 상자 항목이 표시 되는지 확인 합니다.

```
int SetTopIndex(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
목록 상자 항목의 인덱스 (0부터 시작)를 지정 합니다.

### <a name="return-value"></a>Return Value

성공 하면 0이 고, 오류가 발생 하면 LB_ERR입니다.

### <a name="remarks"></a>설명

시스템은 *Nindex* 로 지정 된 항목이 목록 상자 위쪽에 나타나거나 최대 스크롤 범위에 도달할 때까지 목록 상자를 스크롤합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#40](../../mfc/codesnippet/cpp/clistbox-class_40.cpp)]

## <a name="clistboxvkeytoitem"></a><a name="vkeytoitem"></a>CListBox:: VKeyToItem

목록 상자의 부모 창이 목록 상자에서 WM_VKEYTOITEM 메시지를 받을 때 프레임 워크에서 호출 됩니다.

```
virtual int VKeyToItem(
    UINT nKey,
    UINT nIndex);
```

### <a name="parameters"></a>매개 변수

*nKey*<br/>
사용자가 누른 키의 가상 키 코드입니다. 표준 가상 키 코드의 목록은 Winuser.h를 참조 하세요.

*nIndex*<br/>
목록 상자 캐럿의 현재 위치입니다.

### <a name="return-value"></a>Return Value

추가 작업을 수행 하지 않으려면-2를 반환 하 고, 기본 작업의 경우-1을 반환 하 고, 키 입력에 대 한 기본 작업을 수행할 목록 상자 항목의 인덱스를 지정 하려면 음수가 아닌 숫자를 반환 합니다.

### <a name="remarks"></a>설명

목록 상자에서 다음 두 가지를 모두 충족 하는 경우에만 WM_KEYDOWN 메시지를 받을 때 목록 상자에 WM_VKEYTOITEM 메시지가 전송 됩니다.

- [LBS_WANTKEYBOARDINPUT](../../mfc/reference/styles-used-by-mfc.md#list-box-styles) 스타일이 설정 되어 있습니다.

- 에 항목이 하나 이상 있습니다.

이 함수는 직접 호출 하면 안 됩니다. 키보드 메시지의 사용자 지정 처리를 제공 하려면이 함수를 재정의 합니다.

재정의에서 수행한 작업을 프레임 워크에 알리기 위해 값을 반환 해야 합니다. 반환 값-2는 응용 프로그램이 항목을 선택 하는 모든 측면을 처리 하 고 목록 상자에서 추가 작업을 수행 하지 않음을 나타냅니다. -2를 반환 하기 전에 선택 항목을 설정 하거나 캐럿 또는 둘 다를 이동할 수 있습니다. 선택 항목을 설정 하려면 [Setcursel](#setcursel) 또는 [setsel](#setsel)을 사용 합니다. 캐럿을 이동 하려면 [SetCaretIndex](#setcaretindex)를 사용 합니다.

반환 값-1은 목록 상자가 키 입력에 대 한 응답으로 기본 동작을 수행 해야 함을 나타냅니다. 기본 구현에서는-1을 반환 합니다.

반환 값이 0 이상인 경우 목록 상자에 있는 항목의 인덱스를 지정 하 고 목록 상자에서 지정 된 항목의 키 입력에 대 한 기본 작업을 수행 해야 함을 나타냅니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CListBox#41](../../mfc/codesnippet/cpp/clistbox-class_41.cpp)]

## <a name="see-also"></a>참고 항목

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit 클래스](../../mfc/reference/cedit-class.md)<br/>
[CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic 클래스](../../mfc/reference/cstatic-class.md)
