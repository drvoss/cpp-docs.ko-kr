---
title: CMFC폰트콤보박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: 60b4b7cdfdace2332de35dd93c43eacf592e99e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367495"
---
# <a name="cmfcfontcombobox-class"></a>CMFC폰트콤보박스 클래스

클래스는 `CMFCFontComboBox` 글꼴 목록을 포함하는 콤보 상자 컨트롤을 만듭니다.

## <a name="syntax"></a>구문

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC폰트콤보박스::CMFC폰트콤보박스](#cmfcfontcombobox)|`CMFCFontComboBox` 개체를 생성합니다.|
|`CMFCFontComboBox::~CMFCFontComboBox`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|현재 글꼴 콤보 상자 컨트롤의 정렬된 목록 상자에서 새 항목의 상대적 위치를 결정 하기 위해 프레임 워크에 의해 호출 됩니다. [(재정의 CComboBox::비교항목](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|현재 글꼴 콤보 상자 컨트롤에서 지정된 항목을 그리는 프레임 워크에 의해 호출 됩니다. [(재정의 CComboBox::Draw항목](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|현재 선택한 글꼴에 대한 정보를 검색합니다.|
|`CMFCFontComboBox::MeasureItem`|현재 글꼴 콤보 상자 컨트롤에서 목록 상자의 크기를 Windows에 알리기 위해 프레임 워크에 의해 호출 됩니다. [(재정의 CComboBox::측정 항목.)](../../mfc/reference/ccombobox-class.md#measureitem)|
|`CMFCFontComboBox::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMFC글꼴콤보박스::셀렉트글꼴](#selectfont)|글꼴 콤보 상자에서 지정된 조건과 일치하는 글꼴을 선택합니다.|
|[CMFCFontComboBox::Setup](#setup)|글꼴 콤보 상자의 항목 목록을 초기화합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|현재 글꼴 콤보 상자에 항목 레이블을 그리는 데 사용할 글꼴을 프레임워크에 나타냅니다.|

## <a name="remarks"></a>설명

대화 상자에서 개체를 `CMFCFontComboBox` 사용하려면 대화 `CMFCFontComboBox` 상자 클래스에 변수를 추가합니다. 그런 다음 대화 상자 클래스의 `OnInitDialog` 메서드에서 [CMFCFontComboBox::Setup](#setup)를 호출하여 콤보상자 컨트롤의 항목목록을 초기화합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxfontcombobox.h

## <a name="cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>CMFC폰트콤보박스::CMFC폰트콤보박스

`CMFCFontComboBox` 개체를 생성합니다.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>CMFC폰트콤보박스::겟셀폰트

현재 선택한 글꼴에 대한 정보를 검색합니다.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Return Value

글꼴을 설명하는 [CMFCFontInfo 클래스](../../mfc/reference/cmfcfontinfo-class.md) 개체에 대한 포인터입니다. 콤보 상자에서 글꼴을 선택하지 않으면 NULL이 될 수 있습니다.

### <a name="remarks"></a>설명

## <a name="cmfcfontcomboboxm_bdrawusingfont"></a><a name="m_bdrawusingfont"></a>CMFC폰트콤보박스:m_bDrawUsingFont

현재 글꼴 콤보 상자에 항목 레이블을 그리는 데 사용할 글꼴을 프레임워크에 나타냅니다.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>설명

이 멤버를 TRUE로 설정하여 프레임워크가 동일한 글꼴을 사용하여 각 항목 레이블을 그리도록 지시합니다. 이 멤버를 FALSE로 설정하여 프레임워크를 지시하여 이름이 레이블과 동일한 글꼴로 각 항목 레이블을 그립니다. 이 멤버의 기본값은 FALSE입니다.

## <a name="cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>CMFC글꼴콤보박스::셀렉트글꼴

글꼴 콤보 상자에서 지정된 조건과 일치하는 글꼴을 선택합니다.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>매개 변수

*pDesc*<br/>
【인】 글꼴 설명 개체를 가리킵니다.

*lpszName*<br/>
【인】 글꼴 이름을 지정합니다.

*nCharSet*<br/>
【인】 문자 집합을 지정합니다. 기본값은 DEFAULT_CHARSET. 자세한 내용은 `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조의 멤버를 참조하십시오.

### <a name="return-value"></a>Return Value

TRUE 글꼴 콤보 상자의 항목이 지정된 글꼴 설명 개체 또는 글꼴 이름 및 문자 집합과 일치하는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

지정된 글꼴 에 해당하는 글꼴 콤보 상자에서 항목을 선택하고 스크롤하려면 이 메서드를 사용합니다.

### <a name="example"></a>예제

다음 예제에서는 `SelectFont` `CMFCFontComboBox` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

## <a name="cmfcfontcomboboxsetup"></a><a name="setup"></a>CMFC폰트콤보박스::설치

글꼴 콤보 상자의 항목 목록을 초기화합니다.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>매개 변수

*nFontType*<br/>
【인】 글꼴 유형을 지정합니다. 기본값은 DEVICE_FONTTYPE, RASTER_FONTTYPE 및 TRUETYPE_FONTTYPE 비트조합(OR)입니다.

*nCharSet*<br/>
【인】 글꼴 문자 집합을 지정합니다. 기본값은 DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
【인】 글꼴 피치 및 패밀리를 지정합니다. 기본값은 DEFAULT_PITCH.

### <a name="return-value"></a>Return Value

글꼴 콤보 상자가 성공적으로 초기화된 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 지정된 매개 변수와 일치하는 현재 설치된 글꼴을 등록하고 글꼴 콤보 상자에 해당 글꼴 이름을 삽입하여 글꼴 콤보 상자를 초기화합니다.

### <a name="example"></a>예제

다음 예제에서는 `Setup` `CMFCFontComboBox` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFC폰트정보 클래스](../../mfc/reference/cmfcfontinfo-class.md)
