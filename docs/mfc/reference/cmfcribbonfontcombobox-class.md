---
title: CMFC리본글꼴콤보박스 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: dbf28787e0c0f7d89586fbf98632bd9172c12eed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754161"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFC리본글꼴콤보박스 클래스

글꼴 목록이 포함된 콤보 상자를 구현합니다. 콤보 상자를 리본 패널에 배치합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|소멸자|

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|`CMFCRibbonFontComboBox` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|지정된 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|
|`CMFCRibbonFontComboBox::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|지정된 문자 집합을 반환합니다.|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|콤보 상자에 표시할 글꼴 종류를 반환합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|콤보 상자에 표시되는 글꼴의 피치 및 패밀리를 반환합니다.|
|`CMFCRibbonFontComboBox::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|이전에 지정한 글꼴 종류, 문자 집합, 피치 및 패밀리의 글꼴로 리본 글꼴 콤보 상자를 채웁니다.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|콤보 상자에서 지정된 글꼴을 선택합니다.|

## <a name="remarks"></a>설명

객체를 `CMFCRibbonFontComboBox` 만든 후 [CMFCRibbonPanel::Add를](../../mfc/reference/cmfcribbonpanel-class.md#add)호출하여 리본 패널에 추가합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본ComboBox.h

## <a name="cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>CMFC리본글꼴콤보박스::빌드폰트

리본의 콤보 상자를 글꼴로 채웁니다.

```cpp
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>매개 변수

*nFontType*<br/>
【인】 추가할 글꼴의 글꼴 유형을 지정합니다.

*nCharSet*<br/>
【인】 추가할 글꼴의 문자 집합을 지정합니다.

*nPitchAndFamily*<br/>
【인】 추가할 글꼴의 피치와 패밀리를 지정합니다.

## <a name="cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>CMFC리본글꼴콤보박스::CMFC리본글꼴콤보박스

[CMFC리본글꼴 컴보박스](../../mfc/reference/cmfcribbonfontcombobox-class.md) 개체를 생성하고 초기화합니다.

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
【인】 사용자가 콤보 상자에서 항목을 선택할 때 실행되는 명령의 명령 ID입니다.

*nFontType*<br/>
【인】 콤보 상자에 표시할 글꼴 유형을 지정합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.

*nCharSet*<br/>
【인】 콤보 상자의 글꼴을 지정된 문자 집합에 속하는 글꼴로 필터링합니다.

*nPitchAndFamily*<br/>
【인】 콤보 상자에 표시되는 글꼴의 피치와 패밀리를 지정합니다.

*nWidth*<br/>
【인】 콤보 상자의 너비(픽셀)를 지정합니다.

### <a name="remarks"></a>설명

가능한 *nFontType* 매개 변수 값에 대한 자세한 내용은 Windows SDK 설명서의 [EnumFontFamProc을](/previous-versions/dd162621\(v=vs.85\)) 참조하십시오.

*nCharSet에*할당할 수 있는 유효한 문자 집합 및 *nPitchAndFamily에*할당할 수 있는 유효한 값에 대 한 자세한 내용은 Windows SDK 설명서에서 [LOGFONT를](/windows/win32/api/wingdi/ns-wingdi-logfontw) 참조하십시오.

## <a name="cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFC리본글꼴콤보박스::겟폰데스크

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>매개 변수

【인】 *아이 인덱스*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>CMFC리본글꼴콤보박스::리빌드폰트

리본의 콤보 상자를 이전에 지정된 글꼴 유형, 문자 집합, 피치 및 패밀리의 글꼴로 채웁니다.

```cpp
void RebuildFonts();
```

### <a name="remarks"></a>설명

이 클래스의 [생성자의](#cmfcribbonfontcombobox) 리본 글꼴 콤보 상자에 포함하거나 [CMFCRibbonFontFontComboBox::BuildFonts를](#buildfonts)호출하여 글꼴 유형, 문자 집합 및 피치 및 글꼴 패밀리를 지정할 수 있습니다.

## <a name="cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>CMFC리본글꼴콤보박스::세트폰트

콤보 상자에서 지정된 글꼴을 선택합니다.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>매개 변수

'lpszName*는 선택할 글꼴의 이름을 지정합니다.

*nCharSet*<br/>
선택한 글꼴에 대한 문자 집합을 지정합니다.

*bExact*<br/>
TRUE 는 글꼴을 선택할 때 문자 집합이 일치해야 함을 지정합니다. FALSE글꼴을 선택할 때 문자 집합을 무시할 수 있도록 지정합니다.

### <a name="return-value"></a>Return Value

지정된 글꼴을 발견하고 선택한 경우 0이 아닙니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>CMFC리본글꼴콤보박스::겟차셋

지정된 문자 집합을 반환합니다.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Return Value

문자 집합(Windows SDK 설명서의 LOGFONT 참조).

### <a name="remarks"></a>설명

## <a name="cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>CMFC리본글꼴콤보박스::겟폰트타입

콤보 상자에 표시할 글꼴 종류를 반환합니다. 유효한 옵션 DEVICE_FONTTYPE, RASTER_FONTTYPE, TRUETYPE_FONTTYPE 또는 이러한 옵션의 비트 조합입니다.

```
int GetFontType() const;
```

### <a name="return-value"></a>Return Value

글꼴 유형(Windows SDK 설명서의 EnumFontFamProc 참조).

### <a name="remarks"></a>설명

## <a name="cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>CMFC리본글꼴콤보박스::겟피치앤패밀리

콤보 상자에 표시되는 글꼴의 피치 및 패밀리를 반환합니다.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Return Value

피치와 패밀리(Windows SDK 설명서의 LOGFONT 참조).

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본콤보박스 클래스](../../mfc/reference/cmfcribboncombobox-class.md)
