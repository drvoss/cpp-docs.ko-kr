---
title: CMenu 클래스
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: 5ec97d8cf039034078f29b38fb6a41d6ff9a5e53
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369975"
---
# <a name="cmenu-class"></a>CMenu 클래스

Windows `HMENU`의 캡슐화입니다.

## <a name="syntax"></a>구문

```
class CMenu : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C메뉴::C메뉴](#cmenu)|`CMenu` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|이 메뉴의 끝에 새 항목을 추가합니다.|
|[C메뉴::연결](#attach)|Windows 메뉴 핸들을 개체에 연결합니다. `CMenu`|
|[메뉴::검사 메뉴항목](#checkmenuitem)|팝업 메뉴의 메뉴 항목에서 확인 표시를 옆에 배치하거나 제거합니다.|
|[메뉴::체크메뉴라디오항목](#checkmenuradioitem)|메뉴 항목 옆에 라디오 단추를 배치하고 그룹의 다른 모든 메뉴 항목에서 라디오 단추를 제거합니다.|
|[C메뉴::만들기 메뉴](#createmenu)|빈 메뉴를 만들고 개체에 `CMenu` 연결합니다.|
|[C메뉴::만들기팝업메뉴](#createpopupmenu)|빈 팝업 메뉴를 만들고 개체에 `CMenu` 연결합니다.|
|[C메뉴::D수레테메뉴](#deletemenu)|메뉴에서 지정된 항목을 삭제합니다. 메뉴 항목에 연결된 팝업 메뉴가 있는 경우 팝업 메뉴의 핸들을 삭제하고 해당 메뉴에서 사용한 메모리를 해제합니다.|
|[C메뉴::D수레테템맵](#deletetempmap)|멤버 함수에 `CMenu` 의해 생성된 `FromHandle` 임시 개체를 삭제합니다.|
|[C메뉴::D에스트로이메뉴](#destroymenu)|`CMenu` 개체에 연결된 메뉴를 삭제하고 메뉴가 차지하는 메모리를 해제합니다.|
|[C메뉴::D에타치](#detach)|개체에서 Windows 메뉴 핸들을 `CMenu` 분리 하고 핸들을 반환 합니다.|
|[C메뉴::D로상품](#drawitem)|소유자가 그린 메뉴의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.|
|[C메뉴::사용 메뉴항목](#enablemenuitem)|메뉴 항목을 활성화, 비활성화 또는 어둡게(회색)합니다.|
|[C메뉴::시작 핸들](#fromhandle)|Windows 메뉴 핸들이 지정된 `CMenu` 개체에 대한 포인터를 반환합니다.|
|[C메뉴::GetDefault항목](#getdefaultitem)|지정된 메뉴의 기본 메뉴 항목을 결정합니다.|
|[C메뉴::겟메뉴컨텍스트도움말](#getmenucontexthelpid)|메뉴와 연결된 도움말 컨텍스트 ID를 검색합니다.|
|[C메뉴:::GetMenuInfo](#getmenuinfo)|특정 메뉴에 대한 정보를 검색합니다.|
|[메뉴::겟메뉴항목카운트](#getmenuitemcount)|팝업 또는 최상위 메뉴의 항목 수를 결정합니다.|
|[메뉴:::GetMenuItemID](#getmenuitemid)|지정된 위치에 있는 메뉴 항목의 메뉴 항목 식별자를 가져옵니다.|
|[메뉴:::겟메뉴항목정보](#getmenuiteminfo)|메뉴 항목에 대한 정보를 검색합니다.|
|[C메뉴::겟메뉴상태](#getmenustate)|지정된 메뉴 항목의 상태 또는 팝업 메뉴의 항목 수를 반환합니다.|
|[C메뉴::겟메뉴스트링](#getmenustring)|지정된 메뉴 항목의 레이블을 검색합니다.|
|[메뉴::GetSafeHmenu](#getsafehmenu)|이 `CMenu` `m_hMenu` 개체에 의해 래핑된 반환합니다.|
|[C메뉴::GetSubMenu](#getsubmenu)|팝업 메뉴에 대한 포인터를 검색합니다.|
|[CMenu::InsertMenu](#insertmenu)|지정된 위치에 새 메뉴 항목을 삽입하여 다른 항목을 메뉴 아래로 이동합니다.|
|[C메뉴::삽입메뉴항목](#insertmenuitem)|메뉴에서 지정된 위치에 새 메뉴 항목을 삽입합니다.|
|[C메뉴::로드메뉴](#loadmenu)|실행 파일 파일에서 메뉴 리소스를 로드하고 `CMenu` 개체에 연결합니다.|
|[C메뉴::로드메뉴 간접](#loadmenuindirect)|메모리에 있는 메뉴 템플릿에서 메뉴를 로드 하 `CMenu` 고 개체에 연결 합니다.|
|[C메뉴::측정 항목](#measureitem)|소유자가 그린 메뉴를 만들 때 메뉴 차원을 결정하기 위해 프레임워크에서 호출합니다.|
|[CMenu::ModifyMenu](#modifymenu)|지정된 위치에서 기존 메뉴 항목을 변경합니다.|
|[C메뉴::제거메뉴](#removemenu)|지정된 메뉴에서 연결된 팝업 메뉴가 있는 메뉴 항목을 삭제합니다.|
|[C메뉴::설정기본항목](#setdefaultitem)|지정된 메뉴의 기본 메뉴 항목을 설정합니다.|
|[C메뉴::세트메뉴컨텍스트도움말](#setmenucontexthelpid)|메뉴와 연결될 도움말 컨텍스트 ID를 설정합니다.|
|[C메뉴::세트메뉴정보](#setmenuinfo)|특정 메뉴에 대한 정보를 설정합니다.|
|[C메뉴::세트메뉴항목비트맵](#setmenuitembitmaps)|지정된 확인 표시 비트맵을 메뉴 항목과 연결합니다.|
|[C메뉴::세트메뉴항목정보](#setmenuiteminfo)|메뉴 항목에 대한 정보를 변경합니다.|
|[C메뉴::트랙팝메뉴](#trackpopupmenu)|지정된 위치에 부동 팝업 메뉴를 표시하고 팝업 메뉴에서 항목 선택을 추적합니다.|
|[C메뉴:::트랙팝메뉴엑스](#trackpopupmenuex)|지정된 위치에 부동 팝업 메뉴를 표시하고 팝업 메뉴에서 항목 선택을 추적합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[C메뉴::연산자 HMENU](#operator_hmenu)|메뉴 개체의 핸들을 검색합니다.|
|[C메뉴::연산자 !=](#operator_neq)|두 메뉴 개체가 같지 않은지 확인합니다.|
|[C메뉴::연산자 ==](#operator_eq_eq)|두 메뉴 개체가 동일한지 확인합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[C메뉴::m_hMenu](#m_hmenu)|개체에 연결된 Windows 메뉴에 대한 `CMenu` 핸들을 지정합니다.|

## <a name="remarks"></a>설명

메뉴를 생성, 추적, 업데이트 및 삭제하기 위한 멤버 기능을 제공합니다.

스택 `CMenu` 프레임에 개체를 로컬로 만든 `CMenu`다음 멤버 함수를 호출하여 필요에 따라 새 메뉴를 조작합니다. 다음으로 [CWnd::SetMenu를](../../mfc/reference/cwnd-class.md#setmenu) 호출하여 메뉴를 창으로 설정한 다음 `CMenu` 개체의 [Detach](#detach) 멤버 함수를 호출합니다. 멤버 `CWnd::SetMenu` 함수는 창의 메뉴를 새 메뉴로 설정하고, 메뉴 변경을 반영하도록 창을 다시 그려지며, 메뉴의 소유권을 창에 전달합니다. `Detach` 로컬 변수가 범위를 `CMenu` 벗어나면 `CMenu` `CMenu` 개체 소멸자가 더 이상 소유하지 않는 메뉴를 삭제하려고 시도하지 않도록 개체에서 HMENU를 분리하는 호출입니다. 창이 소멸되면 메뉴 자체가 자동으로 소멸됩니다.

[LoadMenuIndirect](#loadmenuindirect) 멤버 함수를 사용하여 메모리의 템플릿에서 메뉴를 만들 수 있지만 [LoadMenu](#loadmenu) 호출을 통해 리소스에서 만든 메뉴가 보다 쉽게 유지 관리되고 메뉴 편집기에서 메뉴 리소스 자체를 만들고 수정할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cmenuappendmenu"></a><a name="appendmenu"></a>C메뉴::부속메뉴

메뉴 끝에 새 항목을 추가합니다.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nFlags*<br/>
새 메뉴 항목이 메뉴에 추가될 때새 메뉴 항목의 상태에 대한 정보를 지정합니다. 주석 섹션에 나열된 하나 이상의 값으로 구성됩니다.

*니드뉴아이템*<br/>
새 메뉴 항목의 명령 ID를 지정하거나 *nFlags가* MF_POPUP 설정된 경우 팝업 `HMENU`메뉴의 메뉴 핸들() 을 지정합니다. *nFlags가* MF_SEPARATOR 설정된 경우 *nIDNewItem* 매개 변수는 무시됩니다(필요하지 않음).

*lpszNewItem*<br/>
새 메뉴 항목의 내용을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *lpszNewItem을* 해석하는 데 사용됩니다.

|nFlags|lpszNew항목의 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램에서 메뉴 항목과 연결된 추가 데이터를 유지 관리하는 데 사용할 수 있는 응용 프로그램에서 제공한 32비트 값을 포함합니다. 이 32비트 값은 WM_MEASUREITEM 메시지를 처리하고 WM_DRAWITEM 때 응용 프로그램에서 사용할 수 있습니다. 값은 해당 메시지와 `itemData` 함께 제공된 구조의 멤버에 저장됩니다.|
|MF_STRING|null 종료 된 문자열에 대 한 포인터를 포함 합니다. 이것이 기본 해석입니다.|
|MF_SEPARATOR|*lpszNewItem* 매개 변수는 무시됩니다(필요하지 않음).|

*pBmp*<br/>
메뉴 항목으로 사용할 `CBitmap` 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 *nFlags에서*값을 설정하여 메뉴 항목의 상태를 지정할 수 있습니다. *nIDNewItem* 팝업 메뉴를 지정하면 추가되는 메뉴의 일부가 됩니다. 해당 메뉴가 소멸되면 추가된 메뉴도 소멸됩니다. 충돌을 방지하려면 추가된 메뉴를 `CMenu` 개체에서 분리해야 합니다. MF_STRING 및 MF_OWNERDRAW 비트맵 버전에 `AppendMenu`대해 유효하지 않습니다.

다음 목록은 *nFlags에서*설정할 수 있는 플래그에 대해 설명합니다.

- MF_CHECKED 항목 옆에 기본 확인 표시를 배치하는 MF_UNCHECKED 있는 토글로 작동합니다. 응용 프로그램이 체크 표시 비트맵을 [제공하면(SetMenuItemBitbitmaps](#setmenuitembitmaps) 멤버 함수 참조) "확인 표시" 비트맵이 표시됩니다.

- MF_UNCHECKED 항목 옆에 있는 확인 표시를 제거하는 MF_CHECKED 있는 토글로 작동합니다. 응용 프로그램이 체크 표시 비트맵을 `SetMenuItemBitmaps` 제공하면(멤버 함수 참조) "체크 표시 끄기" 비트맵이 표시됩니다.

- MF_DISABLED 메뉴 항목을 선택할 수 없지만 흐리게 하지 않도록 설정합니다.

- MF_ENABLED 메뉴 항목을 선택하고 흐리게 표시된 상태에서 복원할 수 있도록 설정합니다.

- MF_GRAYED 메뉴 항목을 선택하지 못하도록 비활성화하고 흐리게 합니다.

- MF_MENUBARBREAK 정적 메뉴의 새 줄이나 팝업 메뉴의 새 열에 항목을 배치합니다. 새 팝업 메뉴 열은 이전 열과 세로 구분선으로 구분됩니다.

- MF_MENUBREAK 정적 메뉴의 새 줄이나 팝업 메뉴의 새 열에 항목을 배치합니다. 열 사이에 구분선이 배치되지 않습니다.

- MF_OWNERDRAW 항목이 소유자-그리기 항목임을 지정합니다. 메뉴가 처음으로 표시되면 메뉴를 소유하는 창은 메뉴 항목의 높이와 너비를 검색하는 WM_MEASUREITEM 메시지를 받습니다. WM_DRAWITEM 메시지는 소유자가 메뉴 항목의 시각적 모양을 업데이트해야 할 때마다 전송되는 메시지입니다. 최상위 메뉴 항목에는 이 옵션이 적용되지 않습니다.

- MF_POPUP 메뉴 항목에 연결된 팝업 메뉴가 있음을 지정합니다. ID 매개 변수는 항목과 연결될 팝업 메뉴에 대한 핸들을 지정합니다. 최상위 팝업 메뉴 또는 계층적 팝업 메뉴를 팝업 메뉴 항목에 추가하는 데 사용됩니다.

- MF_SEPARATOR 수평 구분선을 그립니다. 팝업 메뉴에서만 사용할 수 있습니다. 이 줄은 흐리게 표시하거나 사용하지 않도록 설정하거나 강조 표시할 수 없습니다. 다른 매개 변수는 무시됩니다.

- MF_STRING 메뉴 항목이 문자 문자열임을 지정합니다.

다음 각 그룹에는 상호 배타적이고 함께 사용할 수 없는 플래그가 나열됩니다.

- MF_DISABLED, MF_ENABLED 및 MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR 및 비트맵 버전

- MF_MENUBARBREAK 및 MF_MENUBREAK

- MF_CHECKED 및 MF_UNCHECKED

창에 있는 메뉴가 변경될 때마다(창이 표시되는지 여부) 응용 프로그램은 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)를 호출해야 합니다.

### <a name="example"></a>예제

  [CMenu::CreateMenu](#createmenu)의 예제를 참조하십시오.

## <a name="cmenuattach"></a><a name="attach"></a>C메뉴::연결

기존 Windows 메뉴를 개체에 `CMenu` 연결합니다.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
Windows 메뉴에 대한 핸들을 지정합니다.

### <a name="return-value"></a>Return Value

작업이 성공한 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메뉴가 개체에 이미 연결되어 있는 경우 `CMenu` 이 함수를 호출해서는 안 됩니다. 메뉴 핸들은 데이터 `m_hMenu` 멤버에 저장됩니다.

조작하려는 메뉴가 이미 창과 연결되어 있는 경우 [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) 함수를 사용하여 메뉴에 대한 핸들을 얻을 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenucheckmenuitem"></a><a name="checkmenuitem"></a>메뉴::검사 메뉴항목

팝업 메뉴의 메뉴 항목에서 확인 표시를 추가하거나 체크 표시를 제거합니다.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>매개 변수

*니드체크아이템*<br/>
*nCheck에서*결정한 대로 검사할 메뉴 항목을 지정합니다.

*nCheck*<br/>
메뉴 항목을 확인하는 방법과 메뉴에서 항목의 위치를 확인하는 방법을 지정합니다. *nCheck* 매개 변수는 MF_CHECKED 또는 MF_BYPOSITION 또는 MF_BYCOMMAND 플래그가 있는 MF_UNCHECKED 조합일 수 있습니다. 이러한 플래그는 비트별 OR 연산자사용을 사용하여 결합할 수 있습니다. 다음과 같은 의미가 있습니다.

- MF_BYCOMMAND 매개 변수가 기존 메뉴 항목의 명령 ID를 제공한다고 지정합니다. 이것이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.

- MF_CHECKED 항목 옆에 기본 확인 표시를 배치하는 MF_UNCHECKED 있는 토글로 작동합니다.

- MF_UNCHECKED 항목 옆에 있는 확인 표시를 제거하는 MF_CHECKED 있는 토글로 작동합니다.

### <a name="return-value"></a>Return Value

항목의 이전 상태: MF_CHECKED 또는 MF_UNCHECKED 또는 0xFFFFFFFF 메뉴 항목이 없는 경우.

### <a name="remarks"></a>설명

*nIDCheckItem* 매개 변수는 수정할 항목을 지정합니다.

*nIDCheckItem* 매개 변수는 팝업 메뉴 항목과 메뉴 항목을 식별할 수 있습니다. 팝업 메뉴 항목을 확인하는 데 특별한 단계가 필요하지 않습니다. 최상위 메뉴 항목은 확인할 수 없습니다. 팝업 메뉴 항목과 연결된 메뉴 항목 식별자가 없으므로 위치에 따라 확인해야 합니다.

### <a name="example"></a>예제

  [CMenu::GetMenuState에](#getmenustate)대한 예제를 참조하십시오.

## <a name="cmenucheckmenuradioitem"></a><a name="checkmenuradioitem"></a>메뉴::체크메뉴라디오항목

지정된 메뉴 항목을 확인하고 라디오 항목으로 만듭니다.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*니드퍼스트*<br/>
라디오 단추 그룹의 첫 번째 메뉴 *항목(nFlags*값에 따라 ID 또는 오프셋으로 지정).

*니드라스트*<br/>
라디오 단추 그룹의 마지막 메뉴 *항목(nFlags*값에 따라 ID 또는 오프셋으로 지정).

*니드 아이템*<br/>
라디오 버튼으로 검사할 그룹의 항목을 *지정합니다(nFlags*값에 따라 ID 또는 오프셋).

*nFlags*<br/>
다음과 같은 방법으로 *nIDFirst,* *nIDLast*및 *nIDItem의* 해석을 지정합니다.

|nFlags|해석|
|------------|--------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 0

### <a name="remarks"></a>설명

동시에 이 함수는 연결된 그룹의 다른 모든 메뉴 항목을 체크 아웃하고 해당 항목에 대한 무선 항목 유형 플래그를 지웁습니다. 확인된 항목은 확인 표시 비트맵 대신 라디오 버튼(또는 글머리 기호) 비트맵을 사용하여 표시됩니다.

### <a name="example"></a>예제

  [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range)에 대한 예제를 참조하십시오.

## <a name="cmenucmenu"></a><a name="cmenu"></a>C메뉴::C메뉴

빈 메뉴를 만들고 개체에 `CMenu` 연결합니다.

```
CMenu();
```

### <a name="remarks"></a>설명

만들거나 로드 멤버 함수 중 하나를 호출할 때까지 메뉴가 만들어지지 않습니다.`CMenu:`

- [만들기 메뉴](#createmenu)

- [만들기팝업메뉴](#createpopupmenu)

- [로드 메뉴](#loadmenu)

- [로드메뉴 간접](#loadmenuindirect)

- [연결](#attach)

## <a name="cmenucreatemenu"></a><a name="createmenu"></a>C메뉴::만들기 메뉴

메뉴를 만들고 개체에 `CMenu` 연결합니다.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Return Value

메뉴가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메뉴가 처음에는 비어 있습니다. 메뉴 항목은 또는 `AppendMenu` `InsertMenu` 멤버 함수를 사용하여 추가할 수 있습니다.

메뉴가 창에 할당되면 창이 소멸되면 자동으로 소멸됩니다.

종료하기 전에 메뉴가 창에 할당되지 않은 경우 응용 프로그램은 메뉴와 연결된 시스템 리소스를 해제해야 합니다. 응용 프로그램은 [DestroyMenu](#destroymenu) 멤버 함수를 호출하여 메뉴를 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

## <a name="cmenucreatepopupmenu"></a><a name="createpopupmenu"></a>C메뉴::만들기팝업메뉴

팝업 메뉴를 만들고 개체에 `CMenu` 연결합니다.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Return Value

팝업 메뉴가 성공적으로 생성된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메뉴가 처음에는 비어 있습니다. 메뉴 항목은 또는 `AppendMenu` `InsertMenu` 멤버 함수를 사용하여 추가할 수 있습니다. 응용 프로그램은 기존 메뉴 또는 팝업 메뉴에 팝업 메뉴를 추가할 수 있습니다. 멤버 `TrackPopupMenu` 함수는 이 메뉴를 부동 팝업 메뉴로 표시하고 팝업 메뉴의 선택 항목을 추적하는 데 사용할 수 있습니다.

메뉴가 창에 할당되면 창이 소멸되면 자동으로 소멸됩니다. 메뉴가 기존 메뉴에 추가되면 해당 메뉴가 소멸되면 자동으로 소멸됩니다.

종료하기 전에 메뉴가 창에 할당되지 않은 경우 응용 프로그램은 팝업 메뉴와 연결된 시스템 리소스를 해제해야 합니다. 응용 프로그램은 [DestroyMenu](#destroymenu) 멤버 함수를 호출하여 메뉴를 해제합니다.

### <a name="example"></a>예제

  [CMenu::CreateMenu](#createmenu)의 예제를 참조하십시오.

## <a name="cmenudeletemenu"></a><a name="deletemenu"></a>C메뉴::D수레테메뉴

메뉴에서 항목을 삭제합니다.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
*nFlags에*의해 결정된 대로 삭제할 메뉴 항목을 지정합니다.

*nFlags*<br/>
*nPosition를* 다음과 같은 방식으로 해석하는 데 사용됩니다.

|nFlags|nPosition의 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 항목에 연결된 팝업 메뉴가 있는 `DeleteMenu` 경우 팝업 메뉴의 핸들을 삭제하고 팝업 메뉴에서 사용하는 메모리를 해제합니다.

창에 있는 메뉴가 변경될 때마다(창이 표시되는지 여부) 응용 프로그램은 [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)를 호출해야 합니다.

### <a name="example"></a>예제

  [CWnd::GetMenu에](../../mfc/reference/cwnd-class.md#getmenu)대한 예제를 참조하십시오.

## <a name="cmenudeletetempmap"></a><a name="deletetempmap"></a>C메뉴::D수레테템맵

`CWinApp` 유휴 시간 처리기에 의해 자동으로 호출되어 `CMenu` [FromHandle](#fromhandle) 멤버 함수에서 만든 임시 개체를 삭제합니다.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>설명

`DeleteTempMap`개체를 삭제하기 전에 임시 `CMenu` 개체에 연결된 Windows `CMenu` 메뉴 개체를 분리합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

## <a name="cmenudestroymenu"></a><a name="destroymenu"></a>C메뉴::D에스트로이메뉴

사용된 메뉴 및 Windows 리소스를 삭제합니다.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Return Value

메뉴가 소멸된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메뉴가 삭제되기 `CMenu` 전에 개체에서 분리됩니다. Windows `DestroyMenu` 함수는 `CMenu` 소멸자에서 자동으로 호출됩니다.

### <a name="example"></a>예제

  [CMenu::CreateMenu](#createmenu)의 예제를 참조하십시오.

## <a name="cmenudetach"></a><a name="detach"></a>C메뉴::D에타치

개체에서 Windows 메뉴를 분리하고 핸들을 반환합니다. `CMenu`

```
HMENU Detach();
```

### <a name="return-value"></a>Return Value

성공한 경우 Windows 메뉴에 HMENU 형식의 핸들이 있습니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

데이터 `m_hMenu` 멤버가 NULL로 설정됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

## <a name="cmenudrawitem"></a><a name="drawitem"></a>C메뉴::D로상품

소유자가 그린 메뉴의 시각적 측면이 변경될 때 프레임워크에서 호출됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
필요한 도면 유형에 대한 정보가 포함된 [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 구조에 대한 포인터입니다.

### <a name="remarks"></a>설명

`DRAWITEMSTRUCT` 구조의 멤버는 `itemAction` 수행할 드로잉 작업을 정의합니다. 이 멤버 함수를 재정의하여 소유자-그리기 객체에 대한 그리기를 구현합니다. `CMenu` 응용 프로그램은 이 멤버 함수가 종료되기 전에 *lpDrawItemStruct에* 제공된 디스플레이 컨텍스트에 대해 선택된 모든 GDI(그래픽 장치 인터페이스) 개체를 복원해야 합니다.

구조에 대한 설명은 [CWnd::OnDrawItem을](../../mfc/reference/cwnd-class.md#ondrawitem) `DRAWITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

다음 코드는 MFC [CTRLTEST](../../overview/visual-cpp-samples.md) 샘플에서 나온 것입니다.

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

## <a name="cmenuenablemenuitem"></a><a name="enablemenuitem"></a>C메뉴::사용 메뉴항목

메뉴 항목을 활성화, 비활성화 또는 어둡게 합니다.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>매개 변수

*nID인에이블아이템*<br/>
*nEnable*에 의해 결정된 대로 사용할 메뉴 항목을 지정합니다. 이 매개 변수는 팝업 메뉴 항목과 표준 메뉴 항목을 지정할 수 있습니다.

*n사용 가능*<br/>
취할 작업을 지정합니다. MF_DISABLED, MF_ENABLED 또는 MF_GRAYED 조합하여 MF_BYCOMMAND 또는 MF_BYPOSITION 수 있습니다. 이러한 값은 비트별 OR 연산자사용을 사용하여 결합할 수 있습니다. 이러한 값에는 다음과 같은 의미가 있습니다.

- MF_BYCOMMAND 매개 변수가 기존 메뉴 항목의 명령 ID를 제공한다고 지정합니다. 이것이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.

- MF_DISABLED 메뉴 항목을 선택할 수 없지만 흐리게 하지 않도록 설정합니다.

- MF_ENABLED 메뉴 항목을 선택하고 흐리게 표시된 상태에서 복원할 수 있도록 설정합니다.

- MF_GRAYED 메뉴 항목을 선택하지 못하도록 비활성화하고 흐리게 합니다.

### <a name="return-value"></a>Return Value

이전 상태(MF_DISABLED, MF_ENABLED 또는 MF_GRAYED) 또는 -1(유효하지 않은 경우).

### <a name="remarks"></a>설명

[CreateMenu](#createmenu), [InsertMenu,](#insertmenu) [수정 메뉴](#modifymenu)및 [LoadMenuIndirect](#loadmenuindirect) 멤버 함수는 메뉴 항목의 상태(사용, 사용 안 함 또는 흐리게)를 설정할 수도 있습니다.

MF_BYPOSITION 값을 사용하려면 응용 프로그램에서 `CMenu`올바른 을 사용해야 합니다. 메뉴 `CMenu` 모음을 사용하는 경우 최상위 메뉴 항목(메뉴 모음의 항목)이 영향을 받습니다. 팝업 또는 중첩된 팝업 메뉴에서 항목의 상태를 위치에 따라 설정하려면 응용 `CMenu` 프로그램에서 팝업 메뉴의 상태를 지정해야 합니다.

응용 프로그램이 MF_BYCOMMAND 플래그를 지정하면 Windows는 `CMenu`다음에 종속된 모든 팝업 메뉴 항목을 확인합니다. 따라서 중복 메뉴 항목이 없으면 `CMenu` 메뉴 모음을 사용하는 것으로 충분합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

## <a name="cmenufromhandle"></a><a name="fromhandle"></a>C메뉴::시작 핸들

Windows 핸들이 `CMenu` 지정된 개체에 대한 포인터를 메뉴에 반환합니다.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
메뉴에 대한 Windows 핸들입니다.

### <a name="return-value"></a>Return Value

일시적이거나 `CMenu` 영구적일 수 있는 포인터입니다.

### <a name="remarks"></a>설명

개체가 `CMenu` Windows 메뉴 개체에 아직 연결되어 있지 `CMenu` 않으면 임시 개체가 만들어지고 첨부됩니다.

이 `CMenu` 임시 개체는 다음에 응용 프로그램이 이벤트 루프에서 유휴 시간을 가지며 모든 임시 개체가 삭제될 때까지만 유효합니다.

### <a name="example"></a>예제

  [CMenu::CreateMenu](#createmenu)의 예제를 참조하십시오.

## <a name="cmenugetdefaultitem"></a><a name="getdefaultitem"></a>C메뉴::GetDefault항목

지정된 메뉴의 기본 메뉴 항목을 결정합니다.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*gmdiFlags*<br/>
함수가 메뉴 항목을 검색하는 방법을 지정하는 값입니다. 이 매개 변수는 none, 하나 또는 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|기본 항목이 하위 메뉴를 여는 항목인 경우 함수는 해당 하위 메뉴에서 재귀적으로 검색하는 것입니다. 하위 메뉴에 기본 항목이 없는 경우 반환 값은 하위 메뉴를 여는 항목을 식별합니다.<br /><br /> 기본적으로 함수는 하위 메뉴를 여는 항목인지 여부에 관계없이 지정된 메뉴에서 첫 번째 기본 항목을 반환합니다.|
|GMDI_USEDISABLED|비활성화된 경우에도 함수가 기본 항목을 반환하도록 지정합니다.<br /><br /> 기본적으로 이 함수는 비활성화된 항목이나 회색 항목을 건너뜁니다.|

*fByPos*<br/>
메뉴 항목의 식별자 또는 해당 위치를 검색할지 여부를 지정하는 값입니다. 이 매개 변수가 FALSE이면 식별자가 반환됩니다. 그렇지 않으면 위치가 반환됩니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 메뉴 항목의 식별자 또는 위치입니다. 함수가 실패하면 반환 값은 - 1입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 함수 [GetMenuDefaultItem의](/windows/win32/api/winuser/nf-winuser-getmenudefaultitem)동작을 구현합니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenugetmenucontexthelpid"></a><a name="getmenucontexthelpid"></a>C메뉴::겟메뉴컨텍스트도움말

와 연결된 컨텍스트 도움말 `CMenu`ID를 검색합니다.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Return Value

컨텍스트 도움말 ID가 `CMenu` 현재 연결되어 있는 경우 그렇지 않으면 0.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenugetmenuinfo"></a><a name="getmenuinfo"></a>C메뉴:::GetMenuInfo

메뉴에 대한 정보를 검색합니다.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>매개 변수

*lpcmi*<br/>
메뉴에 대한 정보가 포함된 [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 0이 아닙니다. 그렇지 않으면 반환 값이 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 메뉴에 대한 정보를 검색합니다.

## <a name="cmenugetmenuitemcount"></a><a name="getmenuitemcount"></a>메뉴::겟메뉴항목카운트

팝업 또는 최상위 메뉴의 항목 수를 결정합니다.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Return Value

함수가 성공한 경우 메뉴의 항목 수입니다. 그렇지 않으면 -1.

### <a name="example"></a>예제

  [CWnd::GetMenu에](../../mfc/reference/cwnd-class.md#getmenu)대한 예제를 참조하십시오.

## <a name="cmenugetmenuitemid"></a><a name="getmenuitemid"></a>메뉴:::GetMenuItemID

*nPos에*의해 정의된 위치에 있는 메뉴 항목의 메뉴 항목 식별자를 가져옵니다.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
ID가 검색되는 메뉴 항목의 위치(0기준)를 지정합니다.

### <a name="return-value"></a>Return Value

함수가 성공한 경우 팝업 메뉴에서 지정된 항목의 항목 ID입니다. 지정된 항목이 팝업 메뉴인 경우(팝업 메뉴 내의 항목이 아닌) 반환 값은 -1입니다. *nPos가* SEPARATOR 메뉴 항목에 해당하는 경우 반환 값은 0입니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenugetmenuiteminfo"></a><a name="getmenuiteminfo"></a>메뉴:::겟메뉴항목정보

메뉴 항목에 대한 정보를 검색합니다.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*u항목*<br/>
에 대한 정보를 얻을 수있는 메뉴 항목의 식별자 또는 위치. 이 매개 변수의 의미는 `ByPos`의 값에 따라 다릅니다.

*lpMenu항목정보*<br/>
메뉴에 대한 정보가 포함된 Windows SDK에 설명된 대로 [MENUITEMINFO에](/windows/win32/api/winuser/ns-winuser-menuiteminfow)대한 포인터입니다.

*fByPos*<br/>
의 의미를 지정하는 `nIDItem`값입니다. 기본적으로 `ByPos` false는 uItem이 메뉴 항목 식별자임을 나타냅니다. FALSE로 설정되지 않은 경우 `ByPos` 메뉴 항목 위치를 나타냅니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 0이 아닙니다. 함수가 실패하면 반환 값은 0입니다. 확장 오류 정보를 얻으려면 Windows SDK에 설명된 대로 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)사용합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 함수 [GetMenuItemInfo의](/windows/win32/api/winuser/nf-winuser-getmenuiteminfow)동작을 구현합니다. 의 MFC 구현에서는 `GetMenuItemInfo`메뉴에 대한 핸들을 사용하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

## <a name="cmenugetmenustate"></a><a name="getmenustate"></a>C메뉴::겟메뉴상태

지정된 메뉴 항목의 상태 또는 팝업 메뉴의 항목 수를 반환합니다.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
nFlags에 의해 결정된 메뉴 항목 ID를 *지정합니다.*

*nFlags*<br/>
*nID의*특성을 지정합니다. 다음 값 중 하나일 수 있습니다.

- MF_BYCOMMAND 매개 변수가 기존 메뉴 항목의 명령 ID를 제공한다고 지정합니다. 이것이 기본값입니다.

- MF_BYPOSITION 매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.

### <a name="return-value"></a>Return Value

지정된 항목이 없는 경우 0xFFFFFF값입니다. *nId가* 팝업 메뉴를 식별하는 경우 고급 바이트에는 팝업 메뉴의 항목 수가 포함되고 낮은 순서바이트에는 팝업 메뉴와 연결된 메뉴 플래그가 포함됩니다. 그렇지 않으면 반환 값은 다음 목록의 값의 마스크(부울 OR)입니다(이 마스크는 *nId가* 식별하는 메뉴 항목의 상태를 설명합니다).

- MF_CHECKED 항목 옆에 기본 확인 표시를 배치하는 MF_UNCHECKED 있는 토글로 작동합니다. 응용 프로그램에서 확인 표시 비트맵을 `SetMenuItemBitmaps` 제공하면(멤버 함수 참조) "확인 표시" 비트맵이 표시됩니다.

- MF_DISABLED 메뉴 항목을 선택할 수 없지만 흐리게 하지 않도록 설정합니다.

- MF_ENABLED 메뉴 항목을 선택하고 흐리게 표시된 상태에서 복원할 수 있도록 설정합니다. 이 상수의 값은 0입니다. 응용 프로그램은 이 값을 사용할 때 실패에 대해 0에 대해 테스트해서는 안 됩니다.

- MF_GRAYED 메뉴 항목을 선택하지 못하도록 비활성화하고 흐리게 합니다.

- MF_MENUBARBREAK 정적 메뉴의 새 줄이나 팝업 메뉴의 새 열에 항목을 배치합니다. 새 팝업 메뉴 열은 이전 열과 세로 구분선으로 구분됩니다.

- MF_MENUBREAK 정적 메뉴의 새 줄이나 팝업 메뉴의 새 열에 항목을 배치합니다. 열 사이에 구분선이 배치되지 않습니다.

- MF_SEPARATOR 수평 구분선을 그립니다. 팝업 메뉴에서만 사용할 수 있습니다. 이 줄은 흐리게 표시하거나 사용하지 않도록 설정하거나 강조 표시할 수 없습니다. 다른 매개 변수는 무시됩니다.

- MF_UNCHECKED 항목 옆에 있는 확인 표시를 제거하는 MF_CHECKED 있는 토글로 작동합니다. 응용 프로그램이 체크 표시 비트맵을 `SetMenuItemBitmaps` 제공하면(멤버 함수 참조) "체크 표시 끄기" 비트맵이 표시됩니다. 이 상수의 값은 0입니다. 응용 프로그램은 이 값을 사용할 때 실패에 대해 0에 대해 테스트해서는 안 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

## <a name="cmenugetmenustring"></a><a name="getmenustring"></a>C메뉴::겟메뉴스트링

지정된 메뉴 항목의 레이블을 지정된 버퍼에 복사합니다.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>매개 변수

*니드 아이템*<br/>
*nFlags*의 값에 따라 메뉴 항목의 정수 식별자 또는 메뉴 항목의 오프셋을 지정합니다.

*lpString*<br/>
레이블을 받을 버퍼를 가리킵니다.

*rString*<br/>
복사된 메뉴 `CString` 문자열을 수신하는 개체에 대한 참조입니다.

*n맥스카운트*<br/>
복사할 레이블의 최대 길이(문자)를 지정합니다. 레이블이 *nMaxCount에*지정된 최대값보다 길면 추가 문자가 잘립니다.

*nFlags*<br/>
*nIDItem* 매개 변수의 해석을 지정합니다. 다음 값 중 하나일 수 있습니다.

|nFlags|nID항목 해석|
|------------|-------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

### <a name="return-value"></a>Return Value

null 종사자를 포함하지 않고 버퍼에 복사된 실제 문자 수를 지정합니다.

### <a name="remarks"></a>설명

*nMaxCount* 매개 변수는 문자열을 종료하는 null 문자를 수용하기 위해 레이블의 문자 수보다 큰 매개 변수여야 합니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenugetsafehmenu"></a><a name="getsafehmenu"></a>메뉴::GetSafeHmenu

이 `CMenu` 개체 또는 NULL`CMenu` 포인터로 래핑된 HMENU를 반환합니다.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>예제

  [CMenu::LoadMenu](#loadmenu)의 예제를 참조하십시오.

## <a name="cmenugetsubmenu"></a><a name="getsubmenu"></a>C메뉴::GetSubMenu

팝업 메뉴의 `CMenu` 개체를 검색합니다.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>매개 변수

*Npos*<br/>
메뉴에 포함된 팝업 메뉴의 위치를 지정합니다. 위치 값은 첫 번째 메뉴 항목의 0에서 시작합니다. 이 함수에서는 팝업 메뉴의 식별자를 사용할 수 없습니다.

### <a name="return-value"></a>Return Value

지정된 위치에 `CMenu` 팝업 `m_hMenu` 메뉴가 있는 경우 멤버가 팝업 메뉴에 대한 핸들을 포함하는 개체에 대한 포인터입니다. 그렇지 않으면 NULL. 개체가 `CMenu` 없으면 임시 개체가 만들어집니다. 반환된 포인터를 `CMenu` 저장하면 안 됩니다.

### <a name="example"></a>예제

  [CMenu::TrackPopupMenu에](#trackpopupmenu)대한 예제를 참조하십시오.

## <a name="cmenuinsertmenu"></a><a name="insertmenu"></a>C메뉴::삽입 메뉴

*nPosition에서* 지정한 위치에 새 메뉴 항목을 삽입하고 다른 항목을 메뉴 아래로 이동합니다.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
새 메뉴 항목을 삽입할 메뉴 항목을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *nPosition를* 해석하는 데 사용할 수 있습니다.

|nFlags|nPosition의 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다. *nPosition가* -1이면 새 메뉴 항목이 메뉴 끝에 추가됩니다.|

*nFlags*<br/>
*nPosition가* 해석되는 방법을 지정하고 메뉴에 추가될 때 새 메뉴 항목의 상태에 대한 정보를 지정합니다. 설정할 수 있는 플래그 목록은 [AppendMenu](#appendmenu) 멤버 함수를 참조하십시오. 둘 이상의 값을 지정하려면 비트별 OR 연산자(or)를 사용하여 MF_BYCOMMAND 또는 MF_BYPOSITION 플래그와 결합합니다.

*니드뉴아이템*<br/>
새 메뉴 항목의 명령 ID를 지정하거나 *nFlags가* MF_POPUP 설정된 경우 팝업 메뉴의 메뉴 핸들(HMENU)을 지정합니다. *nFlags가* MF_SEPARATOR 설정된 경우 *nIDNewItem* 매개 변수는 무시됩니다(필요하지 않음).

*lpszNewItem*<br/>
새 메뉴 항목의 내용을 지정합니다. *nFlags는* 다음과 같은 방법으로 *lpszNewItem을* 해석하는 데 사용할 수 있습니다.

|nFlags|lpszNew항목의 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램에서 메뉴 항목과 연결된 추가 데이터를 유지 관리하는 데 사용할 수 있는 응용 프로그램에서 제공한 32비트 값을 포함합니다. 이 32비트 값은 [WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem) 및 `itemData` WM_DRAWITEM 메시지에서 제공하는 구조체의 멤버에서 응용 프로그램에서 사용할 수 [있습니다.](/windows/win32/Controls/wm-drawitem) 이러한 메시지는 메뉴 항목이 처음에 표시되거나 변경될 때 전송됩니다.|
|MF_STRING|null 종료 된 문자열에 대 한 긴 포인터를 포함 합니다. 이것이 기본 해석입니다.|
|MF_SEPARATOR|*lpszNewItem* 매개 변수는 무시됩니다(필요하지 않음).|

*pBmp*<br/>
메뉴 항목으로 사용할 `CBitmap` 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 *nFlags에서*값을 설정하여 메뉴 항목의 상태를 지정할 수 있습니다.

창에 있는 메뉴가 변경될 때마다(창이 표시되는지 여부) 응용 프로그램이 `CWnd::DrawMenuBar`을 호출해야 합니다.

*nIDNewItem* 팝업 메뉴를 지정하면 삽입되는 메뉴의 일부가 됩니다. 해당 메뉴가 소멸되면 삽입된 메뉴도 소멸됩니다. 삽입된 메뉴는 충돌을 방지하기 `CMenu` 위해 개체에서 분리되어야 합니다.

활성 다중 문서 인터페이스(MDI) 자식 창이 최대화되고 응용 프로그램이 이 함수를 호출하고 MF_BYPOSITION 플래그를 지정하여 MDI 응용 프로그램의 메뉴에 팝업 메뉴를 삽입하면 메뉴가 예상보다 멀리 왼쪽으로 삽입됩니다. 활성 MDI 자식 창의 컨트롤 메뉴가 MDI 프레임 창의 메뉴 모음의 첫 번째 위치에 삽입되어 발생합니다. 메뉴를 올바르게 배치하려면 응용 프로그램이 사용할 위치 값에 1을 추가해야 합니다. 응용 프로그램은 WM_MDIGETACTIVE 메시지를 사용하여 현재 활성 자식 창이 최대화되었는지 여부를 결정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

## <a name="cmenuinsertmenuitem"></a><a name="insertmenuitem"></a>C메뉴::삽입메뉴항목

메뉴에서 지정된 위치에 새 메뉴 항목을 삽입합니다.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*u항목*<br/>
Windows SDK의 [InsertMenu항목에서](/windows/win32/api/winuser/nf-winuser-insertmenuitemw) *uItem에* 대한 설명을 참조하십시오.

*lpMenu항목정보*<br/>
Windows SDK에서 `InsertMenuItem` *lpmii에* 대한 설명을 참조하십시오.

*fByPos*<br/>
Windows SDK의 `InsertMenuItem` *fByPosition* 에 대한 설명을 참조하십시오.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명된 [InsertMenuItem을](/windows/win32/api/winuser/nf-winuser-insertmenuitemw)래핑합니다.

## <a name="cmenuloadmenu"></a><a name="loadmenu"></a>C메뉴::로드메뉴

응용 프로그램의 실행 파일에서 메뉴 리소스를 로드 하 고 `CMenu` 개체에 연결 합니다.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
로드할 메뉴 리소스의 이름이 포함된 null 종료 된 문자열을 가리킵니다.

*nIDResource*<br/>
로드할 메뉴 리소스의 메뉴 ID를 지정합니다.

### <a name="return-value"></a>Return Value

메뉴 리소스가 성공적으로 로드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

종료하기 전에 메뉴가 창에 할당되지 않은 경우 응용 프로그램은 메뉴와 연결된 시스템 리소스를 해제해야 합니다. 응용 프로그램은 [DestroyMenu](#destroymenu) 멤버 함수를 호출하여 메뉴를 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

## <a name="cmenuloadmenuindirect"></a><a name="loadmenuindirect"></a>C메뉴::로드메뉴 간접

메모리의 메뉴 템플릿에서 리소스를 로드하고 개체에 `CMenu` 연결합니다.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>매개 변수

*lpMenu템플릿*<br/>
메뉴 템플릿(단일 [MENUITEMTEMPLATEHEADER](/windows/win32/api/winuser/ns-winuser-menuitemtemplateheader) 구조및 하나 이상의 [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) 구조의 컬렉션)을 가리킵니다. 이 두 구조에 대한 자세한 내용은 Windows SDK를 참조하십시오.

### <a name="return-value"></a>Return Value

메뉴 리소스가 성공적으로 로드된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

메뉴 템플릿은 하나 이상의 [MENUITEMTEMPLATE](/windows/win32/api/winuser/ns-winuser-menuitemtemplate) 구조의 컬렉션 다음에 헤더이며, 각 구조에는 하나 이상의 메뉴 항목과 팝업 메뉴가 포함될 수 있습니다.

버전 번호는 0이어야 합니다.

플래그에는 `mtOption` 팝업 목록의 마지막 항목과 기본 목록의 마지막 항목에 대한 MF_END 포함되어야 합니다. 다른 `AppendMenu` 플래그에 대한 멤버 함수를 참조하십시오. `mtId` MF_POPUP 지정될 때 는 MENUITEMTEMPLATE 구조에서 `mtOption`멤버를 생략해야 합니다.

MENUITEMTEMPLATE 구조에 할당된 공간은 메뉴 `mtString` 항목의 이름을 null 종료 문자열로 포함할 수 있을 만큼 커야 합니다.

종료하기 전에 메뉴가 창에 할당되지 않은 경우 응용 프로그램은 메뉴와 연결된 시스템 리소스를 해제해야 합니다. 응용 프로그램은 [DestroyMenu](#destroymenu) 멤버 함수를 호출하여 메뉴를 해제합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

## <a name="cmenum_hmenu"></a><a name="m_hmenu"></a>C메뉴::m_hMenu

개체에 연결된 Windows 메뉴의 HMENU 핸들을 지정합니다. `CMenu`

```
HMENU m_hMenu;
```

### <a name="example"></a>예제

  [CMenu::LoadMenu](#loadmenu)의 예제를 참조하십시오.

## <a name="cmenumeasureitem"></a><a name="measureitem"></a>C메뉴::측정 항목

소유자-그리기 스타일이 있는 메뉴가 만들어지면 프레임워크에서 호출됩니다.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpMeasureItemStruct*<br/>
구조에 대한 `MEASUREITEMSTRUCT` 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 이 멤버 함수는 아무 것도 수행하지 않습니다. 이 멤버 함수를 `MEASUREITEMSTRUCT` 재정의하고 구조를 입력하여 Windows에 메뉴 크기를 알립니다.

구조에 대한 설명은 [CWnd::OnMeasureItem을](../../mfc/reference/cwnd-class.md#onmeasureitem) `MEASUREITEMSTRUCT` 참조하십시오.

### <a name="example"></a>예제

다음 코드는 MFC [CTRLTEST](../../overview/visual-cpp-samples.md) 샘플에서 나온 것입니다.

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

## <a name="cmenumodifymenu"></a><a name="modifymenu"></a>C메뉴::수정 메뉴

*nPosition*에서 지정한 위치에서 기존 메뉴 항목을 변경합니다.

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
변경할 메뉴 항목을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *nPosition를* 해석하는 데 사용할 수 있습니다.

|nFlags|nPosition의 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

*nFlags*<br/>
*nPosition가* 해석되는 방법을 지정하고 메뉴 항목에 대한 변경 사항에 대한 정보를 제공합니다. 설정할 수 있는 플래그 목록은 [AppendMenu](#appendmenu) 멤버 함수를 참조하십시오.

*니드뉴아이템*<br/>
수정된 메뉴 항목의 명령 ID를 지정하거나 *nFlags가* MF_POPUP 설정된 경우 팝업 메뉴의 메뉴 핸들(HMENU)을 지정합니다. *nFlags가* MF_SEPARATOR 설정된 경우 *nIDNewItem* 매개 변수는 무시됩니다(필요하지 않음).

*lpszNewItem*<br/>
새 메뉴 항목의 내용을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *lpszNewItem을* 해석하는 데 사용할 수 있습니다.

|nFlags|lpszNew항목의 해석|
|------------|-----------------------------------|
|MF_OWNERDRAW|응용 프로그램에서 메뉴 항목과 연결된 추가 데이터를 유지 관리하는 데 사용할 수 있는 응용 프로그램에서 제공한 32비트 값을 포함합니다. 이 32비트 값은 MF_MEASUREITEM 및 MF_DRAWITEM 처리할 때 응용 프로그램에서 사용할 수 있습니다.|
|MF_STRING|null 종료 된 문자열 또는 `CString`에 대한 긴 포인터가 포함되어 있습니다.|
|MF_SEPARATOR|*lpszNewItem* 매개 변수는 무시됩니다(필요하지 않음).|

*pBmp*<br/>
메뉴 항목으로 사용할 `CBitmap` 개체를 가리킵니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 *nFlags에서*값을 설정하여 메뉴 항목의 새 상태를 지정합니다. 이 함수가 메뉴 항목과 연결된 팝업 메뉴를 대체하면 이전 팝업 메뉴가 삭제되고 팝업 메뉴에서 사용되는 메모리가 해제됩니다.

*nIDNewItem* 팝업 메뉴를 지정하면 삽입되는 메뉴의 일부가 됩니다. 해당 메뉴가 소멸되면 삽입된 메뉴도 소멸됩니다. 삽입된 메뉴는 충돌을 방지하기 `CMenu` 위해 개체에서 분리되어야 합니다.

창에 있는 메뉴가 변경될 때마다(창이 표시되는지 여부) 응용 프로그램이 `CWnd::DrawMenuBar`을 호출해야 합니다. 기존 메뉴 항목의 속성을 변경하려면 `CheckMenuItem` 및 `EnableMenuItem` 멤버 함수를 사용하는 것이 훨씬 빠릅니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenuoperator-hmenu"></a><a name="operator_hmenu"></a>C메뉴::연산자 HMENU

이 연산자를 사용하여 `CMenu` 개체의 핸들을 검색합니다.

```
operator HMENU() const;
```

### <a name="return-value"></a>Return Value

성공하면 개체의 핸들; `CMenu` 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

핸들을 사용하여 Windows API를 직접 호출할 수 있습니다.

## <a name="cmenuoperator-"></a><a name="operator_neq"></a>C메뉴::연산자 !=

두 메뉴가 논리적으로 같지 않은지 확인합니다.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>매개 변수

*메뉴*<br/>
비교를 위한 `CMenu` 개체입니다.

### <a name="remarks"></a>설명

왼쪽의 메뉴 개체가 오른쪽의 메뉴 개체와 같지 않은지 테스트합니다.

## <a name="cmenuoperator-"></a><a name="operator_eq_eq"></a>C메뉴::연산자 ==

두 메뉴가 논리적으로 동일한지 확인합니다.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>매개 변수

*메뉴*<br/>
비교를 위한 `CMenu` 개체입니다.

### <a name="remarks"></a>설명

왼쪽의 메뉴 개체가 HMENU 값과 오른쪽의 메뉴 개체와 동일한지 테스트합니다.

## <a name="cmenuremovemenu"></a><a name="removemenu"></a>C메뉴::제거메뉴

메뉴에서 연결된 팝업 메뉴가 있는 메뉴 항목을 삭제합니다.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
제거할 메뉴 항목을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *nPosition를* 해석하는 데 사용할 수 있습니다.

|nFlags|nPosition의 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

*nFlags*<br/>
*nPosition가* 해석되는 방법을 지정합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

팝업 메뉴의 핸들이 파괴되지 않으므로 메뉴를 다시 사용할 수 있습니다. 이 함수를 호출하기 전에 `GetSubMenu` 응용 프로그램은 멤버 함수를 `CMenu` 호출하여 다시 사용할 팝업 개체를 검색할 수 있습니다.

창에 있는 메뉴가 변경될 때마다(창이 표시되는지 여부) 응용 프로그램은 `CWnd::DrawMenuBar`을 호출해야 합니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenusetdefaultitem"></a><a name="setdefaultitem"></a>C메뉴::설정기본항목

지정된 메뉴의 기본 메뉴 항목을 설정합니다.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*u항목*<br/>
새 기본 메뉴 항목의 식별자 또는 위치 또는 기본 항목없음의 경우 -1입니다. 이 매개 변수의 의미는 *fByPos*의 값에 따라 다릅니다.

*fByPos*<br/>
*uItem의*의미를 지정하는 값 . 이 매개 변수가 FALSE인 경우 *uItem은* 메뉴 항목 식별자입니다. 그렇지 않으면 메뉴 항목 위치입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 0이 아닙니다. 함수가 실패하면 반환 값은 0입니다. 확장 오류 정보를 얻으려면 Windows SDK에 설명된 대로 Win32 함수 [GetLastError를](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)사용합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명된 대로 Win32 함수 [SetMenuDefaultItem의](/windows/win32/api/winuser/nf-winuser-setmenudefaultitem)동작을 구현합니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenusetmenucontexthelpid"></a><a name="setmenucontexthelpid"></a>C메뉴::세트메뉴컨텍스트도움말

컨텍스트 도움말 ID를 `CMenu`에 연결합니다.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>매개 변수

*dwContextHelpId*<br/>
컨텍스트 도움말 ID를 `CMenu`와 연결합니다.

### <a name="return-value"></a>Return Value

성공하면 영하지 않은; 그렇지 않으면 0

### <a name="remarks"></a>설명

메뉴의 모든 항목은 이 식별자를 공유합니다 — 도움말 컨텍스트 식별자를 개별 메뉴 항목에 연결할 수 없습니다.

### <a name="example"></a>예제

  [CMenu::InsertMenu의](#insertmenu)예제를 참조하십시오.

## <a name="cmenusetmenuinfo"></a><a name="setmenuinfo"></a>C메뉴::세트메뉴정보

메뉴에 대한 정보를 설정합니다.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>매개 변수

*lpcmi*<br/>
메뉴에 대한 정보가 포함된 [MENUINFO](/windows/win32/api/winuser/ns-winuser-menuinfo) 구조에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 반환 값은 0이 아닙니다. 그렇지 않으면 반환 값이 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 메뉴에 대한 특정 정보를 설정합니다.

## <a name="cmenusetmenuitembitmaps"></a><a name="setmenuitembitmaps"></a>C메뉴::세트메뉴항목비트맵

지정된 비트맵을 메뉴 항목과 연결합니다.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>매개 변수

*nPosition*<br/>
변경할 메뉴 항목을 지정합니다. *nFlags* 매개 변수는 다음과 같은 방법으로 *nPosition를* 해석하는 데 사용할 수 있습니다.

|nFlags|nPosition의 해석|
|------------|---------------------------------|
|MF_BYCOMMAND|매개 변수가 기존 메뉴 항목의 명령 ID를 제공되도록 지정합니다. MF_BYCOMMAND 설정되지 MF_BYPOSITION 없는 경우 기본값입니다.|
|MF_BYPOSITION|매개 변수가 기존 메뉴 항목의 위치를 지정합니다. 첫 번째 항목은 위치 0에 있습니다.|

*nFlags*<br/>
*nPosition가* 해석되는 방법을 지정합니다.

*pBmpUnchecked*<br/>
선택되지 않은 메뉴 항목에 사용할 비트맵을 지정합니다.

*pBmp확인*<br/>
선택된 메뉴 항목에 사용할 비트맵을 지정합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 항목을 선택하거나 선택하지 않았는지 여부에 관계없이 Windows는 메뉴 항목 옆에 적절한 비트맵을 표시합니다.

*pBmpUnchecked* 또는 *pBmpChecked가* NULL인 경우 Windows는 해당 특성의 메뉴 항목 옆에 아무 것도 표시되지 않습니다. 두 매개 변수가 NULL인 경우 Windows는 항목을 검사할 때 기본 확인 표시를 사용하고 항목을 선택하지 않으면 확인 표시를 제거합니다.

메뉴가 소멸되면 이러한 비트맵은 소멸되지 않습니다. 응용 프로그램을 파괴해야 합니다.

Windows `GetMenuCheckMarkDimensions` 함수는 메뉴 항목에 사용되는 기본 확인 표시의 크기를 검색합니다. 응용 프로그램은 이러한 값을 사용하여 이 함수와 함께 제공되는 비트맵에 적합한 크기를 결정합니다. 크기를 조정하고 비트맵을 만든 다음 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

## <a name="cmenusetmenuiteminfo"></a><a name="setmenuiteminfo"></a>C메뉴::세트메뉴항목정보

메뉴 항목에 대한 정보를 변경합니다.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>매개 변수

*u항목*<br/>
Windows SDK의 [SetMenuItemInfo에서](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow) *uItem에* 대한 설명을 참조하십시오.

*lpMenu항목정보*<br/>
Windows SDK에서 `SetMenuItemInfo` *lpmii에* 대한 설명을 참조하십시오.

*fByPos*<br/>
Windows SDK의 `SetMenuItemInfo` *fByPosition* 에 대한 설명을 참조하십시오.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명된 [SetMenuItemInfo를](/windows/win32/api/winuser/nf-winuser-setmenuiteminfow)래핑합니다.

## <a name="cmenutrackpopupmenu"></a><a name="trackpopupmenu"></a>C메뉴::트랙팝메뉴

지정된 위치에 부동 팝업 메뉴를 표시하고 팝업 메뉴에서 항목 선택을 추적합니다.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>매개 변수

*nFlags*<br/>
화면 위치 및 마우스 위치 플래그를 지정합니다. 사용 가능한 플래그 목록은 [TrackPopupMenu를](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) 참조하십시오.

*x*<br/>
팝업 메뉴의 화면 좌표에서 가로 위치를 지정합니다. *nFlags* 매개 변수의 값에 따라 메뉴는 이 위치를 기준으로 왼쪽 정렬, 오른쪽 정렬 또는 가운데에 배치될 수 있습니다.

*Y*<br/>
화면 상단의 화면 좌표에서 수직 위치를 지정합니다.

*pWnd*<br/>
팝업 메뉴를 소유하는 창을 식별합니다. TPM_NONOTIFY 플래그가 지정되더라도 이 매개 변수는 NULL이 될 수 없습니다. 이 창은 메뉴에서 모든 WM_COMMAND 메시지를 수신합니다. Windows 버전 3.1 이상에서는 창이 반환될 때까지 `TrackPopupMenu` WM_COMMAND 메시지를 받지 못합니다. Windows 3.0에서 창은 반환하기 `TrackPopupMenu` 전에 WM_COMMAND 메시지를 수신합니다.

*Lprect*<br/>
무시됩니다.

### <a name="return-value"></a>Return Value

이 메서드는 Windows SDK에서 [TrackPopupMenu를](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) 호출하는 결과를 반환합니다.

### <a name="remarks"></a>설명

부동 팝업 메뉴는 화면의 아무 곳에나 나타날 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

## <a name="cmenutrackpopupmenuex"></a><a name="trackpopupmenuex"></a>C메뉴:::트랙팝메뉴엑스

지정된 위치에 부동 팝업 메뉴를 표시하고 팝업 메뉴에서 항목 선택을 추적합니다.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>매개 변수

*후플래그*<br/>
확장 메뉴에 대한 다양한 기능을 지정합니다. 모든 값과 그 의미의 목록은 [TrackPopupMenuEx를](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)참조하십시오.

*x*<br/>
팝업 메뉴의 화면 좌표에서 가로 위치를 지정합니다.

*Y*<br/>
화면 상단의 화면 좌표에서 수직 위치를 지정합니다.

*pWnd*<br/>
팝업 메뉴를 소유하고 생성된 메뉴에서 메시지를 받는 창에 대한 포인터입니다. 이 창은 현재 응용 프로그램의 모든 창일 수 있지만 NULL일 수는 없습니다. *fuFlags* 매개 변수에서 TPM_NONOTIFY 지정하면 함수가 *pWnd*로 메시지를 보내지 않습니다. 함수는 WM_COMMAND 메시지를 수신하려면 *pWnd가* 가리키는 창에 대해 반환해야 합니다.

*lptpm*<br/>
메뉴가 겹치지 않아야 하는 화면 영역을 지정하는 [TPMPARAMS](/windows/win32/api/winuser/ns-winuser-tpmparams) 구조에 대한 포인터입니다. 이 매개 변수는 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

*fuFlags* 매개 변수에 TPM_RETURNCMD 지정하는 경우 반환 값은 사용자가 선택한 항목의 메뉴 항목 식별자입니다. 사용자가 선택하지 않고 메뉴를 취소하거나 오류가 발생하는 경우 반환 값은 0입니다.

*fuFlags* 매개 변수에 TPM_RETURNCMD 지정하지 않으면 함수가 성공하면 반환 값이 0이 되고 실패할 경우 0이 됩니다. 확장 오류 정보를 얻으려면 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)를 호출합니다.

### <a name="remarks"></a>설명

부동 팝업 메뉴는 화면의 아무 곳에나 나타날 수 있습니다. 팝업 메뉴를 만들 때 오류 처리에 대한 자세한 내용은 [TrackPopupMenuEx](/windows/win32/api/winuser/nf-winuser-trackpopupmenuex)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 다이나메뉴](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
