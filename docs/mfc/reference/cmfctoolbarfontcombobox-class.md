---
title: CMFCToolBarFontComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 7b31f4b725a6983171162d9805d08224ad787808
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360461"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox 클래스

사용자가 시스템 글꼴 목록에서 글꼴을 선택할 수 있는 콤보 상자 컨트롤이 포함된 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CMFC툴바폰트콤보박스::CMFC툴바폰트콤보박스](#cmfctoolbarfontcombobox)|`CMFCToolBarFontComboBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC툴바폰트콤보박스::겟폰데스크](#getfontdesc)|콤보 상자에서 `CMFCFontInfo` 지정된 인덱스에 대한 개체에 대한 포인터를 반환합니다.|
|[CMFC툴바폰트콤보박스::세트폰트](#setfont)|글꼴 콤보 상자에서 글꼴 이름 또는 글꼴의 접두사 및 문자 집합에 따라 글꼴을 선택합니다.|

### <a name="data-members"></a>데이터 멤버

[CMFC툴바폰트콤보박스::m_nFontHeight](#m_nfontheight)<br/>
글꼴 콤보 상자에 있는 문자의 높이입니다.

## <a name="remarks"></a>설명

도구 모음에 글꼴 콤보 상자 단추를 추가하려면 다음 단계를 따르십시오.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

1. 개체를 `CMFCToolBarFontComboBox` 생성합니다.

1. AFX_WM_RESETTOOLBAR 메시지를 처리하는 메시지 처리기에서 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)을 사용하여 원래 단추를 새 콤보 상자 단추로 바꿉습니다.

1. [CMFCToolBarFontFontComboBox::SetFont](#setfont) 메서드를 사용하여 콤보 상자에서 선택한 글꼴을 문서의 글꼴과 동기화합니다.

문서의 글꼴을 콤보 상자에서 선택한 글꼴과 동기화하려면 [CMFCToolBarFontComboBox::GetFontDesc 메서드를](#getfontdesc) 사용하여 선택한 글꼴의 속성을 검색하고 이러한 특성을 사용하여 [CFont 클래스](../../mfc/reference/cfont-class.md) 개체를 만듭니다.

글꼴 콤보 상자 단추는 Win32 기능 [EnumFontFamiliesEx를](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) 호출하여 시스템에서 사용할 수 있는 화면 및 프린터 글꼴을 결정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFC툴바콤보박스버튼](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFC툴바폰트콤보박스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>CMFC툴바폰트콤보박스::CMFC툴바폰트콤보박스

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 개체를 생성합니다.

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 콤보 상자의 명령 ID입니다.

*아이 이미지*<br/>
【인】 도구 모음 이미지의 0기반 인덱스입니다. 이미지는 CMFCToolBar 클래스클래스가 유지 관리하는 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md) [개체에](../../mfc/reference/cmfctoolbar-class.md) 있습니다.

*nFontType*<br/>
【인】 콤보 상자에 포함된 글꼴 유형입니다. 이 매개 변수는 다음 값의 조합(부울 OR)일 수 있습니다.

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
【인】 DEFAULT_CHARSET 설정하면 콤보 상자에 모든 문자 집합에 고유한 이름의 글꼴이 모두 포함됩니다. 이름이 같은 두 글꼴이 있는 경우 콤보 상자에 그 중 하나가 들어 있습니다. 유효한 문자 집합 값으로 설정하면 콤보 상자에 지정된 문자 집합에 글꼴만 포함됩니다. 가능한 문자 집합 목록은 [LOGFONT를](/windows/win32/api/wingdi/ns-wingdi-logfontw) 참조하십시오.

*dwStyle*<br/>
【인】 콤보 상자의 스타일입니다. [(콤보 박스 스타일](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)참조)

*아이 폭*<br/>
【인】 편집 컨트롤의 픽셀 너비입니다.

*nPitchAndFamily*<br/>
【인】 DEFAULT_PITCH 설정하면 콤보 상자에 피치에 관계없이 글꼴이 포함되어 있습니다. FIXED_PITCH 또는 VARIABLE_PITCH 설정하면 콤보 상자에 해당 피치 유형이 있는 글꼴만 포함됩니다. 글꼴 패밀리를 기반으로 필터링은 현재 지원되지 않습니다.

*pLst글폰트외부*<br/>
【아웃】 사용 가능한 글꼴을 저장하는 [CObList 클래스](../../mfc/reference/coblist-class.md) 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

일반적으로 `CMFCToolBarFontComboBox` 개체는 사용 가능한 글꼴 목록을 `CObList` 단일 공유 개체에 저장합니다. 생성자의 두 번째 오버로드를 사용하고 *pLstFontsExternal에*대한 유효한 `CMFCToolBarFontComboBox` 포인터를 제공하는 `CObList` 경우 해당 개체는 대신 *해당 pLstFontsExternal* 포인트를 사용 가능한 글꼴로 채웁니다.

### <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCToolBarFontComboBox` 구성하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

## <a name="cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFC툴바폰트콤보박스::겟폰데스크

콤보 상자에서 `CMFCFontInfo` 지정된 인덱스에 대한 개체에 대한 포인터를 반환합니다.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
【인】 콤보 상자 항목의 0기반 인덱스를 지정합니다.

### <a name="return-value"></a>Return Value

`CMFCFontInfo` 개체에 대한 포인터입니다. *iIndex가* 유효한 항목 인덱스를 지정하지 않으면 반환 값은 NULL입니다.

## <a name="cmfctoolbarfontcomboboxm_nfontheight"></a><a name="m_nfontheight"></a>CMFC툴바폰트콤보박스::m_nFontHeight

콤보 상자에 소유자 그리기 스타일이 있는 경우 글꼴 콤보 상자에 있는 문자의 높이(픽셀)를 지정합니다.

```
static int m_nFontHeight
```

### <a name="remarks"></a>설명

변수가 `m_nFontHeight` 0이면 콤보 상자의 기본 글꼴에 따라 높이가 자동으로 계산됩니다. 높이에는 기준선 위의 문자 의 상승과 기준선 아래의 문자의 하강이 모두 포함됩니다.

## <a name="cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>CMFC툴바폰트콤보박스::세트폰트

매개 변수에 지정된 글꼴 이름 및 문자 집합에 따라 글꼴 콤보 상자에서 글꼴을 선택합니다.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 글꼴 이름 또는 접두사를 지정합니다.

*nCharSet*<br/>
【인】 문자 집합을 지정합니다.

*bExact*<br/>
【인】 *lpszName* 글꼴 이름 또는 글꼴 접두사를 포함 하는지 여부를 지정 합니다.

### <a name="return-value"></a>Return Value

글꼴을 성공적으로 선택한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*bExactTRUE인* 경우 이 메서드는 *lpszName*. *bExact가* FALSE인 경우 이 메서드는 *lpszName로* 지정된 텍스트로 시작하여 *nCharSet으로*지정한 문자 집합을 사용하는 글꼴을 선택합니다. *nCharSet이* DEFAULT_CHARSET 설정되면 문자 집합이 무시되고 *lpszName만* 글꼴을 선택하는 데 사용됩니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFC툴바콤보박스버튼 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFC폰트정보 클래스](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFC툴바::대체 버튼](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
