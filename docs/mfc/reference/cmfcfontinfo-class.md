---
title: CMFC폰트정보 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 6e87971e2afefc9cf1574abe951920c254dcd2ae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367476"
---
# <a name="cmfcfontinfo-class"></a>CMFC폰트정보 클래스

클래스는 `CMFCFontInfo` 글꼴의 이름과 기타 특성을 설명합니다.

## <a name="syntax"></a>구문

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCFontInfo`|`CMFCFontInfo` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|글꼴과 해당 문자 집합(스크립트)의 연결된 이름을 검색합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC폰트정보:m_nCharSet](#m_ncharset)|글꼴과 연결된 문자 집합(스크립트)을 지정하는 값입니다.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|글꼴의 피치 와 패밀리를 지정하는 값입니다.|
|[CMFCFontInfo::m_nType](#m_ntype)|글꼴 유형을 지정하는 값입니다.|
|[CMFCFontInfo::m_strName](#m_strname)|글꼴의 이름; 예를 들어, **Arial**.|
|[CMFC폰트정보:m_strScript](#m_strscript)|글꼴과 연결된 문자 집합(스크립트)의 이름입니다.|

## <a name="remarks"></a>설명

`CMFCFontInfo` [CMFCToolBarFontFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 클래스의 항목에 개체를 연결할 수 있습니다. 개체에 대한 포인터를 검색하려면 [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) 메서드를 `CMFCFontInfo` 호출합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스의 다양한 멤버를 `CMFCFontInfo` 사용하는 방법을 보여 줍니다. 이 예제에서는 `CMFCFontInfo` `CMFCRibbonFontComboBox`에서 개체를 얻는 방법과 해당 지역 변수에 액세스하는 방법을 보여 줍니다. 이 예제는 [MSOffice 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarfontcombobox.h

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>CMFC폰트정보::CMFC폰트정보

`CMFCFontInfo` 개체를 생성합니다.

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 글꼴의 이름입니다. 자세한 내용은 `lfFaceName` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조의 멤버를 참조하십시오.

*lpszScript*<br/>
【인】 글꼴의 스크립트(문자 집합)의 이름입니다.

*nCharSet*<br/>
【인】 글꼴의 문자 집합(스크립트)을 지정하는 값입니다. 자세한 내용은 `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조의 멤버를 참조하십시오.

*nPitchAndFamily*<br/>
【인】 글꼴의 피치 와 패밀리를 지정하는 값입니다. 자세한 내용은 `lfPitchAndFamily` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조의 멤버를 참조하십시오.

*nType*<br/>
【인】 글꼴 유형을 지정하는 값입니다. 이 매개 변수는 DEVICE_FONTTYPE, RASTER_FONTTYPE 및 TRUETYPE_FONTTYPE 비트 조합(OR)일 수 있습니다.

*Src*<br/>
【인】 멤버가 `CMFCFontInfo` 이 `CMFCFontInfo` 개체를 생성하는 데 사용되는 기존 개체입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

이 설명서에서는 *문자 집합* 및 *스크립트를* 상호 교환하여 사용합니다. 쓰기 시스템이라고도 하는 *스크립트는*하나 이상의 언어로 해당 문자를 작성하기 위한 문자 및 규칙의 모음입니다. 문자 컬렉션에는 해당 스크립트에 사용된 알파벳과 문장 부호가 포함됩니다. 예를 들어 라틴어 스크립트는 미국에서 음성으로 사용되는 영어에 사용되고 알파벳은 A부터 Z 까지의 문자를 포함합니다. [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조체의 `lfCharSet`멤버는 문자 집합을 지정합니다. 예를 들어 ANSI_CHARSET 값은 라틴어 스크립트의 알파벳을 포함하는 ANSI 문자 집합을 지정합니다.

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a>CMFC폰트 정보::GetFullName

글꼴과 해당 문자 집합(스크립트)의 연결된 이름을 검색합니다.

```
CString GetFullName() const;
```

### <a name="return-value"></a>Return Value

글꼴 이름과 스크립트가 포함된 문자열입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하여 글꼴의 전체 이름을 가져옵니다. 예를 들어 글꼴 이름이 **Arial이고** 글꼴 스크립트가 **키릴**문자인 경우 이 메서드는 "Arial(키릴 문자)"를 반환합니다.

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a>CMFC폰트정보:m_nCharSet

글꼴과 연결된 문자 집합(스크립트)을 지정하는 값입니다.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>설명

자세한 내용은 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자의 *nCharSet* 매개 변수를 참조하십시오.

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a>CMFC폰트 정보::m_nPitchAndFamily

글꼴의 피치(점 크기) 및 패밀리(예: 세리프, 산세리프 및 모노스페이스)를 지정하는 값입니다.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>설명

자세한 내용은 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자의 *nPitchAndFamily* 매개 변수를 참조하십시오.

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a>CMFC폰트정보::m_nType

글꼴 유형을 지정하는 값입니다.

```
const int m_nType;
```

### <a name="remarks"></a>설명

자세한 내용은 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자의 *nType* 매개 변수를 참조하십시오.

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a>CMFC폰트 정보::m_strName

글꼴의 이름: 예를 들어, **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>설명

자세한 내용은 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자의 *lpszName* 매개 변수를 참조하십시오.

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a>CMFC폰트정보:m_strScript

글꼴과 연결된 문자 집합(스크립트)의 이름입니다.

```
const CString m_strScript;
```

### <a name="remarks"></a>설명

자세한 내용은 [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) 생성자의 *lpszScript* 매개 변수를 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox 클래스](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox 클래스](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
