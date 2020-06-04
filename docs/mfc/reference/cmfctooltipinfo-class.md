---
title: CMFC툴팁정보 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 000a2fd33928e59685efa6f145406542a4935819
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377330"
---
# <a name="cmfctooltipinfo-class"></a>CMFC툴팁정보 클래스

도구 설명의 시각적 모양에 대한 정보를 저장합니다.

## <a name="syntax"></a>구문

```
class CMFCToolTipInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolTipInfo::operator=](#operator_eq)||

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC툴팁정보:m_bBalloonTooltip](#m_bballoontooltip)|도구 설명이 풍선 모양인지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|도구 설명 레이블이 굵은 글꼴로 표시되는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|도구 설명이 설명을 포함하는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|도구 설명이 아이콘을 포함하는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|도구 설명 레이블과 도구 설명 사이에 구분 기호가 표시되는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|도구 설명 모서리가 둥근지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|도구 설명의 모양을 시각적 관리자가 제어해야 하는지 여부를 나타내는 부울 [변수입니다(CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)참조).|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|도구 설명 테두리 색입니다.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|도구 설명 배경색입니다.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|도구 설명의 그라데이션 채우기 색입니다.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|도구 설명의 텍스트 색입니다.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|도구 설명의 그라데이션 채우기 각도입니다.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|도구 설명의 가능한 최대 설명 너비(픽셀)입니다.|

## <a name="remarks"></a>설명

[CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo`및 [CTooltipManager 클래스를](../../mfc/reference/ctooltipmanager-class.md) 함께 사용하여 응용 프로그램에서 사용자 지정된 도구 설명서를 구현합니다. 이러한 도구 설명 클래스를 사용하는 방법에 대한 예제는 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목을 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolTipInfo` 클래스에서 다양한 멤버 변수의 값을 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipctrl.h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a>CMFC툴팁정보:m_bBalloonTooltip

모든 도구 설명의 표시 스타일을 지정합니다.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>설명

TRUE는 도구 설명이 부품 번호 스타일을 사용한다는 것을 나타내고 FALSE는 도구 설명이 직사각형 스타일을 사용했음을 나타냅니다.

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a>CMFC툴팁정보:m_bBoldLabel

도구 설명 텍스트의 글꼴이 굵게 표시된지 여부를 지정합니다.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>설명

이 멤버를 TRUE로 설정하여 굵은 글꼴로 도구 설명 텍스트를 표시하거나 FALSE를 사용하여 도구 설명 레이블을 굵게 표시하지 않는 글꼴로 표시합니다.

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a>CMFC툴팁정보::m_bDrawDescription

각 도구 설명에 설명 텍스트가 표시되는지 여부를 지정합니다.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>설명

설명을 표시하려면 이 멤버를 TRUE로 설정하거나 FALSE를 사용하여 설명을 숨깁니다. [CMFCToolTipCtrl::SetDescription을](../../mfc/reference/cmfctooltipctrl-class.md#setdescription) 호출하여 도구 설명에 설명을 지정할 수 있습니다.

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a>CMFC툴팁정보:m_bDrawIcon

모든 도구 설명이 아이콘을 표시할지 여부를 지정합니다.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>설명

이 멤버를 TRUE로 설정하여 각 도구 설명에 아이콘을 표시하거나 FALSE를 사용하여 아이콘 없이 도구 설명팁을 표시합니다.

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a>CMFC툴팁정보::m_bDrawSeparator

각 도구 설명에 레이블과 설명 사이에 구분 기호가 있는지 여부를 지정합니다.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>설명

이 멤버를 TRUE로 설정하여 도구 설명 레이블과 설명 사이에 구분 기호를 표시하거나 FALSE를 설정하여 구분 기호가 없는 도구 설명을 표시합니다.

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a>CMFC툴팁정보:m_bRoundedCorners

모든 도구 설명에 모서리가 둥근지 여부를 지정합니다.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>설명

이 멤버를 TRUE로 설정하여 도구 설명에 둥근 모서리를 표시하거나 FALSE를 사용하여 도구 설명에 직사각형 모서리를 표시합니다.

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a>CMFC툴팁정보::m_clrBorder

모든 도구 설명에서 테두리의 색상을 지정합니다.

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a>CMFC툴팁정보::m_clrFill

도구 설명 배경의 색상을 지정합니다.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>설명

[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1이면 도구 설명 배경색은 `m_clrFill`. `m_clrFill` 그렇지 않으면 그라데이션 시작의 색상을 지정하고 `m_clrFillGradient` 그라데이션 끝의 색상을 지정합니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의 방향을 결정합니다.

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a>CMFC툴팁정보::m_clrFillGradient

도구 설명에 대한 그라데이션 배경의 끝 색상을 지정합니다.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>설명

-1이면 `m_clrFillGradient` 그라데이션이 없습니다. 그렇지 않으면 그라데이션 초기 색상은 [CMFCToolTipInfo:m_clrFill](#m_clrfill) 지정되고 그라데이션 `m_clrFillGradient`마무리 색상은 에 의해 지정됩니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의 방향을 결정합니다.

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a>CMFC툴팁정보:m_clrText

모든 도구 설명의 텍스트 색상을 지정합니다.

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a>CMFC툴팁정보::m_nGradientAngle

도구 설명의 배경에 그라데이션이 그려지는 각도를 지정합니다.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>설명

`m_nGradientAngle`은 공구 팁의 배경에 있는 그라데이션이 수평에서 오프셋되도록 각도를 각도(각도)로 지정합니다. 0이면 `m_nGradientAngle` 그라데이션이 왼쪽에서 오른쪽으로 그려집니다. 1에서 360 사이인 경우 `m_nGradientAngle` 그라데이션은 해당 각도로 시계 방향으로 회전합니다. 기본값인 -1이면 `m_nGradientAngle` 그라데이션이 위에서 아래로 그려집니다. 이는 90으로 `m_nGradientAngle` 설정하는 것과 동일합니다.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` 그라데이션의 시작 부분에 있는 색상을 지정 하 고 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` 그라데이션의 끝의 색상을 지정 합니다. -1이면 `m_clrFillGradient` 그라데이션이 없습니다.

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>CMFC툴팁정보:m_nMaxDescrWidth

각 도구 설명에 표시된 설명의 최대 너비를 지정합니다. 설명 너비가 지정된 값을 초과하면 텍스트가 래핑됩니다.

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>CMFC툴팁정보:m_bVislManagerTheme

응용 프로그램의 시각적 관리자가 모든 도구 설명의 모양을 제어하는지 여부를 지정합니다.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>설명

TRUE인 경우 `m_bVislManagerTheme` 모든 도구 설명은 화면에 나타나기 전에 응용 프로그램의 시각적 관리자로부터 새 [CMFCToolTipInfo를](../../mfc/reference/cmfctooltipinfo-class.md) 요청하고 해당 개체의 값을 사용하여 모양을 결정합니다. [CMFCToolTipInfo의](../../mfc/reference/cmfctooltipinfo-class.md) 다른 멤버는 무시됩니다.

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a>CMFCToolTipInfo::연산자=

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>매개 변수

【인】 *src*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[C툴팁매니저 클래스](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFC툴팁Ctrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)
