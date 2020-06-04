---
title: CMFC아웃아웃바파네 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
ms.openlocfilehash: 97c7edde26bdf13e899d823dcf88d143068d86a4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749614"
---
# <a name="cmfcoutlookbarpane-class"></a>CMFC아웃아웃바파네 클래스

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

Outlook [막대(CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)클래스)에 삽입할 수 있는 [CMFCToolBar 클래스에서](../../mfc/reference/cmfctoolbar-class.md) 파생된 컨트롤입니다. Outlook 표시줄 창에 큰 단추의 열이 포함되어 있습니다. 단추 목록이 창보다 크면 위 아래로 스크롤할 수 있습니다. 사용자가 Outlook 표시줄 창을 Outlook 표시줄에서 분리하면 기본 프레임 창에서 이동하거나 도킹할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|기본 생성자입니다.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC아웃아웃바파인::추가 버튼](#addbutton)|Outlook 막대 창에 단추를 추가합니다.|
|[CMFC아웃아웃바파네::수 첨부](#canbeattached)|창을 다른 창 또는 프레임 창에 도킹할 수 있는지 여부를 결정합니다. [(재정비: :캔비첨부.)](../../mfc/reference/cbasepane-class.md#canbeattached)|
|`CMFCOutlookBarPane::CanBeRestored`|사용자 지정 후 시스템에서 도구 모음을 원래 상태로 복원할 수 있는지 여부를 결정합니다. [(CMFCToolBar 재정의::캔복원.)](../../mfc/reference/cmfctoolbar-class.md#canberestored)|
|[CMFC아웃아웃바파인::클리어올](#clearall)|Outlook 막대 창의 이미지에서 사용하는 리소스를 해제합니다.|
|[CMFC아웃아웃바파네::만들기](#create)|Outlook 막대 창을 만듭니다.|
|`CMFCOutlookBarPane::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCOutlookBarPane::Dock`|Outlook 막대 창을 도킹하는 프레임워크에서 호출됩니다. ( `CPane::Dock`을 재정의합니다.)|
|[CMFC아웃아웃바파인::인에이블페이지스크롤모드](#enablepagescrollmode)|Outlook 막대 창의 스크롤 화살표가 단추 목록을 페이지별로 또는 단추별로 진행할지 여부를 지정합니다.|
|[CMFC아웃아웃바파인::겟레귤러컬러](#getregularcolor)|Outlook 막대 창의 일반(선택되지 않은) 텍스트 색상을 반환합니다.|
|`CMFCOutlookBarPane::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC아웃아웃바파인::IsBackground 텍스처](#isbackgroundtexture)|Outlook 막대 창에 로드된 배경 이미지가 있는지 여부를 확인합니다.|
|`CMFCOutlookBarPane::IsChangeState`|부동 창이 도킹될 수 있는지 여부를 결정합니다. ( `CPane::IsChangeState`을 재정의합니다.)|
|[CMFC아웃아웃바파인::이스드드샤드하이라이트](#isdrawshadedhighlight)|단추를 강조 표시하고 배경 이미지가 표시될 때 단추 테두리가 그늘에 표시되는지 여부를 결정합니다.|
|`CMFCOutlookBarPane::OnBeforeFloat`|창이 부동하려고 할 때 프레임워크에서 호출됩니다. [(재정의 Cpane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFC아웃아웃바파인::제거버튼](#removebutton)|지정된 명령 ID가 있는 단추를 제거합니다.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|도구 모음의 원래 상태를 복원합니다. [(CMFCToolBar 재정의::복원원래](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate)상태.)|
|[CMFC아웃아웃바파인::세트백컬러](#setbackcolor)|배경색을 설정합니다.|
|[CMFC아웃아웃바파인:::세트백이미지](#setbackimage)|배경 이미지를 설정합니다.|
|[CMFC아웃아웃바파인::설정기본 상태](#setdefaultstate)|Outlook 막대 창을 원래 단추 집합으로 재설정합니다.|
|[CMFC아웃아웃바파인::세트엑스트라스페이스](#setextraspace)|Outlook 막대 창의 단추 주위에 사용되는 패딩 픽셀 수를 설정합니다.|
|[CMFC아웃아웃바파네::세트텍스트컬러](#settextcolor)|Outlook 막대 창에서 일반 텍스트와 강조 표시된 텍스트의 색상을 설정합니다.|
|[CMFC아웃아웃바파네::세트투명색상](#settransparentcolor)|Outlook 막대 창의 투명 색상을 설정합니다.|
|`CMFCOutlookBarPane::SmartUpdate`|Outlook 막대를 업데이트하는 데 내부적으로 사용됩니다. ( `CMFCToolBar::SmartUpdate`을 재정의합니다.)|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFC아웃아웃바파인::인에이블컨텍스트메뉴항목](#enablecontextmenuitems)|사용자 지정 모드로 표시되는 바로 가기 메뉴 항목을 지정합니다.|
|[CMFC아웃아웃바파인::모두 제거](#removeallbuttons)|Outlook 막대 창에서 모든 단추를 제거합니다. [(CMFCToolBar 재정의::제거모든 단추.)](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons)|

## <a name="remarks"></a>설명

Outlook 막대를 구현하는 방법에 대한 자세한 내용은 [CMFCOutlookBar 클래스를](../../mfc/reference/cmfcoutlookbar-class.md)참조하십시오.

Outlook 막대의 예는 OutlookDemo 샘플 프로젝트를 참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 클래스의 다양 한 `CMFCOutlookBarPane` 메서드를 사용 하는 방법을 보여 줍니다. 이 예제에서는 Outlook 막대 창을 만들고, 페이지 스크롤 모드를 활성화하고, 도킹을 활성화하고, Outlook 막대의 배경색을 설정하는 방법을 보여 주며, 이 코드 조각은 Outlook [다중 보기 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFC베이스툴바](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxoutlookbarpane.h

## <a name="cmfcoutlookbarpaneaddbutton"></a><a name="addbutton"></a>CMFC아웃아웃바파인::추가 버튼

Outlook 막대 창에 단추를 추가합니다.

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>매개 변수

*ui이미지*<br/>
【인】 비트맵의 리소스 식별자를 지정합니다.

*lpszLabel*<br/>
【인】 단추의 텍스트를 지정합니다.

*아이드커맨드*<br/>
【인】 단추 컨트롤의 ID를 지정합니다.

*아이 인서트*<br/>
【인】 단추를 삽입할 Outlook 막대 의 페이지에 0기준 인덱스를 지정합니다.

*uiLabel*<br/>
【인】 문자열 리소스 ID입니다.

*szBmp파일이름*<br/>
【인】 로드할 디스크 이미지 파일의 이름을 지정합니다.

*szLabel*<br/>
【인】 단추의 텍스트를 지정합니다.

*hBmp*<br/>
【인】 단추의 비트맵에 대한 핸들입니다.

*hIcon*<br/>
【인】 단추 아이콘의 핸들입니다.

### <a name="return-value"></a>Return Value

TRUE 단추를 성공적으로 추가한 경우 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 사용하여 Outlook 막대의 페이지에 새 단추를 삽입합니다. 단추의 이미지는 응용 프로그램 리소스 또는 디스크 파일에서 로드할 수 있습니다.

*uiPageID가* 지정한 페이지 ID가 -1이면 첫 페이지에 버튼이 삽입됩니다.

*iInsertAt에서* 지정한 인덱스가 -1이면 페이지 끝에 단추가 추가됩니다.

## <a name="cmfcoutlookbarpanecanbeattached"></a><a name="canbeattached"></a>CMFC아웃아웃바파네::수 첨부

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcoutlookbarpaneclearall"></a><a name="clearall"></a>CMFC아웃아웃바파인::클리어올

Outlook 막대 창의 이미지에서 사용하는 리소스를 해제합니다.

```cpp
void ClearAll();
```

### <a name="remarks"></a>설명

이 메서드는 [직접 CMFCToolBarImages::지우기](../../mfc/reference/cmfctoolbarimages-class.md#clear)호출 합니다.이 Outlook 막대 창에서 사용 되는 이미지에 호출 됩니다.

## <a name="cmfcoutlookbarpanecreate"></a><a name="create"></a>CMFC아웃아웃바파네::만들기

Outlook 막대 창을 만듭니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
【인】 Outlook 막대 창 컨트롤의 상위 창을 지정합니다. NULL이 아니어야 합니다.

*dwStyle*<br/>
【인】 창 스타일입니다.  창 스타일 목록은 창 [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*uiID*<br/>
【인】 컨트롤 ID입니다. 컨트롤의 상태를 저장하려면 고유해야 합니다.

*dw컨트롤바스타일*<br/>
【인】 Outlook 막대에서 분리될 때 Outlook 막대 창 컨트롤의 동작을 정의하는 특수 스타일을 지정합니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

개체를 `CMFCOutlookBarPane` 생성하려면 먼저 생성자 호출한 `Create`다음 Outlook 막대 창 컨트롤을 만들고 `CMFCOutlookBarPane` 개체에 연결합니다.

자세한 내용은 `dwControlBarStyle` [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)를 참조하십시오.

## <a name="cmfcoutlookbarpaneenablecontextmenuitems"></a><a name="enablecontextmenuitems"></a>CMFC아웃아웃바파인::인에이블컨텍스트메뉴항목

사용자 지정 모드로 표시되는 바로 가기 메뉴 항목을 지정합니다.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>매개 변수

*p 버튼*<br/>
【인】 사용자가 클릭한 도구 모음 단추에 대한 포인터입니다.

*강아지*<br/>
【인】 바로 가기 메뉴에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

바로 가기 메뉴가 표시되어야하는 경우 TRUE를 반환합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 메서드를 재정의하여 프레임워크가 사용자 지정 모드에서 표시되는 프레임워크 표준 바로 가기 메뉴를 수정합니다.

기본 구현은 사용자 지정 [모드(CMFCToolBar::IsCustomizeMode)를](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)검사하고 TRUE로 설정된 경우 **삭제를**제외한 모든 바로 가기 메뉴 항목을 사용하지 않도록 설정합니다. 그런 다음 입력 매개 변수를 `CMFCToolBar::EnableContextMenuItems`에 전달합니다.

> [!NOTE]
> *컨텍스트 메뉴는* 바로 가기 메뉴의 동의어입니다.

## <a name="cmfcoutlookbarpaneenablepagescrollmode"></a><a name="enablepagescrollmode"></a>CMFC아웃아웃바파인::인에이블페이지스크롤모드

Outlook 막대 창의 스크롤 화살표가 단추 페이지 별로 또는 단추별로 단추 목록을 진행할지 여부를 지정합니다.

```cpp
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>매개 변수

*b페이지스크롤*<br/>
【인】 TRUE이면 페이지 스크롤 모드를 사용하도록 설정합니다. FALSE인 경우 페이지 스크롤 모드를 사용하지 않도록 설정합니다.

## <a name="cmfcoutlookbarpanegetregularcolor"></a><a name="getregularcolor"></a>CMFC아웃아웃바파인::겟레귤러컬러

Outlook 막대 창의 일반 텍스트 색상(즉, 선택되지 않은) 텍스트 색상을 반환합니다.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Return Value

RGB 색상 값으로 현재 텍스트 색상입니다.

### <a name="remarks"></a>설명

[CMFCOutlookBarPane::SetTextColor를](#settextcolor) 사용하여 Outlook 막대의 현재(일반 및 선택된) 텍스트 색상을 설정합니다. COLOR_WINDOW 인덱스를 사용 하 여 [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) 함수를 호출 하 여 기본 텍스트 색상을 가져올 수 있습니다.

## <a name="cmfcoutlookbarpaneisbackgroundtexture"></a><a name="isbackgroundtexture"></a>CMFC아웃아웃바파인::IsBackground 텍스처

Outlook 막대 창에 로드된 배경 이미지가 있는지 여부를 확인합니다.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Return Value

표시할 배경 이미지가 있는 경우 TRUE; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

[CMFCOutlookBarPane::SetBackImage](#setbackimage) 함수를 호출하여 배경 이미지를 추가할 수 있습니다.

배경 이미지가 없는 경우 배경은 [CMFCOutlookBarPane::SetBackColor](#setbackcolor)를 사용하여 지정된 색상으로 페인팅됩니다.

## <a name="cmfcoutlookbarpaneisdrawshadedhighlight"></a><a name="isdrawshadedhighlight"></a>CMFC아웃아웃바파인::이스드드샤드하이라이트

단추를 강조 표시하고 배경 이미지가 표시될 때 단추 테두리가 그늘에 표시되는지 여부를 결정합니다.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Return Value

단추의 테두리가 그늘진 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="cmfcoutlookbarpaneremoveallbuttons"></a><a name="removeallbuttons"></a>CMFC아웃아웃바파인::모두 제거

Outlook 막대 창에서 모든 단추를 제거합니다.

```
virtual void RemoveAllButtons();
```

## <a name="cmfcoutlookbarpaneremovebutton"></a><a name="removebutton"></a>CMFC아웃아웃바파인::제거버튼

지정된 명령 ID가 있는 단추를 제거합니다.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>매개 변수

*아이드커맨드*<br/>
【인】 제거할 단추의 명령 ID를 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 단추를 성공적으로 제거한 경우 지정된 명령 ID가 유효하지 않은 경우 FALSE입니다.

## <a name="cmfcoutlookbarpanesetbackcolor"></a><a name="setbackcolor"></a>CMFC아웃아웃바파인::세트백컬러

Outlook 막대의 배경색을 설정합니다.

```cpp
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
[in] 새 배경색을 지정합니다.

### <a name="remarks"></a>설명

Outlook 막대의 현재 배경 색을 설정하려면 이 함수를 호출합니다. 배경 색은 배경 이미지가 없는 경우에만 사용됩니다.

## <a name="cmfcoutlookbarpanesetbackimage"></a><a name="setbackimage"></a>CMFC아웃아웃바파인:::세트백이미지

배경 이미지를 설정합니다.

```cpp
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>매개 변수

*uiImageID*<br/>
【인】 이미지 리소스 ID를 지정합니다.

### <a name="remarks"></a>설명

Outlook 막대의 배경 이미지를 설정하려면 이 메서드를 호출합니다. 배경 이미지 목록은 포함된 [CMFCToolBarImages 클래스](../../mfc/reference/cmfctoolbarimages-class.md) 개체에 의해 관리됩니다.

## <a name="cmfcoutlookbarpanesetdefaultstate"></a><a name="setdefaultstate"></a>CMFC아웃아웃바파인::설정기본 상태

Outlook 막대 창을 원래 단추 집합으로 재설정합니다.

```cpp
void SetDefaultState();
```

### <a name="remarks"></a>설명

이 메서드는 Outlook 막대 단추를 원래 집합으로 복원합니다. 이 메서드는 `CMFCOutlookBarPane::RestoreOriginalstate`Outlook 막대 창의 다시 그리기를 트리거하지 않는다는 점을 제외하면 와 같습니다.

## <a name="cmfcoutlookbarpanesetextraspace"></a><a name="setextraspace"></a>CMFC아웃아웃바파인::세트엑스트라스페이스

Outlook 막대 창의 단추 주위에 사용되는 패딩 픽셀 수를 설정합니다.

```cpp
void SetExtraSpace()
```

## <a name="cmfcoutlookbarpanesettextcolor"></a><a name="settextcolor"></a>CMFC아웃아웃바파네::세트텍스트컬러

Outlook 막대 창에서 일반 텍스트와 강조 표시된 텍스트의 색상을 설정합니다.

```cpp
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>매개 변수

*clrRegText*<br/>
【인】 선택되지 않은 텍스트의 새 색상을 지정합니다.

*clrSelText*<br/>
【인】 선택한 텍스트의 새 색상을 지정합니다.

## <a name="cmfcoutlookbarpanesettransparentcolor"></a><a name="settransparentcolor"></a>CMFC아웃아웃바파네::세트투명색상

Outlook 막대 창의 투명 색상을 설정합니다.

```cpp
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
새 투명 색상을 지정합니다.

### <a name="remarks"></a>설명

투명 한 이미지를 표시 하려면 투명 한 색상이 필요 합니다. 이미지에서 이 색상이 발생하면 대신 배경 색으로 그려집니다.  배경 및 전경 이미지의 혼합은 없습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFC아웃아웃바 클래스](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
