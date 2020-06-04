---
title: CMFCImagePaintArea 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
ms.openlocfilehash: cd74d2418bb874553fbbafa637f527a7b84b73bf
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754270"
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea 클래스

이미지 편집기 대화 상자에서 이미지를 수정하는 데 사용하는 그림 영역을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCImagePaintArea : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFC이미지페인트에어리어::CMFC이미지페인트에어리어](#cmfcimagepaintarea)|`CMFCImagePaintArea` 개체를 생성합니다.|
|`CMFCImagePaintArea::~CMFCImagePaintArea`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC이미지페인트영역::겟모드](#getmode)|현재 도면 모드를 검색합니다.|
|[CMFC이미지페인트영역::세트비트맵](#setbitmap)|그림 영역에 대한 비트맵 이미지를 설정합니다.|
|[CMFC이미지페인트영역::세트컬러](#setcolor)|현재 드로잉 색상을 설정합니다.|
|[CMFC이미지페인트영역::세트모드](#setmode)|현재 도면 모드를 설정합니다.|

### <a name="remarks"></a>설명

이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.

프레임워크는 이 클래스를 사용하여 이미지 편집기 대화 상자에 그림 영역을 표시합니다. 이미지 편집기 대화 상자에 대한 자세한 내용은 [CMFCImageEditorDialog 클래스를](../../mfc/reference/cmfcimageeditordialog-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCImagePaintArea` 클래스의 오브젝트를 생성하고, 현재 드로잉 색상을 설정하고, 현재 드로잉 모드를 설정하고, 그림 영역에 대한 비트맵 이미지를 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFC이미지페인트에어리어](../../mfc/reference/cmfcimagepaintarea-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximagepaintarea.h

## <a name="cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>CMFC이미지페인트에어리어::CMFC이미지페인트에어리어

`CMFCImagePaintArea` 개체를 생성합니다.

```
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pParentDlg*|【인】 이미지 편집기의 부모인 대화 상자에 대한 포인터입니다.|

## <a name="cmfcimagepaintareagetmode"></a><a name="getmode"></a>CMFC이미지페인트영역::겟모드

현재 도면 모드를 검색합니다.

```
IMAGE_EDIT_MODE GetMode() const;
```

### <a name="return-value"></a>Return Value

현재 도면 모드를 지정하는 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 값입니다.

## <a name="cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>CMFC이미지페인트영역::세트비트맵

그림 영역에 대한 비트맵 이미지를 설정합니다.

```cpp
void SetBitmap(CBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*pBitmap*|【인】 표시할 새 비트맵 이미지입니다.|

### <a name="remarks"></a>설명

*pBitmap이* NULL인 경우 이 메서드는 수정 가능한 페인트 영역의 크기를 0으로 설정합니다. 그렇지 않으면 수정 가능한 페인트 영역의 크기를 제공된 비트맵 이미지의 크기로 설정합니다.

## <a name="cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>CMFC이미지페인트영역::세트컬러

현재 드로잉 색상을 설정합니다.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*색*|【인】 새 그리기 색상입니다.|

### <a name="remarks"></a>설명

이미지 편집기 팔레트 표시줄 또는 색상 선택기에서 색상을 선택하면 프레임워크에서 이 메서드를 호출하여 현재 드로잉 색상을 업데이트합니다. 초기 드로잉 색상은 검은색입니다(COLORREF 값 은 0).

그리기 색상은 IMAGE_EDIT_MODE_COLOR 제외한 모든 드로잉 모드에 대한 이미지 편집기 대화 상자에서 사용됩니다. 드로잉 모드에 대한 자세한 내용은 [CMFCImagePaintArea::IMAGE_EDIT_MODE 열거를](cmfcimagepaintarea-image-edit-mode-enumeration.md)참조하십시오.

## <a name="cmfcimagepaintareasetmode"></a><a name="setmode"></a>CMFC이미지페인트영역::세트모드

현재 도면 모드를 설정합니다.

```cpp
void SetMode(IMAGE_EDIT_MODE mode);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*모드*|【인】 현재 도면 모드를 지정하는 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md) 값입니다.|

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC이미지에디터디아로그 클래스](../../mfc/reference/cmfcimageeditordialog-class.md)
