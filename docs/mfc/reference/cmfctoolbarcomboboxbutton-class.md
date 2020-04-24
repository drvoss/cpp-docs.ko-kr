---
title: CMFC툴바콤보박스버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: 995d7d0db55889130e1cad9585b8fc87285ffd27
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754017"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFC툴바콤보박스버튼 클래스

콤보 상자 컨트롤 [(CComboBox 클래스)가](../../mfc/reference/ccombobox-class.md)포함 된 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC툴바콤보박스버튼::CMFC툴바콤보박스버튼](#cmfctoolbarcomboboxbutton)|`CMFCToolBarComboBoxButton`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolBarCombo박스 버튼::추가 항목](#additem)|콤보 상자 목록의 끝에 항목을 추가합니다.|
|[CMFCToolBarComboBox버튼::추가 항목](#addsorteditem)|콤보 상자 목록에 항목을 추가합니다. 목록의 항목 순서는 에 `Compare`의해 지정됩니다.|
|[CMFCToolBarCombo박스 버튼::비교](#compare)|두 항목을 비교합니다. 콤보 상자 `AddSortedItems` 목록에 추가되는 항목을 정렬하도록 호출됩니다.|
|[CMFCToolBarComboBox버튼::만들기 편집](#createedit)|콤보 상자 단추에 대한 새 편집 컨트롤을 만듭니다.|
|[CMFC툴바콤보박스버튼::D](#deleteitem)|콤보 상자 목록에서 항목을 삭제합니다.|
|[CMFCToolBarCombo박스 버튼::찾기항목](#finditem)|지정된 문자열을 포함하는 항목의 인덱스를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::GetByCmd](#getbycmd)|지정된 명령 ID가 있는 콤보 상자 단추에 대한 포인터를 반환합니다.|
|[CMFC툴바콤보박스버튼::겟콤보박스](#getcombobox)|콤보 상자 단추에 포함된 콤보 상자 컨트롤에 대한 포인터를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟카운트](#getcount)|콤보 상자 목록의 항목 수를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟카운트올](#getcountall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾습니다. 해당 단추의 콤보 상자 목록에서 항목 수를 반환합니다.|
|[CMFC툴바콤보박스버튼::겟커셀](#getcursel)|콤보 상자 목록에서 선택한 항목의 인덱스를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟커셀올](#getcurselall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾아 해당 단추의 콤보 상자 목록에서 선택한 항목의 인덱스를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::GetEditCtrl](#geteditctrl)|콤보 상자 단추에 포함된 편집 컨트롤에 대한 포인터를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟아이템](#getitem)|콤보 상자 목록에서 지정된 인덱스와 연결된 문자열을 반환합니다.|
|[CMFCToolBarCombo박스 버튼::GetItemAll](#getitemall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾아 해당 단추의 콤보 상자 목록에서 인덱스와 연결된 문자열을 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟아이템데이터](#getitemdata)|콤보 상자 목록에서 지정된 인덱스와 연결된 32비트 값을 반환합니다.|
|[CMFCToolBarCombo박스 버튼::겟아이템데이터올](#getitemdataall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾아 해당 단추의 콤보 상자 목록에서 인덱스와 연결된 32비트 값을 반환합니다.|
|[CMFCToolBarComboBox버튼::겟아이템데이터Ptrall](#getitemdataptrall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾습니다. 해당 단추의 콤보 상자 목록에서 인덱스와 연결된 32비트 값을 검색하고 32비트 값을 포인터로 반환합니다.|
|[CMFCToolBarCombo박스 버튼::GetText](#gettext)|콤보 상자의 편집 컨트롤에서 텍스트를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::GetTextAll](#gettextall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾아 해당 단추의 편집 컨트롤에서 텍스트를 반환합니다.|
|[CMFCToolBarCombo박스 버튼::IsCenterVert](#iscentervert)|응용 프로그램의 콤보 상자 단추의 가운데또는 도구 모음의 맨 위에 정렬되는지 여부를 결정합니다.|
|[CMFCToolBarCombo박스 버튼::IsFlatmode](#isflatmode)|응용 프로그램의 콤보 상자 단추에 평평한 모양이 있는지 여부를 결정합니다.|
|[CMFCToolBarComboBox버튼::리모크모든항목](#removeallitems)|목록 상자에서 모든 항목을 제거하고 콤보 상자의 컨트롤을 편집합니다.|
|[CMFCToolBarCombo박스 버튼::선택항목](#selectitem)|인덱스, 32비트 값 또는 문자열에 따라 콤보 상자에서 항목을 선택하고 선택 항목에 대해 콤보 상자 컨트롤에 알린다.|
|[CMFCToolBarCombo박스 버튼::선택항목모두](#selectitemall)|지정된 명령 ID가 있는 콤보 상자 단추를 찾습니다. 문자열, 인덱스 또는 32비트 값에 따라 해당 단추의 콤보 상자에서 항목을 선택하려면 호출합니다. `SelectItem`|
|[CMFCToolBarCombo박스 버튼::설정원](#setcentervert)|응용 프로그램의 콤보 상자 단추를 수직으로 가운데에 두거나 도구 모음의 맨 위에 정렬하는지 지정합니다.|
|[CMFCToolBarCombo박스 버튼::세트드롭다운높이](#setdropdownheight)|드롭다운 목록 상자의 높이를 설정합니다.|
|[CMFCToolBarCombo박스 버튼::세트플랫모드](#setflatmode)|응용 프로그램의 콤보 상자 단추에 평평한 모양이 있는지 여부를 지정합니다.|

## <a name="remarks"></a>설명

도구 모음에 콤보 상자 단추를 추가하려면 다음 단계를 따르십시오.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

2. 개체를 `CMFCToolBarComboBoxButton` 생성합니다.

3. AFX_WM_RESETTOOLBAR 메시지를 처리하는 메시지 처리기에서 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)을 사용하여 더미 단추를 새 콤보 상자 단추로 바꿉습니다.

자세한 내용은 [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오. 콤보 상자 도구 모음 단추의 예는 VisualStudioDemo 프로젝트 예제를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarComboBoxButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 편집 및 콤보 상자를 활성화하고, 응용 프로그램에서 콤보 상자 단추의 세로 위치를 설정하고, 아래로 떨어뜨릴 때 목록 상자의 높이를 설정하고, 응용 프로그램에서 콤보 상자 단추의 플랫 스타일 모양을 설정하고, 콤보 상자 단추의 편집 상자에 텍스트를 설정하는 방법을 보여 주며, 이 중 에서 텍스트를 설정합니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFC툴바콤보박스버튼](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarcomboboxbutton.h

## <a name="cmfctoolbarcomboboxbuttonadditem"></a><a name="additem"></a>CMFCToolBarCombo박스 버튼::추가 항목

목록 상자에 고유한 항목을 추가합니다.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
【인】 목록 상자에 추가할 항목의 텍스트입니다.

*dwData*<br/>
【인】 목록 상자에 추가할 항목과 연결된 데이터입니다.

### <a name="return-value"></a>Return Value

목록 상자의 마지막 항목의 인덱스입니다.

### <a name="remarks"></a>설명

목록 상자 스타일이 정렬될 때이 메서드를 사용하지 마십시오.

항목 텍스트가 목록 상자에 이미 있는 경우 새 데이터는 기존 항목과 함께 저장됩니다. 항목에 대한 검색은 대/소문자를 구분합니다.

## <a name="cmfctoolbarcomboboxbuttonaddsorteditem"></a><a name="addsorteditem"></a>CMFCToolBarComboBox버튼::추가 항목

[비교](#compare) 메서드에 의해 정의된 순서대로 목록 상자에 항목을 추가합니다.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
【인】 목록 상자에 추가할 항목의 텍스트입니다.

*dwData*<br/>
【인】 목록 상자에 추가할 항목과 연결된 데이터입니다.

### <a name="return-value"></a>Return Value

목록 상자에 추가된 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 목록 상자에 특정 순서로 항목을 추가합니다.

## <a name="cmfctoolbarcomboboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarCombo박스 버튼::캔스트레치

콤보 상자 단추 크기가 변경될 수 있는지 여부를 나타냅니다.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Return Value

TRUE를 반환합니다.

## <a name="cmfctoolbarcomboboxbuttoncmfctoolbarcomboboxbutton"></a><a name="cmfctoolbarcomboboxbutton"></a>CMFC툴바콤보박스버튼::CMFC툴바콤보박스버튼

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체를 생성합니다.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 새 단추의 명령 ID입니다.

*아이 이미지*<br/>
【인】 새 단추와 연결된 이미지의 이미지 인덱스입니다.

*dwStyle*<br/>
【인】 새 단추의 스타일입니다.

*아이 폭*<br/>
【인】 새 단추의 너비(픽셀 단위)입니다.

### <a name="remarks"></a>설명

기본 너비는 150픽셀입니다.

도구 모음 단추 스타일 목록은 [도구 모음 컨트롤 스타일을](../../mfc/reference/toolbar-control-styles.md) 참조하십시오.

## <a name="cmfctoolbarcomboboxbuttoncleardata"></a><a name="cleardata"></a>CMFCToolBarCombo박스 버튼::클리어 데이터

사용자 정의 데이터를 삭제합니다.

```
virtual void ClearData();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 아무 것도 수행하지 않습니다. 사용자 정의 데이터를 삭제하려면 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfctoolbarcomboboxbuttoncompare"></a><a name="compare"></a>CMFCToolBarCombo박스 버튼::비교

두 문자열을 비교합니다.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>매개 변수

*lpszItem1*<br/>
【인】 비교할 첫 번째 문자열입니다.

*lpsz항목2*<br/>
【인】 비교할 두 번째 문자열입니다.

### <a name="return-value"></a>Return Value

문자열 간의 대/소문자 구분 사전 관계를 나타내는 값입니다. 다음 테이블에서는 가능한 값을 나열합니다.

|값|Description|
|-----------|-----------------|
|\<0|첫 번째 문자열은 두 번째 문자열보다 적습니다.|
|0|첫 번째 문자열은 두 번째 문자열과 같습니다.|
|>0|첫 번째 문자열은 두 번째 문자열보다 큽합니다.|

### <a name="remarks"></a>설명

이 메서드를 재정의하여 목록 상자에서 항목을 정렬하는 방법을 변경합니다.

비교는 대/소문자를 구분합니다.

이 메서드는 [AddSortedItem](#addsorteditem) 메서드에서만 호출됩니다.

## <a name="cmfctoolbarcomboboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarCombo박스 버튼::복사에서

지정된 `CMFCToolBarComboBoxButton` 상태를 현재 개체에 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 소스 `CMFCToolBarComboBoxButton` 개체입니다.

## <a name="cmfctoolbarcomboboxbuttoncreatecombo"></a><a name="createcombo"></a>CMFCToolBarCombo박스 버튼::만들기콤보

콤보 상자 단추에 대 한 새 콤보 상자를 만듭니다.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 단추의 상위 창에 대한 포인터입니다.

*rect*<br/>
【인】 콤보 상자의 경계 사각형입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 새 콤보 상자에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

## <a name="cmfctoolbarcomboboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarComboBox버튼::만들기 편집

콤보 상자 단추에 대한 새 편집 상자를 만듭니다.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 단추의 상위 창에 대한 포인터입니다.

*rect*<br/>
【인】 새 편집 상자의 경계 사각형입니다.

*dwEditStyle*<br/>
【인】 새 편집 상자의 제어 스타일입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 새 편집 상자에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

프레임워크는 콤보 상자 단추에 대한 새 편집 상자를 만들 때 이 메서드를 호출합니다. [CMFCToolBarComboBoxEdit이](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) 생성되는 방법을 변경하려면 이 메서드를 재정의합니다.

## <a name="cmfctoolbarcomboboxbuttondeleteitem"></a><a name="deleteitem"></a>CMFC툴바콤보박스버튼::D

목록 상자에서 지정된 항목을 삭제합니다.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 삭제할 항목의 0기준 인덱스입니다.

*dwData*<br/>
【인】 삭제할 항목과 연결된 데이터입니다.

*lpszText*<br/>
【인】 삭제할 항목의 텍스트입니다. 동일한 텍스트를 가진 여러 항목이 있는 경우 첫 번째 항목이 삭제됩니다.

### <a name="return-value"></a>Return Value

TRUE 항목이 위치하여 성공적으로 삭제된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttonduplicatedata"></a><a name="duplicatedata"></a>CMFCToolBarComboBox버튼::D업리케이트데이터

사용자 정의 데이터를 복제합니다.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 아무 것도 수행하지 않습니다. 사용자 정의 데이터를 복사하려는 경우 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfctoolbarcomboboxbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarCombo박스 버튼::인에이블윈도우

편집 및 콤보 상자를 활성화하거나 사용하지 않도록 설정합니다.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 편집 및 콤보 상자를 활성화합니다. FALSE를 사용하여 편집 및 콤보 상자를 비활성화합니다.

### <a name="remarks"></a>설명

사용하지 않도록 설정하면 컨트롤이 활성화될 수 없으며 사용자 입력을 허용할 수 없습니다.

## <a name="cmfctoolbarcomboboxbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarComboBox버튼::내보내기 메뉴 버튼

콤보 상자 단추 명령 ID를 사용하여 응용 프로그램 문자열 테이블에서 지정된 메뉴로 문자열을 복사합니다.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>매개 변수

*메뉴 버튼*<br/>
【아웃】 메뉴 단추를 참조합니다.

### <a name="return-value"></a>Return Value

항상 TRUE입니다.

## <a name="cmfctoolbarcomboboxbuttonfinditem"></a><a name="finditem"></a>CMFCToolBarCombo박스 버튼::찾기항목

지정된 문자열이 포함된 목록 상자의 첫 번째 항목의 인덱스를 반환합니다.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【인】 목록 상자에서 검색할 텍스트입니다.

### <a name="return-value"></a>Return Value

항목의 인덱스; 또는 CB_ERR 찾을 수 없는 경우

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarCombo박스 버튼::GetByCmd

지정된 명령 ID가 있는 콤보 상자 단추에 대한 포인터를 가져옵니다.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

*비스 포커스*<br/>
【인】 TRUE는 초점을 맞춘 버튼만 검색합니다. FALSE는 모든 버튼을 검색합니다.

### <a name="return-value"></a>Return Value

콤보 상자 단추에 대 한 포인터; 또는 NULL을 찾을 수 없는 경우

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetcombobox"></a><a name="getcombobox"></a>CMFC툴바콤보박스버튼::겟콤보박스

콤보 상자 단추의 콤보 상자에 대한 포인터를 반환합니다.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md) 개체에 대한 포인터입니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarCombo박스 버튼::GetContextMenuID

콤보 상자 단추의 바로 가기 메뉴 리소스 ID를 가져옵니다.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Return Value

바로 가기 메뉴 리소스 ID입니다.

## <a name="cmfctoolbarcomboboxbuttongetcount"></a><a name="getcount"></a>CMFCToolBarCombo박스 버튼::겟카운트

목록 상자의 항목 수를 반환합니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 항목 수입니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetcountall"></a><a name="getcountall"></a>CMFCToolBarCombo박스 버튼::겟카운트올

지정된 명령 ID가 있는 콤보 상자 단추의 목록 상자에 항목 수를 가져옵니다.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

목록 상자의 항목 수입니다. 그렇지 않으면 콤보 상자 버튼을 찾을 수 없는 경우 CB_ERR.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetcursel"></a><a name="getcursel"></a>CMFC툴바콤보박스버튼::겟커셀

목록 상자에서 현재 선택한 항목의 인덱스를 가져옵니다.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

목록 상자에서 현재 선택된 항목의 인덱스입니다. 또는 항목이 선택되지 않은 경우 CB_ERR.

### <a name="remarks"></a>설명

목록 상자 인덱스는 0을 기반으로 합니다.

## <a name="cmfctoolbarcomboboxbuttongetcurselall"></a><a name="getcurselall"></a>CMFCToolBarCombo박스 버튼::겟커셀올

지정된 명령 ID가 있는 콤보 상자 단추의 목록 상자에 현재 선택된 항목의 인덱스를 반환합니다.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

목록 상자에서 현재 선택된 항목의 인덱스입니다. 그렇지 않으면 항목을 선택하지 않거나 콤보 상자 단추를 찾을 수 없는 경우 CB_ERR.

### <a name="remarks"></a>설명

목록 상자 인덱스는 0을 기반으로 합니다.

## <a name="cmfctoolbarcomboboxbuttongeteditctrl"></a><a name="geteditctrl"></a>CMFCToolBarCombo박스 버튼::GetEditCtrl

콤보 상자 단추의 편집 상자에 대한 포인터를 반환합니다.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 편집 상자에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongethwnd"></a><a name="gethwnd"></a>CMFC툴바콤보박스버튼::겟힌드

콤보 상자에 대한 창 핸들을 반환합니다.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Return Value

콤보 상자가 창 개체와 연결되지 않은 경우 창 핸들 또는 NULL입니다.

## <a name="cmfctoolbarcomboboxbuttongetitem"></a><a name="getitem"></a>CMFCToolBarCombo박스 버튼::겟아이템

목록 상자의 지정된 인덱스에서 항목과 연결된 문자열을 반환합니다.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

항목과 연결된 문자열에 대한 포인터입니다. 그렇지 않으면 index 매개 변수가 유효하지 않거나 인덱스 매개 변수가 -1이고 콤보 상자에 선택된 항목이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

-1의 인덱스 매개 변수는 현재 선택된 항목의 문자열을 반환합니다.

## <a name="cmfctoolbarcomboboxbuttongetitemall"></a><a name="getitemall"></a>CMFCToolBarCombo박스 버튼::GetItemAll

지정된 명령 ID가 있는 콤보 상자 단추의 목록 상자에 지정된 인덱스에서 항목과 연결된 문자열을 반환합니다.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 항목의 문자열에 대한 포인터입니다. 그렇지 않으면 인덱스가 유효하지 않은 경우 NULL을 찾을 수 없거나 인덱스가 -1이고 콤보 상자에 선택된 항목이 없는 경우 콤보 상자에서 선택된 항목이 없습니다.

### <a name="remarks"></a>설명

인덱스 값 -1은 현재 선택된 항목의 문자열을 반환합니다.

## <a name="cmfctoolbarcomboboxbuttongetitemdata"></a><a name="getitemdata"></a>CMFCToolBarCombo박스 버튼::겟아이템데이터

목록 상자의 특정 인덱스에서 항목과 연결된 데이터를 반환합니다.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

항목과 연결된 데이터; 또는 0 항목이 없는 경우.

### <a name="remarks"></a>설명

-1의 인덱스 매개 변수는 현재 선택한 항목과 연결된 데이터를 반환합니다.

## <a name="cmfctoolbarcomboboxbuttongetitemdataall"></a><a name="getitemdataall"></a>CMFCToolBarCombo박스 버튼::겟아이템데이터올

특정 명령 ID가 있는 콤보 상자 단추의 목록 상자에 있는 특정 인덱스에서 항목과 관련된 데이터를 반환합니다.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 항목과 연결된 데이터입니다. 그렇지 않으면 지정된 인덱스가 유효하지 않은 경우 0이거나 콤보 상자 단추가 없는 경우 CB_ERR.

### <a name="remarks"></a>설명

-1의 인덱스 매개 변수는 현재 선택한 항목과 연결된 데이터를 반환합니다.

## <a name="cmfctoolbarcomboboxbuttongetitemdataptrall"></a><a name="getitemdataptrall"></a>CMFCToolBarComboBox버튼::겟아이템데이터Ptrall

특정 명령 ID가 있는 콤보 상자 단추의 목록 상자에 있는 특정 인덱스에서 항목과 관련된 데이터를 반환합니다. 이 데이터는 포인터로 반환됩니다.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 항목과 연결된 포인터입니다. 그렇지 않으면 오류가 발생하면 -1, 콤보 상자 단추를 찾을 수 없는 경우 NULL이 나타납니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongetprompt"></a><a name="getprompt"></a>CMFCToolBarComboBox버튼::Get프롬프트

콤보 상자 단추에 대 한 프롬프트 문자열을 반환 합니다.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Return Value

프롬프트 문자열입니다.

### <a name="remarks"></a>설명

이 메서드는 현재 구현되지 않았습니다.

## <a name="cmfctoolbarcomboboxbuttongettext"></a><a name="gettext"></a>CMFCToolBarCombo박스 버튼::GetText

편집 상자에 텍스트를 가져옵니다.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Return Value

편집 상자의 텍스트입니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttongettextall"></a><a name="gettextall"></a>CMFCToolBarCombo박스 버튼::GetTextAll

지정된 명령 ID가 있는 콤보 상자 단추의 편집 상자에 텍스트를 가져옵니다.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 특정 콤보 상자 단추의 명령 ID입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 편집 상자의 텍스트입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarCombo박스 버튼::하스포커스

콤보 상자에 현재 포커스가 있는지 여부를 나타냅니다.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Return Value

콤보 상자에 현재 포커스가 있는 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 현재 콤보 상자의 자식 창에 포커스가 있는 경우 TRUE를 반환합니다.

## <a name="cmfctoolbarcomboboxbuttoniscentervert"></a><a name="iscentervert"></a>CMFCToolBarCombo박스 버튼::IsCenterVert

응용 프로그램에서 콤보 상자 단추의 수직 위치를 반환합니다.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Return Value

TRUE 단추의 가운데가 있는 경우. 버튼이 맨 위에 정렬된 경우 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarCombo박스 버튼::IsFlatmode

응용 프로그램에서 콤보 상자 단추의 플랫 스타일 모양을 반환합니다.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Return Value

단추에 플랫 스타일이 있는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

콤보 상자 단추의 기본 플랫 스타일은 FALSE입니다.

## <a name="cmfctoolbarcomboboxbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarCombo박스 버튼::IsOwnerOf

지정된 핸들이 콤보 상자 단추와 연결되어 있는지 또는 해당 자식 중 하나와 연결되어 있는지 를 나타냅니다.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 창 핸들입니다.

### <a name="return-value"></a>Return Value

핸들이 콤보 상자 버튼 또는 자식 중 하나와 연관된 경우 TRUE; 그렇지 않으면 false입니다.

## <a name="cmfctoolbarcomboboxbuttonisribbonbutton"></a><a name="isribbonbutton"></a>CMFCToolBarCombo상자 버튼::이리본 버튼

콤보 상자 버튼이 리본 패널에 있는지 여부를 나타냅니다.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Return Value

항상 FALSE입니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 항상 FALSE를 반환하므로 콤보 상자 단추가 리본 패널에 표시되지 않습니다.

## <a name="cmfctoolbarcomboboxbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarCombo박스 버튼::이 윈도우 볼 수

콤보 상자 단추의 가시성 상태를 반환합니다.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Return Value

콤보 상자 단추의 가시성 상태입니다.

## <a name="cmfctoolbarcomboboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarComboBox버튼::알림 명령

콤보 상자 단추에서 메시지를 처리하는지 여부를 나타냅니다.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>매개 변수

*iNotifyCode*<br/>
【인】 명령과 연결된 알림 메시지입니다.

### <a name="return-value"></a>Return Value

콤보 상자 단추가 메시지를 처리하는지 여부입니다.

## <a name="cmfctoolbarcomboboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarComboBox버튼::OnAddTo사용자 정의 페이지

단추를 **사용자 지정** 대화 상자에 추가 될 때 프레임 워크에 의해 호출 됩니다.

```
virtual void OnAddToCustomizePage();
```

## <a name="cmfctoolbarcomboboxbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarCombo박스 버튼::온계산크기

단추의 크기를 계산 하는 프레임 워크에 의해 호출 됩니다.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 콤보 상자 단추를 표시 하는 장치 컨텍스트입니다.

*크기기본값*<br/>
【인】 콤보 상자 단추의 기본 크기입니다.

*b호르츠 (주)*<br/>
【인】 상위 도구 모음의 도크 상태입니다. TRUE 도구 모음이 수평으로 도킹되고 도구 모음이 세로로 도킹될 때 FALSE입니다.

### <a name="return-value"></a>Return Value

콤보 상자 단추의 치수를 픽셀 단위로 포함하는 `SIZE` 구조입니다.

## <a name="cmfctoolbarcomboboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarCombo박스 버튼::온체인지부모

콤보 상자 단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 새 상위 도구 모음에 대한 포인터입니다.

## <a name="cmfctoolbarcomboboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarCombo박스 버튼::온클릭

사용자가 콤보 상자 단추를 클릭할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 콤보 상자 단추의 상위 창에 대한 포인터입니다.

*bDelay*<br/>
【인】 파생 클래스에서 사용하도록 예약되었습니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 이벤트를 처리하는 경우; 그렇지 않으면 false입니다.

## <a name="cmfctoolbarcomboboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarCombo박스 버튼::온CtlColor

사용자가 상위 도구 모음 색상을 변경하여 콤보 상자 단추 색상을 설정할 때 프레임워크에서 호출합니다.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 콤보 상자 단추를 표시 하는 장치 컨텍스트입니다.

*nCtlColor*<br/>
【인】 하지 않는.

### <a name="return-value"></a>Return Value

프레임워크가 콤보 상자 단추의 배경을 그리는 데 사용하는 브러시를 처리합니다.

### <a name="remarks"></a>설명

이 메서드는 콤보 상자 단추 텍스트 색상도 설정 합니다.

## <a name="cmfctoolbarcomboboxbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarCombo박스 버튼::온드로우

지정된 스타일과 옵션을 사용하여 콤보 상자 단추를 그리는 프레임 워크에 의해 호출됩니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>매개 변수

*Pdc*<br/>
【인】 단추를 표시 하는 장치 컨텍스트입니다.

*rect*<br/>
【인】 단추의 경계 사각형입니다.

*p 이미지*<br/>
【인】 단추와 연결된 이미지의 컬렉션입니다.

*b호르츠 (주)*<br/>
【인】 상위 도구 모음의 도크 상태입니다. TRUE 도구 모음이 수평으로 도킹되고 도구 모음이 세로로 도킹될 때 FALSE입니다.

*b 사용자 정의 모드*<br/>
【인】 응용 프로그램이 사용자 지정 모드에 있는지 여부입니다.

*bHighlight*<br/>
【인】 콤보 상자 버튼을 그릴지 여부가 강조 표시됩니다.

*b드드로우보더*<br/>
【인】 테두리가 있는 콤보 상자 단추를 그릴지 여부입니다.

*b회색비활성화단추*<br/>
【인】 TRUE는 그늘진 비활성화 된 버튼을 그립니다; FALSE를 사용하여 비활성화된 이미지 컬렉션을 사용합니다.

## <a name="cmfctoolbarcomboboxbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarComboBox버튼::온드로온커스터

**사용자 지정 대화** 상자의 명령 창에서 콤보 상자 단추를 그리는 프레임워크에서 **호출합니다.**

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 콤보 상자 단추를 표시 하는 장치 컨텍스트입니다.

*rect*<br/>
【인】 콤보 상자 단추의 경계 사각형입니다.

*b 선택됨*<br/>
【인】 콤보 상자 버튼을 선택한 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

콤보 상자 단추의 너비(픽셀 단위)입니다.

## <a name="cmfctoolbarcomboboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarCombo박스 버튼::온글로벌폰트변경

응용 프로그램 글꼴이 변경될 때 콤보 상자 단추 글꼴을 설정하려면 프레임워크에서 호출합니다.

```
virtual void OnGlobalFontsChanged();
```

## <a name="cmfctoolbarcomboboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarCombo박스 버튼::온무

상위 도구 모음이 이동할 때 콤보 상자 단추의 위치를 변경하려면 프레임워크에서 호출합니다.

```
virtual void OnMove();
```

## <a name="cmfctoolbarcomboboxbuttononshow"></a><a name="onshow"></a>CMFC툴바콤보박스버튼::온쇼

콤보 상자 단추를 숨기거나 표시 할 때 프레임 워크에 의해 호출됩니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 콤보 상자 단추를 숨기거나 표시할지 여부입니다.

## <a name="cmfctoolbarcomboboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarCombo박스 버튼::온사이즈

상위 도구 모음의 크기를 변경할 때 콤보 상자 단추의 크기를 변경 하려면 프레임 워크에 의해 호출 됩니다.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>매개 변수

*아이 사이즈*<br/>
【인】 콤보 상자 버튼의 새 너비입니다.

## <a name="cmfctoolbarcomboboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarCombo박스 버튼::온업데이트툴팁

사용자가 콤보 상자 단추에 대 한 도구 설명을 변경할 때 프레임 워크에 의해 호출 됩니다.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 콤보 상자 단추의 부모 창에 대한 포인터입니다.

*아이 버튼 인덱스*<br/>
【인】 콤보 상자 버튼의 ID입니다.

*wndToolTip*<br/>
【인】 콤보 상자 단추와 연결할 도구 설명입니다.

*Str*<br/>
【인】 도구 팁 텍스트입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 이벤트를 처리하는 경우; 그렇지 않으면 false입니다.

## <a name="cmfctoolbarcomboboxbuttonremoveallitems"></a><a name="removeallitems"></a>CMFCToolBarComboBox버튼::리모크모든항목

목록에서 모든 항목을 삭제하고 상자를 편집합니다.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>설명

목록 상자에서 모든 항목을 제거하고 콤보 상자의 컨트롤을 편집합니다.

## <a name="cmfctoolbarcomboboxbuttonselectitem"></a><a name="selectitem"></a>CMFCToolBarCombo박스 버튼::선택항목

목록 상자에서 항목을 선택합니다.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

*bNotify*<br/>
【인】 TRUE는 선택의 콤보 박스 버튼을 통지하는; 그렇지 않으면 거짓.

*dwData*<br/>
【인】 목록 상자의 항목과 연결된 데이터입니다.

*lpszText*<br/>
【인】 목록 상자에 있는 항목의 텍스트입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttonselectitemall"></a><a name="selectitemall"></a>CMFCToolBarCombo박스 버튼::선택항목모두

지정된 명령 ID가 있는 콤보 상자 단추의 목록 상자에서 항목을 선택합니다.

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 목록 상자가 포함된 콤보 상자 단추의 명령 ID입니다.

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다. 값이 -1이면 목록 상자의 현재 선택 영역이 제거되고 편집 상자가 지워지습니다.

*dwData*<br/>
【인】 목록 상자의 항목 데이터입니다.

*lpszText*<br/>
【인】 목록 상자에 있는 항목의 텍스트입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfctoolbarcomboboxbuttonserialize"></a><a name="serialize"></a>CMFCToolBarCombo박스 버튼::직렬화

이 개체를 아카이브에서 읽거나 아카이브에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
【인, 아웃】 직렬화할 `CArchive` 개체입니다.

### <a name="remarks"></a>설명

개체의 `CArchive` 설정은 이 메서드가 아카이브에 읽거나 쓰는지 여부를 결정합니다.

## <a name="cmfctoolbarcomboboxbuttonsetaccdata"></a><a name="setaccdata"></a>CMFC툴바콤보박스버튼::세타크데이터

콤보 상자 `CAccessibilityData` 단추의 내게 필요한 옵션 데이터를 사용하여 지정된 개체를 채웁니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
【인】 콤보 상자 단추의 상위 창입니다.

*데이터*<br/>
【아웃】 콤보 상자 단추에서 내게 필요한 옵션 데이터를 수신하는 `CAccessibilityData` 개체입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cmfctoolbarcomboboxbuttonsetcentervert"></a><a name="setcentervert"></a>CMFCToolBarCombo박스 버튼::설정원

응용 프로그램에서 콤보 상자 단추의 수직 위치를 설정합니다.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>매개 변수

*b중심버트*<br/>
【인】 TRUE는 도구 모음의 콤보 상자 버튼을 중앙에 두는 것입니다. FALSE를 클릭하여 콤보 상자 단추를 도구 모음 의 맨 위에 정렬합니다.

### <a name="remarks"></a>설명

기본적으로 콤보 상자 버튼은 맨 위에 정렬됩니다.

## <a name="cmfctoolbarcomboboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarCombo박스 버튼::세트컨텍스트메뉴ID

콤보 상자 단추의 바로 가기 메뉴 리소스 ID를 설정합니다.

```cpp
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>매개 변수

*uiResID*<br/>
【인】 바로 가기 메뉴 리소스 ID입니다.

## <a name="cmfctoolbarcomboboxbuttonsetdropdownheight"></a><a name="setdropdownheight"></a>CMFCToolBarCombo박스 버튼::세트드롭다운높이

목록 상자를 삭제할 때 목록 상자의 높이를 설정합니다.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>매개 변수

*nHeight*<br/>
【인】 목록 상자의 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

기본 높이는 150픽셀입니다.

## <a name="cmfctoolbarcomboboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarCombo박스 버튼::세트플랫모드

응용 프로그램에서 콤보 상자 단추의 플랫 스타일 모양을 설정합니다.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>매개 변수

*b플랫*<br/>
【인】 플랫 스타일 외관에 대한 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

콤보 상자 단추의 기본 플랫 스타일은 FALSE입니다.

## <a name="cmfctoolbarcomboboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarCombo박스 버튼::세트스타일

콤보 상자 단추에 대해 지정된 스타일을 설정하고 비활성화되지 않은 경우 컨트롤을 다시 그립니다.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
【인】 도구 모음 스타일의 비트 조합(OR)입니다.

### <a name="remarks"></a>설명

도구 모음 단추 스타일 목록은 [도구 모음 컨트롤 스타일을](../../mfc/reference/toolbar-control-styles.md) 참조하십시오.

## <a name="cmfctoolbarcomboboxbuttonsettext"></a><a name="settext"></a>CMFCToolBarCombo박스 버튼::세트텍스트

콤보 상자 단추의 편집 상자에 텍스트를 설정합니다.

```cpp
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【인】 편집 상자에 대한 텍스트가 포함된 문자열에 대한 포인터입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CMFC툴바::대체 버튼](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
