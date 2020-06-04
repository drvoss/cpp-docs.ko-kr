---
title: CMFC프로퍼티그리드컬러프로퍼티 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 393a871a881aa4bddd786b1d4333e02d5e0dbef1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751835"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFC프로퍼티그리드컬러프로퍼티 클래스

`CMFCPropertyGridColorProperty` 클래스는 색 선택 항목 대화 상자를 여는 속성 목록 컨트롤 항목을 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|`CMFCPropertyGridColorProperty` 개체를 생성합니다.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|색상 선택 대화 상자의 *자동* 단추를 활성화합니다. (표준 자동 버튼은 **자동으로**레이블이 지정됩니다.)|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|색상 선택 대화 상자의 *다른* 단추를 활성화합니다. (표준 다른 버튼에는 **더 많은 색상이**레이블이 지정됩니다.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|속성 값의 텍스트 표현에 서식을 지정합니다. [(CMFC속성 그리드 속성 재정의::형식 속성.)](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty)|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|속성의 현재 색을 가져옵니다.|
|`CMFCPropertyGridColorProperty::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|`CMFCPropertyGridColorProperty::OnClickButton`|사용자가 속성에 포함된 단추를 클릭하면 프레임워크에서 호출됩니다. [(CMFCPropertyGrid속성 재정의::클릭 단추.)](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|속성 값을 표시하기 위해 프레임워크에서 호출됩니다. [(CMFCPropertyGrid속성 재정의::온드로우값.)](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue)|
|`CMFCPropertyGridColorProperty::OnEdit`|사용자가 속성 값을 수정하려고 할 때 프레임워크에서 호출됩니다. [(CMFCPropertyGrid속성 재정의::온편집.)](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit)|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|편집 가능한 속성 값이 변경되었을 때 프레임워크에서 호출됩니다. [(CMFCPropertyGrid속성 재정의::온업데이트값.)](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|속성에 대한 새로운 색을 설정합니다.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|현재 색 속성 표의 열 수를 지정합니다.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|편집 가능한 속성의 원래 값을 설정합니다.|

## <a name="remarks"></a>설명

`CMFCPropertyGridColorProperty` 클래스는 속성 목록 컨트롤에 추가할 수 있는 색 속성을 지원합니다. 자세한 내용은 [CMFCPropertyGridCtrl 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCPropertyGridColorProperty` 클래스의 개체를 생성하고 `CMFCPropertyGridColorProperty` 클래스의 다양한 메서드를 사용하여 이 개체를 구성하는 방법을 보여 줍니다. 코드에서는 자동 및 기타 단추를 사용하도록 설정하는 방법과 색 및 열 번호를 설정하는 방법을 설명합니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertygridctrl.h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>CMFCProperty그리드컬러속성::CMFC프로퍼티그리드컬러속성

`CMFCPropertyGridColorProperty` 개체를 생성합니다.

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>매개 변수

*strName*<br/>
【인】 속성의 이름입니다.

*색*<br/>
【인】 속성의 색상 값입니다.

*pPalette*<br/>
【인】 색상 팔레트에 대한 포인터입니다. 기본값은 NULL입니다.

*lpszDescr*<br/>
【인】 속성 설명입니다. 기본값은 NULL입니다.

*dwData*<br/>
【인】 속성과 연결된 다른 데이터에 대한 정수 또는 포인터와 같은 응용 프로그램 별 데이터입니다. 기본값은 0입니다.

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCProperty그리드컬러속성::인에이블오토퍼버튼

색상 선택 대화 상자의 *자동* 단추를 활성화합니다. (표준 자동 버튼은 **자동으로**레이블이 지정됩니다.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 자동 단추의 레이블 텍스트입니다.

*colorAutomatic*<br/>
【인】 자동(기본) 색상의 RGB 색상 값입니다.

*bEnable*<br/>
【인】 TRUE는 자동 버튼을 활성화; 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>CMFCProperty그리드컬러속성::인에이블다른버튼

색상 선택 대화 상자의 *다른* 단추를 활성화합니다. (표준 다른 버튼에는 **더 많은 색상이**레이블이 지정됩니다.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
【인】 다른 단추의 레이블 텍스트입니다.

*bAltColorDlg*<br/>
【인】 `CMFCColorDialog` 대화 상자를 표시하려면 TRUE; FALSE를 사용하여 표준 색상 선택 대화 상자를 표시합니다. 기본값은 TRUE입니다.

*bEnable*<br/>
【인】 다른 단추를 표시하는 TRUE; 그렇지 않으면 false입니다.  기본값은 TRUE입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>CMFCProperty그리드컬러속성::겟컬러

속성의 현재 색을 가져옵니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Return Value

RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>CMFCProperty그리드컬러속성::세트컬러

속성에 대한 새로운 색을 설정합니다.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
【인】 RGB 색상 값입니다.

### <a name="remarks"></a>설명

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCProperty그리드컬러속성::세트열번호

현재 색 속성 표의 열 수를 지정합니다.

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>매개 변수

*n열번호*<br/>
【인】 색상 속성 표의 기본 열 수입니다.

### <a name="remarks"></a>설명

이 메서드는 `m_nColumnsNumber` 보호된 데이터 멤버의 값을 설정합니다.

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>CMFCProperty그리드컬러속성::세트 오리지널밸류

편집 가능한 속성의 원래 값을 설정합니다.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>매개 변수

*varValue*<br/>
【인】 값입니다.

### <a name="remarks"></a>설명

[CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) 메서드를 사용하여 편집된 속성의 원래 값을 재설정합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC프로퍼티그리드트럴 클래스](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFC프로퍼티그리드프로퍼티 클래스](../../mfc/reference/cmfcpropertygridproperty-class.md)
