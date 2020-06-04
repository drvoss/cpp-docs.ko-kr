---
title: C콤보박스엑스 클래스
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
ms.openlocfilehash: a948d54be17103fa83848ff5f0e86dd2c522f0a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754816"
---
# <a name="ccomboboxex-class"></a>C콤보박스엑스 클래스

이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.

## <a name="syntax"></a>구문

```
class CComboBoxEx : public CComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CComboBoxEx::만들기](#create)|콤보 상자를 만들고 오브젝트에 `CComboBoxEx` 연결합니다.|
|[CComboBoxEx::CreateEx](#createex)|지정된 Windows 확장 스타일이 있는 콤보 상자를 만들고 `ComboBoxEx` 개체에 연결합니다.|
|[CComboBoxEx::DeleteItem](#deleteitem)|컨트롤에서 항목을 제거합니다. `ComboBoxEx`|
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|자식 콤보 상자 컨트롤에 대한 포인터를 검색합니다.|
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|컨트롤의 편집 컨트롤 부분에 대한 핸들을 검색합니다. `ComboBoxEx`|
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|컨트롤에 사용 중인 확장 스타일을 `ComboBoxEx` 검색합니다.|
|[CComboBoxEx::GetImageList](#getimagelist)|컨트롤에 할당된 이미지 목록에 대한 `ComboBoxEx` 포인터를 검색합니다.|
|[CComboBoxEx::GetItem](#getitem)|지정된 `ComboBoxEx` 항목에 대한 항목 정보를 검색합니다.|
|[CComboBoxEx::HasEditChanged](#haseditchanged)|사용자가 입력하여 `ComboBoxEx` 편집 컨트롤의 내용을 변경했는지 확인합니다.|
|[CComboBoxEx::InsertItem](#insertitem)|컨트롤에 새 항목을 `ComboBoxEx` 삽입합니다.|
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|컨트롤 내에서 확장 `ComboBoxEx` 스타일을 설정합니다.|
|[CComboBoxEx::SetImageList](#setimagelist)|컨트롤에 대한 이미지 `ComboBoxEx` 목록을 설정합니다.|
|[CComboBoxEx::SetItem](#setitem)|`ComboBoxEx` 컨트롤의 항목에 대한 속성을 설정합니다.|
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|확장된 콤보 상자 컨트롤의 시각적 스타일을 설정합니다.|

## <a name="remarks"></a>설명

콤보 `CComboBoxEx` 상자 컨트롤을 만드는 데 사용 하 여 더 이상 사용자 고유의 이미지 그리기 코드를 구현할 필요가 없습니다. 대신 이미지 `CComboBoxEx` 목록에서 이미지에 액세스하는 데 사용합니다.

## <a name="image-list-support"></a>이미지 목록 지원

표준 콤보 상자에서 콤보 상자의 소유자는 소유자 그리기 컨트롤로 콤보 상자를 만들어 이미지를 그리는 역할을 합니다. 을 사용하면 `CComboBoxEx`도면 스타일이 암시되므로 CBS_OWNERDRAWFIXED CBS_HASSTRINGS 설정할 필요가 없습니다. 그렇지 않으면 그리기 작업을 수행하기 위해 코드를 작성해야 합니다. 컨트롤은 `CComboBoxEx` 항목당 최대 3개의 이미지를 지원합니다.

## <a name="styles"></a>스타일

`CComboBoxEx`CBS_SIMPLE, CBS_DROPDOWN, CBS_DROPDOWNLIST 및 WS_CHILD 지원합니다. 창을 만들 때 전달된 다른 모든 스타일은 컨트롤에서 무시됩니다. 창을 만든 후 `CComboBoxEx` 멤버 함수 [SetExtendedStyle을](#setextendedstyle)호출하여 다른 콤보 상자 스타일을 제공할 수 있습니다. 이러한 스타일을 사용하면 다음을 수행할 수 있습니다.

- 목록에서 문자열 검색을 대/소문자 구분으로 설정합니다.

- 슬래시('/'), 백슬래시(''),\\마침표('.') 문자를 단어 구분기호로 사용하는 콤보 상자 컨트롤을 만듭니다. 이를 통해 사용자는 키보드 바로 가기 CTRL + ARROW를 사용하여 단어에서 단어로 이동할 수 있습니다.

- 콤보 상자 컨트롤을 설정하여 이미지를 표시하거나 표시하지 않도록 합니다. 이미지가 표시되지 않으면 콤보 상자에서 이미지를 수용하는 텍스트 들여쓰기를 제거할 수 있습니다.

- 크기 조정을 포함하여 좁은 콤보 상자 컨트롤을 만들어 포함된 더 넓은 콤보 상자를 클립합니다.

이러한 스타일 플래그는 [CComboBoxEx 사용에서](../../mfc/using-ccomboboxex.md)자세히 설명합니다.

## <a name="item-retention-and-callback-item-attributes"></a>항목 보존 및 콜백 항목 특성

항목 및 이미지에 대한 인덱스, 들여쓰기 값 및 텍스트 문자열과 같은 항목 정보는 Windows SDK에 설명된 대로 Win32 구조 [COMBOBOXEXITEM에](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw)저장됩니다. 구조에는 콜백 플래그에 해당하는 멤버도 포함되어 있습니다.

자세한 개념적 토론은 [CComboBoxEx 사용을](../../mfc/using-ccomboboxex.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

`CComboBoxEx`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

## <a name="ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>CComboBoxEx:::콤보박스엑스

이 멤버 함수를 `CComboBoxEx` 호출하여 개체를 만듭니다.

```
CComboBoxEx();
```

## <a name="ccomboboxexcreate"></a><a name="create"></a>CComboBoxEx::만들기

콤보 상자를 만들고 오브젝트에 `CComboBoxEx` 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
콤보 상자에 적용된 콤보 상자 스타일의 조합을 지정합니다. 스타일에 대한 자세한 내용은 아래 **발언을** 참조하십시오.

*rect*<br/>
콤보 상자의 위치와 크기인 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.

*pParentWnd*<br/>
콤보 상자 (일반적으로 `CDialog`)의 부모 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 포인터입니다. NULL이 아니어야 합니다.

*nID*<br/>
콤보 상자의 컨트롤 ID를 지정합니다.

### <a name="return-value"></a>Return Value

개체가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

다음 `CComboBoxEx` 두 단계로 개체를 만듭니다.

1. [CComboBoxEx에](#ccomboboxex) 전화하여 `CComboBoxEx` 개체를 생성합니다.

1. 확장된 Windows 콤보 상자를 만들고 개체에 연결하는 이 `CComboBoxEx` 멤버 함수를 호출합니다.

호출할 `Create`때 MFC는 공통 컨트롤을 초기화합니다.

콤보 상자를 만들 때 다음 콤보 상자 스타일 중 일부를 지정할 수 있습니다.

- CBS_SIMPLE

- CBS_DROPDOWN

- CBS_DROPDOWNLIST

- CBS_AUTOHSCROLL

- WS_CHILD

창을 만들 때 전달된 다른 모든 스타일은 무시됩니다. 이 `ComboBoxEx` 컨트롤은 추가 기능을 제공하는 확장 된 스타일을 지원합니다. 이러한 스타일은 Windows SDK의 [ComboBoxEx 컨트롤 확장 스타일에](/windows/win32/Controls/comboboxex-control-extended-styles)설명되어 있습니다. [SetExtendedStyle을](#setextendedstyle)호출하여 이러한 스타일을 설정합니다.

컨트롤과 함께 확장 된 창 스타일을 사용 하려면 `Create`호출 [CreateEx](#createex) 대신 .

## <a name="ccomboboxexcreateex"></a><a name="createex"></a>CComboBoxEx::CreateEx

이 함수를 호출하여 확장된 콤보 상자 컨트롤(자식 `CComboBoxEx` 창)을 만들고 개체와 연결합니다.

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
콤보 상자 컨트롤의 스타일입니다. 스타일 목록은 [만들기를](#create) 참조하십시오.

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

`CreateEx`*dwExStyle에*의해 지정된 확장 된 Windows 스타일로 컨트롤을 만듭니다. [SetExtendedStyle을](#setextendedstyle)사용하여 확장 된 콤보 상자 컨트롤에 특정 확장 스타일을 설정 해야 합니다. 예를 들어 `CreateEx` WS_EX_CONTEXTHELP 같은 스타일을 설정하지만 `SetExtendedStyle` CBES_EX_CASESENSITIVE 같은 스타일을 설정하는 데 사용합니다. 자세한 내용은 Windows SDK의 [ComboBoxEx 제어 확장 스타일](/windows/win32/Controls/comboboxex-control-extended-styles) 항목에 설명된 스타일을 참조하십시오.

## <a name="ccomboboxexdeleteitem"></a><a name="deleteitem"></a>CComboBoxEx::Delete항목

컨트롤에서 항목을 제거합니다. `ComboBoxEx`

```
int DeleteItem(int iIndex);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
제거할 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

컨트롤에 남아 있는 항목 수입니다. *iIndex가* 잘못되면 함수가 CB_ERR 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_DELETEITEM](/windows/win32/Controls/cbem-deleteitem)메시지의 기능을 구현합니다. DeleteItem을 호출하면 CBEN_DELETEITEM 알림이 있는 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지가 부모 창으로 전송됩니다.

## <a name="ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl

개체 내의 콤보 상자 컨트롤에 대한 포인터를 얻으려면 이 멤버 함수를 호출합니다. `CComboBoxEx`

```
CComboBox* GetComboBoxCtrl();
```

### <a name="return-value"></a>Return Value

`CComboBox` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

컨트롤은 `CComboBoxEx` `CComboBox`를 캡슐화하는 부모 창으로 구성됩니다.

반환 `CComboBox` 값으로 가리키는 개체는 임시 개체이며 다음 유휴 처리 시간 동안 소멸됩니다.

## <a name="ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl

이 멤버 함수를 호출하여 콤보 상자에 대한 편집 컨트롤에 대한 포인터를 가져옵니다.

```
CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Return Value

[CEdit](../../mfc/reference/cedit-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

컨트롤은 `CComboBoxEx` CBS_DROPDOWN 스타일로 만들 때 편집 상자를 사용합니다.

반환 `CEdit` 값으로 가리키는 개체는 임시 개체이며 다음 유휴 처리 시간 동안 소멸됩니다.

## <a name="ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle

`CComboBoxEx` 이 멤버 함수를 호출하여 컨트롤에 사용되는 확장 스타일을 가져옵니다.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Return Value

콤보 상자 컨트롤에 사용되는 확장 된 스타일을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

이러한 스타일에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 제어 확장 스타일을](/windows/win32/Controls/comboboxex-control-extended-styles) 참조하십시오.

## <a name="ccomboboxexgetimagelist"></a><a name="getimagelist"></a>CComboBoxEx::GetImageList

이 멤버 함수를 호출하여 컨트롤에서 사용하는 `CComboBoxEx` 이미지 목록에 대한 포인터를 가져옵니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Return Value

[CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다. 실패하면 이 멤버 함수는 NULL을 반환합니다.

### <a name="remarks"></a>설명

반환 `CImageList` 값으로 가리키는 개체는 임시 개체이며 다음 유휴 처리 시간 동안 소멸됩니다.

## <a name="ccomboboxexgetitem"></a><a name="getitem"></a>CComboBoxEx::GetItem

지정된 `ComboBoxEx` 항목에 대한 항목 정보를 검색합니다.

```
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_GETITEM](/windows/win32/Controls/cbem-getitem)메시지의 기능을 구현합니다.

## <a name="ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>CComboBoxEx::변경되었습니다.

사용자가 입력하여 `ComboBoxEx` 편집 컨트롤의 내용을 변경했는지 확인합니다.

```
BOOL HasEditChanged();
```

### <a name="return-value"></a>Return Value

사용자가 컨트롤의 편집 상자에 입력한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_HASEDITCHANGED](/windows/win32/Controls/cbem-haseditchanged)메시지의 기능을 구현합니다.

## <a name="ccomboboxexinsertitem"></a><a name="insertitem"></a>CComboBoxEx::삽입항목

컨트롤에 새 항목을 `ComboBoxEx` 삽입합니다.

```
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조에 대한 포인터입니다. 이 구조에는 항목에 대한 콜백 플래그 값이 포함되어 있습니다.

### <a name="return-value"></a>Return Value

성공하면 새 항목이 삽입된 인덱스입니다. 그렇지 않으면 -1.

### <a name="remarks"></a>설명

호출할 `InsertItem`때 [CBEN_INSERTITEM](/windows/win32/Controls/cben-insertitem) 알림이 있는 [WM_NOTIFY](/windows/win32/controls/wm-notify) 메시지가 부모 창으로 전송됩니다.

## <a name="ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>CComboBoxEx::세트확장스타일

이 멤버 함수를 호출하여 콤보 상자 확장 컨트롤에 사용되는 확장 스타일을 설정합니다.

```
DWORD SetExtendedStyle(
    DWORD dwExMask,
    DWORD dwExStyles);
```

### <a name="parameters"></a>매개 변수

*dwExMask*<br/>
영향을 받을 *dwExStyles에서* 어떤 스타일을 나타내는 DWORD 값입니다. *dwExMask의* 확장 된 스타일만 변경됩니다. 다른 모든 스타일은 있는 것처럼 유지됩니다. 이 매개변수가 0이면 *dwExStyles의* 모든 스타일이 영향을 받습니다.

*dwExStyles*<br/>
컨트롤에 대해 설정할 콤보 상자 컨트롤 확장 스타일을 포함하는 DWORD 값입니다.

### <a name="return-value"></a>Return Value

컨트롤에 이전에 사용된 확장 스타일을 포함하는 DWORD 값입니다.

### <a name="remarks"></a>설명

이러한 스타일에 대한 자세한 내용은 Windows SDK의 [ComboBoxEx 제어 확장 스타일을](/windows/win32/Controls/comboboxex-control-extended-styles) 참조하십시오.

확장된 창 스타일로 콤보 상자 확장 컨트롤을 만들려면 [CreateEx](#createex)를 사용합니다.

## <a name="ccomboboxexsetimagelist"></a><a name="setimagelist"></a>CComboBoxEx::세트이미지 리스트

컨트롤에 대한 이미지 `ComboBoxEx` 목록을 설정합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
컨트롤과 함께 `CImageList` 사용할 이미지를 포함하는 개체에 `CComboBoxEx` 대한 포인터입니다.

### <a name="return-value"></a>Return Value

컨트롤에서 이전에 사용한 이미지를 포함하는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체에 대한 포인터입니다. `CComboBoxEx` 이미지 목록이 이전에 설정되지 않은 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_SETIMAGELIST](/windows/win32/Controls/cbem-setimagelist)메시지의 기능을 구현합니다. 기본 편집 컨트롤의 높이를 변경하는 경우 Win32 함수 [SetWindowPos를](/windows/win32/api/winuser/nf-winuser-setwindowpos) 호출하여 `SetImageList`호출 한 후 컨트롤크기를 조정하거나 제대로 표시되지 않습니다.

반환 `CImageList` 값으로 가리키는 개체는 임시 개체이며 다음 유휴 처리 시간 동안 소멸됩니다.

## <a name="ccomboboxexsetitem"></a><a name="setitem"></a>CComboBoxEx::세트아이템

`ComboBoxEx` 컨트롤의 항목에 대한 속성을 설정합니다.

```
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```

### <a name="parameters"></a>매개 변수

*pCBItem*<br/>
항목 정보를 수신하는 [COMBOBOXEXITEM](/windows/win32/api/commctrl/ns-commctrl-comboboxexitemw) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_SETITEM](/windows/win32/Controls/cbem-setitem)메시지의 기능을 구현합니다.

## <a name="ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>CComboBoxEx::세트윈도우테마

확장된 콤보 상자 컨트롤의 시각적 스타일을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
설정할 확장 된 콤보 상자 시각적 스타일을 포함 하는 유니코드 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

반환 값은 사용되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 [CBEM_SETWINDOWTHEME](/windows/win32/Controls/cbem-setwindowtheme) 메시지의 기능을 에뮬레이트합니다.

## <a name="see-also"></a>참조

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)
