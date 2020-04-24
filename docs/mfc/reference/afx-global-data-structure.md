---
title: AFX_GLOBAL_DATA 구조체
ms.date: 11/04/2016
f1_keywords:
- AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::CleanUp
- AFXGLOBALS/AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawParentBackground
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawTextOnGlass
- AFXGLOBALS/AFX_GLOBAL_DATA::ExcludeTag
- AFXGLOBALS/AFX_GLOBAL_DATA::GetColor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetDirect2dFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetHandCursor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList3
- AFXGLOBALS/AFX_GLOBAL_DATA::GetNonClientMetrics
- AFXGLOBALS/AFX_GLOBAL_DATA::GetShellAutohideBars
- AFXGLOBALS/AFX_GLOBAL_DATA::GetTextHeight
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWICFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWriteFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::InitD2D
- AFXGLOBALS/AFX_GLOBAL_DATA::Is32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::IsDwmCompositionEnabled
- AFXGLOBALS/AFX_GLOBAL_DATA::IsHighContrastMode
- AFXGLOBALS/AFX_GLOBAL_DATA::OnSettingChange
- AFXGLOBALS/AFX_GLOBAL_DATA::RegisterWindowClass
- AFXGLOBALS/AFX_GLOBAL_DATA::ReleaseTaskBarRefs
- AFXGLOBALS/AFX_GLOBAL_DATA::Resume
- AFXGLOBALS/AFX_GLOBAL_DATA::SetLayeredAttrib
- AFXGLOBALS/AFX_GLOBAL_DATA::SetMenuFont
- AFXGLOBALS/AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateFonts
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateSysColors
- AFXGLOBALS/AFX_GLOBAL_DATA::EnableAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsWindows7
- AFXGLOBALS/AFX_GLOBAL_DATA::clrActiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::clrInactiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseSystemFont
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurHand
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretch
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretchVert
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hiconTool
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
ms.openlocfilehash: 0361d535a31526c5f7b79fdd4eab046dad0435cc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752877"
---
# <a name="afx_global_data-structure"></a>AFX_GLOBAL_DATA 구조체

`AFX_GLOBAL_DATA` 구조는 프레임워크를 관리하거나 애플리케이션의 모양과 동작을 사용자 지정하는 데 사용되는 필드 및 메서드를 포함합니다.

## <a name="syntax"></a>구문

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|`AFX_GLOBAL_DATA` 구조를 생성합니다.|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[AFX_GLOBAL_DATA::CleanUp](#cleanup)|브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.|
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.|
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|지정된 영역에 컨트롤 부모의 배경을 그립니다.|
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|지정된 테마의 비주얼 스타일로 지정된 텍스트를 그립니다.|
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.|
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.|
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|글로벌 데이터에 저장된 `ID2D1Factory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|식별자가 `IDC_HAND`인 손 모양의 미리 정의된 커서를 검색합니다.|
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|ITaskBarList 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|ITaskBarList3 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.|
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|셸 자동 숨기기 막대의 위치를 결정합니다.|
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|현재 글꼴에서 텍스트 문자의 높이를 검색합니다.|
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|글로벌 데이터에 저장된 `IWICImagingFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|글로벌 데이터에 저장된 `IDWriteFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|
|[AFX_GLOBAL_DATA::InitD2D](#initd2d)|`D2D`, `DirectWrite`및 `WIC` 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D` 의 초기화 여부를 확인합니다.|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) 메서드를 호출하는 간단한 방법을 제공합니다.|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|지정된 MFC 창 클래스를 등록합니다.|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList 및 GetITaskbarList3 메서드를 통해 얻은 인터페이스를 해제합니다.|
|[AFX_GLOBAL_DATA::Resume](#resume)|Windows [테마 및 비주얼 스타일](/windows/win32/Controls/visual-styles-overview)을 지원하는 메서드에 액세스하는 내부 함수 포인터를 다시 초기화합니다.|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) 메서드를 호출하는 간단한 방법을 제공합니다.|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|지정된 논리 글꼴을 만듭니다.|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다. Active Accessibility는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 방법을 제공합니다.|
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|현재 운영 체제가 알파 혼합을 지원하는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|애플리케이션이 Windows 7 운영 체제 이상에서 실행되고 있는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.|
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|손 모양 커서에 대한 핸들을 저장합니다.|
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|가로 늘이기 커서에 대한 핸들을 저장합니다.|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|세로 늘이기 커서에 대한 핸들을 저장합니다.|
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|도구 아이콘에 대한 핸들을 저장합니다.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|맨 왼쪽 자동 숨기기 도구 모음에서 도킹 모음의 왼쪽까지의 오프셋을 지정합니다.|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|자동 숨기기 도구 모음 사이의 간격을 지정합니다.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|도킹된 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|부동 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|

### <a name="remarks"></a>설명

`AFX_GLOBAL_DATA` 구조에서 대부분의 데이터는 애플리케이션 시작 시 초기화됩니다.

### <a name="inheritance-hierarchy"></a>상속 계층 구조

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>요구 사항

**헤더:** afxglobals.h

## <a name="afx_global_databisosalphablendingsupport"></a><a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::비소스알파블렌딩지원

운영 체제가 알파 블렌딩을 지원하는지 여부를 나타냅니다.

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>설명

TRUE는 알파 블렌딩이 지원된다는 것을 나타냅니다. 그렇지 않으면 false입니다.

## <a name="afx_global_datacleanup"></a><a name="cleanup"></a>AFX_GLOBAL_DATA::정리

브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.

```cpp
void CleanUp();
```

## <a name="afx_global_datad2d1makerotatematrix"></a><a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1메이크회전매트릭스

지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>매개 변수

*각도*<br/>
시계 방향 회전 각도(도)입니다.

*센터*<br/>
회전할 점입니다.

*매트릭스*<br/>
이 메서드가 반환되면 새 회전 변환이 포함됩니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.

### <a name="return-value"></a>Return Value

성공하면 S_OK 반환하거나 오류 값을 반환합니다.

## <a name="afx_global_datadrawparentbackground"></a><a name="drawparentbackground"></a>AFX_GLOBAL_DATA::D원시부모배경

지정된 영역에 컨트롤 부모의 배경을 그립니다.

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 컨트롤의 창에 대한 포인터입니다.

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*Lprect*<br/>
【인】 그릴 영역을 경계하는 사각형에 대한 포인터입니다. 기본값은 NULL입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="afx_global_datadrawtextonglass"></a><a name="drawtextonglass"></a>AFX_GLOBAL_DATA::D로텍스트온글래스

지정된 테마의 비주얼 스타일로 지정된 텍스트를 그립니다.

```
BOOL DrawTextOnGlass(
    HTHEME hTheme,
    CDC* pDC,
    int iPartId,
    int iStateId,
    CString strText,
    CRect rect,
    DWORD dwFlags,
    int nGlowSize = 0,
    COLORREF clrText = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*hTheme*<br/>
【인】 창 또는 NULL의 테마 데이터를 처리합니다. 이 매개 변수가 NULL이 아니고 테마가 지원되는 경우 프레임워크는 지정된 테마를 사용하여 텍스트를 그립니다. 그렇지 않으면 테마를 사용하여 텍스트를 그리지 않습니다.

[OpenThemeData](/windows/win32/api/uxtheme/nf-uxtheme-openthemedata) 메서드를 사용하여 HTHEME를 만듭니다.

*pDC*<br/>
【인】 장치 컨텍스트에 대한 포인터입니다.

*아이파르티드*<br/>
【인】 원하는 텍스트 모양을 가지는 컨트롤 부분입니다. 자세한 내용은 [파트 및 상태](/windows/win32/controls/parts-and-states)에 설명된 표의 파트 열을 참조하세요. 이 값이 0이면 텍스트가 기본 글꼴로 그려지거나 디바이스 컨텍스트로 선택된 글꼴로 그려집니다.

*아이스테이트아이드*<br/>
【인】 원하는 텍스트 모양을 가지는 컨트롤 상태입니다. 자세한 내용은 [파트 및 상태](/windows/win32/controls/parts-and-states)에 설명된 표의 상태 열을 참조하세요.

*strText*<br/>
【인】 그릴 텍스트입니다.

*rect*<br/>
【인】 지정된 텍스트가 그려지는 영역의 경계입니다.

*dwFlags*<br/>
【인】 지정된 텍스트가 그려지는 방법을 지정하는 플래그의 비트 조합(OR)입니다.

*hTheme* 매개 변수가 `NULL` 있거나 테마가 지원되고 활성화되어 있지 않은 경우 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) 메서드의 *nFormat* 매개 변수는 유효한 플래그를 설명합니다. 테마가 지원되는 경우 [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) 메서드의 *dwFlags* 매개 변수는 유효한 플래그를 설명합니다.

*앤글로우 사이즈*<br/>
【인】 지정된 텍스트를 그리기 전에 배경에 그려진 광선 효과의 크기입니다. 기본값은 0입니다.

*clrText*<br/>
【인】 지정된 텍스트가 그려지는 색상입니다. 기본값은 기본 색입니다.

### <a name="return-value"></a>Return Value

TRUE 테마를 사용하여 지정된 텍스트를 그리는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

테마는 애플리케이션의 비주얼 스타일을 정의합니다. *hTheme* 매개 변수가 NULL이거나 [DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex) 메서드가 지원되지 않거나 데스크톱 창 관리자(DWM) 컴포지션이 비활성화된 경우 테마가 텍스트를 그리는 데 사용되지 않습니다. [Desktop Window Manager](/windows/win32/dwm/dwm-overview)

## <a name="afx_global_dataenableaccessibilitysupport"></a><a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA:::사용 접근성 지원

Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다.

```cpp
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 내게 필요한 옵션 지원을 활성화합니다. FALSE는 내게 필요한 옵션 지원을 사용하지 않도록 설정합니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

Active Accessibility는 프로그램의 방식을 향상시키는 COM 기반의 기술이고 Windows 운영 체제는 보조 기술 제품과 함께 작동합니다. 이는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 메서드를 제공합니다. 그러나 이제부터 Microsoft UI 자동화라고 하는 새로운 내게 필요한 옵션 모델을 사용할 수 있습니다. 두 기술을 비교하면 UI [자동화 및 Microsoft 활성 내게 필요한 옵션](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)모음을 참조하십시오.

[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) 메서드를 사용하여 Microsoft 활성 접근성 지원이 활성화되어 있는지 확인합니다.

## <a name="afx_global_dataexcludetag"></a><a name="excludetag"></a>AFX_GLOBAL_DATA::제외 태그

지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>매개 변수

*스트버퍼*<br/>
【인】 텍스트 버퍼입니다.

*lpszTag*<br/>
【인】 XML 태그 의 열기 및 닫는 쌍의 이름입니다.

*스트태그*<br/>
【아웃】 이 메서드가 반환 하는 경우 *strTag* 매개 *변수는 lpszTag* 매개 변수에 의해 명명 된 여기와 닫는 XML 태그 사이 텍스트를 포함 합니다. 선행 또는 후행 공백은 결과에서 잘립니다.

*비스차르리스트*<br/>
【인】 TRUE는 *strTag* 매개 변수의 이스케이프 문자에 대한 기호를 실제 이스케이프 문자로 변환합니다. FALSE는 변환을 수행하지 않습니다. 기본값은 FALSE입니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

XML 태그 쌍은 지정된 버퍼에서 텍스트 실행의 시작과 끝을 나타내는 명명된 열기 및 닫는 태그로 구성됩니다. *strBuffer* 매개 변수는 버퍼를 지정하고 *lpszTag* 매개 변수는 XML 태그의 이름을 지정합니다.

다음 표의 기호를 사용하여 지정된 버퍼에서 이스케이프 문자 집합을 인코딩합니다. *strTag* 매개 변수의 기호를 실제 이스케이프 문자로 변환하려면 *isCharsList* 매개 변수에 대해 TRUE를 지정합니다. 다음 표에서는 [_T()](../../c-runtime-library/data-type-mappings.md) 매크로를 사용하여 기호 및 이스케이프 문자 문자열을 지정합니다.

|기호|이스케이프 문자|
|------------|----------------------|
|_T("\t")\\|_T("\t")|
|_T("n")\\|_T("\n")|
|_T("\r")\\|_T("\r")|
|_T("\b")\\|_T("\b")|
|_T("LT")|_T("\<")|
|_T("GT")|_T(">")|
|_T("AMP")|_T("&")|

## <a name="afx_global_datagetcolor"></a><a name="getcolor"></a>AFX_GLOBAL_DATA::겟컬러

지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>매개 변수

*n컬러*<br/>
【인】 색상이 검색되는 사용자 인터페이스 요소를 지정하는 값입니다. 유효한 값 목록은 [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) 메서드의 *nIndex* 매개 변수를 참조하십시오.

### <a name="return-value"></a>Return Value

지정된 사용자 인터페이스 요소의 RGB 색상 값입니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="remarks"></a>설명

*nColor* 매개 변수가 범위를 벗어난 경우 반환 값은 0입니다. 0도 유효한 RGB 값이므로 이 메서드를 사용하여 현재 운영 체제에서 시스템 색상을 지원하는지 여부를 확인할 수 없습니다. 대신 색상이 지원되지 않는 경우 NULL을 반환하는 [GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush) 메서드를 사용합니다.

## <a name="afx_global_datagetdirect2dfactory"></a><a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA:::GetDirect2d팩토리

전역 데이터에 저장된 ID2D1Factory 인터페이스에 대한 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>Return Value

팩터리 생성이 성공하는 경우 ID2D1Factory 인터페이스에 대한 포인터 또는 생성이 실패하거나 현재 운영 체제에 D2D 지원이 없는 경우 NULL입니다.

## <a name="afx_global_datagethandcursor"></a><a name="gethandcursor"></a>AFX_GLOBAL_DATA:::겟핸드커서

손과 유사하고 식별자가 IDC_HAND 미리 정의된 커서를 검색합니다.

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>Return Value

손 커서의 손잡이입니다.

## <a name="afx_global_datagetnonclientmetrics"></a><a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA::GetNonClientMetrics

최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>매개 변수

*정보*<br/>
【인, 아웃】 최소화되지 않은 창의 비클라이언트 영역과 관련된 확장 가능한 메트릭을 포함하는 [비CLIENTMETRICS](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw) 구조입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="afx_global_datagettextheight"></a><a name="gettextheight"></a>AFX_GLOBAL_DATA:::GetTextHeight

현재 글꼴에서 텍스트 문자의 높이를 검색합니다.

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>매개 변수

*b호르츠 (주)*<br/>
【인】 TRUE 텍스트가 가로로 실행될 때 문자의 높이를 검색합니다. FALSE 텍스트를 세로로 실행하는 경우 문자의 높이를 검색합니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>Return Value

어센더에서 디센더로 측정되는 현재 글꼴의 높이입니다.

## <a name="afx_global_datagetwicfactory"></a><a name="getwicfactory"></a>AFX_GLOBAL_DATA:::GetWIC팩토리

전역 데이터에 저장된 IWICImagingFactory 인터페이스에 대한 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>Return Value

팩터리 생성이 성공하는 경우 IWICImagingFactory 인터페이스에 대한 포인터 또는 생성이 실패하거나 현재 운영 시스템에 WIC 지원이 없는 경우 NULL입니다.

## <a name="afx_global_datagetwritefactory"></a><a name="getwritefactory"></a>AFX_GLOBAL_DATA::GetWrite팩토리

전역 데이터에 저장된 IDWriteFactory 인터페이스에 대한 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>Return Value

팩터리 생성이 성공하면 IDWriteFactory 인터페이스에 대한 포인터 또는 생성이 실패하거나 현재 운영 체제에 DirectWrite 지원이 없는 경우 NULL입니다.

## <a name="afx_global_datainitd2d"></a><a name="initd2d"></a>AFX_GLOBAL_DATA:::InitD2D

D2D, DirectWrite 및 WIC 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>매개 변수

*d2d팩토리타입*<br/>
D2D 팩터리의 스레딩 모델과 생성되는 리소스입니다.

*쓰기팩토리타입*<br/>
write 팩터리 개체를 공유하거나 격리할지 여부를 지정하는 값입니다.

### <a name="return-value"></a>Return Value

공장이 intilalizrd, FALSE 인 경우 TRUE를 반환 - 그렇지 않으면

## <a name="afx_global_datais32biticons"></a><a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32BitIcons

미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>Return Value

TRUE 미리 정의된 32비트 아이콘이 지원되는 경우 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 메서드는 프레임 워크 32 비트 내장 아이콘을 지원 하는 경우 TRUE를 반환 하 고 운영 체제 픽셀 당 16 비트 이상을 지원 하는 경우, 그리고 이미지 높은 대비에 표시 되지 않는 경우.

## <a name="afx_global_dataisaccessibilitysupport"></a><a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA:::접근성 지원

Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>Return Value

내게 필요한 옵션 지원이 활성화된 경우 TRUE; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

Microsoft 활성 접근성은 응용 프로그램에 액세스할 수 있도록 하기 위한 이전 솔루션이었습니다. Microsoft UI 자동화는 Microsoft Windows의 새로운 내게 필요한 옵션 모델이며 보조 기술 제품 및 자동화된 테스트 도구의 요구 사항을 해결하기 위한 것입니다.

[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport) 메서드를 사용하여 활성 접근성 지원을 사용하거나 사용하지 않도록 설정합니다.

## <a name="afx_global_dataisd2dinitialized"></a><a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2D초기화

D2D초기화 여부 결정

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>Return Value

D2D가 초기화된 경우 TRUE; 그렇지 않으면 거짓.

## <a name="afx_global_dataisdwmcompositionenabled"></a><a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA::IsDwm컴컴포지션 사용 가능

Windows [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) 메서드를 호출하는 간단한 방법을 제공합니다.

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>Return Value

TRUE [데스크톱 창](/windows/win32/dwm/dwm-overview) 관리자(DWM) 컴포지션이 활성화된 경우 그렇지 않으면 false입니다.

## <a name="afx_global_dataishighcontrastmode"></a><a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA::이하이콘트라스트모드

이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.

```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>Return Value

TRUE 이미지가 현재 흑백 고대비 모드로 표시되는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

검은색 고대비 모드에서는 라이트를 향한 가장자리가 흰색이고 배경은 검은색입니다. 흰색 고대비 모드에서는 라이트를 향한 가장자리가 검은색이고 배경이 흰색입니다.

## <a name="afx_global_dataiswindowslayersupportavailable"></a><a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA:::IsWindows레이어지원 가능

운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>Return Value

계층화된 창이 지원되는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

계층화된 창이 지원되는 경우 *스마트 도킹* 마커는 계층화된 창을 사용합니다.

## <a name="afx_global_datam_busebuiltin32biticons"></a><a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA:m_bUseBuiltIn32BitIcons

프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>설명

TRUE는 프레임워크에서 32비트 색상 아이콘을 사용하도록 지정합니다. FALSE는 낮은 해상도 아이콘을 지정합니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 TRUE로 초기화합니다.

이 멤버는 응용 프로그램 시작 시 설정해야 합니다.

## <a name="afx_global_datam_busesystemfont"></a><a name="m_busesystemfont"></a>AFX_GLOBAL_DATA:m_bUseSystemFont

시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>설명

TRUE는 시스템 글꼴을 사용하도록 지정합니다. 그렇지 않으면 false입니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 FALSE로 초기화합니다.

이 멤버를 테스트하는 것만이 프레임워크에서 사용할 글꼴을 결정하는 유일한 방법은 아닙니다. 또한 `AFX_GLOBAL_DATA::UpdateFonts` 기본 및 대체 글꼴을 테스트하여 메뉴, 도구 모음 및 리본에 적용할 수 있는 시각적 스타일을 결정합니다.

## <a name="afx_global_datam_hcurhand"></a><a name="m_hcurhand"></a>AFX_GLOBAL_DATA:m_hcurHand

손 모양 커서에 대한 핸들을 저장합니다.

```
HCURSOR m_hcurHand;
```

## <a name="afx_global_datam_hcurstretch"></a><a name="m_hcurstretch"></a>AFX_GLOBAL_DATA:m_hcurStretch

가로 늘이기 커서에 대한 핸들을 저장합니다.

```
HCURSOR m_hcurStretch;
```

## <a name="afx_global_datam_hcurstretchvert"></a><a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA:m_hcurStretchVert

세로 늘이기 커서에 대한 핸들을 저장합니다.

```
HCURSOR m_hcurStretchVert;
```

## <a name="afx_global_datam_hicontool"></a><a name="m_hicontool"></a>AFX_GLOBAL_DATA:m_hiconTool

도구 아이콘에 대한 핸들을 저장합니다.

```
HICON m_hiconTool;
```

## <a name="afx_global_datam_nautohidetoolbarmargin"></a><a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA:m_nAutoHideToolBarMargin

가장 왼쪽자동숨기기 도구 모음에서 도크 막대의 왼쪽으로 오프셋을 지정합니다.

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>설명

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 4픽셀로 초기화합니다.

## <a name="afx_global_datam_nautohidetoolbarspacing"></a><a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA:m_nAutoHideToolBarSpacing

자동 숨기기 도구 모음 사이의 간격을 지정합니다.

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>설명

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 14픽셀로 초기화합니다.

## <a name="afx_global_datam_ndragframethicknessdock"></a><a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA:m_nDragFrameThicknessDock

도킹된 상태를 나타내는 데 사용되는 드래그 프레임의 두께를 지정합니다.

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>설명

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 3픽셀로 초기화합니다.

## <a name="afx_global_datam_ndragframethicknessfloat"></a><a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA:m_nDragFrameThicknessFloat

부동 상태를 나타내는 데 사용되는 드래그 프레임의 두께를 지정합니다.

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>설명

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자는 이 멤버를 4픽셀로 초기화합니다.

## <a name="afx_global_dataonsettingchange"></a><a name="onsettingchange"></a>AFX_GLOBAL_DATA::온세팅변경

데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.

```cpp
void OnSettingChange();
```

### <a name="remarks"></a>설명

이 메서드는 프레임워크 변수를 사용자 바탕 화면의 특정 특성 의 상태로 설정합니다. 이 메서드는 메뉴 애니메이션, 메뉴 페이드 및 작업 표시줄 자동 숨기기 피처의 현재 상태를 검색합니다.

## <a name="afx_global_dataregisterwindowclass"></a><a name="registerwindowclass"></a>AFX_GLOBAL_DATA:::레지스터윈도우클래스

지정된 MFC 창 클래스를 등록합니다.

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>매개 변수

*lpsz클래스네임 프리픽스*<br/>
【인】 등록할 창 클래스의 이름입니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 등록된 클래스의 정규화된 이름입니다. 그렇지 않으면 [리소스 예외입니다.](exception-processing.md#afxthrowresourceexception)

### <a name="remarks"></a>설명

반환 값은 *lpszClassNamePrefix* 매개 변수 문자열의 콜론 구분 목록 및 현재 응용 프로그램 인스턴스의 핸들의 hexadecimal 텍스트 표현입니다. 식별자가 IDC_ARROW 화살표 커서인 응용 프로그램 커서입니다. 및 배경 브러시. MFC 창 클래스 등록에 대한 자세한 내용은 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)를 참조하십시오.

## <a name="afx_global_dataresume"></a><a name="resume"></a>AFX_GLOBAL_DATA::이력서

Windows 테마 및 비주얼 스타일을 지원하는 메서드에 액세스하는 내부 함수 포인터를 다시 초기화합니다.

```
BOOL Resume();
```

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다. 디버그 모드에서이 메서드는 이 메서드가 실패 하면 어설션합니다.

### <a name="remarks"></a>설명

이 메서드는 프레임워크가 [WM_POWERBROADCAST](/windows/win32/Power/wm-powerbroadcast) 메시지를 수신할 때 호출됩니다.

## <a name="afx_global_datasetlayeredattrib"></a><a name="setlayeredattrib"></a>AFX_GLOBAL_DATA:::세트레이어드아트리브

Windows [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) 메서드를 호출하는 간단한 방법을 제공합니다.

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 계층화된 창에 핸들을 보입니다.

*crKey*<br/>
【인】 [데스크톱 창 관리자가](/windows/win32/dwm/dwm-overview) 계층화된 창을 구성하는 데 사용하는 투명도 색상 키입니다.

*b알파 (주)*<br/>
【인】 계층화된 창의 불투명도를 설명하는 데 사용되는 알파 값입니다.

*dwFlags*<br/>
【인】 사용할 메서드 매개 변수를 지정하는 플래그의 비트 조합(OR)입니다. *crKey* 매개 변수를 투명도 색상으로 사용할 LWA_COLORKEY 지정합니다. *bAlpha* 매개 변수를 사용하여 계층화된 창의 불투명도를 결정할 LWA_ALPHA 지정합니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="afx_global_datasetmenufont"></a><a name="setmenufont"></a>AFX_GLOBAL_DATA:::세트메뉴폰트

지정된 논리 글꼴을 만듭니다.

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*lpLogFont*<br/>
【인】 글꼴의 특성을 포함하는 구조체에 대한 포인터입니다.

*b호르츠 (주)*<br/>
【인】 TRUE 텍스트를 가로로 실행하도록 지정합니다. FALSE텍스트를 세로로 실행하도록 지정합니다.

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다. 디버그 모드에서이 메서드는 이 메서드가 실패 하면 어설션합니다.

### <a name="remarks"></a>설명

이 메서드는 가로 일반 글꼴, 밑줄이 그어진 글꼴 및 기본 메뉴 항목에 사용되는 굵은 글꼴을 만듭니다. 이 메서드는 선택적으로 일반 세로 글꼴을 만듭니다. 논리 글꼴에 대한 자세한 내용은 [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect)를 참조하십시오.

## <a name="afx_global_dataupdatefonts"></a><a name="updatefonts"></a>AFX_GLOBAL_DATA::업데이트글꼴

프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.

```cpp
void UpdateFonts();
```

### <a name="remarks"></a>설명

논리 글꼴에 대한 자세한 `CFont::CreateFontIndirect`내용은 를 참조하십시오.

## <a name="afx_global_dataupdatesyscolors"></a><a name="updatesyscolors"></a>AFX_GLOBAL_DATA::업데이트시스컬러

프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.

```cpp
void UpdateSysColors();
```

## <a name="afx_global_databiswindows7"></a><a name="biswindows7"></a>AFX_GLOBAL_DATA::비스윈도우7

응용 프로그램이 Windows 7 이상에서 실행되고 있는지 여부를 나타냅니다.

```
BOOL bIsWindows7;
```

## <a name="afx_global_dataclractivecaptiongradient"></a><a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA::clrActive캡션그라데이션

활성 캡션의 그라데이션 색상을 지정합니다. 도킹 창에 일반적으로 사용됩니다.

```
COLORREF clrActiveCaptionGradient;
```

## <a name="afx_global_dataclrinactivecaptiongradient"></a><a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA::비활성캡션그라데이션

비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="afx_global_datagetitaskbarlist"></a><a name="getitaskbarlist"></a>AFX_GLOBAL_DATA:::GetITaskbarList

`ITaskBarList` 인터페이스에 대한 포인터를 전역 데이터에 만들고 저장합니다.

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>Return Value

작업 표시줄 `ITaskbarList` 목록 개체를 만드는 데 성공하는 경우 인터페이스에 대한 포인터입니다. 생성에 실패하거나 현재 운영 체제가 Windows 7보다 작으면 NULL입니다.

## <a name="afx_global_datagetitaskbarlist3"></a><a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA::::GetITaskbarList3

`ITaskBarList3` 인터페이스에 대한 포인터를 전역 데이터에 만들고 저장합니다.

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>Return Value

작업 표시줄 `ITaskbarList3` 목록 개체를 만드는 데 성공하는 경우 인터페이스에 대한 포인터입니다. 생성에 실패하거나 현재 운영 체제가 Windows 7보다 작으면 NULL입니다.

## <a name="afx_global_datagetshellautohidebars"></a><a name="getshellautohidebars"></a>AFX_GLOBAL_DATA::겟쉘오토하이드바

셸 자동 숨기기 막대의 위치를 결정합니다.

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>Return Value

자동 숨기기 막대의 위치를 지정하는 인코딩된 플래그가 있는 정수 값입니다. AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT 다음과 같은 값을 결합할 수 있습니다.

## <a name="afx_global_datareleasetaskbarrefs"></a><a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA:::릴리스태스크바레프

`GetITaskbarList` 및 `GetITaskbarList3` 메서드를 통해 얻은 인터페이스를 해제합니다.

```cpp
void ReleaseTaskBarRefs();
```

## <a name="afx_global_datashellcreateitemfromparsingname"></a><a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA:::쉘만들기항목에서분리이름

구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>매개 변수

*pszPath*<br/>
【인】 표시 이름에 대한 포인터입니다.

*Pbc*<br/>
구문 분석 작업을 제어하는 바인딩 컨텍스트에 대한 포인터입니다.

*riid*<br/>
인터페이스 ID에 대한 참조입니다.

*ppv*<br/>
【아웃】 이 함수가 반환되면 riid에서 요청된 인터페이스 포인터가 *포함됩니다.* 일반적으로 `IShellItem` 또는 . `IShellItem2`

### <a name="return-value"></a>Return Value

성공하면 S_OK 반환합니다. 그렇지 않으면 오류 값입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../hierarchy-chart.md)<br/>
[구조체, 스타일, 콜백 및 메시지 맵](structures-styles-callbacks-and-message-maps.md)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[파트 및 상태](/windows/win32/controls/parts-and-states)<br/>
[nFormat](cdc-class.md#drawtext)<br/>
[메서드의](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[바탕 화면 창 관리자](/windows/win32/dwm/dwm-overview)<br/>
[DWM 컴퍼지션 설정 및 제어](/windows/win32/dwm/composition-ovw)<br/>
[UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[겟시스컬러 기능](/windows/win32/api/winuser/nf-winuser-getsyscolor)<br/>
[겟시스컬러브러쉬](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[비클라이언트메트릭 구조](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)
