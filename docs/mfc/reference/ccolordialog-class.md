---
title: CColorDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: 99b4ff27a7686972bcbc85478998b52ed713ab5b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754266"
---
# <a name="ccolordialog-class"></a>CColorDialog 클래스

색상 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.

## <a name="syntax"></a>구문

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|`CColorDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|색상 대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[CColorDialog::GetColor](#getcolor)|선택한 `COLORREF` 색상의 값을 포함하는 구조를 반환합니다.|
|[CColorDialog::GetSaveCustom색상](#getsavedcustomcolors)|사용자가 만든 사용자 지정 색상을 검색합니다.|
|[CColor Dialog::설정현재색상](#setcurrentcolor)|현재 색상 선택을 지정된 색상으로 강제로 지정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|재정의하여 대화 상자에 입력된 색상의 유효성을 검사합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|대화 상자의 설정을 사용자 지정하는 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

`CColorDialog` 개체는 표시 시스템에 대해 정의된 색상 목록이 있는 대화 상자입니다. 사용자는 목록에서 특정 색상을 선택하거나 만들 수 있으며, 대화 상자가 종료될 때 응용 프로그램에 다시 보고됩니다.

개체를 `CColorDialog` 생성하려면 제공된 생성기를 사용하거나 새 클래스를 파생하고 사용자 지정 생성기를 사용합니다.

대화 상자가 생성되면 [m_cc](#m_cc) 구조의 값을 설정하거나 수정하여 대화 상자 컨트롤의 값을 초기화할 수 있습니다. *m_cc* 구조는 [selectCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)유형입니다.

대화 상자의 컨트롤을 초기화한 후 `DoModal` 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 색상을 선택할 수 있도록 합니다. `DoModal`에서는 사용자가 선택한 대화 상자의 확인(IDOK) 또는 취소(IDCANCEL) 단추를 반환합니다.

IDOK를 반환하는 `DoModal` 경우's `CColorDialog`멤버 함수 중 하나를 사용하여 사용자가 입력한 정보를 검색할 수 있습니다.

Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 사용하여 대화 상자 초기화 중에 오류가 발생했는지 확인하고 오류에 대해 자세히 알아볼 수 있습니다.

`CColorDialog`COMMDLG에 의존합니다. Windows 버전 3.1 이상과 함께 제공되는 DLL 파일입니다.

대화 상자를 사용자 지정하려면 에서 `CColorDialog`클래스를 파생합니다. 처리되지 않은 모든 메시지는 기본 클래스에 전달되어야 합니다.

후크 기능을 사용자 지정할 필요는 없습니다.

> [!NOTE]
> 일부 설치에서는 `CColorDialog` 프레임워크를 사용하여 다른 `CDialog` 개체를 회색으로 만드는 경우 개체가 회색 배경으로 표시되지 않습니다.

사용에 `CColorDialog`대한 자세한 내용은 [일반적인 대화 상자 클래스를](../../mfc/common-dialog-classes.md) 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a>CColorDialog::CColorDialog

`CColorDialog` 개체를 생성합니다.

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*클라리니트*<br/>
기본 색상 선택입니다. 값을 지정하지 않으면 기본값은 RGB(0,0,0)(검은색)입니다.

*dwFlags*<br/>
대화 상자의 기능과 모양을 사용자 지정하는 플래그 집합입니다. 자세한 내용은 Windows SDK의 [SELECTCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1) 구조를 참조하십시오.

*pParentWnd*<br/>
대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a>CColorDialog::DoModal

이 함수를 호출하여 Windows 공통 색상 대화 상자를 표시하고 사용자가 색상을 선택할 수 있도록 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL. IDCANCEL가 반환되면 Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 호출하여 오류가 발생했는지 확인합니다.

IDOK 및 IDCANCEL은 사용자가 확인 또는 취소 단추를 선택했는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

[m_cc](#m_cc) 구조의 멤버를 설정하여 다양한 색상 대화 상자 옵션을 초기화하려면 호출하기 `DoModal` 전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

호출 `DoModal`한 후 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력 한 설정 또는 정보를 검색 할 수 있습니다.

### <a name="example"></a>예제

  [CColorDialog::CColorDialog의](#ccolordialog)예제를 참조하십시오.

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a>CColorDialog::GetColor

호출 `DoModal` 후 이 함수를 호출하여 사용자가 선택한 색상에 대한 정보를 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

색상 대화 상자에서 선택한 색상에 대한 RGB 정보가 포함된 [COLORREF](/windows/win32/gdi/colorref) 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>CColorDialog::GetSaveCustom색상

`CColorDialog`개체는 사용자가 색상을 선택하는 것 외에도 최대 16개의 사용자 지정 색상을 정의할 수 있도록 허용합니다.

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>Return Value

사용자가 만든 사용자 지정 색상을 저장하는 16RGB 색상 값의 배열에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 `GetSavedCustomColors` 함수는 이러한 색상에 대한 액세스를 제공합니다. 이러한 색상은 [DoModal이](#domodal) IDOK를 반환한 후 검색할 수 있습니다.

반환된 배열의 16개 RGB 값 각각은 RGB(255,255,255)(흰색)로 초기화됩니다. 사용자가 선택한 사용자 지정 색상은 응용 프로그램 내의 대화 상자 호출 사이에만 저장됩니다. 응용 프로그램의 호출 사이에 이러한 색상을 저장하려면 초기화()와 같은 다른 방식으로 색상을 저장해야 합니다. INI) 파일.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a>CColorDialog::m_cc

대화 상자의 특성과 값을 멤버가 저장하는 [SELECTCOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)형식의 구조입니다.

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>설명

개체를 생성한 `CColorDialog` 후 *m_cc* 사용하여 [DoModal](#domodal) 멤버 함수를 호출하기 전에 대화 상자의 다양한 측면을 설정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a>CColorDialog::OnColorOK

재정의하여 대화 상자에 입력된 색상의 유효성을 검사합니다.

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>Return Value

대화 상자를 해제하지 않아야 하는 경우 0이 아님을 확인합니다. 그렇지 않으면 0을 입력한 색상을 수락합니다.

### <a name="remarks"></a>설명

색상 대화 상자에서 사용자가 선택한 색상에 대한 사용자 지정 유효성 검사를 제공하려는 경우에만 이 함수를 재정의합니다.

사용자는 다음 두 가지 방법 중 하나로 색상을 선택할 수 있습니다.

- 색상 팔레트에서 색상을 클릭합니다. 그런 다음 선택한 색상의 RGB 값이 적절한 RGB 편집 상자에 반영됩니다.

- RGB 편집 상자에 값 입력

재정의를 `OnColorOK` 사용하면 응용 프로그램별 이유로 사용자가 공통 색상 대화 상자에 입력하는 색상을 거부할 수 있습니다.

일반적으로 프레임워크는 기본 색상 유효성 검사를 제공하고 잘못된 색상을 입력하면 메시지 상자를 표시하므로 이 함수를 사용할 필요가 없습니다.

`OnColorOK` [내부에서 SetCurrentColor를](#setcurrentcolor) 호출하여 색상 선택을 강제할 수 있습니다. 일단 `OnColorOK` (즉, 사용자가 색상 변경을 수락 **확인을** 클릭) 일단, 새 색상의 RGB 값을 얻기 위해 [GetColor를](#getcolor) 호출할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CColor Dialog::설정현재색상

호출 `DoModal` 후 이 함수를 호출하여 현재 색상 선택을 *clr에*지정된 색상 값으로 강제로 선택합니다.

```cpp
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*Clr*<br/>
RGB 색상 값입니다.

### <a name="remarks"></a>설명

이 함수는 메시지 처리기 `OnColorOK`또는 에서 호출됩니다. 대화 상자는 *clr* 매개 변수의 값에 따라 사용자의 선택을 자동으로 업데이트합니다.

### <a name="example"></a>예제

  [CColorDialog::OnColorOK에](#oncolorok)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 드로클리](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
