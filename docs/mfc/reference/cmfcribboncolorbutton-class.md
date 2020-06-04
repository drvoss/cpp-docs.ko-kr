---
title: CMFCRibbonColorButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: 528b883d75889589c7021f462324dd9dcb71be25
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754850"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton 클래스

`CMFCRibbonColorButton` 클래스는 리본 표시줄에 추가할 수 있는 색 단추를 구현합니다. 리본 색 단추는 하나 이상의 색상표가 포함된 드롭다운 메뉴를 표시합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본색상 버튼:색상 추가 그룹](#addcolorsgroup)|일반 색 영역에 색 그룹을 추가합니다.|
|[CMFC리본색상 버튼::인에이블오토온버튼](#enableautomaticbutton)|**자동** 단추를 사용할지 여부를 지정합니다.|
|[CMFC리본색상 버튼::인에이블기타버튼](#enableotherbutton)|**기타** 단추를 사용하도록 설정합니다.|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFC리본컬러버튼:겟컬러](#getcolor)|현재 선택된 색을 반환합니다.|
|[CMFC리본컬러버튼:겟컬러박스사이즈](#getcolorboxsize)|색 막대에 표시되는 색 요소의 크기를 반환합니다.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFC리본컬러버튼::Get하이라이트컬러](#gethighlightedcolor)|팝업 색상표에서 현재 선택된 요소의 색을 반환합니다.|
|[CMFC리본컬러버튼:리무드올컬러그룹](#removeallcolorgroups)|일반 색 영역에서 모든 색 그룹을 제거합니다.|
|[CMFC리본컬러버튼::세트컬러](#setcolor)|일반 색 영역에서 색을 선택합니다.|
|[CMFC리본컬러버튼:세트컬러박스사이즈](#setcolorboxsize)|색 막대에 표시되는 모든 색 요소의 크기를 설정합니다.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFC리본색상버튼:세트문서색상](#setdocumentcolors)|문서 색 영역에 표시할 RGB 값의 목록을 지정합니다.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>설명

리본 색 단추는 사용자가 누를 때 색 막대를 표시합니다. 기본적으로 이 색 막대에는 일반 색 영역이라는 색 선택 색상표가 포함되어 있습니다. 필요에 따라 색 막대에 기본 색을 선택할 수 있는 **자동** 단추와 추가 색이 포함된 팝업 색상표를 표시하는 **기타** 단추가 표시될 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonColorButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `CMFCRibbonColorButton` 개체 생성, 큰 이미지 설정, **자동** 단추 사용, **기타** 단추 사용, 열 수 설정, 색 막대에 표시되는 모든 색 요소의 크기 설정, 일반 색 영역에 색 그룹 추가, 문서 색 영역에 표시할 RGB 값 목록 지정 등을 수행하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribboncolorbutton.h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a>CMFC리본색상 버튼:색상 추가 그룹

일반 색 영역에 색 그룹을 추가합니다.

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 그룹 이름입니다.

*lstColors*<br/>
【인】 색상 목록입니다.

*b연상열*<br/>
【인】 색상 항목이 그룹에 표시되는 방법을 제어합니다. TRUE인 경우 색상 항목은 세로 간격 없이 그려집니다. FALSE인 경우 색상 항목은 세로 간격으로 그려집니다.

### <a name="remarks"></a>설명

이 기능을 사용하여 색상 팝업에 여러 색상 그룹을 표시하도록 합니다. 색상이 그룹에 표시되는 방식을 제어할 수 있습니다.

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a>CMFC리본컬러버튼::CMFC리본컬러버튼

`CMFCRibbonColorButton` 개체를 생성합니다.

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 사용자가 단추를 클릭할 때 실행할 명령 ID를 지정합니다.

*lpszText*<br/>
【인】 단추에 표시되도록 텍스트를 지정합니다.

*n스몰 이미지 인덱스*<br/>
【인】 단추에 표시할 작은 이미지의 0기반 인덱스입니다.

*색*<br/>
【인】 단추의 색상(기본값은 검은색으로 설정).

*b심플버튼룩*<br/>
【인】 TRUE이면 단추가 간단한 사각형으로 그려집니다.

*nLarge이미지인덱스*<br/>
【인】 단추에 표시될 큰 이미지의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFC리본색상 버튼::인에이블오토온버튼

**자동** 단추를 사용할지 여부를 지정합니다.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 **자동** 단추의 레이블입니다.

*colorAutomatic*<br/>
【인】 **자동** 단추의 기본 색상을 지정하는 RGB 값입니다.

*bEnable*<br/>
【인】 **자동** 버튼이 활성화되어 있는 경우 TRUE; FALSE를 사용하지 않도록 설정한 경우

*lpszToolTip*<br/>
【인】 **자동** 단추의 도구 설명입니다.

*bOnTop*<br/>
【인】 색상 팔레트 앞에 **자동** 버튼이 맨 위에 있는지 여부를 지정합니다.

*b드드로우보더*<br/>
【인】 TRUE 응용 프로그램이 리본 색상 단추의 색상 막대 주위에 테두리를 그리는 경우. 색상 막대는 현재 선택한 색상을 표시합니다. 응용 프로그램이 테두리를 그리지 않는 경우 FALSE

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFC리본색상 버튼::인에이블기타버튼

**기타** 단추를 사용하도록 설정합니다.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
단추의 레이블입니다.

*lpszToolTip*<br/>
**기타** 단추의 도구 설명 텍스트입니다.

### <a name="remarks"></a>설명

**다른** 단추는 색상 그룹 아래에 표시되는 단추입니다. 사용자가 **기타** 단추를 클릭하면 색상 대화 상자가 표시됩니다.

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFC리본컬러버튼::겟오토마틱컬러

현재 자동 단추 색상을 검색합니다.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Return Value

현재 자동 단추 색상을 나타내는 RGB 색상 값입니다.

### <a name="remarks"></a>설명

자동 단추 색상은 메서드에 `colorAutomatic` 전달된 `CMFCRibbonColorButton::EnableAutomaticButton` 매개 변수에 의해 설정됩니다.

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a>CMFC리본컬러버튼:겟컬러

현재 선택된 색을 반환합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

단추를 클릭하여 선택한 색상입니다.

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a>CMFC리본컬러버튼:겟컬러박스사이즈

색 막대에 표시되는 색 요소의 크기를 반환합니다.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Return Value

드롭다운 색상 팔레트의 색상 단추 크기입니다.

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a>CMFC리본컬러버튼::GetColumns

리본 색상 단추의 갤러리 표시 행에 있는 항목 수를 가져옵니다.

```
int GetColumns() const;
```

### <a name="return-value"></a>Return Value

각 행의 아이콘 수를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFC리본컬러버튼::Get하이라이트컬러

팝업 색상 팔레트에서 현재 선택한 요소의 색상을 반환합니다.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Return Value

팝업 색상 팔레트에서 현재 선택한 요소의 색상입니다.

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a>CMFC리본컬러버튼:리무드올컬러그룹

일반 색 영역에서 모든 색 그룹을 제거합니다.

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a>CMFC리본컬러버튼::세트컬러

일반 색 영역에서 색을 선택합니다.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 설정할 색상입니다.

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a>CMFC리본컬러버튼:세트컬러박스사이즈

색 막대에 표시되는 모든 색 요소의 크기를 설정합니다.

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>매개 변수

*크기상자*<br/>
【인】 색상 팔레트의 새 색상 단추 크기입니다.

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a>CMFC리본컬러버튼:세트컬러네임

지정된 색상에 대한 새 이름을 설정합니다.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 색상의 RGB 값입니다.

*strName*<br/>
【인】 지정된 색상의 새 이름입니다.

### <a name="remarks"></a>설명

호출하기 `CMFCColorBar::SetColorName`때문에 이 메서드는 응용 프로그램의 모든 `CMFCColorBar` 개체에서 지정된 색상의 이름을 변경합니다.

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a>CMFC리본컬러버튼::세트열

사용자의 색상 선택 프로세스 중에 사용자에게 표시되는 색상 표에 표시되는 열 수를 설정합니다.

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>매개 변수

*nColumns*<br/>
【인】 각 행에 표시할 색상 아이콘의 수입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFC리본색상버튼:세트문서색상

문서 색 영역에 표시할 RGB 값의 목록을 지정합니다.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 문서 색상으로 표시할 텍스트입니다.

*lstColors*<br/>
【인】 RGB 값 목록에 대한 참조입니다.

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a>CMFC리본컬러버튼::세팔레트

색상 단추에 표시되는 색상 표에 표시할 표준 색상을 지정합니다.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>매개 변수

*pPalette*<br/>
【인】 색상 팔레트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a>CMFC리본색상 버튼::업데이트컬러

사용자가 색상 단추를 클릭할 때 표시되는 색상 표에서 색상을 선택할 때 프레임워크에서 호출됩니다.

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 사용자가 선택한 색상입니다.

### <a name="remarks"></a>설명

메서드는 `CMFCRibbonColorButton::UpdateColor` 현재 선택한 단추의 색상을 변경 하 고 BN_CLICKED 표준 알림과 함께 WM_COMMAND 메시지를 보내 부모에 게 알림합니다. [CMFC리본색상 단추::GetColor](#getcolor) 메서드를 사용하여 선택한 색상을 검색합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본갤러리 클래스](../../mfc/reference/cmfcribbongallery-class.md)
