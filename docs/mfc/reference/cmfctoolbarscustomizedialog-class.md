---
title: CMFCToolBars커렌드디아로그 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillAllCommandsList
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::FillCategoriesListBox
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCommandName
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetCountInCategory
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::GetFlags
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::OnInitDialog
- AFXTOOLBARSCUSTOMIZEDIALOG/CMFCToolBarsCustomizeDialog::PostNcDestroy
helpviewer_keywords:
- CMFCToolBarsCustomizeDialog [MFC], CMFCToolBarsCustomizeDialog
- CMFCToolBarsCustomizeDialog [MFC], FillAllCommandsList
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesComboBox
- CMFCToolBarsCustomizeDialog [MFC], FillCategoriesListBox
- CMFCToolBarsCustomizeDialog [MFC], GetCommandName
- CMFCToolBarsCustomizeDialog [MFC], GetCountInCategory
- CMFCToolBarsCustomizeDialog [MFC], GetFlags
- CMFCToolBarsCustomizeDialog [MFC], OnInitDialog
- CMFCToolBarsCustomizeDialog [MFC], PostNcDestroy
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
ms.openlocfilehash: 29e2c3d0238ac5a084ea916d95ad953f8c4aedce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753408"
---
# <a name="cmfctoolbarscustomizedialog-class"></a>CMFCToolBars커렌드디아로그 클래스

사용자가 응용 프로그램에서 도구 모음, 메뉴, 키보드 단축키, 사용자 정의 도구 및 시각적 스타일을 사용자 지정할 수 있는 모덜리스 탭 대화 [상자(CPropertySheet](../../mfc/reference/cpropertysheet-class.md)클래스)입니다. 일반적으로 사용자가 **도구** 메뉴에서 **사용자 지정** 을 선택하여 이 대화 상자에 액세스합니다.

**사용자 정의** 대화 상자에는 명령, 도구 **모음,** **도구**모음, **키보드,** **메뉴**및 **옵션의**6개의 탭이 **있습니다.**

## <a name="syntax"></a>구문

```
class CMFCToolBarsCustomizeDialog : public CPropertySheet
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCToolBars커스터마이즈디아로그::CMFCToolBar커스터마이즈디아로그](#cmfctoolbarscustomizedialog)|`CMFCToolBarsCustomizeDialog` 개체를 생성합니다.|
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolBar사용자 정의디아로그::추가 단추](#addbutton)|명령 페이지의 명령 목록에 도구 모음 **단추를 삽입합니다.**|
|[CMFCToolBar사용자 정의디아로그::추가 메뉴](#addmenu)|리소스에서 메뉴를 로드 하 고 [호출 CMFCToolBars사용자 지정::AddMenuCommands](#addmenucommands) **명령** 페이지에서 명령 목록에 해당 메뉴를 추가 합니다.|
|[CMFCToolBar사용자 정의디아로그::추가 메뉴 명령](#addmenucommands)|리소스에서 메뉴를 로드 하 고 [호출 CMFCToolBars사용자 지정::AddMenuCommands](#addmenucommands) **명령** 페이지에서 명령 목록에 해당 메뉴를 추가 합니다.|
|[CMFCToolBar사용자 정의디아로그::추가 도구 바](#addtoolbar)|리소스에서 도구 모음을 로드합니다. 그런 다음 메뉴의 각 명령에 대해 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드를 호출하여 지정된 범주 아래의 명령 페이지에서 명령 목록에 **단추를 삽입합니다.**|
|[CMFCToolBar사용자 정의디아로그::만들기](#create)|사용자 **지정** 대화 상자를 표시합니다.|
|`CMFCToolBarsCustomizeDialog::EnableTools`|다음에 사용하도록 예약됩니다.|
|[CMFCToolBar사용자 정의디아로그::인에이블유저 정의 도구 모음](#enableuserdefinedtoolbars)|**사용자 지정** 대화 상자를 사용하여 새 도구 모음만들기를 활성화하거나 사용하지 않도록 설정합니다.|
|[CMFCToolBar사용자 정의디아로그::FillAllCommandsList](#fillallcommandslist)|제공된 `CListBox` 개체를 **모든 명령** 범주의 명령으로 채웁니다.|
|[CMFCToolBar사용자 정의디아로그::채우기 범주콤보박스](#fillcategoriescombobox)|제공된 `CComboBox` 개체를 **사용자 지정** 대화 상자에 각 명령 범주의 이름으로 채웁니다.|
|[CMFCToolBar사용자 정의디아로그::채우기범주목록상자](#fillcategorieslistbox)|제공된 `CListBox` 개체를 **사용자 지정** 대화 상자에 각 명령 범주의 이름으로 채웁니다.|
|[CMFCToolBar사용자 정의디아로그::GetCommandName](#getcommandname)|지정된 명령 ID와 연결된 이름을 검색합니다.|
|[CMFCToolBars사용자 정의디아로그 ::GetCountIn카테고리](#getcountincategory)|지정된 텍스트 레이블이 있는 제공된 목록의 항목 수를 검색합니다.|
|[CMFCToolBar사용자 정의디아로그::겟플래그](#getflags)|대화 상자의 동작에 영향을 주는 플래그 집합을 검색합니다.|
|`CMFCToolBarsCustomizeDialog::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCToolBar사용자 정의대화 : ::OnEdit도구 모음메뉴이미지](#onedittoolbarmenuimage)|사용자가 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기시작합니다.|
|[CMFCToolBar사용자 정의대화 : ::InInitDialog](#oninitdialog)|속성 시트 초기화를 보강하기 위해 재정의합니다. [(재정의 시트 재정의::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog).)|
|[CMFCToolBars커스터마이즈디아로그::PostNcDestroy](#postncdestroy)|창이 소멸된 후 프레임워크에서 호출됩니다. ( `CPropertySheet::PostNcDestroy`을 재정의합니다.)|
|[CMFCToolBar사용자 정의디아로그::제거 버튼](#removebutton)|지정된 범주 또는 모든 범주에서 지정된 명령 ID가 있는 단추를 제거합니다.|
|[CMFCToolBar사용자 정의대화 : :이름 바꾸기범주](#renamecategory)|명령 탭의 범주 목록 상자에서 범주 이름을 **바꿉니다.**|
|[CMFCToolBar사용자 정의Dialog::바꾸기 단추](#replacebutton)|명령 탭의 명령 목록의 단추를 새 도구 모음 단추 개체로 **바꿉습니다.**|
|[CMFCToolBar사용자 정의디아로그::SetuserCategory](#setusercategory)|명령 탭에 표시될 범주 목록에 **범주를 추가합니다.**|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CMFCToolBar사용자 정의디아로그::체크툴유효성](#checktoolsvalidity)|사용자 정의 도구 목록이 유효한지 여부를 확인하기 위해 프레임워크에서 호출합니다.|
|[CMFCToolBar사용자 정의디아로그::온애프터체인지툴](#onafterchangetool)|사용자 정의 도구의 속성이 변경될 때 프레임워크에서 호출됩니다.|
|[CMFCToolBar사용자 정의대화: ::OnAssign키](#onassignkey)|지정된 키보드 단축을 작업에 할당할 수 있는지 여부를 결정합니다.|
|[CMFCToolBar사용자 정의디아로그::OnBeforeChangeTool](#onbeforechangetool)|사용자 정의 도구를 변경할 수 있는지 여부를 결정합니다.|
|[CMFCToolBars사용자 정의대화 : ::IninitToolsPage](#oninittoolspage)|사용자가 **도구** 탭을 선택할 때 프레임워크에서 호출됩니다.|

## <a name="remarks"></a>설명

**사용자 지정** 대화 상자를 표시하려면 `CMFCToolBarsCustomizeDialog` 개체를 만들고 [CMFCToolBars사용자 지정Dialog::만들기](#create) 메서드를 호출합니다.

사용자 **지정** 대화 상자가 활성화되어 있는 동안 응용 프로그램은 사용자를 사용자 지정 작업으로 제한하는 특수 모드에서 작동합니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarsCustomizeDialog` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 **명령** 페이지의 명령 목록 상자에 있는 도구 모음 단추를 바꾸고, **사용자 지정** 대화 상자를 사용하여 새 도구 모음을 만들 수 있도록 설정하고, **사용자 지정** 대화 상자를 표시하는 방법을 보여 주었습니다. 이 코드 조각은 IE [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

`CMFCToolBarsCustomizeDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxToolBar사용자 정의디아로그.h

## <a name="cmfctoolbarscustomizedialogaddbutton"></a><a name="addbutton"></a>CMFCToolBar사용자 정의디아로그::추가 단추

명령 페이지의 명령 목록에 도구 모음 **단추를 삽입합니다.**

```cpp
void AddButton(
    UINT uiCategoryId,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);

void AddButton(
    LPCTSTR lpszCategory,
    const CMFCToolBarButton& button,
    int iInsertBefore=-1);
```

### <a name="parameters"></a>매개 변수

*ui범주Id*<br/>
【인】 단추를 삽입할 범주 ID를 지정합니다.

*단추*<br/>
【인】 삽입할 단추를 지정합니다.

*i인서접전*<br/>
【인】 단추를 삽입하기 전에 도구 모음 단추의 0기반 인덱스를 지정합니다.

*lpsz범주*<br/>
【인】 단추를 삽입할 범주 문자열을 지정합니다.

### <a name="remarks"></a>설명

이 `AddButton` 메서드는 표준 명령 ID_FILE_MRU_FILE1 있는 단추, 허용되지 않는 명령(CMFCToolBar::IsCommand허용됨 참조) 및 더미 단추를 무시합니다. [CMFCToolBar::IsCommandPermitted](../../mfc/reference/cmfctoolbar-class.md#iscommandpermitted)

이 메서드는 단추의 런타임 `button` 클래스를 사용 하 여 (일반적으로 [CMFCToolBarButton 클래스)와](../../mfc/reference/cmfctoolbarbutton-class.md)동일한 형식의 새 개체를 만듭니다. 그런 다음 [CMFCToolBarButton::CopyFrom을](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom) 호출하여 단추의 데이터 멤버를 복사하고 지정된 범주에 복사본을 삽입합니다.

새 단추를 삽입 하면 `OnAddToCustomizePage` 알림을 받습니다.

-1이면 `iInsertBefore` 단추는 범주 목록에 추가됩니다. 그렇지 않으면 지정된 인덱스가 있는 항목 앞에 삽입됩니다.

### <a name="example"></a>예제

다음 예제에서는 `AddButton` `CMFCToolBarsCustomizeDialog` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 슬라이더 [샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_Slider#1](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_2.cpp)]

## <a name="cmfctoolbarscustomizedialogaddmenu"></a><a name="addmenu"></a>CMFCToolBar사용자 정의디아로그::추가 메뉴

리소스에서 메뉴를 로드 하 고 [호출 CMFCToolBars사용자 지정::AddMenuCommands](#addmenucommands) **명령** 페이지에서 명령 목록에 해당 메뉴를 추가 합니다.

```
BOOL AddMenu(UINT uiMenuResId);
```

### <a name="parameters"></a>매개 변수

*uiMenuResId*<br/>
【인】 로드할 메뉴의 리소스 ID를 지정합니다.

### <a name="return-value"></a>Return Value

메뉴가 성공적으로 추가된 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

`AddMenuCommands` *호출에서 bPopup은* FALSE입니다. 따라서 이 메서드는 명령 목록에 하위 메뉴가 포함된 메뉴 항목을 추가하지 않습니다. 이 메서드는 하위 메뉴의 메뉴 항목을 명령 목록에 추가합니다.

## <a name="cmfctoolbarscustomizedialogaddmenucommands"></a><a name="addmenucommands"></a>CMFCToolBar사용자 정의디아로그::추가 메뉴 명령

**명령** 페이지의 명령 목록에 항목을 추가하여 지정된 메뉴의 모든 항목을 나타냅니다.

```cpp
void AddMenuCommands(
    const CMenu* pMenu,
    BOOL bPopup,
    LPCTSTR lpszCategory=NULL,
    LPCTSTR lpszMenuPath=NULL);
```

### <a name="parameters"></a>매개 변수

*p메뉴*<br/>
【인】 추가할 CMenu 개체에 대한 포인터입니다.

*bPopup*<br/>
【인】 팝업 메뉴 항목을 명령 목록에 삽입할지 여부를 지정합니다.

*lpsz범주*<br/>
【인】 메뉴를 삽입할 범주의 이름입니다.

*lpszMenu패스*<br/>
【인】 명령이 **모든 범주** 목록에 표시될 때 이름에 추가되는 접두사입니다.

### <a name="remarks"></a>설명

메서드는 `AddMenuCommands` *pMenu의*모든 메뉴 항목을 반복합니다. 하위 메뉴를 포함 하지 않는 각 메뉴 항목에 대 한이 메서드는 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체를 만들고 [CMFCToolBarCustomizeDialog::AddButton](#addbutton) **메서드를** 호출 하는 명령 페이지의 명령 목록에 도구 모음 단추로 메뉴 항목을 추가 합니다. 이 과정에서 구분 기호는 무시됩니다.

*bPopup이* TRUE인 경우 하위 메뉴가 포함된 각 메뉴 항목에 대해 이 메서드는 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md) 개체를 만들고 호출하여 `AddButton`명령 목록에 삽입합니다. 그렇지 않으면 하위 메뉴가 포함된 메뉴 항목은 명령 목록에 표시되지 않습니다. 두 경우 모두 `AddMenuCommands` 하위 메뉴가 있는 메뉴 항목이 발생하면 자체를 재귀적으로 호출하여 하위 메뉴에 포인터를 *pMenu* 매개 변수로 전달하고 하위 메뉴의 *레이블을 lpszMenuPath에*추가합니다.

## <a name="cmfctoolbarscustomizedialogaddtoolbar"></a><a name="addtoolbar"></a>CMFCToolBar사용자 정의디아로그::추가 도구 바

리소스에서 도구 모음을 로드합니다. 그런 다음 메뉴의 각 명령에 대해 [CMFCToolBarsCustomizeDialog::AddButton](#addbutton) 메서드를 호출하여 지정된 범주 아래의 명령 페이지에서 명령 목록에 **단추를 삽입합니다.**

```
BOOL AddToolBar(
    UINT uiCategoryId,
    UINT uiToolbarResId);

BOOL AddToolBar(
    LPCTSTR lpszCategory,
    UINT uiToolbarResId);
```

### <a name="parameters"></a>매개 변수

*ui범주Id*<br/>
【인】 도구 모음을 추가할 범주의 리소스 ID를 지정합니다.

*uiToolbarResId*<br/>
【인】 명령 목록에 명령이 삽입된 도구 모음의 리소스 ID를 지정합니다.

*lpsz범주*<br/>
【인】 도구 모음을 추가할 범주의 이름을 지정합니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 거짓.

### <a name="example"></a>예제

다음 예제에서는 `AddToolBar` `CMFCToolBarsCustomizeDialog` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../overview/visual-cpp-samples.md)의 일부입니다.

[!code-cpp[NVC_MFC_WordPad#11](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_3.cpp)]

### <a name="remarks"></a>설명

각 명령을 나타내는 데 사용되는 컨트롤은 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체입니다. 도구 모음을 추가한 후 [CMFCToolBars사용자 지정Dialog::ReplaceButton](#replacebutton)을 호출하여 단추를 파생 형식의 컨트롤로 바꿀 수 있습니다.

## <a name="cmfctoolbarscustomizedialogchecktoolsvalidity"></a><a name="checktoolsvalidity"></a>CMFCToolBar사용자 정의디아로그::체크툴유효성

사용자 도구 목록의 유효성을 확인합니다.

```
virtual BOOL CheckToolsValidity(const CObList& lstTools);
```

### <a name="parameters"></a>매개 변수

*lstTools*<br/>
【인】 확인할 사용자 정의 도구 목록입니다.

### <a name="return-value"></a>Return Value

사용자 정의 도구 목록이 유효한 경우 TRUE를 반환합니다. 그렇지 않으면 거짓. 기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

프레임워크는 이 메서드를 호출하여 [CMFCToolBarsCustomizeDialog에서](#checktoolsvalidity)반환된 사용자 정의 도구를 나타내는 개체의 유효성을 확인합니다.

사용자가 대화 `CheckToolsValidity` 상자를 닫기 전에 `CMFCToolBarsCustomizeDialog` 사용자 도구의 유효성을 검사하려는 경우 파생된 클래스에서 메서드를 재정의합니다. 사용자가 대화 상자의 오른쪽 위 모서리에 있는 **닫기** 단추또는 대화 상자의 오른쪽 아래 모서리에 **Close라는** 레이블이 있는 단추를 클릭할 때 이 메서드가 FALSE를 반환하면 대화 상자가 닫히는 대신 **도구** 탭이 표시됩니다. 사용자가 **도구** 탭에서 멀리 이동하기 위해 탭을 클릭할 때 이 메서드가 FALSE를 반환하면 탐색이 수행되지 않습니다. 유효성 검사가 실패하게 된 문제를 사용자에게 알리는 적절한 메시지 상자를 표시해야 합니다.

## <a name="cmfctoolbarscustomizedialogcmfctoolbarscustomizedialog"></a><a name="cmfctoolbarscustomizedialog"></a>CMFCToolBars커스터마이즈디아로그::CMFCToolBar커스터마이즈디아로그

`CMFCToolBarsCustomizeDialog` 개체를 생성합니다.

```
CMFCToolBarsCustomizeDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bAutoSetFromMenus = FALSE,
    UINT uiFlags = (AFX_CUSTOMIZE_MENU_SHADOWS | AFX_CUSTOMIZE_TEXT_LABELS | AFX_CUSTOMIZE_MENU_ANIMATIONS | AFX_CUSTOMIZE_NOHELP),
    CList <CRuntimeClass*, CRuntimeClass*>* p listCustomPages = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd부모프레임*<br/>
【인】 상위 프레임에 대한 포인터입니다. 이 매개 변수는 NULL이 아니어야 합니다.

*b자동셋부터메뉴*<br/>
【인】 **명령** 페이지의 명령 목록에 모든 메뉴의 메뉴 명령을 추가할지 여부를 지정하는 부울 값입니다. 이 매개 변수가 TRUE이면 메뉴 명령이 추가됩니다. 그렇지 않으면 메뉴 명령이 추가되지 않습니다.

*uiFlags*<br/>
【인】 대화 상자의 동작에 영향을 주는 플래그의 조합입니다. 이 매개 변수는 다음 값 중 하나 이상일 수 있습니다.

- AFX_CUSTOMIZE_MENU_SHADOWS

- AFX_CUSTOMIZE_TEXT_LABELS

- AFX_CUSTOMIZE_MENU_ANIMATIONS

- AFX_CUSTOMIZE_NOHELP

- AFX_CUSTOMIZE_CONTEXT_HELP

- AFX_CUSTOMIZE_NOTOOLS

- AFX_CUSTOMIZE_MENUAMPERS

- AFX_CUSTOMIZE_NO_LARGE_ICONS

*plist 사용자 정의 페이지*<br/>
【인】 추가 사용자 지정 `CRuntimeClass` 페이지를 지정하는 개체 목록에 대한 포인터입니다.

### <a name="remarks"></a>설명

*plistCustomPages* 매개 변수는 추가 `CRuntimeClass` 사용자 지정 페이지를 지정 하는 개체 의 목록을 참조 합니다. 생성자는 [CRuntimeClass::CreateObject](../../mfc/reference/cruntimeclass-structure.md#createobject) 메서드를 사용하여 대화 상자에 더 많은 페이지를 추가합니다. 사용자 지정 대화 상자에 더 많은 페이지를 추가하는 예제는 CustomPages 샘플을 **참조하세요.**

*uiFlags* 매개 변수에서 전달할 수 있는 값에 대 한 자세한 내용은 [참조 CMFCToolBars사용자 지정Dialog::GetFlags](#getflags).

### <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarsCustomizeDialog` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 코드 조각은 사용자 [지정 페이지 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_CustomPages#3](../../mfc/reference/codesnippet/cpp/cmfctoolbarscustomizedialog-class_4.cpp)]

## <a name="cmfctoolbarscustomizedialogcreate"></a><a name="create"></a>CMFCToolBar사용자 정의디아로그::만들기

사용자 **지정** 대화 상자를 표시합니다.

```
virtual BOOL Create();
```

### <a name="return-value"></a>Return Value

사용자 지정 속성 시트가 성공적으로 만들어지면 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

클래스를 `Create` 완전히 초기화한 후에만 메서드를 호출합니다.

## <a name="cmfctoolbarscustomizedialogenableuserdefinedtoolbars"></a><a name="enableuserdefinedtoolbars"></a>CMFCToolBar사용자 정의디아로그::인에이블유저 정의 도구 모음

**사용자 지정** 대화 상자를 사용하여 새 도구 모음만들기를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void EnableUserDefinedToolbars(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
【인】 TRUE는 사용자 정의 도구 모음을 활성화합니다. FALSE를 사용하여 도구 모음을 사용하지 않도록 설정합니다.

### <a name="remarks"></a>설명

*bEnable가* TRUE이면 **새**것, **이름 바꾸기** 및 **삭제** 버튼이 도구 **모음** 페이지에 표시됩니다.

기본적으로 또는 *bEnable가* FALSE인 경우 이러한 단추는 표시되지 않으며 사용자는 새 도구 모음을 정의할 수 없습니다.

## <a name="cmfctoolbarscustomizedialogfillallcommandslist"></a><a name="fillallcommandslist"></a>CMFCToolBar사용자 정의디아로그::FillAllCommandsList

제공된 `CListBox` 개체를 **모든 명령** 범주의 명령으로 채웁니다.

```
virtual void FillAllCommandsList(CListBox& wndListOfCommands) const;
```

### <a name="parameters"></a>매개 변수

*wndListOfCommands*<br/>
【아웃】 채울 개체에 `CListBox` 대한 참조입니다.

### <a name="remarks"></a>설명

**모든 명령** 범주에는 모든 범주의 명령이 포함되어 있습니다. [CMFCToolBars사용자 정의Dialog::AddButton](#addbutton) 메서드는 제공 된 단추와 관련 된 명령을 모든 명령 범주에 추가 **합니다.**

이 메서드는 모든 `CListBox` **명령** 범주의 명령으로 채우기 전에 제공된 개체의 내용을 지웁니다.

클래스는 `CMFCMousePropertyPage` 이 메서드를 사용하여 두 번 클릭 이벤트 목록 상자를 채웁니다.

## <a name="cmfctoolbarscustomizedialogfillcategoriescombobox"></a><a name="fillcategoriescombobox"></a>CMFCToolBar사용자 정의디아로그::채우기 범주콤보박스

제공된 `CComboBox` 개체를 **사용자 지정** 대화 상자에 각 명령 범주의 이름으로 채웁니다.

```cpp
void FillCategoriesComboBox(
    CComboBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*wnd범주*<br/>
【아웃】 채울 개체에 `CComboBox` 대한 참조입니다.

*bAddEmpty*<br/>
【인】 명령이 없는 콤보 상자에 범주를 추가할지 여부를 지정하는 부울 값입니다. 이 매개 변수가 TRUE이면 빈 범주가 콤보 상자에 추가됩니다. 그렇지 않으면 빈 범주가 추가되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCToolBars사용자 지정과 같습니다.:FillCategoriesListBox](#fillcategorieslistbox) 메서드는 이 `CComboBox` 메서드가 개체와 함께 작동 한다는 점을 제외하여.

이 메서드는 `CComboBox` 개체를 채우기 전에 개체의 내용을 지우지 않습니다. 모든 명령 범주가 콤보 상자의 마지막 항목임을 **보장합니다.**

[CMFCToolBar사용자 지정Dialog::AddButton](#addbutton) 메서드를 사용 하 여 새 명령 범주를 추가할 수 있습니다. [CMFCToolBar사용자 정의Dialog::renameCategory](#renamecategory) 메서드를 사용 하 여 기존 범주의 이름을 변경할 수 있습니다.

및 `CMFCToolBarsKeyboardPropertyPage` `CMFCKeyMapDialog` 클래스는 이 메서드를 사용하여 키보드 매핑을 분류합니다.

## <a name="cmfctoolbarscustomizedialogfillcategorieslistbox"></a><a name="fillcategorieslistbox"></a>CMFCToolBar사용자 정의디아로그::채우기범주목록상자

제공된 `CListBox` 개체를 **사용자 지정** 대화 상자에 각 명령 범주의 이름으로 채웁니다.

```cpp
void FillCategoriesListBox(
    CListBox& wndCategory,
    BOOL bAddEmpty = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*wnd범주*<br/>
【아웃】 채울 개체에 `CListBox` 대한 참조입니다.

*bAddEmpty*<br/>
【인】 명령이 없는 목록 상자에 범주를 추가할지 여부를 지정하는 부울 값입니다. 이 매개 변수가 TRUE이면 빈 범주가 목록 상자에 추가됩니다. 그렇지 않으면 빈 범주가 추가되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 [CMFCToolBars사용자 지정과 같습니다.:FillCategoriesComboBox](#fillcategoriescombobox) 메서드는이 메서드가 `CListBox` 개체와 함께 작동 한다는 것을 제외 하 고 있습니다.

이 메서드는 `CListBox` 개체를 채우기 전에 개체의 내용을 지우지 않습니다. 모든 명령 범주가 목록 상자의 마지막 항목임을 **보장합니다.**

[CMFCToolBar사용자 지정Dialog::AddButton](#addbutton) 메서드를 사용 하 여 새 명령 범주를 추가할 수 있습니다. [CMFCToolBar사용자 정의Dialog::renameCategory](#renamecategory) 메서드를 사용 하 여 기존 범주의 이름을 변경할 수 있습니다.

클래스는 `CMFCToolBarsCommandsPropertyPage` 이 메서드를 사용하여 각 명령 범주와 연결된 명령 목록을 표시합니다.

## <a name="cmfctoolbarscustomizedialoggetcommandname"></a><a name="getcommandname"></a>CMFCToolBar사용자 정의디아로그::GetCommandName

지정된 명령 ID와 연결된 이름을 검색합니다.

```
LPCTSTR GetCommandName(UINT uiCmd) const;
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 검색할 명령의 ID입니다.

### <a name="return-value"></a>Return Value

지정된 명령 ID 또는 명령이 없는 경우 NULL과 연결된 이름입니다.

## <a name="cmfctoolbarscustomizedialoggetcountincategory"></a><a name="getcountincategory"></a>CMFCToolBars사용자 정의디아로그 ::GetCountIn카테고리

지정된 텍스트 레이블이 있는 제공된 목록의 항목 수를 검색합니다.

```
int GetCountInCategory(
    LPCTSTR lpszItemName,
    const CObList& lstCommands) const;
```

### <a name="parameters"></a>매개 변수

*lpszItemName*<br/>
【인】 일치할 텍스트 레이블입니다.

*lstCommands*<br/>
【인】 개체가 포함된 `CMFCToolBarButton` 목록에 대한 참조입니다.

### <a name="return-value"></a>Return Value

제공된 목록의 항목 수로 텍스트 레이블이 *lpszItemName*.

### <a name="remarks"></a>설명

제공된 개체 목록의 각 요소는 `CMFCToolBarButton`형식이어야 합니다. 이 메서드는 *lpszItemName* [을 CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext) 데이터 멤버와 비교합니다.

## <a name="cmfctoolbarscustomizedialoggetflags"></a><a name="getflags"></a>CMFCToolBar사용자 정의디아로그::겟플래그

대화 상자의 동작에 영향을 주는 플래그 집합을 검색합니다.

```
UINT GetFlags() const;
```

### <a name="return-value"></a>Return Value

대화 상자의 동작에 영향을 주는 플래그 집합입니다.

### <a name="remarks"></a>설명

이 메서드는 생성자에 전달 되는 *uiFlags* 매개 변수의 값을 검색 합니다. 반환 값은 다음 값 중 하나 이상일 수 있습니다.

|||
|-|-|
|AFX_CUSTOMIZE_MENU_SHADOWS|사용자가 메뉴의 그림자 모양을 지정할 수 있습니다.  |
|AFX_CUSTOMIZE_TEXT_LABELS|사용자가 도구 모음 단추 이미지 아래에 텍스트 레이블이 표시되는지 여부를 지정할 수 있습니다.  |
|AFX_CUSTOMIZE_MENU_ANIMATIONS|사용자가 메뉴 애니메이션 스타일을 지정할 수 있습니다.  |
|AFX_CUSTOMIZE_NOHELP|사용자 지정 대화 상자에서 도움말 단추를 제거합니다.  |
|AFX_CUSTOMIZE_CONTEXT_HELP|WS_EX_CONTEXTHELP 비주얼 스타일을 활성화합니다.  |
|AFX_CUSTOMIZE_NOTOOLS|사용자 지정 대화 상자에서 **도구** 페이지를 제거합니다. 이 플래그는 응용 프로그램에서 `CUserToolsManager` 클래스를 사용하는 경우 유효합니다.  |
|AFX_CUSTOMIZE_MENUAMPERS|단추 캡션에 앰퍼샌드 () **&** 문자를 포함하도록 허용합니다.  |
|AFX_CUSTOMIZE_NO_LARGE_ICONS|사용자 지정 대화 상자에서 큰 아이콘 옵션을 **제거합니다.**  |

WS_EX_CONTEXTHELP 비주얼 스타일에 대한 자세한 내용은 [확장 창 스타일을](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)참조하십시오.

## <a name="cmfctoolbarscustomizedialogonafterchangetool"></a><a name="onafterchangetool"></a>CMFCToolBar사용자 정의디아로그::온애프터체인지툴

사용자 도구가 발생한 직후 변경 된 변경에 응답 합니다.

```
virtual void OnAfterChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>매개 변수

*pSelTool*<br/>
【인, 아웃】 변경된 사용자 도구 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용자가 사용자 정의 도구의 속성을 변경할 때 이 메서드는 프레임워크에서 호출됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. 사용자 도구가 변경된 후 처리를 `CMFCToolBarsCustomizeDialog` 수행하기 위해 파생된 클래스에서 이 메서드를 재정의합니다.

## <a name="cmfctoolbarscustomizedialogonassignkey"></a><a name="onassignkey"></a>CMFCToolBar사용자 정의대화: ::OnAssign키

사용자가 정의할 때 바로 가기 키의 유효성을 검사합니다.

```
virtual BOOL OnAssignKey(ACCEL* pAccel);
```

### <a name="parameters"></a>매개 변수

*파셀 (것)과 함께*<br/>
【인, 아웃】 [ACCEL](/windows/win32/api/winuser/ns-winuser-accel) 구조체로 표현되는 제안된 키보드 어구에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

TRUE 키를 할당할 수 있는 경우, 또는 키를 할당할 수 없는 경우 FALSE입니다. 기본 구현은 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

사용자가 새 키보드 단축키를 할당할 때 추가 처리를 수행하거나 사용자가 정의할 때 키보드 단축키의 유효성을 검사하기 위해 파생 클래스에서 이 메서드를 재정의합니다. 바로 가기를 할당하지 않도록 하려면 FALSE를 반환합니다. 또한 메시지 상자를 표시하거나 키보드 단축성이 거부된 이유를 사용자에게 알려야 합니다.

## <a name="cmfctoolbarscustomizedialogonbeforechangetool"></a><a name="onbeforechangetool"></a>CMFCToolBar사용자 정의디아로그::OnBeforeChangeTool

사용자가 변경 을 적용하려고 할 때 사용자 도구에 대한 변경이 있을 때 사용자 지정 처리를 수행합니다.

```
virtual void OnBeforeChangeTool(CUserTool* pSelTool);
```

### <a name="parameters"></a>매개 변수

*pSelTool*<br/>
【인, 아웃】 대체할 사용자 도구 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

사용자 정의 도구의 속성이 변경될 때 이 메서드는 프레임워크에서 호출됩니다. 기본 구현은 아무 작업도 수행하지 않습니다. `OnBeforeChangeTool` *pSelTool에서* 사용하는 리소스를 `CMFCToolBarsCustomizeDialog` 해제하는 등 사용자 도구가 변경되기 전에 처리를 수행하려는 경우 파생된 클래스의 메서드를 재정의합니다.

## <a name="cmfctoolbarscustomizedialogonedittoolbarmenuimage"></a><a name="onedittoolbarmenuimage"></a>CMFCToolBar사용자 정의대화 : ::OnEdit도구 모음메뉴이미지

사용자가 도구 모음 단추 또는 메뉴 항목 아이콘을 사용자 지정할 수 있도록 이미지 편집기시작합니다.

```
virtual BOOL OnEditToolbarMenuImage(
    CWnd* pWndParent,
    CBitmap& bitmap,
    int nBitsPerPixel);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 상위 창에 대한 포인터입니다.

*비트맵*<br/>
【인】 편집할 비트맵 개체에 대한 참조입니다.

*n비트퍼픽셀*<br/>
【인】 픽셀당 비트의 비트맵 색상 해상도입니다.

### <a name="return-value"></a>Return Value

변경이 커밋되는 경우 TRUE; 그렇지 않으면 거짓. 기본 구현에는 대화 상자가 표시되고 사용자가 **확인을**클릭하면 TRUE가 반환되고 사용자가 **취소** 또는 **닫기** 단추를 클릭하면 FALSE가 반환됩니다.

### <a name="remarks"></a>설명

이 메서드는 사용자가 이미지 편집기 실행 할 때 프레임 워크에 의해 호출 됩니다. 기본 구현에는 [CMFCImageEditorDialog 클래스](../../mfc/reference/cmfcimageeditordialog-class.md) 대화 상자가 표시됩니다. 파생 `OnEditToolbarMenuImage` 클래스에서 재정의하여 사용자 지정 이미지 편집기를 사용합니다.

## <a name="cmfctoolbarscustomizedialogoninitdialog"></a><a name="oninitdialog"></a>CMFCToolBar사용자 정의대화 : ::InInitDialog

속성 시트 초기화를 보강하기 위해 재정의합니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

[CPropertySheet::OnInitDialog](../../mfc/reference/cpropertysheet-class.md#oninitdialog) 메서드를 호출한 결과입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 합니다 [CPropertySheet:OnInitDialog,](../../mfc/reference/cpropertysheet-class.md#oninitdialog) **닫기** 단추를 표시 하 여 대화 상자가 현재 화면 크기에 맞는지 확인 하 고 대화 상자의 왼쪽 아래 모서리에 **도움말** 단추를 이동 하 여 확장 합니다.

## <a name="cmfctoolbarscustomizedialogoninittoolspage"></a><a name="oninittoolspage"></a>CMFCToolBars사용자 정의대화 : ::IninitToolsPage

**도구** 페이지를 초기화하려고 하는 프레임워크에서 알림을 처리합니다.

```
virtual void OnInitToolsPage();
```

### <a name="remarks"></a>설명

기본 구현은 아무 작업도 수행하지 않습니다. 파생 클래스에서 이 메서드를 재정의하여 이 알림을 처리합니다.

## <a name="cmfctoolbarscustomizedialogpostncdestroy"></a><a name="postncdestroy"></a>CMFCToolBars커스터마이즈디아로그::PostNcDestroy

창이 소멸된 후 프레임워크에서 호출됩니다.

```
virtual void PostNcDestroy();
```

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램을 `CPropertySheet::PostNcDestroy`이전 모드로 복원하여 기본 클래스 구현을 확장합니다.

[CMFCToolBar사용자 정의Dialog:만들기](#create) 메서드는 사용자를 사용자 지정 작업으로 제한하는 특수 모드로 응용 프로그램을 넣습니다.

## <a name="cmfctoolbarscustomizedialogremovebutton"></a><a name="removebutton"></a>CMFCToolBar사용자 정의디아로그::제거 버튼

지정된 범주 또는 모든 범주에서 지정된 명령 ID가 있는 단추를 제거합니다.

```
int RemoveButton(
    UINT uiCategoryId,
    UINT uiCmdId);

int RemoveButton(
    LPCTSTR lpszCategory,
    UINT uiCmdId);
```

### <a name="parameters"></a>매개 변수

*ui범주Id*<br/>
【인】 단추를 제거할 범주 ID를 지정합니다.

*uiCmdId*<br/>
【인】 단추의 명령 ID를 지정합니다.

*lpsz범주*<br/>
【인】 단추를 제거할 범주의 이름을 지정합니다.

### <a name="return-value"></a>Return Value

제거된 단추의 0기반 인덱스 또는 지정된 명령 ID가 지정된 범주에서 찾을 수 없는 경우 -1입니다. *uiCategoryId가* -1이면 반환 값은 0입니다.

### <a name="remarks"></a>설명

모든 범주에서 단추를 제거하려면 이 메서드의 첫 번째 오버로드를 호출하고 *uiCategoryId를* -1로 설정합니다.

## <a name="cmfctoolbarscustomizedialogrenamecategory"></a><a name="renamecategory"></a>CMFCToolBar사용자 정의대화 : :이름 바꾸기범주

명령 페이지의 범주 목록 상자에서 범주 이름을 **바꿉니다.**

```
BOOL RenameCategory(
    LPCTSTR lpszCategoryOld,
    LPCTSTR lpszCategoryNew);
```

### <a name="parameters"></a>매개 변수

*lpsz범주이전*<br/>
【인】 변경할 범주 이름입니다.

*lpsz범주신규*<br/>
【인】 새 범주 이름입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 TRUE입니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

범주 이름은 고유해야 합니다.

## <a name="cmfctoolbarscustomizedialogreplacebutton"></a><a name="replacebutton"></a>CMFCToolBar사용자 정의Dialog::바꾸기 단추

명령 페이지의 명령 목록 상자에서 도구 모음 **단추를 바꿉습니다.**

```cpp
void ReplaceButton(
    UINT uiCmd,
    const CMFCToolBarButton& button);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 교체할 단추의 명령을 지정합니다.

*단추*<br/>
【인】 이전 단추를 대체하는 도구 모음 단추 개체에 대한 **const** 참조입니다.

### <a name="remarks"></a>설명

때 [CMFCToolBar사용자 정의Dialog::AddMenu,](#addmenu) [CMFCToolBar사용자 정의디아로그::AddMenu명령,](#addmenucommands)또는 [CMFCToolBar사용자 정의디아로그::AddToolBar](#addtoolbar) **명령** 페이지에 명령을 추가, 해당 명령은 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md) 개체의 형태로 (또는 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) 클래스 `AddMenuCommands`개체에 의해 추가 된 하위 메뉴 항목에 대 한). 또한 프레임워크는 이러한 세 가지 메서드를 호출하여 명령을 자동으로 추가합니다. 명령을 파생 된 형식으로 대신 표시 하려는 경우 `ReplaceButton` 호출 하 고 파생 된 형식의 단추를 전달 합니다.

### <a name="example"></a>예제

다음 예제에서는 `ReplaceButton` `CMFCToolBarsCustomizeDialog` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 Visual [Studio 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#34](../../mfc/codesnippet/cpp/cmfctoolbarscustomizedialog-class_5.cpp)]

## <a name="cmfctoolbarscustomizedialogsetusercategory"></a><a name="setusercategory"></a>CMFCToolBar사용자 정의디아로그::SetuserCategory

명령 페이지의 범주 목록에서 사용자 범주가 사용자 범주인 **범주를 지정합니다.** [CMFCToolBar사용자 정의 @:Create를](#create)호출하기 전에 이 함수를 호출해야 합니다.

```
BOOL SetUserCategory(LPCTSTR lpszCategory);
```

### <a name="parameters"></a>매개 변수

*lpsz범주*<br/>
【인】 범주의 이름입니다.

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

사용자 범주 설정은 현재 프레임워크에서 사용되지 않습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CProperty시트 클래스](../../mfc/reference/cpropertysheet-class.md)
