---
title: C컨텍스트 메뉴관리자 클래스
ms.date: 11/04/2016
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
ms.openlocfilehash: c676355ebf44d6cc02bfa66ac870757627ae5a58
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754810"
---
# <a name="ccontextmenumanager-class"></a>C컨텍스트 메뉴관리자 클래스

개체는 `CContextMenuManager` 바로 가기 메뉴(컨텍스트 메뉴라고도 함)를 관리합니다.

## <a name="syntax"></a>구문

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C컨텍스트 메뉴 관리자::C컨텍스트 메뉴 관리자](#ccontextmenumanager)|`CContextMenuManager` 개체를 생성합니다.|
|`CContextMenuManager::~CContextMenuManager`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C컨텍스트 메뉴 관리자::추가 메뉴](#addmenu)|새 바로 가기 메뉴를 추가합니다.|
|[CContextMenu관리자::GetMenuById](#getmenubyid)|제공된 리소스 ID와 연결된 메뉴에 핸들을 반환합니다.|
|[CContext메뉴 관리자::GetMenuByName](#getmenubyname)|제공된 메뉴 이름과 일치하는 메뉴에 핸들을 반환합니다.|
|[C컨텍스트 메뉴 관리자::GetMenu 이름](#getmenunames)|메뉴 이름 목록을 반환합니다.|
|[C컨텍스트 메뉴 관리자::로드 상태](#loadstate)|Windows 레지스트리에 저장된 바로 가기 메뉴를 로드합니다.|
|[C컨텍스트 메뉴 관리자::재설정 상태](#resetstate)|컨텍스트 메뉴 관리자에서 바로 가기 메뉴를 지웁힙으로 지웁힙으로 지웁힙입니다.|
|[C컨텍스트 메뉴 관리자::저장 상태](#savestate)|바로 가기 메뉴를 Windows 레지스트리에 저장합니다.|
|[C컨텍스트 메뉴 관리자::SetDont닫기 활성 메뉴](#setdontcloseactivemenu)|새 바로 `CContextMenuManager` 가기 메뉴가 표시될 때 활성 바로 가기 메뉴를 닫는지 여부를 제어합니다.|
|[C컨텍스트 메뉴 관리자::쇼팝메뉴](#showpopupmenu)|지정된 바로 가기 메뉴를 표시합니다.|
|[C컨텍스트 메뉴 관리자::트랙팝메뉴](#trackpopupmenu)|지정된 바로 가기 메뉴를 표시합니다. 선택한 메뉴 명령의 인덱스를 반환합니다.|

## <a name="remarks"></a>설명

`CContextMenuManager`바로 가기 메뉴를 관리하고 일관된 모양을 가지고 있는지 확인합니다.

개체를 `CContextMenuManager` 수동으로 만들지 않아야 합니다. 응용 프로그램의 프레임워크는 `CContextMenuManager` 개체를 만듭니다. 그러나 응용 프로그램이 초기화될 때 [CWinAppEx::InitContextMenuManager를](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) 호출해야 합니다. 컨텍스트 관리자를 초기화한 후 [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) 메서드를 사용하여 응용 프로그램에 대한 컨텍스트 관리자에 대한 포인터를 가져옵니다.

을 호출하여 `AddMenu`런타임에 바로 가기 메뉴를 만들 수 있습니다. 사용자 입력을 먼저 받지 않고 메뉴를 표시하려면 을 호출합니다. `ShowPopupMenu` `TrackPopupMenu`는 메뉴를 만들고 사용자 입력을 기다릴 때 사용됩니다. `TrackPopupMenu`은 사용자가 아무 것도 선택하지 않고 종료된 경우 선택한 명령의 인덱스 또는 0을 반환합니다.

또한 `CContextMenuManager` Windows 레지스트리에 상태를 저장하고 로드할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CContextMenuManager` 개체에 메뉴를 추가하는 방법과 `CContextMenuManager` 개체에 새 팝업 메뉴가 표시될 때 활성 팝업 메뉴를 닫지 않는 방법을 보여 줍니다. 이 코드 조각은 사용자 [지정 페이지 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxcontextmenumanager.h

## <a name="ccontextmenumanageraddmenu"></a><a name="addmenu"></a>C컨텍스트 메뉴 관리자::추가 메뉴

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)에 새 바로 가기 메뉴를 추가합니다.

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>매개 변수

*uiMenuNameResId*<br/>
【인】 새 메뉴의 이름을 포함하는 문자열의 리소스 ID입니다.

*uiMenuResId*<br/>
【인】 메뉴 리소스 ID입니다.

*lpszName*<br/>
【인】 새 메뉴의 이름을 포함하는 문자열입니다.

### <a name="return-value"></a>Return Value

메서드가 성공한 경우 0이 아닙니다. 메서드가 실패하면 0입니다.

### <a name="remarks"></a>설명

*uiMenuResId가* 유효하지 않거나 이름이 같은 다른 메뉴가 이미 에 `CContextMenuManager`있는 경우 이 메서드가 실패합니다.

## <a name="ccontextmenumanagerccontextmenumanager"></a><a name="ccontextmenumanager"></a>C컨텍스트 메뉴 관리자::C컨텍스트 메뉴 관리자

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) 개체를 생성합니다.

```
CContextMenuManager();
```

### <a name="remarks"></a>설명

대부분의 경우 수동으로 만들지 않아야 `CContextMenuManager` 합니다. 응용 프로그램의 프레임워크는 `CContextMenuManager` 개체를 만듭니다. 응용 프로그램의 초기화 중에 [CWinAppEx::InitContextMenuManager를](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) 호출해야 합니다. 컨텍스트 관리자에 대한 포인터를 얻으려면 [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)를 호출합니다.

## <a name="ccontextmenumanagergetmenubyid"></a><a name="getmenubyid"></a>CContextMenu관리자::GetMenuById

지정된 리소스 ID와 연결된 메뉴에 핸들을 반환합니다.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>매개 변수

*nMenuResid*<br/>
【인】 메뉴의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

연결된 메뉴또는 `NULL` 메뉴를 찾을 수 없는 핸들입니다.

## <a name="ccontextmenumanagergetmenubyname"></a><a name="getmenubyname"></a>CContext메뉴 관리자::GetMenuByName

핸들을 특정 메뉴로 반환합니다.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 검색할 메뉴의 이름이 포함된 문자열입니다.

*푸오리그레시드*<br/>
【아웃】 UINT에 대한 포인터입니다. 이 매개 변수에는 지정된 메뉴의 리소스 ID(있는 경우)가 포함되어 있습니다.

### <a name="return-value"></a>Return Value

*lpszName에*의해 지정된 이름과 일치하는 메뉴에 대한 핸들입니다. *lpszName이라는*메뉴가 없는 경우 NULL .

### <a name="remarks"></a>설명

이 메서드가 *lpszName과*일치하는 `GetMenuByName` 메뉴를 찾으면 메뉴 리소스 ID를 매개 변수 *puiOrigResID에 저장합니다.*

## <a name="ccontextmenumanagergetmenunames"></a><a name="getmenunames"></a>C컨텍스트 메뉴 관리자::GetMenu 이름

[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)에 추가된 메뉴 이름 목록을 반환합니다.

```cpp
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>매개 변수

*목록이름*<br/>
【아웃】 [CStringList](../../mfc/reference/cstringlist-class.md) 매개 변수에 대 한 참조입니다. 이 메서드는 이 매개 변수에 메뉴 이름 목록을 씁니다.

## <a name="ccontextmenumanagerloadstate"></a><a name="loadstate"></a>C컨텍스트 메뉴 관리자::로드 상태

Windows 레지스트리에서 [CContextMenuManager 클래스와](../../mfc/reference/ccontextmenumanager-class.md) 관련된 정보를 로드합니다.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 레지스트리 키의 상대 경로를 포함하는 문자열입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*lpszProfileName* 매개 변수는 레지스트리 항목에 대 한 절대 경로 아닙니다. 응용 프로그램의 기본 레지스트리 키 끝에 추가되는 상대 경로입니다. 기본 레지스트리 키를 얻거나 설정하려면 [각각 CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) 및 [CWinAppYBase::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) 메서드를 사용합니다.

[CContextMenuManager:SaveState](#savestate) 메서드를 사용하여 바로 가기 메뉴를 레지스트리에 저장합니다.

## <a name="ccontextmenumanagerresetstate"></a><a name="resetstate"></a>C컨텍스트 메뉴 관리자::재설정 상태

[CContextMenuManager 클래스와](../../mfc/reference/ccontextmenumanager-class.md)연결된 바로 가기 메뉴에서 모든 항목을 지웁힙입니다.

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Return Value

TRUE 메서드가 성공하면 오류가 발생하는 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 팝업 메뉴를 지우고 `CContextMenuManager`에서 제거합니다.

## <a name="ccontextmenumanagersavestate"></a><a name="savestate"></a>C컨텍스트 메뉴 관리자::저장 상태

[CContextMenuManager 클래스와](../../mfc/reference/ccontextmenumanager-class.md) 관련된 정보를 Windows 레지스트리에 저장합니다.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 레지스트리 키의 상대 경로를 포함하는 문자열입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

*lpszProfileName* 매개 변수는 레지스트리 항목에 대 한 절대 경로 아닙니다. 응용 프로그램의 기본 레지스트리 키 끝에 추가되는 상대 경로입니다. 기본 레지스트리 키를 얻거나 설정하려면 [각각 CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) 및 [CWinAppYBase::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) 메서드를 사용합니다.

[CContextMenuManager::LoadState](#loadstate) 메서드를 사용하여 레지스트리에서 바로 가기 메뉴를 로드합니다.

## <a name="ccontextmenumanagersetdontcloseactivemenu"></a><a name="setdontcloseactivemenu"></a>C컨텍스트 메뉴 관리자::SetDont닫기 활성 메뉴

[CContextMenuManager새](../../mfc/reference/ccontextmenumanager-class.md) 팝업 메뉴를 표시할 때 활성 팝업 메뉴를 닫는지 여부를 제어합니다.

```cpp
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
【인】 활성 팝업 메뉴를 닫을지 여부를 제어하는 부울 매개 변수입니다. TRUE 값은 활성 팝업 메뉴가 닫혀 있지 않음을 나타냅니다. FALSE는 활성 팝업 메뉴가 닫혀 있음을 나타냅니다.

### <a name="remarks"></a>설명

기본적으로 활성 `CContextMenuManager` 팝업 메뉴를 닫습니다.

## <a name="ccontextmenumanagershowpopupmenu"></a><a name="showpopupmenu"></a>C컨텍스트 메뉴 관리자::쇼팝메뉴

지정된 바로 가기 메뉴를 표시합니다.

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>매개 변수

*uiMenuResId*<br/>
【인】 이 메서드가 표시하는 메뉴의 리소스 ID입니다.

*x*<br/>
【인】 클라이언트 좌표의 바로 가기 메뉴의 수평 오프셋입니다.

*Y*<br/>
【인】 클라이언트 좌표의 바로 가기 메뉴의 수직 오프셋

*pWnd소유자*<br/>
【인】 바로 가기 메뉴의 상위 창에 대한 포인터입니다.

*bOwn 메시지*<br/>
【인】 메시지가 라우팅되는 방법을 나타내는 부울 매개 변수입니다. *bOwnMessage가* FALSE이면 표준 MFC 라우팅이 사용됩니다. 그렇지 않으면 *pWndOwner* 메시지를 받습니다.

*hmenuPopup*<br/>
【인】 이 메서드가 표시하는 메뉴의 핸들입니다.

*b오토파괴*<br/>
【인】 메뉴가 자동으로 소멸되는지 여부를 나타내는 부울 매개 변수입니다.

*bRightAlign*<br/>
【인】 메뉴 항목이 정렬되는 방법을 나타내는 부울 매개 변수입니다. *bRightAlign이* TRUE이면 오른쪽에서 왼쪽 읽기 순서로 메뉴가 오른쪽으로 정렬됩니다.

### <a name="return-value"></a>Return Value

메서드가 메뉴를 성공적으로 표시하면 첫 번째 메서드 오버로드가 비영을 반환합니다. 그렇지 않으면 0. 두 번째 메서드 오버로드는 바로 가기 메뉴가 올바르게 표시되는 경우 [CMFCPopupMenu에](../../mfc/reference/cmfcpopupmenu-class.md) 대한 포인터를 반환합니다. 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

이 메서드는 두 메서드모두 바로 가기 메뉴를 표시한다는 점에서 [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) 메서드와 유사합니다. 그러나 `TrackPopupMenu` 선택한 메뉴 명령의 인덱스를 반환 합니다.

매개 변수 *bAutoDestroyFALSE* 인 경우 수동으로 상속 `DestroyMenu` 된 메서드를 호출 하여 메모리 리소스를 해제해야 합니다. 기본 구현은 `ShowPopupMenu` 매개 변수 *bAutoDestroy를*사용하지 않습니다. 나중에 사용하거나 클래스에서 파생된 사용자 지정 `CContextMenuManager` 클래스용으로 제공됩니다.

## <a name="ccontextmenumanagertrackpopupmenu"></a><a name="trackpopupmenu"></a>C컨텍스트 메뉴 관리자::트랙팝메뉴

지정된 바로 가기 메뉴를 표시하고 선택한 바로 가기 메뉴 명령의 인덱스를 반환합니다.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>매개 변수

*hmenuPopup*<br/>
【인】 이 메서드가 표시하는 바로 가기 메뉴의 핸들입니다.

*x*<br/>
【인】 클라이언트 좌표의 바로 가기 메뉴의 수평 오프셋입니다.

*Y*<br/>
【인】 클라이언트 좌표의 바로 가기 메뉴의 수직 오프셋입니다.

*pWnd소유자*<br/>
【인】 바로 가기 메뉴의 상위 창에 대한 포인터입니다.

*bRightAlign*<br/>
【인】 메뉴 항목이 정렬되는 방법을 나타내는 부울 매개 변수입니다. *bRightAlign이* TRUE이면 오른쪽에서 왼쪽 읽기 순서로 메뉴가 오른쪽으로 정렬됩니다. *bRightAlign이* FALSE이면 메뉴가 왼쪽에서 오른쪽 읽기 순서로 정렬됩니다.

### <a name="return-value"></a>Return Value

사용자가 선택하는 명령의 메뉴 명령 ID; 사용자가 메뉴 명령을 선택하지 않고 바로 가기 메뉴를 닫는 경우 0입니다.

### <a name="remarks"></a>설명

이 메서드는 바로 가기 메뉴를 표시 하는 모달 호출으로 작동 합니다. 사용자가 바로 가기 메뉴를 닫거나 명령을 선택할 때까지 응용 프로그램은 코드에서 다음 줄로 계속되지 않습니다. 바로 가기 메뉴를 표시하는 데 사용할 수있는 다른 방법은 [CContextMenuManager ::ShowPopupMenu](#showpopupmenu). 이 메서드는 모달 호출이 아니며 선택한 명령의 ID를 반환하지 않습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
