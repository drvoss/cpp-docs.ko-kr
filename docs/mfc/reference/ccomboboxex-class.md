---
title: CComboBoxEx 클래스
ms.date: 11/04/2016
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
ms.openlocfilehash: 7d46f175a62cda7f1ff08327830f1dffe2967727
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425990"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx 클래스

이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.

## <a name="syntax"></a>구문

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>구성원

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComboBoxEx::Create](#create)|콤보 상자를 만들어 `CComboBoxEx` 개체에 연결 합니다.|
|[CComboBoxEx::CreateEx](#createex)|지정 된 Windows 확장 스타일을 사용 하 여 콤보 상자를 만들고 `ComboBoxEx` 개체에 연결 합니다.|
|[CComboBoxEx::DeleteItem](#deleteitem)|`ComboBoxEx` 컨트롤에서 항목을 제거 합니다.|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|자식 콤보 상자 컨트롤에 대 한 포인터를 검색 합니다.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|`ComboBoxEx` 컨트롤의 편집 컨트롤 부분에 대 한 핸들을 검색 합니다.|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|`ComboBoxEx` 컨트롤에 사용 되는 확장 스타일을 검색 합니다.|
|[CComboBoxEx::GetImageList](#getimagelist)|`ComboBoxEx` 컨트롤에 할당 된 이미지 목록에 대 한 포인터를 검색 합니다.|
|[CComboBoxEx::GetItem](#getitem)|지정 된 `ComboBoxEx` 항목에 대 한 항목 정보를 검색 합니다.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|사용자가를 입력 하 여 `ComboBoxEx` 편집 컨트롤의 콘텐츠를 변경 했는지 여부를 확인 합니다.|
|[CComboBoxEx::InsertItem](#insertitem)|`ComboBoxEx` 컨트롤에 새 항목을 삽입 합니다.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|`ComboBoxEx` 컨트롤 내에서 확장 스타일을 설정 합니다.|
|[CComboBoxEx::SetImageList](#setimagelist)|`ComboBoxEx` 컨트롤의 이미지 목록을 설정 합니다.|
|[CComboBoxEx::SetItem](#setitem)|`ComboBoxEx` 컨트롤의 항목에 대 한 특성을 설정 합니다.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|확장 된 콤보 상자 컨트롤의 비주얼 스타일을 설정 합니다.|

## <a name="remarks"></a>설명

`CComboBoxEx`를 사용 하 여 콤보 상자 컨트롤을 만드는 경우에는 더 이상 고유한 이미지 그리기 코드를 구현할 필요가 없습니다. 대신 `CComboBoxEx`를 사용 하 여 이미지 목록에서 이미지에 액세스 합니다.

## <a name="image-list-support"></a>이미지 목록 지원

표준 콤보 상자에서 콤보 상자의 소유자는 콤보 상자를 소유자 그리기 컨트롤로 만들어 이미지를 그릴 책임이 있습니다. `CComboBoxEx`를 사용 하는 경우에는 CBS_OWNERDRAWFIXED 및 CBS_HASSTRINGS 그리기 스타일을 설정 하지 않아도 됩니다. 그렇지 않으면 그리기 작업을 수행 하는 코드를 작성 해야 합니다. `CComboBoxEx` 컨트롤은 항목당 최대 3 개의 이미지 (선택 된 상태, 선택 되지 않은 상태, 오버레이 이미지용)를 지원 합니다.

## <a name="styles"></a>스타일

`CComboBoxEx`는 CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST 및 WS_CHILD 스타일을 지원 합니다. 창을 만들 때 전달 되는 다른 모든 스타일은 컨트롤에서 무시 됩니다. 창을 만든 후 `CComboBoxEx` 멤버 함수 [SetExtendedStyle](#setextendedstyle)를 호출 하 여 다른 콤보 상자 스타일을 제공할 수 있습니다. 이러한 스타일을 사용 하 여 다음을 수행할 수 있습니다.

- 대/소문자를 구분 하려면 목록에서 문자열 검색을 설정 합니다.

- 슬래시 ('/'), 백슬래시 ('\\') 및 마침표 ('. ') 문자를 단어 구분 기호로 사용 하는 콤보 상자 컨트롤을 만듭니다. 이를 통해 사용자는 바로 가기 키 CTRL + 화살표를 사용 하 여 word에서 word로 이동할 수 있습니다.

- 표시 하거나 이미지를 표시 하지 않도록 콤보 상자 컨트롤을 설정 합니다. 이미지가 표시 되지 않으면 콤보 상자에서 이미지를 수용 하는 텍스트 들여쓰기를 제거할 수 있습니다.

- 크기를 조정 하는 것을 포함 하 여 좁은 콤보 상자 컨트롤을 만듭니다 .이 컨트롤에 포함 된 넓은 콤보 상자를 클리핑 합니다.

이러한 스타일 플래그는 [CComboBoxEx 사용](../../mfc/using-ccomboboxex.md)에 자세히 설명 되어 있습니다.

## <a name="item-retention-and-callback-item-attributes"></a>항목 보존 및 콜백 항목 특성

항목 및 이미지, 들여쓰기 값 및 텍스트 문자열에 대 한 인덱스와 같은 항목 정보는 Windows SDK 설명 된 대로 Win32 구조 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)에 저장 됩니다. 구조체에는 콜백 플래그에 해당 하는 멤버도 포함 됩니다.

개념에 대 한 자세한 내용은 [CComboBoxEx 사용](../../mfc/using-ccomboboxex.md)을 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[에서 파생되지 않은](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx

이 멤버 함수를 호출 하 여 `CComboBoxEx` 개체를 만듭니다.

```
CComboBoxEx();
```

##  <a name="create"></a>  CComboBoxEx::Create

콤보 상자를 만들어 `CComboBoxEx` 개체에 연결 합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
콤보 상자에 적용 되는 콤보 상자 스타일의 조합을 지정 합니다. 스타일에 대 한 자세한 내용은 아래 **설명 부분** 을 참조 하세요.

*rect*<br/>
콤보 상자의 위치와 크기에 해당 하는 [Crect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조에 대 한 참조입니다.

*pParentWnd*<br/>
콤보 상자 (일반적으로 [)의 부모 창인 ](../../mfc/reference/cwnd-class.md)CWnd`CDialog` 개체에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
콤보 상자의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 만들어진 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

두 단계로 `CComboBoxEx` 개체를 만듭니다.

1. [CComboBoxEx](#ccomboboxex) 를 호출 하 여 `CComboBoxEx` 개체를 생성 합니다.

1. 확장 된 Windows 콤보 상자를 만들고 `CComboBoxEx` 개체에 연결 하는이 멤버 함수를 호출 합니다.

`Create`를 호출 하는 경우 MFC는 공용 컨트롤을 초기화 합니다.

콤보 상자를 만들 때 다음 콤보 상자 스타일 중 일부 또는 모두를 지정할 수 있습니다.

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

창을 만들 때 전달 되는 다른 모든 스타일은 무시 됩니다. 또한 `ComboBoxEx` 컨트롤은 추가 기능을 제공 하는 확장 스타일을 지원 합니다. 이러한 스타일은 Windows SDK의 [ComboBoxEx 컨트롤 확장 스타일](/windows/win32/Controls/comboboxex-control-extended-styles)에 설명 되어 있습니다. [SetExtendedStyle](#setextendedstyle)을 호출 하 여 이러한 스타일을 설정 합니다.

컨트롤과 함께 확장 된 windows 스타일을 사용 하려면 `Create`대신 [Createex](#createex) 를 호출 합니다.

##  <a name="createex"></a>  CComboBoxEx::CreateEx

확장 된 콤보 상자 컨트롤 (자식 창)을 만들어 `CComboBoxEx` 개체와 연결 하려면이 함수를 호출 합니다.

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
만들려는 컨트롤의 확장 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록에 대해서는 Windows SDK의 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) 에 대 한 *dwexstyle* 매개 변수를 참조 하세요.

*dwStyle*<br/>
콤보 상자 컨트롤의 스타일입니다. 스타일 목록은 [Create](#create) 를 참조 하세요.

*rect*<br/>
*PParentWnd*의 클라이언트 좌표에서 만들 창의 크기와 위치를 설명 하는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조체에 대 한 참조입니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Create` 대신 `CreateEx`를 사용 하 여 Windows 확장 스타일 앞에 **WS_EX_** 지정 된 확장 된 windows 스타일을 적용 합니다.

`CreateEx` *Dwexstyle*으로 지정 된 확장 된 Windows 스타일을 사용 하 여 컨트롤을 만듭니다. [SetExtendedStyle](#setextendedstyle)를 사용 하 여 확장 된 콤보 상자 컨트롤과 관련 된 확장 스타일을 설정 해야 합니다. 예를 들어 `CreateEx`를 사용 하 여 이러한 스타일을 WS_EX_CONTEXTHELP으로 설정 하지만 `SetExtendedStyle`를 사용 하 여 이러한 스타일을 CBES_EX_CASESENSITIVE로 설정 합니다. 자세한 내용은 Windows SDK [ComboBoxEx 컨트롤 확장 스타일](/windows/win32/Controls/comboboxex-control-extended-styles) 항목에서 설명 하는 스타일을 참조 하세요.

##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem

`ComboBoxEx` 컨트롤에서 항목을 제거 합니다.

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
제거할 항목의 인덱스 (0부터 시작)입니다.

### <a name="return-value"></a>Return Value

컨트롤에 남아 있는 항목의 수입니다. *Iindex* 가 잘못 된 경우 함수는 CB_ERR을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)메시지의 기능을 구현 합니다. DeleteItem을 호출 하면 CBEN_DELETEITEM 알림이 포함 된 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지가 부모 창으로 전송 됩니다.

##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl

이 멤버 함수를 호출 하 여 `CComboBoxEx` 개체 내에서 콤보 상자 컨트롤에 대 한 포인터를 가져옵니다.

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Return Value

`CComboBox` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

`CComboBoxEx` 컨트롤은 `CComboBox`를 캡슐화 하는 부모 창으로 구성 됩니다.

반환 값이 가리키는 `CComboBox` 개체는 임시 개체 이며 다음 유휴 처리 시간 중에 제거 됩니다.

##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl

콤보 상자의 편집 컨트롤에 대 한 포인터를 가져오려면이 멤버 함수를 호출 합니다.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Return Value

[CEdit](../../mfc/reference/cedit-class.md) 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`CComboBoxEx` 컨트롤은 CBS_DROPDOWN 스타일을 사용 하 여 만들 때 편집 상자를 사용 합니다.

반환 값이 가리키는 `CEdit` 개체는 임시 개체 이며 다음 유휴 처리 시간 중에 제거 됩니다.

##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle

이 멤버 함수를 호출 하 여 `CComboBoxEx` 컨트롤에 사용 되는 확장 스타일을 가져옵니다.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Return Value

콤보 상자 컨트롤에 사용 되는 확장 스타일을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

이러한 스타일에 대 한 자세한 내용은 Windows SDK [ComboBoxEx 컨트롤 확장 스타일](/windows/win32/Controls/comboboxex-control-extended-styles) 을 참조 하세요.

##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList

이 멤버 함수를 호출 하 여 `CComboBoxEx` 컨트롤에서 사용 하는 이미지 목록에 대 한 포인터를 가져옵니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Return Value

[CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대 한 포인터입니다. 실패 하면이 멤버 함수는 NULL을 반환 합니다.

### <a name="remarks"></a>설명

반환 값이 가리키는 `CImageList` 개체는 임시 개체 이며 다음 유휴 처리 시간 중에 제거 됩니다.

##  <a name="getitem"></a>  CComboBoxEx::GetItem

지정 된 `ComboBoxEx` 항목에 대 한 항목 정보를 검색 합니다.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신 하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

작업이 성공 하면 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)메시지의 기능을 구현 합니다.

##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged

사용자가를 입력 하 여 `ComboBoxEx` 편집 컨트롤의 콘텐츠를 변경 했는지 여부를 확인 합니다.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Return Value

사용자가 컨트롤의 편집 상자에 입력 한 경우 0이 아닌 값입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)메시지의 기능을 구현 합니다.

##  <a name="insertitem"></a>  CComboBoxEx::InsertItem

`ComboBoxEx` 컨트롤에 새 항목을 삽입 합니다.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신 하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조체에 대 한 포인터입니다. 이 구조체는 항목에 대 한 콜백 플래그 값을 포함 합니다.

### <a name="return-value"></a>Return Value

성공 하는 경우 새 항목이 삽입 된 인덱스입니다. 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

`InsertItem`를 호출 하면 [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) 알림이 포함 된 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지가 부모 창으로 전송 됩니다.

##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle

콤보 상자 확장 컨트롤에 사용 되는 확장 스타일을 설정 하려면이 멤버 함수를 호출 합니다.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>매개 변수

*dwExMask*<br/>
영향을 받을 *Dwexstyles* 스타일을 나타내는 DWORD 값입니다. *Dwexmask* 의 확장 된 스타일만 변경 됩니다. 다른 모든 스타일은 그대로 유지 됩니다. 이 매개 변수가 0 이면 *Dwexstyles* 의 모든 스타일이 영향을 받게 됩니다.

*dwExStyles*<br/>
컨트롤에 대해 설정할 콤보 상자 컨트롤 확장 스타일을 포함 하는 DWORD 값입니다.

### <a name="return-value"></a>Return Value

컨트롤에 이전에 사용 된 확장 스타일을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

이러한 스타일에 대 한 자세한 내용은 Windows SDK [ComboBoxEx 컨트롤 확장 스타일](/windows/win32/Controls/comboboxex-control-extended-styles) 을 참조 하세요.

확장 된 windows 스타일을 사용 하 여 콤보 상자 확장 컨트롤을 만들려면 [Createex](#createex)를 사용 합니다.

##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList

`ComboBoxEx` 컨트롤의 이미지 목록을 설정 합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
`CComboBoxEx` 컨트롤과 함께 사용할 이미지를 포함 하는 `CImageList` 개체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

`CComboBoxEx` 컨트롤에서 이전에 사용한 이미지를 포함 하는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대 한 포인터입니다. 이전에 설정 된 이미지 목록이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)메시지의 기능을 구현 합니다. 기본 편집 컨트롤의 높이를 변경 하는 경우 `SetImageList`호출한 후 Win32 함수 [Setwindowpos](/windows/win32/api/winuser/nf-winuser-setwindowpos) 를 호출 하 여 컨트롤의 크기를 조정 하거나 제대로 표시 되지 않습니다.

반환 값이 가리키는 `CImageList` 개체는 임시 개체 이며 다음 유휴 처리 시간 중에 제거 됩니다.

##  <a name="setitem"></a>  CComboBoxEx::SetItem

`ComboBoxEx` 컨트롤의 항목에 대 한 특성을 설정 합니다.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신 하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조체에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

작업이 성공 하면 0이 아닌 값이 고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)메시지의 기능을 구현 합니다.

##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme

확장 된 콤보 상자 컨트롤의 비주얼 스타일을 설정 합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
설정할 확장 된 콤보 상자 비주얼 스타일을 포함 하는 유니코드 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

반환 값은 사용 되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) 메시지의 기능을 에뮬레이트합니다.

## <a name="see-also"></a>참고 항목

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)
