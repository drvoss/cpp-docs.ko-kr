---
title: CFontDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: 6a8e24b68f377235c1f1e21fbcd5618aebbe299a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755020"
---
# <a name="cfontdialog-class"></a>CFontDialog 클래스

글꼴 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.

## <a name="syntax"></a>구문

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|`CFontDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|대화 상자를 표시하고 사용자가 선택할 수 있습니다.|
|[CFontDialog::GetCharFormat](#getcharformat)|선택한 글꼴의 문자 서식을 검색합니다.|
|[CFontDialog::GetColor](#getcolor)|선택한 글꼴의 색상을 반환합니다.|
|[CFontDialog::GetCurrent글꼴](#getcurrentfont)|현재 선택된 글꼴의 특성을 `LOGFONT` 구조체에 할당합니다.|
|[CFontDialog::GetFaceName](#getfacename)|선택한 글꼴의 얼굴 이름을 반환합니다.|
|[CFontDialog::GetSize](#getsize)|선택한 글꼴의 포인트 크기를 반환합니다.|
|[CFontDialog::GetStyleName](#getstylename)|선택한 글꼴의 스타일 이름을 반환합니다.|
|[CFontDialog::Getweight](#getweight)|선택한 글꼴의 가중치를 반환합니다.|
|[CFontDialog::IsBold](#isbold)|글꼴이 굵게 표시된지 여부를 결정합니다.|
|[CFontDialog::이이타릭](#isitalic)|글꼴이 기울임꼴인지 여부를 결정합니다.|
|[CFontDialog::IsStrikeOut](#isstrikeout)|글꼴이 스트라이크아웃으로 표시되는지 여부를 결정합니다.|
|[CFontDialog::IsUnderline](#isunderline)|글꼴에 밑줄이 그어져 있는지 여부를 결정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|개체를 사용자 지정하는 `CFontDialog` 데 사용되는 구조입니다.|

## <a name="remarks"></a>설명

`CFontDialog` 개체는 현재 시스템에 설치된 글꼴 목록이 있는 대화 상자입니다. 사용자는 목록에서 특정 글꼴을 선택할 수 있으며 이 선택 영역은 응용 프로그램에 다시 보고됩니다.

개체를 `CFontDialog` 생성하려면 제공된 생성기를 사용하거나 새 하위 클래스를 파생하고 사용자 지정 생성기를 사용합니다.

개체가 `CFontDialog` 생성되면 `m_cf` 구조를 사용하여 대화 상자에서 컨트롤의 값이나 상태를 초기화할 수 있습니다. [m_cf](#m_cf) 구조는 [SELECTFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw)형식입니다. 이 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

대화 상자 개체의 컨트롤을 초기화한 `DoModal` 후 멤버 함수를 호출하여 대화 상자를 표시하고 사용자가 글꼴을 선택할 수 있도록 합니다. `DoModal`사용자가 확인(IDOK) 또는 취소(IDCANCEL) 단추를 선택했는지 여부를 반환합니다.

IDOK를 반환하는 `DoModal` 경우's `CFontDialog`멤버 함수 중 하나를 사용하여 사용자가 입력한 정보를 검색할 수 있습니다.

Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 사용하여 대화 상자 초기화 중에 오류가 발생했는지 확인하고 오류에 대해 자세히 알아볼 수 있습니다. 이 기능에 대한 자세한 내용은 Windows SDK를 참조하십시오.

`CFontDialog`COMMDLG에 의존합니다. Windows 버전 3.1 이상과 함께 제공되는 DLL 파일입니다.

대화 상자를 사용자 지정하려면 에서 `CFontDialog`클래스를 파생 합니다 . 처리되지 않은 모든 메시지는 기본 클래스에 전달되어야 합니다.

후크 기능을 사용자 지정할 필요는 없습니다.

사용에 `CFontDialog`대한 자세한 내용은 [일반적인 대화 상자 클래스를](../../mfc/common-dialog-classes.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cfontdialogcfontdialog"></a><a name="cfontdialog"></a>CFontDialog::CFontDialog

`CFontDialog` 개체를 생성합니다.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*plf초기*<br/>
글꼴의 일부 특성을 설정할 수 있는 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 데이터 구조에 대한 포인터입니다.

*Charformat*<br/>
풍부한 편집 컨트롤에서 글꼴의 일부 특성을 설정할 수 있는 [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) 데이터 구조에 대한 포인터입니다.

*dwFlags*<br/>
하나 이상의 글꼴 선택 플래그를 지정합니다. 비트 OR 연산자를 사용하여 하나 이상의 미리 설정된 값을 결합할 수 있습니다. `m_cf.Flag` 구조체 멤버를 수정하는 경우 기본 동작을 그대로 유지하려면 변경에서 비트 OR 연산자를 사용해야 합니다. 이러한 각 플래그에 대한 자세한 내용은 Windows SDK의 [SELECTFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw) 구조에 대한 설명을 참조하십시오.

*pdc프린터*<br/>
프린터 디바이스 컨텍스트에 대한 포인터입니다. 제공하는 경우 이 매개 변수는 글꼴을 선택할 프린터에 대한 프린터 디바이스 컨텍스트를 가리킵니다.

*pParentWnd*<br/>
글꼴 대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

생성자는 `CHOOSEFONT` 구조의 멤버를 자동으로 채웁니다. 기본값과는 다른 글꼴 대화 상자를 사용하려는 경우에만 이러한 멤버를 변경해야 합니다.

> [!NOTE]
> rich edit 컨트롤이 지원되지 않는 경우에만 이 함수의 첫 번째 버전이 제공됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

## <a name="cfontdialogdomodal"></a><a name="domodal"></a>CFontDialog::DoModal

이 함수를 호출하여 Windows 공통 글꼴 대화 상자를 표시하고 사용자가 글꼴을 선택할 수 있도록 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL. IDCANCEL가 반환되면 Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 함수를 호출하여 오류가 발생했는지 확인합니다.

IDOK 및 IDCANCEL은 사용자가 확인 또는 취소 단추를 선택했는지 여부를 나타내는 상수입니다.

### <a name="remarks"></a>설명

[m_cf](#m_cf) 구조의 멤버를 설정하여 다양한 글꼴 대화 상자 컨트롤을 초기화하려면 `DoModal`호출하기 전에 이 작업을 수행해야 하지만 대화 상자 개체가 생성된 후에는 이 작업을 수행해야 합니다.

IDOK를 반환하는 경우 `DoModal` 다른 멤버 함수를 호출하여 사용자가 대화 상자에 입력한 설정 또는 정보를 검색할 수 있습니다.

### <a name="example"></a>예제

  [CFontDialog::CFontDialog](#cfontdialog) 및 [CFontDialog::GetColor에](#getcolor)대한 예제를 참조하십시오.

## <a name="cfontdialoggetcharformat"></a><a name="getcharformat"></a>CFontDialog::GetCharFormat

선택한 글꼴의 문자 서식을 검색합니다.

```cpp
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>매개 변수

*Cf*<br/>
선택한 글꼴의 문자 서식지정에 대한 정보가 포함된 [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata) 구조입니다.

## <a name="cfontdialoggetcolor"></a><a name="getcolor"></a>CFontDialog::GetColor

선택한 글꼴 색상을 검색하려면 이 함수를 호출합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴의 색입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

## <a name="cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a>CFontDialog::GetCurrent글꼴

이 함수를 호출하여 현재 선택된 글꼴의 특성을 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조체의 멤버에 할당합니다.

```cpp
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>매개 변수

*lplf*<br/>
구조에 대한 `LOGFONT` 포인터입니다.

### <a name="remarks"></a>설명

현재 `CFontDialog` 글꼴의 개별 특성에 액세스하기 위해 다른 멤버 함수가 제공됩니다.

[DoModal을](#domodal)호출하는 동안 이 함수가 호출되면 현재 선택 항목(사용자가 대화 상자에서 보거나 변경한 내용)을 반환합니다. 이 함수가 호출 후 `DoModal` 호출된 `DoModal` 경우(IDOK를 반환하는 경우에만) 사용자가 실제로 선택한 내용을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

## <a name="cfontdialoggetfacename"></a><a name="getfacename"></a>CFontDialog::GetFaceName

선택한 글꼴의 얼굴 이름을 검색하려면 이 함수를 호출합니다.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Return Value

대화 상자에서 선택한 글꼴의 얼굴 이름입니다. `CFontDialog`

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

## <a name="cfontdialoggetsize"></a><a name="getsize"></a>CFontDialog::GetSize

선택한 글꼴의 크기를 검색하려면 이 함수를 호출합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>Return Value

글꼴의 크기(점의 10분의 1)입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

## <a name="cfontdialoggetstylename"></a><a name="getstylename"></a>CFontDialog::GetStyleName

선택한 글꼴의 스타일 이름을 검색하려면 이 함수를 호출합니다.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Return Value

글꼴의 스타일 이름입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

## <a name="cfontdialoggetweight"></a><a name="getweight"></a>CFontDialog::Getweight

선택한 글꼴의 가중치를 검색하려면 이 함수를 호출합니다.

```
int GetWeight() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴의 가중치입니다.

### <a name="remarks"></a>설명

글꼴의 무게에 대한 자세한 내용은 [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

## <a name="cfontdialogisbold"></a><a name="isbold"></a>CFontDialog::IsBold

이 함수를 호출하여 선택한 글꼴이 굵게 표시된지 확인합니다.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴에 굵게 특성이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

## <a name="cfontdialogisitalic"></a><a name="isitalic"></a>CFontDialog::이이타릭

이 함수를 호출하여 선택한 글꼴이 기울임꼴인지 확인합니다.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴에 기울임꼴 특성이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

## <a name="cfontdialogisstrikeout"></a><a name="isstrikeout"></a>CFontDialog::IsStrikeOut

이 함수를 호출하여 선택한 글꼴이 스트라이크아웃으로 표시되는지 확인합니다.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴에 스트라이크아웃 특성이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

## <a name="cfontdialogisunderline"></a><a name="isunderline"></a>CFontDialog::IsUnderline

이 함수를 호출하여 선택한 글꼴에 밑줄이 있는지 확인합니다.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴에 밑줄 특성이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

## <a name="cfontdialogm_cf"></a><a name="m_cf"></a>CFontDialog::m_cf

멤버가 대화 상자 개체의 특성을 저장하는 구조체입니다.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>설명

개체를 생성한 `CFontDialog` 후 멤버 `m_cf` 함수를 호출하기 전에 대화 상자의 다양한 측면을 수정하는 `DoModal` 데 사용할 수 있습니다. 이 구조에 대한 자세한 내용은 Windows SDK의 [SELECTFONT를](/windows/win32/api/commdlg/ns-commdlg-choosefontw) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
