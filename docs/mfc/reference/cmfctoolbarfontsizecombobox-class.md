---
title: CMFCToolBarFontSizeComboBox 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 6c90bb1ce464a90295e7edb933d87594444c3648
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745314"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox 클래스

사용자가 글꼴 크기를 선택할 수 있도록 하는 콤보 상자 컨트롤이 포함된 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|속성|Description|
|----------|-----------------|
|[CMFC툴바글폰트크기콤보박스::CMFC툴바글폰트사이즈콤보박스](#cmfctoolbarfontsizecombobox)|`CMFCToolBarFontSizeComboBox` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC툴바글폰트사이즈콤보박스::겟트위프사이즈](#gettwipsize)|선택한 글꼴 크기를 트윕으로 반환합니다.|
|[CMFCToolBar글폰트크기콤보박스::리빌드폰트사이즈](#rebuildfontsizes)|지정된 글꼴에 대해 지원되는 모든 글꼴 크기로 콤보 상자 목록을 채웁니다.|
|[CMFC툴바글폰트크기콤보박스::셋트위프사이즈](#settwipsize)|트윕에서 글꼴 크기를 설정합니다.|

## <a name="remarks"></a>설명

`CMFCToolBarFontSizeComboBox` [CMFCToolBarFontFontComboBox 클래스 개체와](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 함께 개체를 사용하여 사용자가 글꼴 및 글꼴 크기를 선택할 수 있도록 할 수 있습니다.

글꼴 콤보 상자 단추를 추가하는 것처럼 도구 모음에 글꼴 크기 콤보 상자 단추를 추가할 수 있습니다. 자세한 내용은 [CMFCToolBarFontFontComboBox 클래스를](../../mfc/reference/cmfctoolbarfontcombobox-class.md)참조하십시오.

사용자가 `CMFCToolBarFontComboBox` 개체에서 새 글꼴을 선택하면 [CMFCToolBarFontFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) 메서드를 사용하여 해당 글꼴에 대해 지원되는 크기로 글꼴 크기 콤보 상자를 채울 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 클래스에서 개체를 구성 `CMFCToolBarFontSizeComboBox` 하는 다양 `CMFCToolBarFontSizeComboBox` 한 메서드를 사용 하는 방법을 보여 줍니다. 이 예제에서는 텍스트 상자에서 트윕에서 글꼴 크기를 검색하고, 지정된 글꼴의 모든 유효한 크기로 글꼴 크기 콤보 상자를 채우고, 트윕에서 글꼴 크기를 지정하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFC툴바콤보박스버튼](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFC툴바폰트사이즈콤보박스](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a>CMFC툴바글폰트크기콤보박스::CMFC툴바글폰트사이즈콤보박스

`CMFCToolBarFontSizeComboBox` 개체를 생성합니다.

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a>CMFC툴바글폰트사이즈콤보박스::겟트위프사이즈

글꼴 크기 콤보 상자의 텍스트 상자에서 트윕에서 글꼴 크기를 검색합니다.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Return Value

반환 값이 양수이면 트윕의 글꼴 크기입니다. 콤보 상자의 텍스트 상자가 비어 있으면 -1입니다. 오류가 발생하면 -2입니다.

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a>CMFCToolBar글폰트크기콤보박스::리빌드폰트사이즈

지정된 글꼴의 모든 유효한 크기로 글꼴 크기 콤보 상자를 채웁니다.

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>매개 변수

*strFontName*<br/>
【인】 글꼴 이름을 지정합니다.

### <a name="remarks"></a>설명

글꼴 콤보 상자의 선택 항목과 [CMFCToolBarFontFontComboBox 클래스와](../../mfc/reference/cmfctoolbarfontcombobox-class.md)같은 글꼴 크기 콤보 상자 간에 동기화하려는 경우 이 함수를 호출합니다.

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a>CMFC툴바글폰트크기콤보박스::셋트위프사이즈

지정된 크기(트윕)를 포인트의 가장 가까운 크기로 반올림한 다음 콤보 상자에서 선택한 크기를 해당 값으로 설정합니다.

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
【인】 설정할 글꼴 크기(트윕)를 지정합니다.

### <a name="remarks"></a>설명

[나중에 CMFCToolBarFontFontSizeComboBox::GetTwipSize](#gettwipsize) 메서드를 호출하여 이전 유효한 글꼴 크기를 검색할 수 있습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFC툴바콤보박스버튼 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFC폰트정보 클래스](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFC툴바::대체 버튼](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
