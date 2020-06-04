---
title: CMFC드롭다운툴바 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: 68dd976471b39d7f50c2f0378b2fce99ad3feeca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367598"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFC드롭다운툴바 클래스

사용자가 최상위 도구 모음 단추를 누르고 있을 때 나타나는 도구 모음입니다.

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC드롭다운툴바::허용쇼온파인메뉴](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`을 재정의합니다.)|
|[CMFC드롭다운툴바::로드비트맵](#loadbitmap)|[(CMFCToolBar 재정의::로드비트맵.)](../../mfc/reference/cmfctoolbar-class.md#loadbitmap)|
|[CMFC드롭다운툴바::로드툴바](#loadtoolbar)|[(CMFCToolBar 재정의::로드툴바.)](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar)|
|[CMFC드롭다운툴바::온버튼업](#onlbuttonup)||
|[CMFC드롭다운툴바::온마우스무브](#onmousemove)||
|[CMFC드롭다운툴바::온센드커맨드](#onsendcommand)|( `CMFCToolBar::OnSendCommand`을 재정의합니다.)|
|[CMFC드롭다운툴바::온업데이트CmdUI](#onupdatecmdui)|[(CMFCToolBar 재정의::OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>설명

개체는 `CMFCDropDownToolBar` 도구 모음의 시각적 모양과 팝업 메뉴의 동작을 결합합니다. 사용자가 드롭다운 도구 모음 단추를 누르고 [있으면(CMFCDropDownToolBarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)참조) 드롭다운 도구 모음이 나타나고 드롭다운 도구 모음에서 단추를 스크롤하여 마우스 버튼을 해제하여 단추를 선택할 수 있습니다. 사용자가 드롭다운 도구 모음에서 단추를 선택하면 해당 버튼이 최상위 도구 모음의 현재 단추로 표시됩니다.

드롭다운 도구 모음은 사용자 지정하거나 도킹할 수 없으며 찢어짐 상태가 없습니다.

다음 그림에서는 `CMFCDropDownToolBar` 개체를 보여 주며, 다음 그림에서는 개체를 보여 주실 수 있습니다.

![CMFCDropDownToolbar의 예제](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar의 예제")

일반 도구 `CMFCDropDownToolBar` 모음을 만드는 것과 동일한 방식으로 [개체를 만듭니다(CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)참조).

드롭다운 도구 모음을 상위 도구 모음에 삽입하려면 다음을 수행하십시오.

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

2. 드롭다운 `CMFCDropDownToolBarButton` 도구 모음이 포함된 개체를 만듭니다(자세한 내용은 [CMFCDropDownToolBAR Button::CMFCDropDownToolBARButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)참조).

3. `CMFCDropDownToolBarButton` [CMFCToolBar::ReplaceButton을](../../mfc/reference/cmfctoolbar-class.md#replacebutton)사용하여 더미 단추를 개체로 바꿉꿉니까?

도구 모음 단추에 대한 자세한 내용은 [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오. 드롭다운 도구 모음의 예는 샘플 프로젝트 VisualStudioDemo를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `Create` `CMFCDropDownToolBar` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFC드롭다운툴바::허용쇼온파인메뉴

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>CMFC드롭다운툴바::로드비트맵

애플리케이션 리소스에서 도구 모음 이미지를 로드합니다.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>매개 변수

*uiResID*<br/>
【인】 핫 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.

*uiColdResID*<br/>
【인】 콜드 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.

*uiMenuResID*<br/>
【인】 일반 메뉴 이미지를 참조하는 비트맵의 리소스 ID입니다.

*차단*<br/>
【인】 TRUE는 도구 모음을 잠급전지 않습니다. 그렇지 않으면 거짓.

*ui장애인ResID*<br/>
【인】 비활성화된 도구 모음 이미지를 참조하는 비트맵의 리소스 ID입니다.

*uiMenu장애인ResID*<br/>
【인】 비활성화된 메뉴 이미지를 참조하는 비트맵의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아니고, 실패하면 0입니다.

### <a name="remarks"></a>설명

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 메서드는 이 메서드를 호출하여 도구 모음과 관련된 이미지를 로드합니다. 이미지 리소스의 사용자 지정 로드를 수행하려면 이 메서드를 재정의합니다.

`LoadBitmapEx` 메서드를 호출하여 도구 모음을 만든 후 추가 이미지를 로드합니다.

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CMFC드롭다운툴바::로드툴바

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>매개 변수

【인】 *uiResID*<br/>

【인】 *uiColdResID*<br/>

【인】 *uiMenuResID*<br/>

【인】 *불 (것)이*<br/>

【인】 *ui장애인ResID*<br/>

【인】 *uiMenu장애인ResID*<br/>

【인】 *uiHotResID*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>CMFC드롭다운툴바::온버튼업

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

【인】 *nFlags*<br/>

【인】 *점*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>CMFC드롭다운툴바::온마우스무브

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

【인】 *nFlags*<br/>

【인】 *점*<br/>

### <a name="remarks"></a>설명

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>CMFC드롭다운툴바::온센드커맨드

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

【인】 *p 버튼*<br/>

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFC드롭다운툴바::온업데이트CmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>매개 변수

【인】 *p Target*<br/>

【인】 *bDisableIfNohndler*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFC툴바::만들기](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFC툴바::대체 버튼](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFC드롭다운툴버튼 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
