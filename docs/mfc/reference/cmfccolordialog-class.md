---
title: CMFC컬러디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
ms.openlocfilehash: 1d4bd31d5095f572ee80f0357a2d7526482f1caa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752550"
---
# <a name="cmfccolordialog-class"></a>CMFC컬러디아로그 클래스

클래스는 `CMFCColorDialog` 색상 선택 대화 상자를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCColorDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC컬러디아로그::CMFC컬러디아로그](#cmfccolordialog)|`CMFCColorDialog` 개체를 생성합니다.|
|`CMFCColorDialog::~CMFCColorDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC컬러디아로그::겟컬러](#getcolor)|선택한 현재 색상을 반환합니다.|
|[CMFC컬러디아로그::겟팔레트](#getpalette)|색상의 팔레트를 반환합니다.|
|`CMFCColorDialog::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. 구문 및 자세한 내용은 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 참조하십시오. ( `CDialogEx::PreTranslateMessage`을 재정의합니다.)|
|[CMFC컬러디아로그::리빌드팔레트](#rebuildpalette)|시스템 팔레트에서 팔레트를 파생합니다.|
|[CMFC컬러 디아로그::세트전류색상](#setcurrentcolor)|선택한 현재 색상을 설정합니다.|
|[CMFC컬러디아로그::셋뉴컬러](#setnewcolor)|지정된 RGB 값과 가장 동일한 색상을 설정합니다.|
|[CMFC컬러디아로그::세트페이지원](#setpageone)|첫 번째 속성 페이지에 대한 RGB 값을 선택합니다.|
|[CMFC컬러디아로그::세트페이지투](#setpagetwo)|두 번째 속성 페이지에 대한 RGB 값을 선택합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|속성|Description|
|----------|-----------------|
|`m_bIsMyPalette`|TRUE 색상 선택 대화 상자가 고유한 색상 팔레트를 사용하는 경우 또는 대화 상자가 `CMFCColorDialog` 생성자에 지정된 팔레트를 사용하는 경우 FALSE입니다.|
|`m_bPickerMode`|TRUE 사용자가 선택 대화 상자에서 색상을 선택하는 동안; 그렇지 않으면 false입니다.|
|`m_btnColorSelect`|사용자가 선택한 색상 단추입니다.|
|`m_CurrentColor`|현재 선택한 색상입니다.|
|`m_hcurPicker`|색상을 선택하는 데 사용되는 커서입니다.|
|`m_NewColor`|영구적으로 선택되거나 원래 색상으로 되돌릴 수 있는 예상 선택된 색상입니다.|
|`m_pColourSheetOne`|색상 선택 속성 시트의 첫 번째 속성 페이지에 대한 포인터입니다.|
|`m_pColourSheetTwo`|색상 선택 속성 시트의 두 번째 속성 페이지에 대한 포인터입니다.|
|`m_pPalette`|현재 논리 팔레트입니다.|
|`m_pPropSheet`|색상 선택 대화 상자에 대한 속성 시트에 대한 포인터입니다.|
|`m_wndColors`|색상 선택기 컨트롤 개체입니다.|
|`m_wndStaticPlaceHolder`|색상 선택기 속성 시트의 자리 표시자인 정적 컨트롤입니다.|

## <a name="remarks"></a>설명

색상 선택 대화 상자는 두 페이지가 있는 속성 시트로 표시됩니다. 첫 번째 페이지에서 시스템 팔레트에서 표준 색상을 선택합니다. 두 번째 페이지에서 사용자 지정 색상을 선택합니다.

스택에서 개체를 생성한 `CMFCColorDialog` 다음 `DoModal`호출하여 초기 색상을 `CMFCColorDialog` 생성자에게 매개 변수로 전달할 수 있습니다. 그런 다음 색상 선택 대화 상자는 각 색상 팔레트를 처리하는 여러 [CMFCColorPickerCtrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md) 개체를 만듭니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

## <a name="example"></a>예제

다음 예제에서는 `CMFCColorDialog` 클래스에서 다양 한 메서드를 사용 하 여 색상 대화 상자를 구성 하는 방법을 보여 줍니다. 이 예제에서는 대화상자의 현재 및 새 색상을 설정하는 방법과 색상 대화 상자의 두 속성 페이지에서 선택한 색상의 빨간색, 녹색 및 파란색 구성 요소를 설정하는 방법을 보여 주며, 이 방법을 보여 주며, 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxcolordialog.h

## <a name="cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>CMFC컬러디아로그::CMFC컬러디아로그

`CMFCColorDialog` 개체를 생성합니다.

```
CMFCColorDialog(
    COLORREF clrInit=0,
    DWORD dwFlags=0,
    CWnd* pParentWnd=NULL,
    HPALETTE hPal=NULL);
```

### <a name="parameters"></a>매개 변수

*클라리니트*<br/>
【인】 기본 색상 선택입니다. 값을 지정하지 않으면 기본값은 RGB(0,0,0)(검은색)입니다.

*dwFlags*<br/>
[in] 예약되어 있습니다.

*pParentWnd*<br/>
【인】 대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

*hPal*<br/>
【인】 컬러 팔레트의 손잡이.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfccolordialoggetcolor"></a><a name="getcolor"></a>CMFC컬러디아로그::겟컬러

사용자가 색상 대화 상자에서 선택하는 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

색상 대화 상자에서 선택한 색상에 대한 RGB 정보가 포함된 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="remarks"></a>설명

메서드를 호출한 후 `DoModal` 이 함수를 호출합니다.

## <a name="cmfccolordialoggetpalette"></a><a name="getpalette"></a>CMFC컬러디아로그::겟팔레트

현재 색상 대화 상자에서 사용할 수 있는 색상 팔레트를 검색합니다.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Return Value

생성자에서 `CPalette` 지정된 개체에 대한 `CMFCColorDialog` 포인터입니다.

### <a name="remarks"></a>설명

색상 팔레트는 사용자가 선택할 수 있는 색상을 지정합니다.

## <a name="cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>CMFC컬러디아로그::리빌드팔레트

시스템 팔레트에서 팔레트를 파생합니다.

```cpp
void RebuildPalette();
```

## <a name="cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CMFC컬러 디아로그::세트전류색상

대화 상자의 현재 색상을 설정합니다.

```cpp
void SetCurrentColor(COLORREF rgb);
```

### <a name="parameters"></a>매개 변수

*Rgb*<br/>
【인】 RGB 색상 값

### <a name="remarks"></a>설명

## <a name="cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>CMFC컬러디아로그::셋뉴컬러

현재 색상을 가장 유사한 현재 팔레트의 색상으로 설정합니다.

```cpp
void SetNewColor(COLORREF rgb);
```

### <a name="parameters"></a>매개 변수

*Rgb*<br/>
【인】 RGB 색상을 지정하는 [COLORREF입니다.](/windows/win32/gdi/colorref)

### <a name="remarks"></a>설명

## <a name="cmfccolordialogsetpageone"></a><a name="setpageone"></a>CMFC컬러디아로그::세트페이지원

색상 대화 상자의 첫 번째 속성 페이지에서 선택한 색상의 빨간색, 녹색 및 파란색 구성 요소를 명시적으로 지정합니다.

```cpp
void SetPageOne(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
【인】 RGB 값의 빨간색 구성 요소를 지정합니다.

*G*<br/>
【인】 RGB 값의 녹색 구성 요소를 지정합니다.

*B*<br/>
【인】 RGB 값의 파란색 구성 요소를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>CMFC컬러디아로그::세트페이지투

색상 대화 상자의 두 번째 속성 페이지에서 선택한 색상의 빨간색, 녹색 및 파란색 구성 요소를 명시적으로 지정합니다.

```cpp
void SetPageTwo(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
【인】 RGB 값의 빨간색 구성 요소를 지정합니다.

*G*<br/>
【인】 RGB 값의 녹색 구성 요소를 지정합니다.

*B*<br/>
【인】 RGB 값의 파란색 구성 요소를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC컬러피커Ctrl 클래스](../../mfc/reference/cmfccolorpickerctrl-class.md)
