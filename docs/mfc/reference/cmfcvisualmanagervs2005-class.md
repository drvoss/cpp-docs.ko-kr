---
title: CMFC비주얼매니저VS2005 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
ms.openlocfilehash: b92077ecf4670dd5395296327c767ee3c7b848ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319911"
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFC비주얼매니저VS2005 클래스

`CMFCVisualManagerVS2005`응용 프로그램에 마이크로 소프트 비주얼 스튜디오 2005 모양을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC비주얼매니저VS2005::겟도킹탭스테두리크기](#getdockingtabsborderssize)|프레임워크는 도킹되고 탭된 창을 그릴 때 이 메서드를 호출합니다. [(재정의 CMFC비주얼 매니저::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|
|[CMFC비주얼매니저VS2005::겟MDITabsBordersSize](#getmditabsborderssize)|프레임워크는 창을 그리기 전에 MDITabs 창의 테두리 크기를 결정하기 위해 이 메서드를 호출합니다. [(재정의 CMFC비주얼 매니저::GetMDITabsBordersSize.)](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)|
|[CMFC비주얼매니저VS2005::겟프로퍼티그리드그룹컬러](#getpropertygridgroupcolor)|[(재정의 CMFC비주얼 매니저Office2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor).)|
|[CMFC비주얼매니저VS2005::겟탭프레임컬러](#gettabframecolors)|[(재정의 CMFC비주얼 매니저Office2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors).)|
|[CMFC비주얼매니저VS2005::하오버랩자동숨기기버튼](#hasoverlappedautohidebuttons)|자동 숨기기 버튼이 현재 시각적 관리자에서 겹치는지 여부를 반환합니다. [(재정의 CMFC비주얼 매니저::하스오버랩자동하이드버튼.)](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons)|
|[CMFC비주얼매니저VS2005::에드로드자동하이드버튼보더](#ondrawautohidebuttonborder)|[(재정의 CMFC비주얼 매니저Office2003::에드드로자동하이드버튼경계](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder).)|
|[CMFC비주얼매니저VS2005::온드로우캡션버튼](#ondrawcaptionbutton)|( `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`을 재정의합니다.)|
|[CMFC비주얼매니저VS2005::온드로우파네캡션](#ondrawpanecaption)|[(재정의 CMFC비주얼 매니저Office2003::온드로우파네 캡션](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption).)|
|[CMFC비주얼매니저VS2005::온드로우세파레이터](#ondrawseparator)|[(재정의 CMFC비주얼 매니저Office2003::에그리기세파레이터](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator).)|
|[CMFC비주얼매니저VS2005::온드로우탭](#ondrawtab)|[(재정의 CMFC비주얼 매니저오피스2003::온드로우탭.)](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab)|
|[CMFC비주얼매니저VS2005::온드로우툴박스프레임](#ondrawtoolboxframe)|[(CMFC 비주얼 관리자 재정의::온드로우툴박스프레임.)](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe)|
|[CMFC비주얼매니저VS2005::에라아제탭스에어리어](#onerasetabsarea)|[(재정의 CMFC비주얼 매니저Office2003::에라아제탭 영역](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea).)|
|[CMFC비주얼매니저VS2005::에필자동하이드버튼백](#onfillautohidebuttonbackground)|[(재정의 CMFC비주얼 매니저Office2003::에필자동 하이드버튼배경](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground).)|
|[CMFC비주얼매니저VS2005::온필하이라이트에어리어](#onfillhighlightedarea)|[(재정의 CMFC비주얼 매니저Office2003::OnFill강조 영역](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|
|[CMFC비주얼매니저VS2005:::온필미니프레임캡션](#onfillminiframecaption)|( `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`을 재정의합니다.)|
|[CMFC비주얼매니저VS2005::업데이트시스템색상](#onupdatesystemcolors)|[(재정의 CMFC비주얼 매니저Office2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors).)|

## <a name="remarks"></a>설명

CMFCVisualManagerVS2005 클래스를 사용하여 응용 프로그램의 시각적 모양을 Microsoft Visual Studio 2005와 유사하게 변경합니다.

이 클래스의 모든 구성원은 이 클래스의 상위 인 [CMFCVisualManager 클래스에서](../../mfc/reference/cmfcvisualmanager-class.md)파생 된 가상 함수입니다.

## <a name="example"></a>예제

다음 예제에서는 VISUAL 관리자 VS 2005를 사용하는 방법을 보여 줍니다. 이 코드 조각은 데스크톱 [경고 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFC베이스비주얼매니저](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFC비주얼매니저오피스XP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)

[CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxvisualmanagervs2005.h

## <a name="cmfcvisualmanagervs2005getdockingtabsborderssize"></a><a name="getdockingtabsborderssize"></a>CMFC비주얼매니저VS2005::겟도킹탭스테두리크기

```
virtual int GetDockingTabsBordersSize();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005getmditabsborderssize"></a><a name="getmditabsborderssize"></a>CMFC비주얼매니저VS2005::겟MDITabsBordersSize

```
virtual int GetMDITabsBordersSize();
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005getpropertygridgroupcolor"></a><a name="getpropertygridgroupcolor"></a>CMFC비주얼매니저VS2005::겟프로퍼티그리드그룹컬러

```
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```

### <a name="parameters"></a>매개 변수

【인】 *프로펠리스트*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005gettabframecolors"></a><a name="gettabframecolors"></a>CMFC비주얼매니저VS2005::겟탭프레임컬러

```
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,
    COLORREF& clrDark,
    COLORREF& clrBlack,
    COLORREF& clrHighlight,
    COLORREF& clrFace,
    COLORREF& clrDarkShadow,
    COLORREF& clrLight,
    CBrush*& pbrFace,
    CBrush*& pbrBlack);
```

### <a name="parameters"></a>매개 변수

【인】 *pTabWnd*<br/>
【인】 *클래다크*<br/>
【인】 *클러 블랙*<br/>
【인】 *clr하이라이트*<br/>
【인】 *클러 페이스*<br/>
【인】 *클러 다크 섀도우*<br/>
【인】 *clrLight*<br/>
【인】 *pbrFace*<br/>
【인】 *pbr블랙*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005hasoverlappedautohidebuttons"></a><a name="hasoverlappedautohidebuttons"></a>CMFC비주얼매니저VS2005::하오버랩자동숨기기버튼

```
virtual BOOL HasOverlappedAutoHideButtons() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawautohidebuttonborder"></a><a name="ondrawautohidebuttonborder"></a>CMFC비주얼매니저VS2005::에드로드자동하이드버튼보더

```
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *정류 바운드*<br/>
【인】 *직사각형 테두리크기*<br/>
【인】 *p 버튼*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawcaptionbutton"></a><a name="ondrawcaptionbutton"></a>CMFC비주얼매니저VS2005::온드로우캡션버튼

```
virtual void OnDrawCaptionButton(
    CDC* pDC,
    CMFCCaptionButton* pButton,
    BOOL bActive,
    BOOL bHorz,
    BOOL bMaximized,
    BOOL bDisabled,
    int nImageID = -1);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *p 버튼*<br/>
【인】 *b활성*<br/>
【인】 *b호르츠 (주)*<br/>
【인】 *b최대화*<br/>
【인】 *b 장애인*<br/>
【인】 *n이미지 ID*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawpanecaption"></a><a name="ondrawpanecaption"></a>CMFC비주얼매니저VS2005::온드로우파네캡션

```
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,
    CDockablePane* pBar,
    BOOL bActive,
    CRect rectCaption,
    CRect rectButtons);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *pBar*<br/>
【인】 *b활성*<br/>
【인】 *정류 캡션*<br/>
【인】 *정사각형 버튼*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawseparator"></a><a name="ondrawseparator"></a>CMFC비주얼매니저VS2005::온드로우세파레이터

```
virtual void OnDrawSeparator(
    CDC* pDC,
    CBasePane* pBar,
    CRect rect,
    BOOL bIsHoriz);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *pBar*<br/>
[in] *rect*<br/>
【인】 *비쇼리즈*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawtab"></a><a name="ondrawtab"></a>CMFC비주얼매니저VS2005::온드로우탭

```
virtual void OnDrawTab(
    CDC* pDC,
    CRect rectTab,
    int iTab,
    BOOL bIsActive,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *정사각형 탭*<br/>
[in] *iTab*<br/>
【인】 *비스액티브*<br/>
【인】 *pTabWnd*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005ondrawtoolboxframe"></a><a name="ondrawtoolboxframe"></a>CMFC비주얼매니저VS2005::온드로우툴박스프레임

```
virtual void OnDrawToolBoxFrame(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
[in] *rect*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005onerasetabsarea"></a><a name="onerasetabsarea"></a>CMFC비주얼매니저VS2005::에라아제탭스에어리어

```
virtual void OnEraseTabsArea(
    CDC* pDC,
    CRect rect,
    const CMFCBaseTabCtrl* pTabWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
[in] *rect*<br/>
【인】 *pTabWnd*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005onfillautohidebuttonbackground"></a><a name="onfillautohidebuttonbackground"></a>CMFC비주얼매니저VS2005::에필자동하이드버튼백

```
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,
    CRect rect,
    CMFCAutoHideButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
[in] *rect*<br/>
【인】 *p 버튼*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005onfillhighlightedarea"></a><a name="onfillhighlightedarea"></a>CMFC비주얼매니저VS2005::온필하이라이트에어리어

```
virtual void OnFillHighlightedArea(
    CDC* pDC,
    CRect rect,
    CBrush* pBrush,
    CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
[in] *rect*<br/>
【인】 *p브러시*<br/>
【인】 *p 버튼*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005onfillminiframecaption"></a><a name="onfillminiframecaption"></a>CMFC비주얼매니저VS2005:::온필미니프레임캡션

```
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,
    CRect rectCaption,
    CPaneFrameWnd* pFrameWnd,
    BOOL bActive);
```

### <a name="parameters"></a>매개 변수

【인】 *pDC*<br/>
【인】 *정류 캡션*<br/>
【인】 *pFrameWnd*<br/>
【인】 *b활성*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagervs2005onupdatesystemcolors"></a><a name="onupdatesystemcolors"></a>CMFC비주얼매니저VS2005::업데이트시스템색상

```
virtual void OnUpdateSystemColors();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC비주얼매니저 클래스](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerOfficeXP 클래스](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)<br/>
[CMFC비주얼매니저윈도우 클래스](../../mfc/reference/cmfcvisualmanagerwindows-class.md)<br/>
[CMFC비주얼매니저오피스2003 클래스](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)
