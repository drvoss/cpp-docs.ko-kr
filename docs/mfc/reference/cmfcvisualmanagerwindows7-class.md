---
title: CMFC비주얼매니저윈도우7 클래스
ms.date: 03/27/2019
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
ms.openlocfilehash: 6686afecc2b8ef97ea24ef45ff5225433677a954
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319842"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFC비주얼매니저윈도우7 클래스

는 `CMFCVisualManagerWindows7` 응용 프로그램에 윈도우 7 응용 프로그램의 모양을 제공합니다.

## <a name="syntax"></a>구문

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC비주얼매니저윈도우7::CMFC비주얼매니저윈도우7](#cmfcvisualmanagerwindows7)|기본 생성자입니다.|
|[CMFC비주얼매니저윈도우7::~CMFC비주얼매니저윈도우7](#_dtorcmfcvisualmanagerwindows7)|기본 소멸자.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|현재 시각적 스타일을 지우고 기본 시각적 스타일을 재설정합니다.|
|`CMFCVisualManagerWindows7::CleanUp`|사용자 인터페이스의 모든 개체를 지우고 메뉴를 재설정합니다.|
|`CMFCVisualManagerWindows7::DrawNcBtn`|프레임의 클라이언트가 아닌 영역에 단추를 그립니다. 프레임워크는 이 메서드를 사용하여 창 프레임의 오른쪽 상단 모서리에 있는 단추를 최소화, 최대화, 닫기 및 복원합니다. 이 메서드는 프로그램이 테마를 `Aero` 사용하는 경우에만 호출됩니다.|
|`CMFCVisualManagerWindows7::DrawNcText`|프레임의 클라이언트가 아닌 영역에 텍스트를 그립니다. 프레임워크는 이 메서드를 사용하여 프레임 창 맨 위에 있는 제목 표시줄에 응용 프로그램 제목을 그립니다.|
|`CMFCVisualManagerWindows7::DrawSeparator`|[CMFCToolBar 클래스에](../../mfc/reference/cmfctoolbar-class.md)구분 기호를 그립니다.|
|`CMFCVisualManagerWindows7::GetRibbonBar`|사용자 인터페이스와 연결된 [CMFC리본바 클래스를](../../mfc/reference/cmfcribbonbar-class.md) 검색합니다.|
|[CMFC비주얼매니저윈도우7::Get리본편집백컬러](#getribboneditbackgroundcolor)|리본 편집 상자 배경색을 가져옵니다.|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[재정의 CMFC비주얼 매니저::GetRibbonPopup국경 크기](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[재정의 CMFC비주얼 매니저::Get리본빠른액세스툴바셰브론오프셋](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[재정의 CMFC비주얼 매니저::Get리본빠른액세스툴바라이트마진](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[재정의 CMFC비주얼 매니저윈도우::이하이라이트전체메뉴항목](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[재정의 CMFC비주얼 매니저::IsOwner드로우메뉴체크](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|a가 `CMFCRibbonBar` 존재하고 표시되는지 여부를 결정합니다.|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[CMFC비주얼매니저윈도우 재정의::온드로우버튼보더](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[재정의 CMFC비주얼매니저윈도우::온드로우체크박스엑스](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[재정의 CMFC비주얼 매니저윈도우::온드로우컴보드롭버튼](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[CMFC 비주얼 관리자 재정의::온드로우디폴드리본이미지](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[재정의 CMFC비주얼 매니저윈도우::온드로우메뉴보더](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[재정의 CMFC비주얼 매니저::온드로우 메뉴체크](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[CMFC 비주얼 관리자 재정의::온드로우 메뉴라벨](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|`CMFCVisualManager::OnDrawRadioButton`를 재정의합니다.|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[CMFC VisualManager 재정의::온드로우리본응용 프로그램 단추](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[CMFC 비주얼 관리자 재정의::온드로우리본단추테두리](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[CMFC 비주얼 관리자 재정의::온드로우리본 캡션](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[CMFC 비주얼 관리자 재정의::온드로우리본 캡션버튼](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[CMFC 비주얼 관리자 재정의::온드로우리본카테고리](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[CMFC 비주얼 관리자 재정의::온드로우리본카테고리탭](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[CMFC 비주얼 관리자 재정의::온드로우리본기본판 버튼](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[CMFC 비주얼 관리자 재정의::온드로우리본 갤러리 단추](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|`CMFCVisualManager::OnDrawRibbonLaunchButton`를 재정의합니다.|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[재정의 CMFC 비주얼 관리자::에 그리기 리본 메뉴체크프레임](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[CMFC 비주얼 관리자 재정의::온드로우리본패널](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[CMFC 비주얼 관리자 재정의::온드로우리본패널캡션](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[CMFC 비주얼 관리자 재정의::온드로우리본진행바](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[재정의 CMFC 비주얼 관리자::에 그리기리본최근파일프레임](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[CMFC 비주얼 매니저 재정의::온드로우리본 슬라이더 채널](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[CMFC 비주얼 관리자 재정의::온드로우리본슬라이더엄지](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[CMFC 비주얼 관리자 재정의::에 그리기 리본 슬라이더 줌 버튼](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[재정의 CMFC비주얼 매니저::에 그리기리본 상태바파인](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[CMFC 비주얼 관리자 재정의::온드로우리본탭프레임](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[재정의 CMFC비주얼 매니저윈도우::에드로인상태바사이즈박스](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[재정의 CMFC비주얼매니저윈도우::온필바백](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[재정의 CMFC비주얼 매니저윈도우::온필 버튼인테리어](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|
|[CMFC비주얼매니저윈도우7::온필메뉴이미지렉트](#onfillmenuimagerect)|프레임워크는 메뉴 항목 이미지 주위에 영역을 채울 때 이 메서드를 호출합니다.|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[CMFC 비주얼 관리자 재정의::온필리본 버튼](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[재정의 CMFC비주얼 매니저::에필리본퀵액세스툴바팝업](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[재정의 CMFC비주얼 매니저윈도우::에 하이라이트 메뉴항목](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|
|`CMFCVisualManagerWindows7::OnNcActivate`|[CMFC 비주얼 관리자 재정의::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|
|`CMFCVisualManagerWindows7::OnNcPaint`|[CMFC비주얼매니저 재정의::온씨페인트](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[재정의 CMFC비주얼 매니저윈도우::온업데이트시스템색상](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|
|`CMFCVisualManagerWindows7::SetResourceHandle`|시각적 관리자의 특성을 설명하는 리소스 핸들을 설정합니다.|
|`CMFCVisualManagerWindows7::SetStyle`|`CMFCVisualManagerWindows7` GUI의 색 구성표를 설정합니다.|

## <a name="remarks"></a>설명

클래스를 `CMFCVisualManagerWindows7` 사용하여 기본 Windows 7 응용 프로그램을 모방하도록 응용 프로그램의 모양을 변경합니다. 응용 프로그램이 Windows 7 이전 버전의 Windows에서 실행 중인 경우 이 클래스가 유효하지 않을 수 있습니다. 이 시나리오에서 응용 프로그램은 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)에 정의된 기본 시각적 관리자를 사용합니다.

CMFCVisualManagerWindows7은 [CMFCVisualManagerWindows 클래스와](../../mfc/reference/cmfcvisualmanagerwindows-class.md) 클래스 모두에서 여러 `CMFCVisualManager` 메서드를 상속합니다. 이전 섹션에 나열된 메서드는 클래스에 `CMFCVisualManagerWindows7` 새로 접하는 메서드입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFC베이스비주얼매니저](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFC비주얼매니저오피스XP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>요구 사항

**헤더:** afxvisualmanagerwindows7.h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a>CMFC비주얼매니저윈도우7::~CMFC비주얼매니저윈도우7

기본 소멸자.

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a>CMFC비주얼매니저윈도우7::CMFC비주얼매니저윈도우7

기본 생성자입니다.

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a>CMFC비주얼매니저윈도우7::Get리본편집백컬러

리본 편집 상자의 배경색을 가져옵니다.

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>매개 변수

*Pedit*<br/>
【인】 편집 컨트롤에 대한 포인터입니다. 이 값은 NULL일 수 없습니다.

*비스하이라이트*<br/>
【아웃】 리본 상자가 강조 표시되어 있는지 여부를 반환합니다.

*비스파인 강조 표시*<br/>
【아웃】 *pEdit이* 포함된 리본 패널이 강조 표시되면 TRUE를 반환합니다.

*isdisabled*<br/>
【아웃】 *pEdit이* 비활성화되었는지 여부를 반환합니다.

### <a name="return-value"></a>Return Value

편집 상자의 배경 색 *pEdit*.

### <a name="remarks"></a>설명

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a>CMFC비주얼매니저윈도우7::온필메뉴이미지렉트

프레임워크는 메뉴 항목 이미지 주위의 영역을 채울 때 이 메서드를 호출합니다.

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 메뉴 단추의 장치 컨텍스트에 대한 포인터입니다.

*p 버튼*<br/>
【인】 에 대한 `CMFCToolBarButton`포인터입니다. 프레임워크는 이 단추의 배경을 채웁니다.

*사각형*<br/>
【인】 메뉴 단추 이미지 영역의 경계를 지정하는 사각형입니다.

*상태*<br/>
【인】 단추 상태입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC비주얼매니저 클래스](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFC비주얼매니저윈도우 클래스](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
