---
title: CMFC툴팁Ctrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
ms.openlocfilehash: 6c8bb41b82d1dca9235e1184c2152a61c07c8071
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377349"
---
# <a name="cmfctooltipctrl-class"></a>CMFC툴팁Ctrl 클래스

[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)를 기반으로 하는 확장된 도구 설명 구현입니다. `CMFCToolTipCtrl` 클래스 기반의 도구 설명은 아이콘, 레이블 및 설명을 표시할 수 있습니다. 그라데이션 채우기, 사용자 지정 텍스트와 테두리 색, 굵은 텍스트, 둥근 모서리 또는 풍선 스타일을 사용하여 시각적인 모양을 사용자 지정할 수 있습니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```cpp
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|도구 설명에 아이콘 크기를 반환합니다.|
|[CMFCToolTipCtrl::GetParams](#getparams)|도구 설명의 표시 설정을 반환합니다.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|도구 설명의 테두리를 그립니다.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|도구 설명에 아이콘을 표시합니다.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|도구 설명의 레이블을 그리거나 레이블의 크기를 계산합니다.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|도구 설명에서 레이블과 설명 사이에 구분 기호를 그립니다.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|도구 설명 배경을 채웁니다.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|도구 설명에 표시할 설명을 설정합니다.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|`CMFCToolTipInfo` 개체를 사용하여 도구 설명의 시각적 모양을 지정합니다.|

## <a name="remarks"></a>설명

에서 `CMFCToolTipCtrl` `CMFCToolTipInfo`및 [CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md) 개체를 함께 사용하여 응용 프로그램에서 사용자 지정된 도구 설명서를 구현합니다.

예를 들어 풍선 스타일의 도구 설명을 사용하려면 다음 단계를 수행합니다.

1. [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md) 메서드를 사용하여 응용 프로그램에서 도구 설명 관리자를 초기화합니다.

2. `CMFCToolTipInfo` 구조체를 만들어 원하는 시각적 스타일을 지정합니다.

    ```cpp
    CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
    {
        params.m_clrFill = RGB (255, 255, 255);
        params.m_clrFillGradient = RGB (228, 228, 240);
        params.m_clrText = RGB (61, 83, 80);
        params.m_clrBorder = RGB (144, 149, 168);

    }
    ```

3. [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) 메서드를 사용하여 `CMFCToolTipInfo` 개체에 정의된 스타일을 사용하여 응용 프로그램의 모든 도구 설명에 대한 시각적 스타일을 설정합니다.

    ```cpp
    theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
        RUNTIME_CLASS (CMFCToolTipCtrl), &params);
    ```

`CMFCToolTipCtrl`에서 새 클래스를 파생시켜 도구 설명 동작과 렌더링을 제어할 수도 있습니다. 새 도구 설명 컨트롤 클래스를 지정하려면 `CTooltipManager::SetTooltipParams` 메서드를 사용합니다.

```cpp
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```

기본 도구 설명 컨트롤 클래스를 복원하고 도구 설명 모양을 기본 상태로 다시 설정하려면 `SetTooltipParams`의 런타임 클래스 및 도구 설명 정보 매개 변수에 NULL을 지정합니다.

```cpp
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolTipCtrl` 개체를 생성하고, 도구 설명에 표시되는 설명을 설정하고, 도구 설명 컨트롤의 너비를 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipctrl.h

## <a name="cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a>CMFC툴팁Ctrl:::CMFC툴팁Ctrl

```cpp
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>매개 변수

【인】 *pParams*<br/>

### <a name="remarks"></a>설명

## <a name="cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a>CMFCTool팁Ctrl::GetIconSize

도구 설명에 아이콘 크기를 반환합니다.

```cpp
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Return Value

아이콘의 크기(픽셀)입니다.

## <a name="cmfctooltipctrlgetparams"></a><a name="getparams"></a>CMFC툴팁Ctrl::겟파라름

도구 설명의 표시 설정을 반환합니다.

```cpp
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Return Value

[CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md) 개체에 저장되는 현재 도구 설명 표시 설정입니다.

## <a name="cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a>CMFC툴팁Ctrl::온드로우보더

도구 설명의 테두리를 그립니다.

```cpp
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 도구 설명의 경계 사각형입니다.

*클라인*<br/>
【인】 테두리 색상입니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 도구 설명 테두리의 모양을 사용자 지정합니다.

## <a name="cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a>CMFCTool팁Ctrl::에 드로인 설명

```cpp
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
[in] *rect*<br/>
【인】 *bCalc만*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a>CMFCTool팁Ctrl::온드로우아이콘

도구 설명에 아이콘을 표시합니다.

```cpp
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rectImage*<br/>
【인】 아이콘의 좌표입니다.

### <a name="return-value"></a>Return Value

아이콘이 그려진 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 아이콘을 표시합니다. 또한 [CMFCToolTipCtrl::GetIconSize를](#geticonsize) 재정의하여 도구 설명이 텍스트 및 설명의 레이아웃을 올바르게 계산할 수 있도록 해야 합니다.

## <a name="cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a>CMFCTool팁Ctrl::온드로우 라벨

도구 설명의 레이블을 그리거나 레이블의 크기를 계산합니다.

```cpp
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 레이블 영역의 경계 사각형입니다.

*bCalcOnly*<br/>
【인】 TRUE이면 레이블이 그려지지 않습니다.

### <a name="return-value"></a>Return Value

레이블의 크기(픽셀)입니다.

### <a name="remarks"></a>설명

도구 설명 레이블의 모양을 사용자 지정하려는 경우 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a>CMFCTool팁Ctrl::에드로드세파레이터

도구 설명에서 레이블과 설명 사이에 구분 기호를 그립니다.

```cpp
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*x1*<br/>
【인】 구분 기호의 왼쪽 끝의 수평 좌표입니다.

*x2*<br/>
【인】 구분 기호의 오른쪽 끝의 수평 좌표입니다.

*Y*<br/>
【인】 구분 기호의 수직 좌표입니다.

### <a name="remarks"></a>설명

기본 구현은 점(x1, y)에서 점(x2, y)까지 선을 그립니다.

파생 클래스에서 이 메서드를 재정의하여 구분 기호의 모양을 사용자 지정합니다.

## <a name="cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCTool팁Ctrl::에필백

도구 설명 배경을 채웁니다.

```cpp
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 채울 영역의 경계 사각형을 지정합니다.

*clrText*<br/>
【인】 도구 팁 전경 색상입니다.

*클라인*<br/>
【인】 테두리의 색상과 레이블과 설명 사이의 구분 기호입니다.

### <a name="remarks"></a>설명

기본 구현은 [CMFCToolTipCtrl::SetParams에](#setparams)대한 가장 최근 호출에 의해 지정된 색상이나 패턴으로 *정류로* 지정된 사각형을 채웁니다.

도구 설명의 모양을 사용자 지정하려는 경우 파생 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfctooltipctrlsetdescription"></a><a name="setdescription"></a>CMFCTool팁Ctrl::세트 설명

도구 설명에 표시할 설명을 설정합니다.

```cpp
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>매개 변수

*스트라이시션*<br/>
【인】 설명 텍스트입니다.

### <a name="remarks"></a>설명

설명 텍스트는 구분 기호 아래의 도구 설명에 표시됩니다.

## <a name="cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a>CMFCTool팁Ctrl::고정폭 설정

```cpp
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>매개 변수

【인】 *n폭 일반*<br/>
【인】 *n너비큰이미지*<br/>

### <a name="remarks"></a>설명

## <a name="cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a>CMFCTool팁Ctrl::세트핫리본 버튼

```cpp
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>매개 변수

【인】 *p리본 버튼*<br/>

### <a name="remarks"></a>설명

## <a name="cmfctooltipctrlsetlocation"></a><a name="setlocation"></a>CMFCTool팁Ctrl::설정 위치

```cpp
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>매개 변수

【인】 *pt*<br/>

### <a name="remarks"></a>설명

## <a name="cmfctooltipctrlsetparams"></a><a name="setparams"></a>CMFC툴팁Ctrl::세트파라름

[CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md) 개체를 사용하여 도구 설명의 시각적 모양을 지정합니다.

```cpp
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>매개 변수

*pParams*<br/>
【인】 표시 매개 변수를 포함하는 [CMFCToolTipInfo 클래스 개체에](../../mfc/reference/cmfctooltipinfo-class.md) 대한 포인터입니다.

### <a name="remarks"></a>설명

도구 설명이 표시될 때마다 *pParams에서* 지정하는 색상 및 시각적 스타일을 사용하여 그려집니다. *pParams의* 값은 `m_Params` [CMFCToolTipCtrl::OnDrawBorder:](#ondrawborder) [CMFCToolTipCtrl:::OnDrawIcon,](#ondrawicon) [CMFCToolTipCtrl:::OnDrawLabel,](#ondrawlabel) [CMFCToolTipCtrl:::OnDrawSeparator,](#ondrawseparator)또는 [CMFCToolTipCtrl:::OnBackground](#onfillbackground) 모양을 유지 하도록 사용 되는 파생 된 클래스에 의해 액세스할 수 있는 보호 된 멤버에 저장 됩니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl 클래스](../../mfc/reference/ctooltipctrl-class.md)<br/>
[C툴팁매니저 클래스](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFC툴팁정보 클래스](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
