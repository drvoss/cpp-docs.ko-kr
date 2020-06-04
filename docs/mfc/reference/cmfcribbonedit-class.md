---
title: CMFC리본 편집 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: ab621a05f9b658eee9babb14e257680fa95e0f96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375174"
---
# <a name="cmfcribbonedit-class"></a>CMFC리본 편집 클래스

리본 막대에 있는 편집 컨트롤을 구현합니다.

## <a name="syntax"></a>구문

```cpp
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|컨트롤의 높이가 `CMFCRibbonEdit` 리본 행의 높이까지 수직으로 증가할 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` 개체를 생성합니다.|
|[CMFC리본 편집::복사에서](#copyfrom)|지정된 `CMFCRibbonEdit` 개체의 상태를 현재 `CMFCRibbonEdit` 개체에 복사합니다.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|`CMFCRibbonEdit` 개체에 대한 새 텍스트 상자를 만듭니다.|
|[CMFC리본 편집::D에스트로이트툴](#destroyctrl)|개체를 `CMFCRibbonEdit` 삭제합니다.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|목록 상자를 삭제합니다.|
|[CMFC리본 편집::사용 스핀 버튼](#enablespinbuttons)|텍스트 상자의 스핀 단추 범위를 활성화하고 설정합니다.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|개체의 컴팩트한 크기를 `CFMCRibbonEdit` 검색합니다.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|텍스트 상자에서 텍스트를 검색합니다.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|개체의 중간 크기를 `CMFCRibbonEdit` 검색합니다.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|텍스트 상자에서 텍스트의 정렬을 검색합니다.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|컨트롤의 너비를 픽셀 단위로 검색합니다. `CMFCRibbonEdit`|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|`CMFCRibbonEdit` 컨트롤의 디스플레이 크기를 압축할 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|컨트롤에 `CMFCRIbbonEdit` 포커스가 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|`CMFCRibbonEdit` 컨트롤의 표시 크기가 클 수 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|텍스트 상자에 스핀 버튼이 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|컨트롤이 `CMFCRibbonEdit` 강조 표시되어 있는지 여부를 나타냅니다.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|컨트롤에 대한 표시 사각형의 치수가 변경될 때 `CMFCRibbonEdit` 프레임워크에서 호출됩니다.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|컨트롤을 그리는 프레임워크에서 호출합니다. `CMFCRibbonEdit`|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|컨트롤에 대 한 레이블 및 이미지를 `CMFCRibbonEdit` 그리는 프레임 워크에 의해 호출 됩니다.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|명령 목록 상자에 `CMFCRibbonEdit` 컨트롤을 그리는 프레임 워크에 의해 호출 됩니다.|
|[CMFCRibbonEdit::OnEnable](#onenable)|컨트롤을 사용하거나 사용하지 않도록 `CMFCRibbonEdit` 설정하려면 프레임워크에서 호출합니다.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|포인터가 컨트롤의 경계를 입력하거나 떠날 때 프레임워크에서 `CMFCRibbonEdit` 호출됩니다.|
|[CMFCRibbonEdit::OnKey](#onkey)|사용자가 키팁을 누르고 `CMFCRibbonEdit` 컨트롤에 포커스가 있을 때 프레임워크에서 호출됩니다.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|사용자가 `CMFCRibbonEdit` 컨트롤의 왼쪽 마우스 단추를 누를 때 컨트롤을 업데이트하려면 프레임워크에서 호출됩니다.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|사용자가 왼쪽 마우스 단추를 해제할 때 프레임워크에서 호출됩니다.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|레이아웃이 방향을 변경할 `CMFCRibbonEdit` 때 컨트롤을 업데이트하기 위해 프레임워크에서 호출합니다.|
|[CMFCRibbonEdit::OnShow](#onshow)|컨트롤을 표시하거나 숨기기 `CMFCRibbonEdit` 위해 프레임워크에서 호출합니다.|
|[CMFCRibbonEdit::Redraw](#redraw)|컨트롤의 표시를 `CMFCRibbonEdit` 업데이트합니다.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|개체에 대한 내게 `CMFCRibbonEdit` 필요한 옵션 데이터를 설정합니다.|
|[CMFC리본 편집::설정 편집텍스트](#setedittext)|텍스트 상자에 텍스트를 설정합니다.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|텍스트 상자의 텍스트 정렬을 설정합니다.|
|[CMFC리본 편집::세트 너비](#setwidth)|컨트롤의 텍스트 상자 너비를 `CMFCRibbonEdit` 설정합니다.|

## <a name="remarks"></a>설명

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonEdit` 객체를 생성하고, 편집 컨트롤 옆에 스핀 단추를 표시하고, 편집 컨트롤의 텍스트를 설정하는 방법을 보여 줍니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonEdit.h

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFC리본 편집 :: 수 있습니다

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 높이가 리본 행의 높이까지 수직으로 증가할 수 있는지 여부를 나타냅니다.

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Return Value

항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>CMFC리본 편집::CMFC리본 편집

[CMFC리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 개체를 생성합니다.

```cpp
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 컨트롤에 대한 `CMFCRibbonEdit` 명령 ID입니다.

*nWidth*<br/>
【인】 컨트롤에 대한 텍스트 상자의 너비(픽셀 `CMFCRibbonEdit` 단위)입니다.

*lpszLabel*<br/>
【인】 컨트롤의 레이블입니다. `CMFCRibbonEdit`

*nImage*<br/>
【인】 컨트롤에 사용할 작은 이미지의 `CMFCRibbonEdit` 인덱스입니다. 작은 이미지의 컬렉션은 부모 리본 범주에 의해 유지됩니다.

### <a name="remarks"></a>설명

컨트롤은 `CMFCRibbonEdit` 큰 이미지를 사용하지 않습니다.

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>CMFC리본 편집::복사에서

지정된 [CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체의 상태를 현재 [CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체에 복사합니다.

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>매개 변수

*Src*<br/>
【인】 소스 `CMFCRibbonEdit` 개체입니다.

### <a name="remarks"></a>설명

*src* 매개 변수는 `CMFCRibbonEdit`형식이어야 합니다.

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a>CMFC리본 편집::편집 만들기

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체에 대한 새 텍스트 상자를 만듭니다.

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 개체의 상위 창에 `CMFCRibbonEdit` 대한 포인터입니다.

*dwEditStyle*<br/>
【인】 텍스트 상자의 스타일을 지정합니다. 주석 섹션에 나열된 창 스타일과 Windows SDK에 설명된 [편집 컨트롤 스타일을](/windows/win32/Controls/edit-control-styles) 결합할 수 있습니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 새 텍스트 상자에 대한 포인터입니다. 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 텍스트 상자를 만듭니다.

다음 [창 스타일을](../../mfc/reference/styles-used-by-mfc.md#window-styles) 텍스트 상자에 적용할 수 있습니다.

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>CMFC리본 편집::D에스트로이트툴

[CMFC리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 개체를 삭제합니다.

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>설명

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>CMFC리본 편집::DropdownList

목록 상자를 삭제합니다.

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>설명

기본적으로 이 메서드는 아무 것도 수행하지 않습니다. 이 메서드를 재정의하여 목록 상자를 드롭다운합니다.

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>CMFC리본 편집::사용 스핀 버튼

텍스트 상자의 스핀 단추 범위를 활성화하고 설정합니다.

```cpp
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
【인】 스핀 버튼의 최소값입니다.

*nMax*<br/>
【인】 스핀 버튼의 최대값입니다.

### <a name="remarks"></a>설명

스핀 버튼은 위쪽 및 아래쪽 화살표를 표시하고 사용자가 고정 된 값 집합을 통해 이동할 수 있습니다.

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>CMFC리본 편집::GetCompactSize

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체의 컴팩트한 크기를 검색합니다.

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 개체에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

개체의 컴팩트한 `CMFCRibbonEdit` 크기입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a>CMFC리본 편집::GetEdit텍스트

텍스트 상자에서 텍스트를 검색합니다.

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>Return Value

텍스트 상자의 텍스트입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>CMFC리본 편집::Getintermediatesizesize

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체의 중간 크기를 검색합니다.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 개체에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

개체의 중간 `CMFCRibbonEdit` 크기입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a>CMFC리본 편집::GetText정렬

텍스트 상자에서 텍스트의 정렬을 검색합니다.

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>Return Value

텍스트 정렬이 값을 수반합니다. 가능한 값은 비고 섹션을 참조하십시오.

### <a name="remarks"></a>설명

반환된 값은 다음 편집 컨트롤 스타일 중 하나입니다.

- 왼쪽 맞춤의 **ES_LEFT**

- 중심 맞춤을 위한 **ES_CENTER**

- 올바른 정렬을 위한 **ES_RIGHT**

이러한 스타일에 대한 자세한 내용은 [컨트롤 스타일 편집을](/windows/win32/Controls/edit-control-styles)참조하십시오.

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a>CMFC리본 편집::GetWidth

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 너비를 픽셀 단위로 검색합니다.

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>매개 변수

*bInFloatyMode*<br/>
【인】 컨트롤이 `CMFCRibbonEdit` 부동 모드에 있는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

컨트롤의 너비(픽셀)입니다. `CMFCRibbonEdit`

### <a name="remarks"></a>설명

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>CMFC리본 편집::하스콤팩트 모드

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 디스플레이 크기를 컴팩트할 수 있는지 여부를 나타냅니다.

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 항상 TRUE를 반환합니다. 이 메서드를 재정의하여 디스플레이 크기를 작게 만들 수 있는지 여부를 나타냅니다.

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a>CMFC리본 편집::하스포커스

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있는지 여부를 나타냅니다.

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Return Value

컨트롤에 `CMFCRibbonEdit` 포커스가 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>CMFC리본 편집::하스라지모드

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 디스플레이 크기가 클 수 있는지 여부를 나타냅니다.

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Return Value

항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 이 메서드는 항상 FALSE를 반환합니다. 이 메서드를 재정의하여 표시 크기가 클 수 있는지 여부를 나타냅니다.

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFC리본 편집::하스스핀 버튼

텍스트 상자에 스핀 버튼이 있는지 여부를 나타냅니다.

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Return Value

텍스트 상자에 스핀 버튼이 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFC리본 편집::강조 표시

[CMFC리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤이 강조 표시되어 있는지 여부를 나타냅니다.

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Return Value

컨트롤이 `CMFCRibbonEdit` 강조 표시되면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>CMFC 리본 편집::온애프터체인지렉트

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 대한 표시 사각형의 치수가 변경될 때 프레임워크에서 호출됩니다.

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 컨트롤에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a>CMFC리본 편집::온드로우

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 그리는 프레임워크에서 호출합니다.

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 컨트롤에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>CMFC 리본 편집::온드로우 라벨및이미지

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 대한 레이블과 이미지를 그리는 프레임워크에서 호출합니다.

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 컨트롤에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>CMFC 리본 편집::온드로우온리스트

명령 목록 상자에 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 그리는 프레임 워크에 의해 호출 됩니다.

```cpp
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 컨트롤에 대한 장치 `CMFCRibbonEdit` 컨텍스트에 대한 포인터입니다.

*strText*<br/>
【인】 표시 텍스트 [ ](../../mfc/reference/cmfcribbonedit-class.md "cmfc리본 데리트 클래스")입니다.

*nTextOffset*<br/>
【인】 목록 상자의 왼쪽에서 표시 텍스트까지의 거리(픽셀 단위)입니다.

*rect*<br/>
【인】 컨트롤의 표시 사각형입니다. `CMFCRibbonEdit`

*bIsSelected*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

*b 강조 표시*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

### <a name="remarks"></a>설명

명령 목록 상자에는 사용자가 빠른 액세스 도구 모음을 사용자 지정할 수 있도록 리본 컨트롤이 표시됩니다.

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a>CMFC리본 편집::사용 가능

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 사용하거나 사용하지 않도록 설정하려면 프레임워크에서 호출합니다.

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 제어를 활성화하는; FALSE로 컨트롤을 사용하지 않도록 설정합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFC리본 편집::에 하이라이트

포인터가 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 경계를 입력하거나 떠날 때 프레임워크에서 호출됩니다.

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
【인】 TRUE 포인터가 `CMFCRibbonEdit` 컨트롤의 경계에 있는 경우입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a>CMFC리본 편집::온키

사용자가 키팁을 누르면 프레임워크에서 호출되고 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤에 포커스가 있습니다.

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>매개 변수

*bIsMenuKey*<br/>
【인】 키 팁에 팝업 메뉴가 표시되는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>Return Value

TRUE 이벤트가 처리된 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>CMFC 리본 편집::OnLButtonDown

사용자가 컨트롤의 왼쪽 마우스 단추를 누를 때 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 업데이트하는 프레임워크에서 호출합니다.

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>CMFC 리본 편집::OnLButtonUp

사용자가 왼쪽 마우스 단추를 해제할 때 프레임워크에서 호출됩니다.

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
【인】 이 매개 변수는 사용되지 않습니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>CMFC리본 편집::온틀변경

레이아웃이 방향을 변경할 때 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 업데이트하는 프레임워크에서 호출됩니다.

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>매개 변수

*bIsRTL*<br/>
【인】 레이아웃이 오른쪽에서 왼쪽인 경우 TRUE입니다. 레이아웃이 왼쪽에서 오른쪽인 경우 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a>CMFC리본 편집::에쇼

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤을 표시하거나 숨기려면 프레임워크에서 호출합니다.

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
【인】 TRUE는 컨트롤을 표시합니다. FALSE를 사용하여 컨트롤을 숨깁니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a>CMFC리본 편집::다시 그리기

[CMFC리본 편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 표시를 업데이트합니다.

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>설명

이 메서드는 `CMFCRibbonEdit` [cWnd::RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) RDW_INVALIDATE, RDW_ERASE 및 RDW_UPDATENOW 플래그 집합을 사용 하 여 개체에 대 한 표시 사각형을 다시 그립니다.

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>CMFC리본 편집::세액데이터

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 개체에 대한 내게 필요한 옵션 데이터를 설정합니다.

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
개체의 부모 창에 `CMFCRibbonEdit` 대한 포인터입니다.

*데이터*<br/>
개체에 대한 `CMFCRibbonEdit` 내게 필요한 옵션 데이터입니다.

### <a name="return-value"></a>Return Value

항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a>CMFC리본 편집::설정 편집텍스트

텍스트 상자에 텍스트를 설정합니다.

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>매개 변수

*strText*<br/>
【인】 텍스트 상자의 텍스트입니다.

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a>CMFC리본 편집::설정텍스트정렬

텍스트 상자의 텍스트 정렬을 설정합니다.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>매개 변수

*nAlign*<br/>
【인】 텍스트 정렬이 값을 수반합니다. 가능한 값은 비고 섹션을 참조하십시오.

### <a name="remarks"></a>설명

매개 변수 *nAlign은* 다음 편집 컨트롤 스타일 중 하나입니다.

- 왼쪽 맞춤의 ES_LEFT

- 중심 맞춤을 위한 ES_CENTER

- 올바른 정렬을 위한 ES_RIGHT

이러한 스타일에 대한 자세한 내용은 [컨트롤 스타일 편집을](/windows/win32/Controls/edit-control-styles)참조하십시오.

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a>CMFC리본 편집::세트 너비

[CMFCRibbon편집](../../mfc/reference/cmfcribbonedit-class.md) 컨트롤의 텍스트 상자 너비를 설정합니다.

```cpp
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
【인】 텍스트 상자의 너비(픽셀 단위)입니다.

*bInFloatyMode*<br/>
플로팅 모드의 너비를 설정하는 TRUE; FALSE를 사용하여 일반 모드의 너비를 설정합니다.

### <a name="remarks"></a>설명

컨트롤은 `CMFCRibbonEdit` 디스플레이 모드에 따라 두 가지 너비를 가지며 부동 모드와 일반 모드가 있습니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)
