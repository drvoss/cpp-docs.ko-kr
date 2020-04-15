---
title: CMFC리본콤보박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: 5846b1c5590a756f0a0820583af3d0b159968ea2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375234"
---
# <a name="cmfcribboncombobox-class"></a>CMFC리본콤보박스 클래스

클래스는 `CMFCRibbonComboBox` 리본 막대, 리본 패널 또는 리본 팝업 메뉴에 추가할 수 있는 콤보 상자 컨트롤을 구현합니다.

## <a name="syntax"></a>구문

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본콤보박스::CMFC리본콤보박스](#cmfcribboncombobox)|CMFC리본ComboBox 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본콤보박스::추가 항목](#additem)|목록 상자에 고유한 항목을 추가합니다.|
|[CMFC리본콤보박스::D](#deleteitem)|목록 상자에서 지정된 항목을 삭제합니다.|
|[CMFC리본콤보박스::인에이블드롭다운리스트리사이즈](#enabledropdownlistresize)|목록 상자가 떨어질 때 크기를 변경할 수 있는지 여부를 지정합니다.|
|[CMFC리본콤보박스::찾기항목](#finditem)|지정된 문자열과 일치하는 목록 상자에서 첫 번째 항목의 인덱스를 반환합니다.|
|[CMFC리본콤보박스::겟카운트](#getcount)|목록 상자의 항목 수를 반환합니다.|
|[CMFC리본콤보박스::겟커셀](#getcursel)|목록 상자에서 현재 선택한 항목의 인덱스를 가져옵니다.|
|[CMFC리본콤보박스::드롭다운높이](#getdropdownheight)|목록 상자를 삭제하면 목록 상자의 높이를 가져옵니다.|
|[CMFC리본콤보박스::겟중간크기](#getintermediatesize)|중간 모드에 표시된 콤보 상자의 크기를 반환합니다.|
|[CMFC리본콤보박스::겟아이템](#getitem)|목록 상자의 지정된 인덱스에서 항목과 연결된 문자열을 반환합니다.|
|[CMFC리본콤보박스::겟아이템데이터](#getitemdata)|목록 상자의 지정된 인덱스에서 항목과 연결된 데이터를 반환합니다.|
|[CMFC리본콤보박스::하세티박스](#haseditbox)|컨트롤에 편집 상자가 포함되어 있는지 여부를 나타냅니다.|
|[CMFC리본콤보박스::이스리사이즈드롭다운리스트](#isresizedropdownlist)|목록 상자의 크기를 조정할 수 있는지 여부를 나타냅니다.|
|[CMFC리본콤보박스::온셀렉션아이템](#onselectitem)|사용자가 목록 상자에서 항목을 선택할 때 프레임워크에서 호출됩니다.|
|[CMFC리본콤보박스::리모그올아이템](#removeallitems)|목록 상자에서 모든 항목을 삭제하고 편집 상자를 지웁습니다.|
|[CMFC리본콤보박스::선택항목](#selectitem)|목록 상자에서 항목을 선택합니다.|
|[CMFC리본콤보박스::세트드롭다운높이](#setdropdownheight)|목록 상자를 삭제할 때 목록 상자의 높이를 설정합니다.|

## <a name="remarks"></a>설명

리본 콤보 상자는 사용자가 편집할 수 있는 정적 레이블 또는 레이블과 결합된 목록 상자로 구성됩니다. 리본 콤보 상자를 만들 때 원하는 유형을 지정해야 합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonComboBox` 클래스의 개체를 구성하고, 콤보 상자에 항목을 추가하고, 콤보 상자에서 항목을 선택하고, 패널에 콤보 상자를 추가하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribboncombobox.h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a>CMFC리본콤보박스::추가 항목

목록 상자에 고유한 항목을 추가합니다.

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>매개 변수

*lpszItem*<br/>
【인】 추가할 항목의 문자열입니다.

*dwData*<br/>
【인】 추가할 항목과 연결된 데이터입니다.

### <a name="return-value"></a>Return Value

추가된 항목의 0기준 인덱스입니다.

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a>CMFC리본콤보박스::CMFC리본콤보박스

`CMFCRibbonComboBox` 개체를 생성합니다.

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 콤보 상자의 ID입니다.

*bHasEditBox*<br/>
【인】 TRUE 컨트롤 내에서 편집 상자를 원하는 경우. 그렇지 않으면 거짓.

*nWidth*<br/>
【인】 픽셀 단위로 콤보 상자의 너비; 또는 기본 너비에 대해 -1입니다.

*lpszLabel*<br/>
【인】 콤보 상자의 표시 레이블입니다.

*nImage*<br/>
【인】 콤보 상자의 작은 이미지 인덱스입니다.

### <a name="remarks"></a>설명

기본 너비는 108픽셀입니다.

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a>CMFC리본콤보박스::D

목록 상자에서 지정된 항목을 삭제합니다.

```cpp
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
【인】 삭제할 항목의 문자열입니다. 문자열이 같은 항목이 여러 개 있는 경우 첫 번째 항목이 삭제됩니다.

### <a name="return-value"></a>Return Value

TRUE 지정된 항목이 삭제된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a>CMFC리본콤보박스::인에이블드롭다운리스트리사이즈

목록 상자가 떨어질 때 크기를 변경할 수 있는지 여부를 지정합니다.

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 크기 조정을 가능하게 합니다. 크기 조정을 사용하지 않도록 설정하는 FALSE입니다.

### <a name="remarks"></a>설명

크기 조정을 사용하도록 설정하면 목록 상자가 표시되는 항목에 맞게 크기가 변경됩니다.

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a>CMFC리본콤보박스::찾기항목

지정된 문자열과 일치하는 목록 상자에서 첫 번째 항목의 인덱스를 반환합니다.

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
【인】 목록 상자에 있는 항목의 문자열입니다.

### <a name="return-value"></a>Return Value

항목의 0기반 인덱스; 또는 -1 항목을 찾을 수 없는 경우

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a>CMFC리본콤보박스::겟카운트

목록 상자의 항목 수를 반환합니다.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 항목 수 또는 목록 상자에 항목이 없는 경우 0입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a>CMFC리본콤보박스::겟커셀

목록 상자에서 현재 선택한 항목의 인덱스를 가져옵니다.

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>Return Value

목록 상자에서 현재 선택된 항목의 0기반 인덱스; 또는 -1 을 선택하지 않으면 -1이 됩니다.

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a>CMFC리본콤보박스::드롭다운높이

목록 상자를 삭제하면 목록 상자의 높이를 가져옵니다.

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>Return Value

목록 상자의 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFC리본콤보박스::겟중간크기

중간 모드에 표시된 콤보 상자의 크기를 반환합니다.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 콤보 상자에 대한 장치 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

콤보 상자의 크기입니다.

### <a name="remarks"></a>설명

반환되는 크기는 작은 이미지를 표시할 때 콤보 상자의 크기를 기준으로 합니다.

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a>CMFC리본콤보박스::겟아이템

목록 상자의 지정된 인덱스에서 항목과 연결된 문자열을 반환합니다.

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

항목과 연결된 문자열에 대한 포인터입니다. 그렇지 않으면 index 매개 변수가 유효하지 않거나 인덱스 매개 변수가 -1이고 콤보 상자에 선택된 항목이 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a>CMFC리본콤보박스::겟아이템데이터

목록 상자의 지정된 인덱스에서 항목과 연결된 데이터를 반환합니다.

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

### <a name="return-value"></a>Return Value

항목과 연결된 데이터; 또는 항목이 존재하지 않거나 인덱스 매개 변수가 -1이고 목록 상자에 선택된 항목이 없는 경우 또는 0입니다.

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a>CMFC리본콤보박스::하세티박스

컨트롤에 편집 상자가 포함되어 있는지 여부를 나타냅니다.

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Return Value

TRUE 컨트롤에 편집 상자가 포함되어 있는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a>CMFC리본콤보박스::이스리사이즈드롭다운리스트

목록 상자의 크기를 조정할 수 있는지 여부를 나타냅니다.

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Return Value

목록 상자의 크기를 조정할 수 있는 경우 TRUE입니다. 그렇지 않으면 거짓. [CMFC리본콤보박스::인에이블드롭다운리스트리사이즈](#enabledropdownlistresize)

### <a name="remarks"></a>설명

[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) 메서드를 사용하여 목록 상자 크기 조정을 활성화할 수 있습니다.

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a>CMFC리본콤보박스::온셀렉션아이템

사용자가 목록 상자에서 항목을 선택할 때 프레임워크에서 호출됩니다.

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>매개 변수

*nItem*<br/>
【인】 선택한 항목의 인덱스입니다.

### <a name="remarks"></a>설명

사용자 입력 선택을 처리하려는 경우 이 메서드를 재정의합니다.

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a>CMFC리본콤보박스::리모그올아이템

목록 상자에서 모든 항목을 삭제하고 편집 상자를 지웁습니다.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a>CMFC리본콤보박스::선택항목

목록 상자에서 항목을 선택합니다.

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 목록 상자에 있는 항목의 0기준 인덱스입니다.

*dwData*<br/>
【인】 목록 상자의 항목과 연결된 데이터입니다.

*lpszText*<br/>
【인】 목록 상자에 있는 항목의 문자열입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a>CMFC리본콤보박스::세트드롭다운높이

목록 상자를 삭제할 때 목록 상자의 높이를 설정합니다.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>매개 변수

*nHeight*<br/>
【인】 목록 상자의 높이(픽셀 단위)입니다.

### <a name="remarks"></a>설명

기본 높이는 150픽셀입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본 편집 클래스](../../mfc/reference/cmfcribbonedit-class.md)
