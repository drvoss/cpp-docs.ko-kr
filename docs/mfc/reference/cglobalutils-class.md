---
title: CGlobalUtils 클래스
ms.date: 10/18/2018
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
ms.openlocfilehash: dbac56ea7efca98218133b23657f8508ea6bac28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752911"
---
# <a name="cglobalutils-class"></a>CGlobalUtils 클래스

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CGlobalUtils
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils::CanBeAttached](#canbeattached)||
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils::CheckAlignment](#checkalignment)||
|[CGlobalUtils::CyFromString](#cyfromstring)||
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||
|[CGlobalUtils::FlipRect](#fliprect)||
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils::GetWndIcon](#getwndicon)||
|[CGlobalUtils::SetNewParent](#setnewparent)||
|[CGlobalUtils::StringFromCy](#stringfromcy)||
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxglobalutils.h

## <a name="cglobalutilsadjustrecttoworkarea"></a><a name="adjustrecttoworkarea"></a>CGlobalUtils::adjustRectToWorkArea

```cpp
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>매개 변수

【인, 아웃】 *정류*<br/>
【인】 *프렉트델타*<br/>

### <a name="remarks"></a>설명

## <a name="cglobalutilscalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CGlobalUtils::CalcExpectedDockedRect

```cpp
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

【인】 *바 컨테이너 관리자*<br/>

【인】 *pWndTodock*<br/>

【인】 *pt마우스*<br/>

【아웃】 *정류 결과*<br/>

【아웃】 *b그리기 탭*<br/>

【아웃】 *ppTargetBar*<br/>

### <a name="remarks"></a>설명

## <a name="cglobalutilscanbeattached"></a><a name="canbeattached"></a>CGlobalUtils::수 있습니다연결

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilscanpanebeinfloatingmultipaneframewnd"></a><a name="canpanebeinfloatingmultipaneframewnd"></a>CGlobalUtils::칸파네빈플로팅멀티파인프레임

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilscheckalignment"></a><a name="checkalignment"></a>CGlobalUtils::체크정렬

```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>매개 변수

【인】 *점*<br/>

【인】 *pBar*<br/>

【인】 *n감도*<br/>

【인】 *pDockManager*<br/>

【인】 *bOuterEdge*<br/>

【아웃】 *dw정렬*<br/>

【인】 *dwEnabledDockBar*<br/>

【인】 *lpRect바운드*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilscyfromstring"></a><a name="cyfromstring"></a>CGlobalUtils::사이프프스트링

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>매개 변수

【아웃】 *사이 (것)에*<br/>

【인】 *psz*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsdecimalfromstring"></a><a name="decimalfromstring"></a>CGlobalUtils::D에시멀스트링

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>매개 변수

【아웃】 *십진수*<br/>

【인】 *psz*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsfliprect"></a><a name="fliprect"></a>CGlobalUtils::플립렉트

```cpp
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>매개 변수

【인, 아웃】 *정류*<br/>
【인】 *n도*<br/>

### <a name="remarks"></a>설명

## <a name="cglobalutilsforceadjustlayout"></a><a name="forceadjustlayout"></a>CGlobalUtils::포스조정레이아웃

```cpp
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>매개 변수

【인, 아웃】 *pDockManager*<br/>

【인】 *bForce*<br/>

【인】 *b인가볼*<br/>

### <a name="remarks"></a>설명

## <a name="cglobalutilsgetdockingmanager"></a><a name="getdockingmanager"></a>CGlobalUtils::GetDockingManager

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsgetoppositealignment"></a><a name="getoppositealignment"></a>CGlobalUtils::Get반대 정렬

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>매개 변수

【인】 *dwAlign*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsgetpaneandalignfrompoint"></a><a name="getpaneandalignfrompoint"></a>CGlobalUtils::겟파네앤정렬From포인트

```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>매개 변수

【인】 *바 컨테이너 관리자*<br/>

【인】 *pt*<br/>

【아웃】 *ppTargetControlBar*<br/>

【아웃】 *dw정렬*<br/>

【아웃】 *bTabArea*<br/>

【아웃】 *b캡션*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsgetwndicon"></a><a name="getwndicon"></a>CGlobalUtils::GetWndicon

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

【인】 *pWnd*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilssetnewparent"></a><a name="setnewparent"></a>CGlobalUtils::SetNewParent

```cpp
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>매개 변수

【인】 *lstControlBars*<br/>

【인】 *pNewParent*<br/>

【인】 *b체크가시성*<br/>

### <a name="remarks"></a>설명

## <a name="cglobalutilsstringfromcy"></a><a name="stringfromcy"></a>CGlobalUtils::문자열FromCy

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>매개 변수

【아웃】 *str*<br/>

【인】 *사이 (것)에*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cglobalutilsstringfromdecimal"></a><a name="stringfromdecimal"></a>CGlobalUtils::문자열출신데시

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>매개 변수

【아웃】 *str*<br/>

【인】 *십진수*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
