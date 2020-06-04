---
title: CMFCRibbonButtonsGroup 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: d690e8bf306234e7b742a4c6a0917e5430d92d10
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754108"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>CMFCRibbonButtonsGroup 클래스

이 `CMFCRibbonButtonsGroup` 클래스를 사용하면 리본 단추 집합을 그룹으로 구성할 수 있습니다. 그룹의 모든 단추는 가로로 서로 직접 인접해 있으며 테두리로 둘러싸여 있습니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|`CMFCRibbonButtonsGroup` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC 리본 단추 그룹::추가 단추](#addbutton)|그룹에 단추를 추가합니다.|
|[CMFC리본 단추 그룹::추가 단추](#addbuttons)|그룹에 단추 목록을 추가합니다.|
|[CMFC 리본 단추 그룹::GetButton](#getbutton)|지정된 인덱스에 있는 단추에 대한 포인터를 반환합니다.|
|[CMFC리본 버튼 그룹::겟카운트](#getcount)|그룹의 단추 수를 반환합니다.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|리본 그룹의 일반 이미지 의 이미지 크기를 [반환합니다(CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)재정의.)|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|리본 요소의 일반 크기를 [반환합니다(CMFC리본베이스요소 재정의::GetRegularSize.)](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|개체에 `CMFCRibbonButtonsGroup` 도구 모음 이미지가 포함되어 있는지 여부를 보고합니다.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|단추의 정상 여부, 강조 표시 또는 사용 안 함 여부에 따라 지정된 단추에 대 한 적절 한 이미지를 그립니다.|
|[CMFCRibbonButtonsGroup::RemoveAll](#removeall)|개체에서 모든 단추를 `CMFCRibbonButtonsGroup` 제거합니다.|
|[CMFC리본 단추 그룹::세트 이미지](#setimages)|그룹에 이미지를 할당합니다.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|개체의 `CMFCRibbonCategory` 상위 및 개체 내의 모든 단추를 설정합니다(CMFCRibbonBaseElement:SetParentCategory 재정의.) [CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory) `CMFCRibbonButtonsGroup`|

## <a name="remarks"></a>설명

이 그룹은 [CMFCBaseRibbonElement에서](../../mfc/reference/cmfcribbonbaseelement-class.md) 파생되며 단일 엔터티로 조작할 수 있습니다. 모든 패널 또는 팝업 메뉴에 그룹을 배치할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonButtonsGroup` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 개체를 `CMFCRibbonButtonsGroup` 구성하고, 리본 단추 그룹에 이미지를 할당하고, 리본 단추 그룹에 단추를 추가하는 방법을 보여 주며, 단추를 추가합니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonbuttonsgroup.h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a>CMFC 리본 단추 그룹::추가 단추

그룹에 단추를 추가합니다.

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>매개 변수

*p 버튼*<br/>
【인】 추가할 단추에 대한 포인터입니다.

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a>CMFC리본 단추 그룹::추가 단추

그룹에 단추 목록을 추가합니다.

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>매개 변수

*lstButtons*<br/>
【인】 추가하려는 단추에 대한 포인터 목록입니다.

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a>CMFC리본 단추 그룹::CMFC리본 단추 그룹

`CMFCRibbonButtonsGroup` 개체를 생성합니다.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>매개 변수

*p 버튼*<br/>
【인】 새로 만든 `CMFCRibbonButtonsGroup` 개체에 추가할 단추를 지정합니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a>CMFC 리본 단추 그룹::GetButton

지정된 인덱스에 있는 단추에 대한 포인터를 반환합니다.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>매개 변수

*Ⅰ*<br/>
【인】 반환할 단추의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 인덱스에 있는 단추에 대한 포인터입니다. 지정된 인덱스가 범위를 벗어난 경우 NULL입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a>CMFC리본 버튼 그룹::겟카운트

그룹의 단추 수를 반환합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>Return Value

그룹의 단추 수입니다.

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a>CMFC리본 단추 그룹::GetImageSize

보호된 `CMFCToolBarImages` 멤버의 `m_Images`원본 이미지 크기를 검색합니다.

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Return Value

도구 모음 이미지의 원본 이미지 크기(있는 경우)를 `CSize` 반환하거나 그렇지 않은 경우 0을 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a>CMFC 리본 버튼 그룹 ::GetRegularsize

리본 그룹 요소의 가능한 최대 크기를 검색합니다.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 리본 그룹의 장치 컨텍스트에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a>CMFC리본버튼그룹::하스이미지

개체에 `CMFCRibbonButtonsGroup` 도구 모음 이미지가 포함되어 있는지 여부를 보고합니다.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Return Value

보호된 `CMFCToolBarImages` 멤버에 `m_Images` 이미지가 포함된 경우 TRUE를 반환하거나 그렇지 않은 경우 FALSE를 반환합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a>CMFC리본 단추 그룹::온드로우 이미지

단추의 정상 여부, 강조 표시 또는 사용 안 함 여부에 따라 지정된 단추에 대 한 적절 한 이미지를 그립니다.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 개체의 장치 컨텍스트에 `CMFCRibbonButtonsGroup` 대한 포인터입니다.

*rectImage*<br/>
【인】 이미지를 그릴 사각형입니다.

*p 버튼*<br/>
【인】 이미지를 그릴 버튼입니다.

*n이미지 인덱스*<br/>
【인】 단추에 그릴 이미지의 인덱스입니다(일반, 강조 표시 또는 비활성화된 단추의 세 가지 이미지 배열 중 하나).

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a>CMFC리본 버튼 그룹::모두 제거

개체에서 모든 단추를 `CMFCRibbonButtonsGroup` 제거합니다.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>설명

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a>CMFC리본 단추 그룹::세트 이미지

리본 단추 그룹에 이미지를 할당합니다.

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>매개 변수

*p 이미지*<br/>
【인】 일반 이미지.

*pHotimages*<br/>
【인】 뜨거운 이미지.

*p장애인 이미지*<br/>
【인】 비활성화된 이미지입니다.

### <a name="remarks"></a>설명

그룹에 `SetImages` 단추를 추가하기 전에 전화를 합니다. 이미지 수는 그룹에 추가할 단추 수와 같거나 같아야 합니다.

> [!NOTE]
> 핫 이미지는 사용자가 단추 위로 마우스를 가져간 경우 표시되는 이미지입니다. 비활성화된 이미지는 단추를 사용하지 않도록 설정하면 표시되는 이미지입니다.

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a>CMFC리본 단추 그룹::설정 부모 범주

`CMFCRibbonButtonsGroup` 개체의 상위 `CMFCRibbonCategory` 및 개체 내의 모든 단추를 설정합니다.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>매개 변수

*p카테고리*<br/>
【인】 설정할 상위 범주에 대한 포인터(리본 컨트롤의 탭그룹을 범주라고 함).

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
