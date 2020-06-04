---
title: CMFC드래그프레임임플 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 527fd089962e05c44a7e47b1ae52345116da4470
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752448"
---
# <a name="cmfcdragframeimpl-class"></a>CMFC드래그프레임임플 클래스

클래스는 `CMFCDragFrameImpl` 사용자가 표준 도크 모드에서 창을 끌 때 나타나는 드래그 사각형을 그립니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>설명

이 클래스의 개체는 각 [CPane 클래스](../../mfc/reference/cpane-class.md) 개체에 포함 됩니다. 따라서 메서드를 `CanFloat` 사용하는 각 창에는 사용자가 드래그할 때 드래그 사각형이 표시됩니다.

[AFX_GLOBAL_DATA:m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) 및 [AFX_GLOBAL_DATA:m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock)를 사용하여 드래그 사각형의 두께를 제어할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdragframeimpl.h

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a>CMFC드래그프레임임플::엔드드로우드래그프레임

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *b클리어내부트렉트*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdragframeimplinit"></a><a name="init"></a>CMFC드래그프레임임플::이니트

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pDraggedWnd*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a>CMFC드래그프레임임플::무브드래그프레임

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>매개 변수

【인】 *b포스무브*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a>CMFC드래그프레임임플::P레이스탭사전도킹

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>매개 변수

【인】 *pTabbedBar*<br/>

【인】 *b퍼스트타임*<br/>

【인】 *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a>CMFC드래그프레임임플::제거탭사전도킹

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *pOldTargetBar*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a>CMFC드래그프레임임플::리셋상태

```cpp
void ResetState();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane 클래스](../../mfc/reference/cpane-class.md)
