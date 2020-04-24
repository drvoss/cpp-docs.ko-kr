---
title: CMFCBaseVisualManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
ms.openlocfilehash: ac64a3feac5d124c2bfa67fc857dad5045c2dd28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754881"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager 클래스

파생된 시각적 관리자와 Windows 테마 API 간의 계층입니다.

`CMFCBaseVisualManager`사용 가능한 경우 UxTheme.dll을 로드하고 Windows 테마 API 메서드에 대한 액세스를 관리합니다.

이 클래스는 내부 용으로만 사용됩니다.

## <a name="syntax"></a>구문

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFC베이스비주얼매니저::CMFC베이스비주얼매니저](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC베이스비주얼매니저::D로체크박스](#drawcheckbox)|현재 Windows 테마를 사용하여 확인란 컨트롤을 그립니다.|
|[CMFC베이스비주얼매니저::D로콤보보보보보보보](#drawcomboborder)|현재 Windows 테마를 사용하여 콤보 상자 테두리를 그립니다.|
|[CMFC베이스비주얼매니저::D로컴보드롭버튼](#drawcombodropbutton)|현재 Windows 테마를 사용하여 콤보 상자 드롭다운 단추를 그립니다.|
|[CMFC베이스비주얼매니저::D로 푸시버튼](#drawpushbutton)|현재 Windows 테마를 사용하여 푸시 버튼을 그립니다.|
|[CMFC베이스비주얼매니저::D로라디오버튼](#drawradiobutton)|현재 Windows 테마를 사용하여 라디오 단추 컨트롤을 그립니다.|
|[CMFC베이스 비주얼 매니저::D원시 상태표시진행](#drawstatusbarprogress)|현재 Windows 테마를 사용하여 상태 표시줄 [컨트롤(CMFCStatusBar 클래스)에](../../mfc/reference/cmfcstatusbar-class.md)진행률 표시줄을 그립니다.|
|[CMFC베이스비주얼매니저::필레바파네](#fillrebarpane)|현재 Windows 테마를 사용하여 철근 컨트롤의 배경을 채웁니다.|
|[CMFC베이스 비주얼 매니저::겟스탠다드윈도우테마](#getstandardwindowstheme)|현재 Windows 테마를 가져옵니다.|

### <a name="protected-methods"></a>Protected 메서드

|||
|-|-|
|속성|Description|
|[CMFC베이스비주얼매니저::정리테마](#cleanupthemes)|에서 `CloseThemeData` `UpdateSystemColors`얻은 모든 핸들에 대한 호출|
|[CMFC베이스 비주얼 매니저::업데이트시스템색상](#updatesystemcolors)|창, 도구 모음, 단추 등 다양한 컨트롤을 그리기 위한 핸들을 얻기 위한 호출입니다. `OpenThemeData`|

## <a name="remarks"></a>설명

이 클래스의 개체를 직접 인스턴스화할 필요는 없습니다.

모든 시각적 관리자의 기본 클래스이기 때문에 [CMFCVisualManager::GetInstance를](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)호출하고 현재 Visual Manager에 대한 포인터를 `CMFCBaseVisualManager` 가져오고 해당 포인터를 사용하는 메서드에 액세스할 수 있습니다. 그러나 현재 Windows 테마를 사용 하 여 컨트롤을 표시 해야 하는 `CMFCVisualManagerWindows` 경우 인터페이스를 사용 하는 것이 좋습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFC베이스비주얼매니저](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxvisualmanager.h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a>CMFC베이스비주얼매니저::정리테마

에서 `CloseThemeData` `UpdateSystemColors`얻은 모든 핸들에 대한 호출

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>설명

내부 전용입니다.

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a>CMFC베이스비주얼매니저::CMFC베이스비주얼매니저

`CMFCBaseVisualManager` 개체를 생성하고 초기화합니다.

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a>CMFC베이스비주얼매니저::D로체크박스

현재 Windows 테마를 사용하여 확인란 컨트롤을 그립니다.

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터

*rect*<br/>
【인】 확인란의 경계 사각형입니다.

*b 강조 표시*<br/>
【인】 확인란이 강조 표시되어 있는지 여부를 지정합니다.

*nState*<br/>
[in] 0: 체크무미, 1은 보통,

2 혼합 정상.

*bEnabled*<br/>
【인】 확인란이 활성화되어 있는지 여부를 지정합니다.

*bpressed*<br/>
【인】 확인란을 눌렀는지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

*nState값은* 다음 확인란 스타일에 해당합니다.

|nState|확인란 스타일|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a>CMFC베이스비주얼매니저::D로콤보보보보보보보

현재 Windows 테마를 사용하여 콤보 상자 테두리를 그립니다.

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 콤보 상자 테두리의 경계 사각형입니다.

*b 장애인*<br/>
【인】 콤보 상자 테두리를 사용하지 않도록 설정했는지 여부를 지정합니다.

*비스드 드롭*<br/>
【인】 콤보 상자 테두리를 삭제하는지 여부를 지정합니다.

*비스하이라이트*<br/>
【인】 콤보 상자 테두리가 강조 표시되어 있는지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a>CMFC베이스비주얼매니저::D로컴보드롭버튼

현재 Windows 테마를 사용하여 콤보 상자 드롭다운 단추를 그립니다.

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pDC*|【인】 장치 컨텍스트에 대한 포인터입니다.|
|*rect*|【인】 콤보 상자 드롭다운 버튼의 경계 사각형입니다.|
|*b 장애인*|【인】 콤보 상자 드롭다운 단추를 사용하지 않도록 설정했는지 여부를 지정합니다.|
|*비스드 드롭*|【인】 콤보 상자 드롭다운 버튼을 삭제할지 여부를 지정합니다.|
|*비스하이라이트*|【인】 콤보 상자 드롭다운 버튼이 강조 표시되어 있는지 여부를 지정합니다.|

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a>CMFC베이스비주얼매니저::D로 푸시버튼

현재 Windows 테마를 사용하여 푸시 버튼을 그립니다.

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 푸시 버튼의 경계 사각형입니다.

*p 버튼*<br/>
【인】 그릴 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md) 개체에 대한 포인터입니다.

*uiState*<br/>
【인】 무시. 상태는 *pButton에서*가져온 것입니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a>CMFC베이스비주얼매니저::D로라디오버튼

현재 Windows 테마를 사용하여 라디오 단추 컨트롤을 그립니다.

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*rect*<br/>
【인】 라디오 단추의 경계 사각형입니다.

*b 강조 표시*<br/>
【인】 라디오 버튼이 강조 표시되어 있는지 여부를 지정합니다.

*b 확인됨*<br/>
【인】 라디오 단추를 선택했는지 여부를 지정합니다.

*bEnabled*<br/>
【인】 라디오 버튼이 활성화되어 있는지 여부를 지정합니다.

*bpressed*<br/>
【인】 라디오 버튼을 누를지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a>CMFC베이스 비주얼 매니저::D원시 상태표시진행

현재 Windows 테마를 사용하여 상태 표시줄 [컨트롤(CMFCStatusBar 클래스)에서](../../mfc/reference/cmfcstatusbar-class.md)진행률 표시줄을 그립니다.

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*pStatusBar*<br/>
【인】 상태 표시줄에 대한 포인터입니다. 이 값은 무시됩니다.

*직류 진행률*<br/>
【인】 *pDC* 좌표에서 진행률 표시줄의 경계 사각형입니다.

*nProgressTotal*<br/>
【인】 총 진행률 값입니다.

*nProgressCurr*<br/>
【인】 현재 진행률 값입니다.

*클러바*<br/>
【인】 시작 색상입니다. `CMFCBaseVisualManager`무시합니다. 파생 클래스는 색상 그라데이션에 사용할 수 있습니다.

*clrProgressBarDest*<br/>
【인】 끝 색상입니다. `CMFCBaseVisualManager`무시합니다. 파생 클래스는 색상 그라데이션에 사용할 수 있습니다.

*clrProgressText*<br/>
【인】 텍스트 색상을 진행합니다. `CMFCBaseVisualManager`무시합니다. 텍스트 색상은 에 `afxGlobalData.clrBtnText`의해 정의됩니다.

*bProgressText*<br/>
【인】 진행률 텍스트를 표시할지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a>CMFC베이스비주얼매니저::필레바파네

현재 Windows 테마를 사용하여 철근 컨트롤의 배경을 채웁니다.

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*pBar*<br/>
【인】 배경을 그려야 하는 창에 대한 포인터입니다.

*rectClient*<br/>
【인】 채울 영역의 경계 사각형입니다.

### <a name="return-value"></a>Return Value

TRUE 테마 API가 활성화되어 있는 경우; 그렇지 않으면 거짓.

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a>CMFC베이스 비주얼 매니저::겟스탠다드윈도우테마

현재 Windows 테마를 가져옵니다.

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>Return Value

현재 선택한 Windows 테마 색상입니다. 다음 열거된 값 중 하나가 될 수 있습니다.

- `WinXpTheme_None`- 테마가 활성화되지 않습니다.

- `WinXpTheme_NonStandard`- 비 표준 테마가 선택됩니다 (테마가 선택되었지만 아래 목록에서 는 선택되지 않습니다).

- `WinXpTheme_Blue`- 파란색 테마 (루나).

- `WinXpTheme_Olive`- 올리브 테마.

- `WinXpTheme_Silver`- 실버 테마.

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a>CMFC베이스 비주얼 매니저::업데이트시스템색상

창, 도구 모음, 단추 등 다양한 컨트롤을 그리기 위한 핸들을 얻기 위한 호출입니다. `OpenThemeData`

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>설명

내부 전용입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
