---
title: CMFC리본컨텍스트 캡션 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: 7aacbe23684914c91129d9962ae847d442cc411b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375216"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFC리본컨텍스트 캡션 클래스

리본 범주 맨 위 또는 컨텍스트 범주에 나타나는 색 지정된 캡션을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|캡션 색을 반환합니다.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|

## <a name="remarks"></a>설명

이 클래스는 직접 인스턴스화할 수 없습니다. [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md) 클래스는 내부적으로 이 클래스를 사용하여 리본 범주에 색상을 추가합니다.

리본 범주의 색상을 설정하려면 [CMFC리본 범주::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)를 호출합니다. 컨텍스트 범주의 색상을 설정하려면 [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonBar.h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a>CMFC리본컨텍스트캡션::겟컬러

캡션의 배경색을 반환합니다.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Return Value

반환된 값은 다음 열거된 값 중 하나일 수 있습니다.

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>설명

캡션의 색상은 [CMFC리본범주::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) 또는 [CMFC리본바::추가컨텍스트범주를](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)호출하여 설정할 수 있습니다.

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a>CMFC리본컨텍스트캡션::겟라이트탭스

범주의 리본 탭의 오른쪽 가장자리 위치를 검색합니다.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Return Value

`CMFCRibbonCategory` 개체의 리본 탭을 둘러싸는 사각형의 오른쪽 X 값 또는 탭이 잘린 경우 -1 값을 반환합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본버튼 클래스](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFC리본카테고리 클래스](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFC리본바 클래스](../../mfc/reference/cmfcribbonbar-class.md)
