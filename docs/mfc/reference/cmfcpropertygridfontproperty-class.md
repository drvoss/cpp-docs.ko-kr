---
title: CMFC프로퍼티그리드글폰트속성 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: a1c9905d8d7f32a049496c4e164c9eaac13455d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361843"
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFC프로퍼티그리드글폰트속성 클래스

클래스는 `CMFCPropertyGridFileProperty` 글꼴 선택 대화 상자를 여는 속성 목록 컨트롤 항목을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCProperty그리드폰트속성::CMFC프로퍼티그리드글폰트속성](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` 개체를 생성합니다.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다. [(CMFC속성 그리드 속성 재정의::형식 속성.)](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)|
|[CMFCProperty그리드폰트속성::겟컬러](#getcolor)|사용자가 글꼴 대화 상자에서 선택하는 글꼴 색상을 검색합니다.|
|[CMFCProperty그리드폰트속성::겟로그폰트](#getlogfont)|사용자가 글꼴 대화 상자에서 선택한 글꼴을 검색합니다.|
|`CMFCPropertyGridFontProperty::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|`CMFCPropertyGridFontProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다. [(CMFCPropertyGrid속성 재정의::클릭 단추.)](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>CMFCProperty그리드폰트속성::CMFC프로퍼티그리드글폰트속성

`CMFCPropertyGridFontProperty` 개체를 생성합니다.

```
CMFCPropertyGridFontProperty(
    const CString& strName,
    LOGFONT& lf,
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0,
    COLORREF color = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
【인】 속성의 이름입니다.

*Lf*<br/>
【인】 글꼴의 속성을 지정하는 논리 글꼴 구조입니다.

*dw폰트디아로그플래그*<br/>
【인】 속성 값 드롭다운 단추를 클릭할 때 표시되는 글꼴 대화 상자에 적용되는 스타일입니다. 기본값은 CF_EFFECTS 및 CF_SCREENFONTS 비트조합(OR)입니다. 자세한 내용은 [SELECTFONT 구조의](/windows/win32/api/commdlg/ns-commdlg-choosefontw) *Flags* 매개 변수를 참조하십시오.

*lpszDescr*<br/>
【인】 글꼴 속성에 대한 설명입니다. 기본값은 NULL입니다.

*dwData*<br/>
【인】 속성과 연결된 다른 데이터에 대한 정수 또는 포인터와 같은 응용 프로그램 별 데이터입니다. 기본값은 0입니다.

*색*<br/>
【인】 글꼴의 색상입니다. 기본값은 기본 색입니다.

### <a name="remarks"></a>설명

개체는 `CMFCPropertyGridFontProperty` 속성 그리드 글꼴 컨트롤의 글꼴 속성을 나타냅니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCPropertyGridFontProperty` 클래스의 개체를 구성하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

## <a name="cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>CMFCProperty그리드폰트속성::겟컬러

사용자가 글꼴 대화 상자에서 선택하는 글꼴 색상을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

선택한 글꼴 색상을 나타내는 RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>CMFCProperty그리드폰트속성::겟로그폰트

사용자가 글꼴 대화 상자에서 선택한 글꼴을 검색합니다.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Return Value

선택한 글꼴을 설명하는 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC프로퍼티그리드트럴 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFC프로퍼티그리드프로퍼티 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)
