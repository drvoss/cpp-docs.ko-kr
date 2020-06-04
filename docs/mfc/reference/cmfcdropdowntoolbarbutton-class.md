---
title: CMFC드롭다운툴버튼 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: f09a2f3fe66abb86a8f220dbdf6744813ad9db0d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752398"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFC드롭다운툴버튼 클래스

클릭할 때 일반 단추처럼 동작하는 도구 모음 단추의 한 종류입니다. 그러나 사용자가 도구 모음 단추를 누르고 있으면 드롭다운 도구 [모음(CMFCDropDownToolBar 클래스)이](../../mfc/reference/cmfcdropdowntoolbar-class.md) 열립니다.

## <a name="syntax"></a>구문

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC드롭다운툴바버튼::CMFC드롭다운툴버튼버튼](#cmfcdropdowntoolbarbutton)|`CMFCDropDownToolbarButton` 개체를 생성합니다.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC드롭다운툴바버튼::복사에서](#copyfrom)|다른 도구 모음 단추의 속성을 현재 단추에 복사합니다. [(CMFCToolBar 단추 재정의::복사에서.)](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCDropDownToolbarButton::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFC드롭다운툴바버튼::D롭다운툴바](#dropdowntoolbar)|드롭다운 도구 모음을 엽니다.|
|[CMFC드롭다운툴바버튼::내보내기메뉴버튼](#exporttomenubutton)|도구 모음 단추에서 메뉴로 텍스트를 복사합니다. [(CMFCToolBar 단추 재정의::내보내기 메뉴 단추.)](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|
|[CMFC드롭다운툴바버튼::겟드롭다운툴바](#getdropdowntoolbar)|단추와 연결된 드롭다운 도구 모음을 검색합니다.|
|`CMFCDropDownToolbarButton::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC드롭다운툴바버튼::이드롭다운](#isdropdown)|드롭다운 도구 모음이 현재 열려 있는지 여부를 결정합니다.|
|[CMFC드롭다운툴바버튼::이엑스트라사이즈](#isextrasize)|확장된 테두리로 단추를 표시할 수 있는지 여부를 결정합니다. [(CMFCToolBar 단추 재정의::IsExtraSize.)](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)|
|[CMFC드롭다운툴바버튼::온계산크기](#oncalculatesize)|지정된 장치 컨텍스트 및 도킹 상태에 대한 단추 크기를 계산하기 위해 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::계산 크기.)](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)|
|`CMFCDropDownToolbarButton::OnCancelMode`|[WM_CANCELMODE](/windows/win32/winmsg/wm-cancelmode) 메시지를 처리 하는 프레임 워크에 의해 호출 됩니다. ( `CMCToolBarButton::OnCancelMode`을 재정의합니다.)|
|[CMFC드롭다운툴바버튼::온체인지부모](#onchangeparentwnd)|단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnChangeParentWnd.)](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)|
|[CMFC드롭다운툴바버튼::클릭](#onclick)|사용자가 마우스 단추를 클릭할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnClick.)](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)|
|[CMFC드롭다운툴바버튼::온클릭업](#onclickup)|사용자가 마우스 단추를 해제할 때 프레임워크에서 호출됩니다. [(CMFCToolBar 단추 재정의::OnClickup.)](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)|
|[CMFC드롭다운툴바버튼::온컨텍스트 도움말](#oncontexthelp)|상위 도구 모음에서 WM_HELPHITTEST 메시지를 처리할 때 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온컨텍스트 도움말.)](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)|
|[CMFC드롭다운툴바버튼::온커스터마이즈메뉴](#oncustomizemenu)|응용 프로그램이 상위 도구 모음에 바로 가기 메뉴를 표시할 때 제공된 메뉴를 수정합니다. [(CMFCToolBar 단추 재정의::온커민메뉴.)](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)|
|[CMFC드롭다운툴바버튼::온드로우](#ondraw)|지정된 스타일과 옵션을 사용하여 단추를 그리는 프레임워크에서 호출합니다. [(CMFCToolBar 단추 재정의::온드로우.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw)|
|[CMFC드롭다운툴바버튼::온드로온커스터](#ondrawoncustomizelist)|**사용자 지정 대화** 상자의 명령 창에서 단추를 그리는 프레임워크에서 **호출합니다.** [(CMFCToolBar 단추 재정의:OnDrawOn 사용자 지정 목록.)](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[CMFC드롭다운툴바버튼::직렬화](#serialize)|이 개체를 아카이브에서 읽거나 아카이브에 씁니다. [(CMFCToolBar 단추 재정의::직렬화.)](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)|
|[CMFC드롭다운툴바버튼::설정기본명령](#setdefaultcommand)|사용자가 단추를 클릭할 때 프레임워크에서 사용하는 기본 명령을 설정합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CMFC드롭다운툴버튼:m_uiShowBarDelay](#m_uishowbardelay)|드롭다운 도구 모음이 나타나기 전에 사용자가 마우스 단추를 누를 수 있어야 하는 시간을 지정합니다.|

## <a name="remarks"></a>설명

A는 `CMFCDropDownToolBarButton` 버튼의 오른쪽 아래 모서리에 작은 화살표가 있다는 점에서 일반 버튼과 다릅니다. 사용자가 드롭다운 도구 모음에서 단추를 선택하면 프레임워크는 최상위 도구 모음 단추(오른쪽 아래 모서리에 작은 화살표가 있는 단추)에 아이콘이 표시됩니다.

드롭다운 도구 모음을 구현하는 방법에 대한 자세한 내용은 [CMFCDropDownToolBar 클래스를](../../mfc/reference/cmfcdropdowntoolbar-class.md)참조하십시오.

개체를 `CMFCDropDownToolBarButton` [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 개체로 내보내고 팝업 메뉴가 있는 메뉴 단추로 표시할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>CMFC드롭다운툴바버튼::복사에서

다른 도구 모음 단추의 속성을 현재 단추에 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
【인】 복사할 소스 단추에 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드를 호출하여 다른 도구 모음 단추를 이 도구 모음 단추에 복사합니다. *src는* 유형이어야합니다 `CMFCDropDownToolbarButton`.

## <a name="cmfcdropdowntoolbarbuttoncmfcdropdowntoolbarbutton"></a><a name="cmfcdropdowntoolbarbutton"></a>CMFC드롭다운툴바버튼::CMFC드롭다운툴버튼버튼

`CMFCDropDownToolbarButton` 개체를 생성합니다.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 단추의 기본 텍스트입니다.

*pToolBar*<br/>
【인】 사용자가 단추를 `CMFCDropDownToolBar` 누를 때 표시되는 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

생성자의 두 번째 오버로드는 *pToolBar가* 지정한 도구 모음의 첫 번째 단추를 드롭다운 단추로 복사합니다.

일반적으로 드롭다운 도구 모음 단추는 *pToolBar가* 지정한 도구 모음에서 가장 최근에 사용한 단추의 텍스트를 사용합니다. 단추를 메뉴 단추로 변환 하거나 **사용자 지정** 대화 상자의 **명령** 탭에 표시 될 때 *lpszName에* 의해 지정 된 텍스트를 사용 합니다. **사용자 지정** 대화 상자에 대한 자세한 내용은 [CMFCToolBar사용자 지정 Dialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)를 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 `CMFCDropDownToolbarButton` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

## <a name="cmfcdropdowntoolbarbuttondropdowntoolbar"></a><a name="dropdowntoolbar"></a>CMFC드롭다운툴바버튼::D롭다운툴바

드롭다운 도구 모음을 엽니다.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 드롭다운 프레임 또는 NULL의 상위 창으로 드롭다운 도구 모음 단추의 상위 창을 사용합니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CMFCDropDownToolbarButton::OnClick](#onclick) 메서드는 사용자가 도구 모음 단추를 누르고 누를 때 드롭다운 도구 모음을 열기 위해 이 메서드를 호출합니다.

이 메서드는 [CMFCDropDownFrame:만들기](../../mfc/reference/cmfcdropdownframe-class.md#create) 메서드를 사용하여 드롭다운 도구 모음을 만듭니다. 상위 도구 모음이 수직으로 도킹된 경우 이 방법은 맞춤에 따라 드롭다운 도구 모음을 상위 도구 모음의 왼쪽 또는 오른쪽에 배치합니다. 그렇지 않으면 이 메서드는 상위 도구 모음 아래에 드롭다운 도구 모음을 배치합니다.

*pWnd가* NULL이고 드롭다운 도구 모음 단추에 상위 창이 없는 경우 이 메서드가 실패합니다.

## <a name="cmfcdropdowntoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFC드롭다운툴바버튼::내보내기메뉴버튼

도구 모음 단추에서 메뉴로 텍스트를 복사합니다.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>매개 변수

*메뉴 버튼*<br/>
【인】 대상 메뉴 단추에 대한 참조입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아니고, 실패하면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현 [(CMFCToolBarButton::ExportToMenuButton)을](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)호출 하 고 대상 메뉴 단추에 이 단추의 각 도구 모음 메뉴 항목을 포함 하는 팝업 메뉴에 추가 합니다. 이 메서드는 팝업 메뉴에 하위 메뉴를 추가 하지 않습니다.

상위 도구 모음이 `m_pToolBar`NULL이거나 기본 클래스 구현이 FALSE를 반환하는 경우 이 메서드가 실패합니다.

## <a name="cmfcdropdowntoolbarbuttongetdropdowntoolbar"></a><a name="getdropdowntoolbar"></a>CMFC드롭다운툴바버튼::겟드롭다운툴바

단추와 연결된 드롭다운 도구 모음을 검색합니다.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Return Value

단추와 연결된 드롭다운 도구 모음입니다.

### <a name="remarks"></a>설명

이 메서드는 `m_pToolBar` 데이터 멤버를 반환합니다.

## <a name="cmfcdropdowntoolbarbuttonisdropdown"></a><a name="isdropdown"></a>CMFC드롭다운툴바버튼::이드롭다운

드롭다운 도구 모음이 현재 열려 있는지 여부를 결정합니다.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Return Value

드롭다운 도구 모음이 현재 열려 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

프레임워크는 [CMFCDropDownToolBarButton::DropDownToolbar](#dropdowntoolbar) 메서드를 사용하여 드롭다운 도구 모음을 엽니다. 사용자가 드롭다운 도구 모음의 클라이언트가 아닌 영역에서 왼쪽 마우스 단추를 누르면 프레임워크가 드롭다운 도구 모음을 닫습니다.

## <a name="cmfcdropdowntoolbarbuttonisextrasize"></a><a name="isextrasize"></a>CMFC드롭다운툴바버튼::이엑스트라사이즈

확장된 테두리로 단추를 표시할 수 있는지 여부를 결정합니다.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Return Value

도구 모음 단추를 확장된 테두리로 표시할 수 있는 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

확장 된 테두리에 대 한 자세한 내용은 [참조 CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

## <a name="cmfcdropdowntoolbarbuttonm_uishowbardelay"></a><a name="m_uishowbardelay"></a>CMFC드롭다운툴버튼:m_uiShowBarDelay

드롭다운 도구 모음이 나타나기 전에 사용자가 마우스 단추를 누를 수 있어야 하는 시간을 지정합니다.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>설명

지연 시간은 밀리초 단위로 측정됩니다. 기본값은 500입니다. 이 공유 데이터 멤버의 값을 변경하여 다른 지연을 설정할 수 있습니다.

## <a name="cmfcdropdowntoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFC드롭다운툴바버튼::온계산크기

지정된 장치 컨텍스트 및 도킹 상태에 대한 단추 크기를 계산하기 위해 프레임워크에서 호출합니다.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시 하는 장치 컨텍스트입니다.

*크기기본값*<br/>
【인】 단추의 기본 크기입니다.

*b호르츠 (주)*<br/>
【인】 상위 도구 모음의 도크 상태입니다. 이 매개변수는 도구 모음이 수평으로 도킹되거나 부동 인 경우 TRUE이거나 도구 모음이 수직으로 도킹된 경우 FALSE입니다.

### <a name="return-value"></a>Return Value

단추의 치수를 픽셀 단위로 포함하는 `SIZE` 구조입니다.

### <a name="remarks"></a>설명

이 메서드는 단추 크기의 수평 차원에 드롭다운 화살표의 너비를 추가하여 기본 클래스 [구현(CMFCToolBarButton::OnCalculateSize)을](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)확장합니다.

## <a name="cmfcdropdowntoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFC드롭다운툴바버튼::온체인지부모

단추를 새 도구 모음에 삽입할 때 프레임워크에서 호출됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 새 부모 창입니다.

### <a name="remarks"></a>설명

이 메서드는 텍스트 레이블 [(CMFCToolBarButton::m_strText)을](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)지우고 [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) 및 [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) 데이터 멤버를 FALSE로 설정하여 기본 클래스 구현(CMFCToolBarButton::OnChangeParentWnd)을 재정의합니다. [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)

## <a name="cmfcdropdowntoolbarbuttononclick"></a><a name="onclick"></a>CMFC드롭다운툴바버튼::클릭

사용자가 마우스 단추를 클릭할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 도구 모음 단추의 상위 창입니다.

*bDelay*<br/>
【인】 TRUE 메시지가 지연된 처리되어야 하는 경우

### <a name="return-value"></a>Return Value

버튼이 클릭 메시지를 처리하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), 드롭다운 도구 모음의 상태를 업데이트 하 여.

사용자가 도구 모음 단추를 클릭하면 이 메서드는 [CMFCDropDownToolBarButton::m_uiShowBarDelay](#m_uishowbardelay) 데이터 멤버에 의해 지정된 시간을 기다린 다음 [CMFCDropDownToolBarButton::DropDownToolbar](#dropdowntoolbar) 메서드를 사용하여 드롭다운 도구 모음을 여는 타이머를 만듭니다. 이 메서드는 사용자가 도구 모음 단추를 두 번째로 클릭할 때 드롭다운 도구 모음을 닫습니다.

## <a name="cmfcdropdowntoolbarbuttononclickup"></a><a name="onclickup"></a>CMFC드롭다운툴바버튼::온클릭업

사용자가 마우스 단추를 해제할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Return Value

버튼이 클릭 메시지를 처리하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 드롭다운 도구 모음의 상태를 업데이트하여 기본 클래스 구현인 [CMFCToolBarButton::OnClickUp을](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)확장합니다.

이 메서드는 활성 상태인 경우 드롭다운 도구 모음 타이머를 중지합니다. 열린 경우 드롭다운 도구 모음을 닫습니다.

드롭다운 도구 모음 및 드롭다운 도구 모음 타이머에 대한 자세한 내용은 [CMFCDropDownToolbar 단추::OnClick](#onclick)을 참조하십시오.

## <a name="cmfcdropdowntoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFC드롭다운툴바버튼::온컨텍스트 도움말

상위 도구 모음에서 WM_HELPHITTEST 메시지를 처리할 때 프레임워크에서 호출합니다.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
【인】 도구 모음 단추의 상위 창입니다.

### <a name="return-value"></a>Return Value

버튼이 도움말 메시지를 처리하는 경우 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnContextHelp)](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp) [CMFC드롭다운 툴바 단추::OnClick](#onclick) 메서드를 호출 하여 false로 설정 된 *bDelay.* 이 메서드는 [CMFCDropDownToolbarButton::OnClick에서](#onclick)반환되는 값을 반환합니다.

WM_HELPHITTEST 메시지에 대한 자세한 내용은 [TN028: 컨텍스트 구분 도움말 지원을](../../mfc/tn028-context-sensitive-help-support.md)참조하십시오.

## <a name="cmfcdropdowntoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>CMFC드롭다운툴바버튼::온커스터마이즈메뉴

응용 프로그램이 상위 도구 모음에 바로 가기 메뉴를 표시할 때 제공된 메뉴를 수정합니다.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>매개 변수

*p메뉴*<br/>
【인】 사용자 정의 할 메뉴입니다.

### <a name="return-value"></a>Return Value

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 다음 메뉴 항목을 사용 하지 않도록 설정 하 여 기본 클래스 구현 [(CMFCToolBarButton::OnCustomizeMenu)를](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)확장 합니다.

- **복사 단추 이미지**

- **단추 모양**

- **이미지**

- **텍스트**

- **이미지 및 텍스트**

이 메서드를 재정의하여 프레임워크가 사용자 지정 모드에서 표시하는 바로 가기 메뉴를 수정합니다.

## <a name="cmfcdropdowntoolbarbuttonondraw"></a><a name="ondraw"></a>CMFC드롭다운툴바버튼::온드로우

지정된 스타일과 옵션을 사용하여 단추를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시 하는 장치 컨텍스트입니다.

*rect*<br/>
【인】 단추의 경계 사각형입니다.

*p 이미지*<br/>
【인】 단추와 연결된 도구 모음 이미지의 컬렉션입니다.

*b호르츠 (주)*<br/>
【인】 상위 도구 모음의 도크 상태입니다. 이 매개 변수는 단추를 가로로 도킹할 때 TRUE이고 단추를 세로로 도킹할 때 FALSE입니다.

*b 사용자 정의 모드*<br/>
【인】 도구 모음이 사용자 지정 모드에 있는지 여부를 지정합니다. 이 매개 변수는 도구 모음이 사용자 지정 모드에 있을 때 TRUE이고 도구 모음이 사용자 지정 모드에 있지 않은 경우 FALSE입니다.

*bHighlight*<br/>
【인】 단추를 강조 표시할지 여부를 지정합니다. 이 매개 변수는 단추가 강조 표시될 때 TRUE이고 단추를 강조 표시하지 않을 때 FALSE입니다.

*b드드로우보더*<br/>
【인】 단추에 테두리를 표시할지 여부를 지정합니다. 이 매개 변수는 단추에 테두리를 표시 해야 하는 경우 TRUE 및 FALSE 단추에 테두리를 표시 하지 않아야 합니다.

*b회색비활성화단추*<br/>
【인】 비활성화된 단추를 음영할지 아니면 비활성화된 이미지 컬렉션을 사용할지 지정합니다. 이 매개 변수는 비활성화된 단추를 그늘에 가두어야 하는 경우 TRUE이고 이 메서드는 비활성화된 이미지 컬렉션을 사용해야 하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

도구 모음 단추 그리기를 사용자 지정하려면 이 메서드를 재정의합니다.

## <a name="cmfcdropdowntoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFC드롭다운툴바버튼::온드로온커스터

**사용자 지정 대화** 상자의 명령 창에서 단추를 그리는 프레임워크에서 **호출합니다.**

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
【인】 단추를 표시 하는 장치 컨텍스트입니다.

*rect*<br/>
【인】 단추의 경계 사각형입니다.

*b 선택됨*<br/>
【인】 단추를 선택했는지 여부입니다. 이 매개 변수가 TRUE이면 단추가 선택됩니다. 이 매개 변수가 FALSE이면 단추가 선택되지 않습니다.

### <a name="return-value"></a>Return Value

지정된 장치 컨텍스트의 단추 너비(픽셀 단위)입니다.

### <a name="remarks"></a>설명

이 메서드는 소유자-그리기 목록 상자에 자신을 표시 하는 데 필요한 경우 사용자 지정 대화 상자 **(명령** 탭)에 의해 호출 됩니다.

이 메서드는 기본 클래스 구현을 확장 [(CMFCToolBarButton::OnDrawOnCustomizeList)](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)단추의 이름으로 단추의 텍스트 레이블을 변경 하 여 (즉, 생성자에 전달 하는 *lpszName* 매개 변수의 값).

## <a name="cmfcdropdowntoolbarbuttonserialize"></a><a name="serialize"></a>CMFC드롭다운툴바버튼::직렬화

이 개체를 아카이브에서 읽거나 아카이브에 씁니다.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
【인】 직렬화할 `CArchive` 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 상위 도구 모음의 리소스 ID를 직렬화 하여 기본 클래스 [구현(CMFCToolBarButton::Serialize)을](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)확장합니다. 아카이브가 로드중일 때(CArchive::IsLoading이 비영값을 반환함) 이 메서드는 직렬화된 리소스 ID를 [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) `m_pToolBar` 포함하는 도구 모음으로 데이터 멤버를 설정합니다.

## <a name="cmfcdropdowntoolbarbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFC드롭다운툴바버튼::설정기본명령

사용자가 단추를 클릭할 때 프레임워크에서 사용하는 기본 명령을 설정합니다.

```cpp
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 기본 명령의 ID입니다.

### <a name="remarks"></a>설명

사용자가 단추를 클릭할 때 프레임워크가 실행되는 기본 명령을 지정하려면 이 메서드를 호출합니다. *uiCmd가* 지정한 명령 ID가 있는 항목은 상위 드롭다운 도구 모음에 있어야 합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC드롭다운툴바 클래스](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFC툴바 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFC툴바메뉴버튼 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
