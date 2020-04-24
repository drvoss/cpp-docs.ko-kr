---
title: CProperty시트 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
ms.openlocfilehash: e8ab91b9a6fe76070d79ea2eee2e5765db2e99e3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750978"
---
# <a name="cpropertysheet-class"></a>CProperty시트 클래스

속성 시트(탭 대화 상자라고도 함)를 나타냅니다.

## <a name="syntax"></a>구문

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CPropertySheet::CProperty시트](#cpropertysheet)|`CPropertySheet` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CPropertySheet::추가 페이지](#addpage)|속성 시트에 페이지를 추가합니다.|
|[CPropertySheet::구문](#construct)|`CPropertySheet` 개체를 생성합니다.|
|[CPropertySheet::만들기](#create)|모덜리스 속성 시트를 표시합니다.|
|[CPropertySheet::DoModal](#domodal)|모달 속성 시트를 표시합니다.|
|[CPropertySheet::인에이블스택탭](#enablestackedtabs)|속성 시트에서 누적 탭또는 스크롤 탭을 사용하는지 여부를 나타냅니다.|
|[CPropertySheet::끝 디아로그](#enddialog)|속성 시트를 종료합니다.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|속성 시트의 활성 페이지의 인덱스를 검색합니다.|
|[CPropertySheet::GetActivePage](#getactivepage)|활성 페이지 개체를 반환합니다.|
|[CPropertySheet::GetPage](#getpage)|지정된 페이지에 대한 포인터를 검색합니다.|
|[CPropertySheet::GetPageCount](#getpagecount)|속성 시트의 페이지 수를 검색합니다.|
|[CPropertySheet::GetPageIndex](#getpageindex)|속성 시트의 지정된 페이지의 인덱스를 검색합니다.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|탭 컨트롤에 대한 포인터를 검색합니다.|
|[CPropertySheet::맵디아로그렉트](#mapdialogrect)|사각형의 대화 상자 단위를 화면 단위로 변환합니다.|
|[CPropertySheet:::온이니티디아로그](#oninitdialog)|속성 시트 초기화를 보강하기 위해 재정의합니다.|
|[CPropertySheet::P레스버튼](#pressbutton)|속성 시트에서 지정된 단추의 선택을 시뮬레이션합니다.|
|[CPropertySheet::제거 페이지](#removepage)|속성 시트에서 페이지를 제거합니다.|
|[CPropertySheet::설정활성 페이지](#setactivepage)|프로그래밍 방식으로 활성 페이지 개체를 설정합니다.|
|[C 속성 시트::설정완료 텍스트](#setfinishtext)|완료 단추의 텍스트를 설정합니다.|
|[CPropertySheet::세트제목](#settitle)|속성 시트의 캡션을 설정합니다.|
|[CPropertySheet::셋마법사 버튼](#setwizardbuttons)|마법사 단추를 활성화합니다.|
|[CProperty시트::세트위저모드](#setwizardmode)|마법사 모드를 활성화합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|윈도우 [소품 헤더](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) 구조입니다. 기본 속성 시트 매개 변수에 대한 액세스를 제공합니다.|

## <a name="remarks"></a>설명

속성 시트는 개체와 하나 이상의 `CPropertySheet` [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체로 구성됩니다. 프레임워크는 탭 인덱스 집합과 현재 선택한 페이지를 포함하는 영역이 있는 창으로 속성 시트를 표시합니다. 사용자는 적절한 탭을 사용하여 특정 페이지로 이동합니다.

`CPropertySheet`Windows 98 및 Windows NT 2000에 도입된 확장된 [PROPSHEETHEADER](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2) 구조에 대한 지원을 제공합니다. 구조에는 "워터마크" 배경 비트맵을 사용하는 추가 플래그와 멤버가 포함되어 있습니다.

속성 시트 개체에 이러한 새 이미지를 자동으로 표시하려면 [CPropertySheet:::Construct](#construct) 또는 [CPropertySheet::CPropertySheet](#cpropertysheet): 호출에서 비트맵 및 팔레트 이미지에 대한 유효한 값을 전달합니다.

`CPropertySheet` [CDialog에서](../../mfc/reference/cdialog-class.md)파생되지 않더라도 개체를 `CPropertySheet` 관리하는 것은 개체를 `CDialog` 관리하는 것과 같습니다. 예를 들어 속성 시트를 만들려면 생성자를 호출한 다음 모달 속성 시트에 [DoModal을](#domodal) 호출하거나 모덜리스 속성 시트에 대해 [만들기라는](#create) 두 부분으로 구성된 구성이 필요합니다. `CPropertySheet`생성자의 두 가지 유형이 있습니다: [CPropertySheet::생성](#construct) 및 [CPropertySheet::CPropertySheet](#cpropertysheet).

개체를 생성할 `CPropertySheet` 때 일부 [창 스타일은](../../mfc/reference/styles-used-by-mfc.md#window-styles) 첫 번째 예외가 발생할 수 있습니다. 이는 시트를 작성하기 전에 속성 시트의 스타일을 변경하려는 시스템에서 발생합니다. 이 예외를 방지하려면 `CPropertySheet`다음 스타일을 만들 때 다음 스타일을 설정해야 합니다.

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

다음 스타일은 선택 사항이며 첫 번째 예외가 발생하지 않습니다.

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

다른 `Window Styles` 모든 것은 금지되어 있으며 이를 활성화해서는 안 됩니다.

`CPropertySheet` 개체와 외부 개체 간에 데이터를 교환하는 것은 개체와 `CDialog` 데이터를 교환하는 것과 유사합니다. 중요한 차이점은 속성 시트의 설정이 일반적으로 `CPropertyPage` `CPropertySheet` 개체 자체가 아니라 개체의 멤버 변수라는 것입니다.

장치 설정 또는 뉴스레터 만들기와 같은 작업 단계를 안내하는 속성 페이지 시퀀스가 있는 속성 시트로 구성된 마법사라는 탭 대화 상자 유형을 만들 수 있습니다. 마법사 유형 탭 대화 상자에서 속성 페이지에는 탭이 없으며 한 번에 하나의 속성 페이지만 표시됩니다. 또한 **확인** 및 **지금 적용** 단추 대신 마법사 유형 탭 대화 **상자에는 뒤로** 버튼, **다음** 또는 **완료** 버튼, **취소** 단추 및 **도움말** 버튼이 있습니다.

마법사 유형 대화 상자를 만들려면 표준 속성 시트를 만들기 위해 따르는 것과 동일한 단계를 따르지만 [DoModal](#domodal)을 호출하기 전에 [SetWizardMode를](#setwizardmode) 호출합니다. 마법사 단추를 사용하려면 [플래그를 사용하여 SetWizardButtons를](#setwizardbuttons)호출하여 기능 및 모양을 사용자 지정합니다. **완료** 단추를 사용하려면 사용자가 마법사의 마지막 페이지에서 작업을 수행한 후 [SetFinishText를](#setfinishtext) 호출합니다.

개체 를 사용하는 `CPropertySheet` 방법에 대한 자세한 내용은 속성 시트 및 속성 [페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md)문서를 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

## <a name="cpropertysheetaddpage"></a><a name="addpage"></a>CPropertySheet::추가 페이지

제공된 페이지를 속성 시트에 가장 오른쪽 탭으로 추가합니다.

```cpp
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
속성 시트에 추가할 페이지를 가리킵니다. NULL이 될 수 없습니다.

### <a name="remarks"></a>설명

속성을 표시할 왼쪽에서 오른쪽 순서로 속성 시트에 페이지를 추가합니다.

`AddPage`[CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) 개체를 `CPropertySheet` 개체의 페이지 목록에 추가하지만 실제로 페이지의 창을 만들지는 않습니다. 프레임워크는 사용자가 해당 페이지를 선택할 때까지 페이지에 대한 창 만들기를 연기합니다.

을 사용하여 `AddPage`속성 페이지를 추가할 `CPropertySheet` 때 은 `CPropertyPage`의 부모입니다. 속성 페이지에서 속성 시트에 액세스하려면 [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)로 전화하십시오.

호출할 속성 시트 창이 만들어지때까지 기다릴 `AddPage`필요가 없습니다. 일반적으로 DoModal `AddPage` 또는 [Create를](#create)호출하기 전에 [호출합니다.](#domodal)

속성 페이지를 `AddPage` 표시한 후 호출하면 탭 행에 새로 추가된 페이지가 반영됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

## <a name="cpropertysheetconstruct"></a><a name="construct"></a>CPropertySheet::구문

`CPropertySheet` 개체를 생성합니다.

```cpp
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>매개 변수

*nIDCaption*<br/>
속성 시트에 사용할 캡션의 ID입니다.

*pParentWnd*<br/>
속성 시트의 상위 창에 대한 포인터입니다. NULL이면 부모 창이 응용 프로그램의 기본 창이 됩니다.

*아이 셀렉토리페이지*<br/>
처음에 맨 위에 있을 페이지의 인덱스입니다. 기본값은 시트에 추가된 첫 번째 페이지입니다.

*pszCaption*<br/>
속성 시트에 사용할 캡션을 포함하는 문자열에 대한 포인터입니다. NULL이 될 수 없습니다.

*hbm워터마크*<br/>
속성 페이지의 워터마크 비트맵을 처리합니다.

*hpal워터마크*<br/>
워터마크 비트맵 및/또는 헤더 비트맵의 팔레트를 처리합니다.

*hbm헤더*<br/>
속성 페이지의 헤더 비트맵을 처리합니다.

### <a name="remarks"></a>설명

클래스 생성자 중 하나가 아직 호출되지 않은 경우 이 멤버 함수를 호출합니다. 예를 들어 `Construct` 개체의 `CPropertySheet` 배열을 선언하거나 할당할 때 호출합니다. 배열의 경우 배열의 각 `Construct` 멤버를 호출해야 합니다.

속성 시트를 표시하려면 [DoModal](#domodal) 또는 [만들기를](#create)호출합니다. 첫 번째 매개 변수에 포함된 문자열은 속성 시트의 캡션 막대에 배치됩니다.

위에 나열된 `Construct`의 세 번째 또는 네 번째 프로토타입을 사용하는 경우 워터마크 및/또는 헤더 이미지를 자동으로 표시하고 *hbmWatermark,* *hpalWatermark*및/또는 *hbmHeader* 매개 변수에 대해 유효한 값을 전달할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 어떤 상황에서 호출할 `Construct`지 보여 줍니다.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

## <a name="cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>CPropertySheet::CProperty시트

`CPropertySheet` 개체를 생성합니다.

```
CPropertySheet();

explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>매개 변수

*nIDCaption*<br/>
속성 시트에 사용할 캡션의 ID입니다.

*pParentWnd*<br/>
속성 시트의 상위 창을 가리킵니다. NULL이면 부모 창이 응용 프로그램의 기본 창이 됩니다.

*아이 셀렉토리페이지*<br/>
처음에 맨 위에 있을 페이지의 인덱스입니다. 기본값은 시트에 추가된 첫 번째 페이지입니다.

*pszCaption*<br/>
속성 시트에 사용할 캡션이 포함된 문자열을 가리킵니다. NULL이 될 수 없습니다.

*hbm워터마크*<br/>
속성 시트의 백그라운드 비트맵에 대한 핸들입니다.

*hpal워터마크*<br/>
워터마크 비트맵 및/또는 헤더 비트맵의 팔레트에 대한 핸들입니다.

*hbm헤더*<br/>
속성 페이지의 헤더 비트맵에 대한 핸들입니다.

### <a name="remarks"></a>설명

속성 시트를 표시하려면 [DoModal](#domodal) 또는 [만들기를](#create)호출합니다. 첫 번째 매개 변수에 포함된 문자열은 속성 시트의 캡션 막대에 배치됩니다.

여러 매개 변수가 있는 경우(예: 배열을 사용하는 경우) `CPropertySheet`대신 [Construct를](#construct) 사용합니다.

`CPropertySheet`위의 세 번째 또는 네 번째 프로토타입을 사용하는 경우 워터마크 및/또는 헤더 이미지를 자동으로 표시하고 *hbmWatermark,* *hpalWatermark*및/또는 *hbmHeader* 매개 변수에 대해 유효한 값을 전달할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

## <a name="cpropertysheetcreate"></a><a name="create"></a>CPropertySheet::만들기

모덜리스 속성 시트를 표시합니다.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
상위 창을 가리킵니다. NULL인 경우 부모가 바탕 화면입니다.

*dwStyle*<br/>
속성 시트의 창 스타일입니다. 사용 가능한 스타일의 전체 목록은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)을 참조하십시오.

*dwExStyle*<br/>
속성 시트에 대한 확장된 창 스타일입니다. 사용 가능한 스타일 전체 목록은 [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) 참조

### <a name="return-value"></a>Return Value

속성 시트가 성공적으로 만들어지면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

호출은 `Create` 생성자 내부에 있거나 생성자가 호출된 후 호출할 수 있습니다.

*dwStyle으로*-1을 전달하여 표현되는 기본 스타일은 실제로&#124;&#124;&#124;WS_POPUP WS_POPUP WS_POPUP DS_MODALFRAME WS_CAPTION&#124;&#124;WS_SYSMENU&#124;&#124;WS_VISIBLE&#124;DS_CONTEXTHELP&#124;&#124;. *dwExStyle으로*0을 전달하여 표현되는 기본 확장 창 스타일은 실제로 WS_EX_DLGMODALFRAME.

멤버 `Create` 함수는 속성 시트를 만든 후 즉시 반환됩니다. 속성 시트를 파괴하려면 [CWnd::DestroyWindow를](../../mfc/reference/cwnd-class.md#destroywindow)호출합니다.

모달 속성 시트처럼 확인, 취소, 지금 적용 및 도움말 버튼이 없는 호출과 `Create` 함께 표시되는 Modeless 속성 시트입니다. 원하는 단추는 사용자가 만들어야 합니다.

모달 속성 시트를 표시하려면 대신 [DoModal을](#domodal) 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

## <a name="cpropertysheetdomodal"></a><a name="domodal"></a>CPropertySheet::DoModal

모달 속성 시트를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Return Value

IDOK 또는 IDCANCEL 함수가 성공한 경우; 그렇지 않으면 0 또는 -1. 속성 시트가 마법사로 설정된 경우(SetWizardMode `DoModal` 참조) ID_WIZFINISH 또는 IDCANCEL을 반환합니다. [SetWizardMode](#setwizardmode)

### <a name="remarks"></a>설명

반환 값은 속성 시트를 닫은 컨트롤의 ID에 해당 합니다. 이 함수가 반환되면 속성 시트에 해당하는 창과 모든 페이지가 소멸됩니다. 개체 자체는 여전히 존재합니다. 일반적으로 IDOK를 반환한 후 `DoModal` [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체에서 데이터를 검색합니다.

모덜리스 속성 시트를 표시하려면 대신 [만들기를](#create) 호출합니다.

속성 페이지가 해당 대화 상자 리소스에서 만들어지면 첫 번째 예외가 발생할 수 있습니다. 이렇게 하면 페이지를 만들 기 전에 대화 상자 리소스의 스타일을 필수 스타일로 변경하는 속성 페이지가 발생합니다. 리소스는 일반적으로 읽기 전용이므로 예외가 발생합니다. 시스템은 예외를 처리하고 수정된 리소스의 복사본을 만듭니다. 따라서 첫 번째 기회 예외는 무시할 수 있습니다.

> [!NOTE]
> 비동기 예외 처리 모델로 컴파일하는 경우 운영 체제에서 이 예외를 처리해야 합니다. 예외 처리 모델에 대한 자세한 내용은 [/EH(예외 처리 모델)를](../../build/reference/eh-exception-handling-model.md)참조하십시오. 이 경우 catch가 모든 `CPropertySheet::DoModal` 예외를 처리하는 C++ try-catch 블록(예: `catch (...)`)을 사용하여 호출을 래핑하지 마십시오. 이 블록은 운영 체제에 대한 예외를 처리하고 예기치 않은 동작을 일으킵니다. 그러나 액세스 위반 예외가 운영 체제로 전달되는 특정 예외 유형 또는 구조화 된 예외 처리와 함께 C ++ 예외 처리를 안전하게 사용할 수 있습니다.

이 첫 번째 기회 예외를 생성 하지 않으려면 속성 시트에 올바른 [창 스타일이](../../mfc/reference/styles-used-by-mfc.md#window-styles)있는지 수동으로 보장할 수 있습니다. 속성 시트에 대해 다음 스타일을 설정해야 합니다.

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

첫 번째 예외를 일으키지 않고 다음 선택적 스타일을 사용할 수 있습니다.

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

속성 시트와 호환되지 않으므로 다른 모든 Windows 스타일을 사용하지 않도록 설정합니다. 이 권장 사항은 확장 스타일에는 적용되지 않습니다. 이러한 표준 스타일을 적절하게 설정하면 속성 시트를 수정할 필요가 없으며 첫 번째 예외가 발생하지 않습니다.

### <a name="example"></a>예제

[CPropertySheet::AddPage](#addpage)에 대한 예제를 참조하십시오.

## <a name="cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>CPropertySheet::인에이블스택탭

속성 시트에 탭 행을 스택할지 여부를 나타냅니다.

```cpp
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>매개 변수

*b스택*<br/>
속성 시트에서 누적된 탭이 활성화되어 있는지 여부를 나타냅니다. *bStacked를* FALSE로 설정하여 누적된 태그 행을 비활성화합니다.

### <a name="remarks"></a>설명

기본적으로 속성 시트에 속성 시트너비의 단일 행에 맞는 것보다 많은 탭이 있는 경우 탭이 여러 행에 쌓입니다. 탭을 쌓는 대신 스크롤 탭을 사용하려면 `EnableStackedTabs` [DoModal](#domodal) 또는 [Create를](#create)호출하기 전에 *false로 설정된 bStacked를* 사용하여 호출합니다.

모달 `EnableStackedTabs` 또는 모덜리스 속성 시트를 만들 때 호출해야 합니다. 이 스타일을 -derived `CPropertySheet`클래스에 통합하려면 WM_CREATE 대한 메시지 처리기를 작성합니다. 재정의된 버전의 [CWnd::OnCreate에서는](../../mfc/reference/cwnd-class.md#oncreate) `EnableStackedTabs( FALSE )` 기본 클래스 구현을 호출하기 전에 호출합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

## <a name="cpropertysheetenddialog"></a><a name="enddialog"></a>CPropertySheet::끝 디아로그

속성 시트를 종료합니다.

```cpp
void EndDialog(int nEndID);
```

### <a name="parameters"></a>매개 변수

*nEndID*<br/>
속성 시트의 반환 값으로 사용할 식별자입니다.

### <a name="remarks"></a>설명

확인, 취소 또는 닫기 단추를 누를 때 이 멤버 함수는 프레임워크에서 호출됩니다. 속성 시트를 닫아야 하는 이벤트가 발생하는 경우 이 멤버 함수를 호출합니다.

이 멤버 함수는 모달 대화 상자에서만 사용됩니다.

### <a name="example"></a>예제

[CPropertySheet::P ressButton에](#pressbutton)대한 예제를 참조하십시오.

## <a name="cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>CPropertySheet::GetActiveIndex

속성 시트 창의 활성 페이지의 인덱스 번호를 가져옵니다. `GetPage`

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>Return Value

활성 페이지의 인덱스 번호입니다.

### <a name="example"></a>예제

[CPropertySheet::GetActivePage](#getactivepage)에 대한 예제를 참조하십시오.

## <a name="cpropertysheetgetactivepage"></a><a name="getactivepage"></a>CPropertySheet::GetActivePage

속성 시트 창의 활성 페이지를 검색합니다.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>Return Value

활성 페이지에 대한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용하여 활성 페이지에서 일부 작업을 수행합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

## <a name="cpropertysheetgetpage"></a><a name="getpage"></a>CPropertySheet::GetPage

이 속성 시트의 지정된 페이지에 대한 포인터를 반환합니다.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>매개 변수

*n페이지*<br/>
0부터 시작하여 원하는 페이지의 인덱스를 만듭니다. 속성 시트의 페이지 수(포함)보다 0에서 1 사이여야 합니다.

### <a name="return-value"></a>Return Value

*nPage* 매개 변수에 해당하는 페이지에 대한 포인터입니다.

### <a name="example"></a>예제

[CPropertyPage::On위저드피니에](../../mfc/reference/cpropertypage-class.md#onwizardfinish)대한 예제를 참조하십시오.

## <a name="cpropertysheetgetpagecount"></a><a name="getpagecount"></a>CPropertySheet::GetPageCount

현재 속성 시트에 있는 페이지 수를 결정합니다.

```
int GetPageCount() const;
```

### <a name="return-value"></a>Return Value

속성 시트의 페이지 수입니다.

### <a name="example"></a>예제

[CPropertyPage::On위저드피니에](../../mfc/reference/cpropertypage-class.md#onwizardfinish)대한 예제를 참조하십시오.

## <a name="cpropertysheetgetpageindex"></a><a name="getpageindex"></a>CPropertySheet::GetPageIndex

속성 시트에서 지정된 페이지의 인덱스 번호를 검색합니다.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
찾을 인덱스가 있는 페이지를 가리킵니다. NULL이 될 수 없습니다.

### <a name="return-value"></a>Return Value

페이지의 인덱스 번호입니다.

### <a name="remarks"></a>설명

예를 들어 `GetPageIndex` [SetActivePage](#setactivepage) 또는 [GetPage](#getpage)를 사용 하려면 페이지 인덱스를 가져옵니다.

### <a name="example"></a>예제

[CPropertySheet::GetActivePage](#getactivepage)에 대한 예제를 참조하십시오.

## <a name="cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>CPropertySheet::GetTabControl

탭 컨트롤에 대한 포인터를 검색하여 탭 컨트롤과 관련된 작업을 수행합니다(즉, [CTabCtrl의](../../mfc/reference/ctabctrl-class.md)API를 사용).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>Return Value

탭 컨트롤에 대한 포인터입니다.

### <a name="remarks"></a>설명

예를 들어 초기화 하는 동안 각 탭에 비트 맵을 추가 하려는 경우이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

## <a name="cpropertysheetm_psh"></a><a name="m_psh"></a>CPropertySheet::m_psh

[PROPSHEETHEADER의](/windows/win32/api/prsht/ns-prsht-propsheetheadera_v2)특성을 저장하는 멤버의 구조입니다.

### <a name="remarks"></a>설명

이 구조를 사용하여 속성 시트가 생성된 후 [DoModal](#domodal) 멤버 함수와 함께 표시되기 전에 속성 시트의 모양을 초기화합니다. 예를 들어 속성 시트에 사용할 `m_psh` 크기로 *dwSize* 멤버를 설정합니다.

멤버 목록을 포함하여 이 구조에 대한 자세한 내용은 Windows SDK의 PROPSHEETHEADER를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

## <a name="cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>CPropertySheet::맵디아로그렉트

사각형의 대화 상자 단위를 화면 단위로 변환합니다.

```cpp
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*Lprect*<br/>
변환할 대화 상자 좌표를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체를 가리킵니다.

### <a name="remarks"></a>설명

대화 상자 단위는 대화 상자 텍스트에 사용되는 글꼴의 문자의 평균 너비와 높이에서 파생된 현재 대화 상자 기본 단위의 관점에서 표시됩니다. 하나의 수평 단위는 대화 상자 기본 너비 단위의 1/4이며, 하나의 수직 단위는 대화 상자 기본 높이 단위의 1/8입니다.

[GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) Windows 함수는 시스템 글꼴에 대한 크기 정보를 반환하지만 리소스 정의 파일에서 DS_SETFONT 스타일을 사용하는 경우 각 속성 시트에 대해 다른 글꼴을 지정할 수 있습니다. Windows SDK에 설명된 [MapDialogRect](/windows/win32/api/winuser/nf-winuser-mapdialogrect) Windows 함수는 이 대화 상자에 적합한 글꼴을 사용합니다.

멤버 `MapDialogRect` 함수는 *lpRect의* 대화 상자 단위를 화면 단위(픽셀)로 대체하므로 사각형을 사용하여 대화 상자를 만들거나 상자 내에 컨트롤을 배치할 수 있습니다.

## <a name="cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>CPropertySheet:::온이니티디아로그

속성 시트 초기화를 보강하기 위해 재정의합니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

응용 프로그램이 속성 시트의 컨트롤 중 하나에 입력 포커스를 설정했는지 여부를 지정합니다. 0이 아닌 것을 반환하는 경우 `OnInitDialog` Windows는 입력 포커스를 속성 시트의 첫 번째 컨트롤로 설정합니다. 응용 프로그램은 속성 시트의 컨트롤 중 하나에 입력 포커스를 명시적으로 설정한 경우에만 0을 반환할 수 있습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 WM_INITDIALOG 메시지에 대한 응답으로 호출됩니다. 이 메시지는 속성 시트가 표시되기 직전에 발생하는 [Create](#create) 또는 [DoModal](#domodal) 호출 중에 속성 시트로 전송됩니다.

속성 시트가 초기화될 때 특수 처리를 수행해야 하는 경우 이 멤버 함수를 재정의합니다. 재정의된 버전에서는 먼저 기본 클래스를 `OnInitDialog` 호출하지만 반환 값을 무시합니다. 일반적으로 재정의된 멤버 함수에서 TRUE를 반환합니다.

이 멤버 함수에 대한 메시지 맵 항목이 필요하지 않습니다.

## <a name="cpropertysheetpressbutton"></a><a name="pressbutton"></a>CPropertySheet::P레스버튼

속성 시트에서 지정된 단추의 선택을 시뮬레이션합니다.

```cpp
void PressButton(int nButton);
```

### <a name="parameters"></a>매개 변수

*nButton*<br/>
nButton : 누를 단추를 식별합니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- PSBTN_BACK 뒤로 버튼을 선택합니다.

- PSBTN_NEXT 다음 버튼을 선택합니다.

- PSBTN_FINISH 완료 버튼을 선택합니다.

- PSBTN_OK 확인 버튼을 선택합니다.

- PSBTN_APPLYNOW 지금 적용 버튼을 선택합니다.

- PSBTN_CANCEL 취소 단추를 선택합니다.

- PSBTN_HELP 도움말 단추를 선택합니다.

### <a name="remarks"></a>설명

Windows SDK 프레스 버튼 메시지에 대한 자세한 내용은 [PSM_PRESSBUTTON](/windows/win32/Controls/psm-pressbutton) 참조하십시오.

`PressButton` 호출은 속성 페이지에서 프레임워크로 [PSN_APPLY](/windows/win32/Controls/psn-apply) 알림을 보내지 않습니다. 이 알림을 보내려면 [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok)로 전화하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

## <a name="cpropertysheetremovepage"></a><a name="removepage"></a>CPropertySheet::제거 페이지

속성 시트에서 페이지를 제거하고 연결된 창을 삭제합니다.

```cpp
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>매개 변수

*p페이지*<br/>
속성 시트에서 제거할 페이지를 가리킵니다. NULL이 될 수 없습니다.

*n페이지*<br/>
제거할 페이지의 인덱스입니다. 속성 시트의 페이지 수(포함)보다 0에서 1 사이여야 합니다.

### <a name="remarks"></a>설명

`CPropertySheet` [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체 자체는 창의 소유자가 닫혀 때까지 소멸 되지 않습니다.

## <a name="cpropertysheetsetactivepage"></a><a name="setactivepage"></a>CPropertySheet::설정활성 페이지

활성 페이지를 변경합니다.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*n페이지*<br/>
설정할 페이지의 인덱스입니다. 속성 시트의 페이지 수(포함)보다 0~1개 미만이어야 합니다.

*p페이지*<br/>
속성 시트에 설정할 페이지를 가리킵니다. NULL일 수는 없습니다.

### <a name="return-value"></a>Return Value

속성 시트가 성공적으로 활성화된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

예를 들어 `SetActivePage` 한 페이지에서 사용자의 동작으로 인해 다른 페이지가 활성 페이지가 되어야 하는 경우 사용합니다.

### <a name="example"></a>예제

[CPropertySheet::GetActivePage](#getactivepage)에 대한 예제를 참조하십시오.

## <a name="cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>C 속성 시트::설정완료 텍스트

[완료 명령] 단추에서 텍스트를 설정합니다.

```cpp
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
[완료 명령] 버튼에 표시할 텍스트를 가리킵니다.

### <a name="remarks"></a>설명

사용자가 `SetFinishText` 마법사의 마지막 페이지에서 작업을 완료한 후 명령 완료 단추에 텍스트를 표시하고 다음 및 뒤로 단추를 숨깁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsettitle"></a><a name="settitle"></a>CPropertySheet::세트제목

속성 시트의 캡션(프레임 창의 제목 표시줄에 표시되는 텍스트)을 지정합니다.

```cpp
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
속성 시트 제목의 스타일을 지정합니다. 스타일은 0 또는 PSH_PROPTITLE 지정해야 합니다. 스타일이 PSH_PROPTITLE 설정된 경우 캡션으로 지정된 텍스트 다음의 단어 "속성"이 나타납니다. 예를 들어 `SetTitle`호출("단순", PSH_PROPTITLE)은 "단순 속성"의 속성 시트 캡션을 생성합니다.

*lpszText*<br/>
속성 시트의 제목 표시줄에 캡션으로 사용할 텍스트를 가리킵니다.

### <a name="remarks"></a>설명

기본적으로 속성 시트는 속성 시트 생성자의 캡션 매개 변수를 사용합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

## <a name="cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>CPropertySheet::셋마법사 버튼

마법사 속성 시트에서 뒤로, 다음 또는 완료 단추를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
마법사 단추의 기능과 모양을 사용자 지정하는 플래그 집합입니다. 이 매개 변수는 다음 값의 조합일 수 있습니다.

- PSWIZB_BACK 뒤로 버튼

- 다음 PSWIZB_NEXT 버튼

- PSWIZB_FINISH 마무리 버튼

- PSWIZB_DISABLEDFINISH 비활성화 완료 버튼

### <a name="remarks"></a>설명

대화 `SetWizardButtons` 상자가 열린 후에만 호출합니다. [DoModal을](#domodal) `SetWizardButtons` 호출하기 전에는 전화를 걸 수 없습니다. 일반적으로 `SetWizardButtons` [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)에서 호출해야 합니다.

사용자가 마법사를 완료한 후 완료 단추의 텍스트를 변경하거나 다음 및 뒤로 단추를 숨기려면 [SetFinishText](#setfinishtext)를 호출합니다. 완료 및 다음에 대해 동일한 버튼이 공유됩니다. 한 번에 완료 또는 다음 단추를 표시할 수 있지만 둘 다 표시할 수는 없습니다.

### <a name="example"></a>예제

`CPropertySheet` A에는 세 개의 `CStylePage`마법사 `CColorPage`속성 `CShapePage`페이지가 있습니다.  아래 코드 조각에서는 마법사 속성 페이지에서 **뒤로** 및 **다음** 단추를 활성화하고 사용하지 않도록 설정하는 방법을 보여 주며 있습니다.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

## <a name="cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>CProperty시트::세트위저모드

속성 페이지를 마법사로 설정합니다.

```cpp
void SetWizardMode();
```

### <a name="remarks"></a>설명

마법사 속성 페이지의 주요 특징은 사용자가 탭 대신 다음 또는 끝, 뒤로 및 취소 단추를 사용하여 탐색한다는 것입니다.

`SetWizardMode` [DoModal에](#domodal)전화하기 전에 전화하십시오. 호출 `SetWizardMode`한 `DoModal` 후 ID_WIZFINISH (사용자가 완료 버튼으로 닫히는 경우) 또는 IDCANCEL중 하나를 반환합니다.

`SetWizardMode`PSH_WIZARD 플래그를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
