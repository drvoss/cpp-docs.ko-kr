---
title: CMFCOutlookBarTabCtrl Class
ms.date: 10/18/2018
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
ms.openlocfilehash: 9c5d7d5135c3b207bbf113970deb8cbeb186bcca
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749569"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Microsoft Outlook의 **탐색 창** 과 시각적으로 유사한 탭 컨트롤입니다.
자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

## <a name="syntax"></a>구문

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|기본 생성자입니다.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCOutlook바탭트rl::추가 제어](#addcontrol)|Outlook 막대에 새 탭으로 Windows 컨트롤을 추가합니다.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|사용자가 탭의 이름을 바꿉니다 편집 상자의 크기를 결정 하기 위해 프레임 워크에 의해 호출 됩니다.(재정의.) `CMFCBaseTabCtrl::CalcRectEdit`|
|[CMFCOutlookBarTabCtrl::수표시더 적은 페이지 버튼](#canshowfewerpagebuttons)|작업 크기를 조정하는 동안 프레임워크에서 호출하여 현재 표시되는 것보다 적은 수의 Outlook 막대 탭 단추를 표시할 수 있는지 확인합니다.|
|[CMFCOutlookBarTabctrl::캔쇼더페이지버튼](#canshowmorepagebuttons)|크기 조정 작업 중에 프레임워크에서 호출하여 현재 표시되는 것보다 더 많은 Outlook 막대 탭 단추를 표시할 수 있는지 확인합니다.|
|[CMFC아웃바탭트rl::만들기](#create)|Outlook 막대 탭 컨트롤을 만듭니다.|
|`CMFCOutlookBarTabCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCOutlookBarTabCtrl::인에이블 애니메이션](#enableanimation)|활성 탭 간 전환 중에 발생하는 애니메이션이 활성화되어 있는지 여부를 지정합니다.|
|[CMFC아웃아웃바탭트rl::인에이블인플레이스편집](#enableinplaceedit)|사용자가 Outlook 막대의 탭 단추에서 텍스트 레이블을 수정할 수 있는지 여부를 지정합니다. [(CMFCBaseTabCtrl 재정의::인에이블인플레이스 편집.)](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit)|
|[CMFCOutlookBarTabCtrl:::인에이블스크롤 버튼](#enablescrollbuttons)|사용자가 Outlook 막대 창에서 단추를 스크롤할 수 있도록 하는 단추를 사용하도록 설정 하려면 프레임 워크에서 호출 합니다.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|지정된 지점에 포함된 창을 확인합니다. [(CMFCBaseTabCtrl 재정의::FindTargetWnd.)](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd)|
|[CMFC아웃바탭트rl::겟보더사이즈](#getbordersize)|Outlook 탭 컨트롤의 테두리 크기를 반환합니다.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|탭 컨트롤의 탭 영역 크기 및 위치를 검색합니다. [(CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea)재정의.)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCOutlookBarTabCtrl:::보이지 않는 페이지 버튼](#getvisiblepagebuttons)||
|[CMFC아웃바탭트rl::이애니메이션](#isanimation)|활성 탭 간 전환 중에 발생하는 애니메이션이 활성화되어 있는지 여부를 결정합니다.|
|[CMFC아웃바탭트rl::IsMode2003](#ismode2003)|Outlook 막대 탭 컨트롤이 Microsoft Outlook 2003을 에뮬레이트하는 모드에 있는지 확인합니다.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|지점이 탭 영역 내에 있는지 여부를 확인합니다. [(CMFCBaseTabCtrl 재정의::IsPtInTabarea.)](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|탭이 분리 가능한지 여부를 나타냅니다. [(CMFCBaseTabCtrl 재정의::이스탭데타카블.)](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|탭이 삽입되거나 제거될 때 프레임워크에서 호출됩니다. ( `CMFCBaseTabCtrl::OnChangeTabs`을 재정의합니다.)|
|[CMFCOutlookBarTabCtrl:::에더적은 페이지 버튼](#onshowfewerpagebuttons)|표시되는 탭 페이지 단추 수를 줄이기 위해 프레임워크에서 호출합니다.|
|[CMFCOutlookBarTabctrl::에더페이지버튼](#onshowmorepagebuttons)|표시되는 탭 페이지 단추 수를 늘리기 위해 프레임워크에서 호출합니다.|
|[CMFC아웃아웃바탭트rl::온쇼옵션](#onshowoptions)|탐색 창 옵션 대화 상자를 **표시합니다.**|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|탭 컨트롤의 내부 레이아웃을 다시 계산합니다. [(CMFCBaseTabCtrl 재정의::RecalcLayout.)](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout)|
|[CMFC아웃바탭트rl::설정액티브탭](#setactivetab)|활성 탭 을 [설정합니다(CMFCBaseTabCtrl 재정의::SetActiveTab.)](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab)|
|[CMFC아웃바탭트rl:::세트보더사이즈](#setbordersize)|Outlook 탭 컨트롤의 테두리 크기를 설정합니다.|
|[CMFCOutlook바탭트rl:::설정 단추텍스트정렬](#setpagebuttontextalign)|Outlook 막대의 탭 단추에서 텍스트 레이블의 정렬을 설정합니다.|
|[CMFC아웃아웃바탭트rl:::세트툴바이미지리스트](#settoolbarimagelist)|Outlook 2003 모드에서 Outlook 막대 하단에 표시되는 아이콘이 포함된 비트맵을 [설정합니다(CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)참조).|
|[CMFCOutlookBarTabCtrl:::가시적 페이지 버튼 설정](#setvisiblepagebuttons)||

## <a name="remarks"></a>설명

도킹 지원이 있는 Outlook 막대를 만들려면 개체를 `CMFCOutlookBar` 사용하여 Outlook 막대 탭 컨트롤을 호스팅합니다. 자세한 내용은 [CMFCOutlookBar 클래스를](../../mfc/reference/cmfcoutlookbar-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCOutlookBarTabCtrl` 초기화하고 클래스에서 다양한 `CMFCOutlookBarTabCtrl` 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 Outlook 막대의 탭 페이지 단추에서 텍스트 레이블을 설치하도록 설정하고, 애니메이션을 활성화하고, 사용자가 Outlook 막대 창의 단추를 스크롤할 수 있도록 하는 스크롤 핸들을 활성화하고, Outlook 탭 컨트롤의 테두리 크기를 설정하고, Outlook 막대의 탭 단추에서 텍스트 레이블의 정렬을 설정하는 방법을 보여 주며, 이 예제에서는 텍스트 레이블의 위치를 설정하는 방법을 보여 주며, 사용자가 Outlook 막대의 단추를 스크롤할 수 있도록 합니다. 이 코드 조각은 Outlook [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxoutlookbarttrl.h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a>CMFCOutlook바탭트rl::추가 제어

Outlook 막대에 새 탭으로 Windows 컨트롤을 추가합니다.

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
【인】 추가할 컨트롤에 대한 포인터입니다.

*lpszName*<br/>
【인】 탭 이름을 지정합니다.

*bDetachable*<br/>
【인】 TRUE이면 페이지가 분리 가능한 페이지로 만들어집니다.

*n이미지 ID*<br/>
【인】 이미지가 새 탭에 표시될 내부 이미지 목록의 이미지 인덱스입니다.

*dw컨트롤바스타일*<br/>
【인】 래핑된 도킹 창에 대한 AFX_ CBRS_* 스타일을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 컨트롤을 Outlook 막대의 새 페이지로 추가합니다.

이 함수는 내부적으로 [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).

*bDetachable을* TRUE로 설정하면 `AddControl` 내부적으로 `CDockablePaneAdapter` 개체를 만들고 추가된 컨트롤을 래핑합니다. 탭된 창의 런타임 클래스를 런타임 클래스의 런타임 클래스와 부동 프레임의 `CMFCOutlookBar` `CMultiPaneFrameWnd`런타임 클래스로 자동으로 설정합니다.

### <a name="example"></a>예제

다음 예제에서는 `AddControl` `CMFCOutlookBarTabCtrl` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 Outlook [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::수표시더 적은 페이지 버튼

크기 조정 작업 중에 프레임워크에서 호출하여 현재 표시되는 것보다 적은 수의 Outlook 막대 탭 단추를 표시할 수 있는지 확인합니다.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Return Value

두 개 이상의 단추가 있는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

Outlook 막대 탭 컨트롤은 사용 가능한 공간에 따라 디스플레이에서 탭을 동적으로 추가하거나 제거합니다. 이 메서드는 해당 프로세스를 지원하기 위해 프레임워크에서 사용됩니다.

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabctrl::캔쇼더페이지버튼

크기 조정 작업 중에 프레임워크에서 호출하여 현재 표시되는 것보다 더 많은 Outlook 막대 탭 단추를 표시할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Return Value

현재 표시되지 않는 단추가 있는 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

Outlook 막대 탭 컨트롤은 사용 가능한 공간에 따라 디스플레이에서 탭을 동적으로 추가하거나 제거합니다. 이 메서드는 해당 프로세스를 지원하기 위해 프레임워크에서 사용됩니다.

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a>CMFC아웃바탭트rl::만들기

Outlook 막대 탭 컨트롤을 만듭니다.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
【인】 초기 크기와 위치를 픽셀 단위로 지정합니다.

*pParentWnd*<br/>
【인】 상위 창을 가리킵니다. NULL이 아니어야 합니다.

*nID*<br/>
【인】 컨트롤 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤이 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

일반적으로 [CMFCOutlookBar 클래스가](../../mfc/reference/cmfcoutlookbar-class.md) 프로세스의 WM_CREATE 메시지를 제어할 때 Outlook 막대 탭 컨트롤이 만들어집니다.

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a>CMFCOutlookBarTabCtrl::인에이블 애니메이션

활성 탭 간 전환 중에 발생하는 애니메이션이 활성화되어 있는지 여부를 지정합니다.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 애니메이션을 활성화할지 비활성화할지 여부를 지정합니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 애니메이션을 활성화 및 비활성화합니다. 사용자가 탭 페이지를 열면 애니메이션이 활성화된 경우 페이지의 캡션이 위 또는 아래로 슬라이드됩니다. 애니메이션을 사용하지 않도록 설정하면 페이지가 즉시 활성화됩니다.

기본적으로 애니메이션이 활성화됩니다.

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a>CMFC아웃아웃바탭트rl::인에이블인플레이스편집

사용자가 Outlook 막대의 탭 페이지 단추에서 텍스트 레이블을 수정할 수 있는지 여부를 지정합니다.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
TRUE인 경우 텍스트 레이블의 현재 편집을 사용하도록 설정합니다. FALSE인 경우 현재 작업 중 편집을 사용하지 않도록 설정합니다.

### <a name="remarks"></a>설명

탭 페이지 단추에서 텍스트 레이블의 현재 편집을 활성화하거나 사용하지 않도록 하려면 이 함수를 호출합니다. 기본적으로 현재 위치 편집은 사용할 수 없습니다.

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl:::인에이블스크롤 버튼

사용자가 Outlook 막대 창에서 단추를 스크롤할 수 있도록 하는 스크롤 핸들을 활성화하기 위해 프레임워크에서 호출합니다.

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 스크롤 단추가 표시되는지 여부를 결정합니다.

*비스업*<br/>
【인】 위쪽 스크롤 막대가 표시되는지 여부를 결정합니다.

*비스다운*<br/>
【인】 아래쪽 스크롤 막대가 표시되는지 여부를 결정합니다.

### <a name="remarks"></a>설명

스크롤 단추를 표시할 수 있습니다. 활성 탭이 스크롤 단추를 복원하기 위해 변경될 때 이 메서드는 프레임워크에서 호출됩니다.

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a>CMFC아웃바탭트rl::겟보더사이즈

Outlook 탭 컨트롤의 테두리 크기를 반환합니다.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Return Value

테두리 크기(픽셀)입니다.

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl:::보이지 않는 페이지 버튼

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a>CMFC아웃바탭트rl::이애니메이션

활성 탭 간 전환 중에 발생하는 애니메이션이 활성화되어 있는지 여부를 지정합니다.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Return Value

애니메이션이 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CMFCOutlookBarTabCtrl::인에이블애니메이션](#enableanimation) 함수를 호출하여 애니메이션을 사용 또는 비활성화합니다.

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a>CMFC아웃바탭트rl::IsMode2003

Outlook 막대 탭 컨트롤이 Microsoft Outlook 2003을 에뮬레이트하는 모드에 있는지 여부를 확인합니다.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Return Value

Outlook 막대 탭 컨트롤이 Outlook 2003 모드에 있는 경우 TRUE; 그렇지 않으면 거짓;

### <a name="remarks"></a>설명

이 값은 [CMFCOutlookBar::SetMode2003에](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003)의해 설정됩니다.

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl:::에더적은 페이지 버튼

표시되는 탭 페이지 단추 수를 줄이기 위해 프레임워크에서 호출합니다.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>설명

이 메서드는 컨트롤크기를 조정할 때 표시되는 페이지 탭 단추수를 조정합니다.

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabctrl::에더페이지버튼

표시되는 탭 페이지 단추 수를 늘리기 위해 프레임워크에서 호출합니다.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>설명

이 메서드는 컨트롤 크기를 조정할 때 표시되는 탭 페이지 단추 수를 조정합니다.

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a>CMFC아웃아웃바탭트rl::온쇼옵션

탐색 창 옵션 대화 상자를 **표시합니다.**

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>설명

**탐색 창 옵션** 대화 상자를 사용하면 표시할 탭 페이지 단추와 표시되는 순서를 선택할 수 있습니다.

사용자가 컨트롤의 사용자 지정 메뉴에서 **탐색 창 옵션** 메뉴 항목을 선택할 때 이 메서드는 프레임워크에서 호출됩니다.

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a>CMFC아웃바탭트rl::설정액티브탭

활성 탭을 설정합니다. 활성 탭은 열려 있는 탭이며 내용이 표시됩니다.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>매개 변수

*iTab*<br/>
【인】 열 수 있는 탭의 0기반 인덱스입니다.

### <a name="return-value"></a>Return Value

지정된 탭이 성공적으로 열려 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

활성 탭을 설정하는 시각적 효과는 애니메이션을 활성화했는지 여부에 따라 달라집니다. 자세한 내용은 [CMFCOutlookBarTabCtrl::인에이블애니메이션](#enableanimation)을 참조하십시오.

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a>CMFC아웃바탭트rl:::세트보더사이즈

Outlook 탭 컨트롤의 테두리 크기를 설정합니다.

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>매개 변수

*n보더사이즈*<br/>
【인】 새 테두리 크기를 픽셀단위로 지정합니다.

### <a name="remarks"></a>설명

새 테두리 크기를 설정하고 outlook 창 레이아웃을 다시 계산합니다.

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a>CMFCOutlook바탭트rl:::설정 단추텍스트정렬

Outlook 막대의 탭 단추에서 텍스트 레이블의 정렬을 설정합니다.

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>매개 변수

*uiAlign*<br/>
【인】 텍스트 정렬을 지정합니다.

*bRedraw*<br/>
【인】 TRUE이면 Outlook 창이 다시 그려집니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 페이지 단추의 텍스트 정렬을 변경합니다.

*uiAlign은* 다음 값 중 하나일 수 있습니다.

|상수|의미|
|--------------|-------------|
|TA_LEFT|왼쪽 맞춤|
|TA_CENTER|중심 맞춤|
|TA_RIGHT|오른쪽 정렬|

기본값은 TA_CENTER.

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a>CMFC아웃아웃바탭트rl:::세트툴바이미지리스트

Outlook 2003 모드에서 Outlook 막대 아래쪽에 표시되는 아이콘이 포함된 비트맵을 설정합니다.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
【인】 로드할 이미지의 리소스 ID를 지정합니다.

*Cx*<br/>
【인】 이미지 목록에서 이미지 너비를 픽셀 단위로 지정합니다.

*clrTransp*<br/>
【인】 투명 색상을 지정하는 RGB 값입니다.

### <a name="return-value"></a>Return Value

성공하면 TRUE를 반환합니다. 그렇지 않으면 FALSE를 반환합니다.

### <a name="remarks"></a>설명

이 기능을 사용하여 이미지가 Microsoft Office 2003 모드의 도구 모음 단추에 표시되는 이미지 목록을 첨부합니다. 이미지 인덱스는 페이지 인덱스에 해당해야 합니다.

이 메서드는 Microsoft Office 2003 모드에서 호출되지 않아야 합니다. 자세한 내용은 [CMFCOutlookBar 클래스를](../../mfc/reference/cmfcoutlookbar-class.md)참조하십시오.

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl:::가시적 페이지 버튼 설정

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>매개 변수

【인】 *n인가 페이지 단추*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[CMFC아웃아웃바 클래스](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFC아웃아웃바파네 클래스](../../mfc/reference/cmfcoutlookbarpane-class.md)
