---
title: C마우스관리자 클래스
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 1394a1b47a86022e37b11e032b87ee2a2a369862
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752802"
---
# <a name="cmousemanager-class"></a>C마우스관리자 클래스

사용자가 해당 보기 내에서 두 번 클릭할 때 사용자가 다른 명령을 특정 [CView](../../mfc/reference/cview-class.md) 개체와 연결할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMouseManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C마우스 관리자::추가 보기](#addview)|사용자 지정 대화 상자에 개체를 추가합니다. **Customization** `CView` **사용자 지정** 대화 상자를 사용하면 나열된 각 보기에 대한 명령과 두 번 클릭을 연결할 수 있습니다.|
|[C마우스 매니저::GetViewDblClickCommand](#getviewdblclickcommand)|사용자가 제공된 보기 내에서 두 번 클릭할 때 실행되는 명령을 반환합니다.|
|[C마우스 매니저::겟뷰아이콘](#getviewiconid)|제공된 뷰 ID와 연결된 아이콘을 반환합니다.|
|[C마우스 매니저::GetViewIdByName](#getviewidbyname)|제공된 뷰 이름과 연결된 뷰 ID를 반환합니다.|
|[C마우스 관리자::GetView 이름](#getviewnames)|추가된 모든 뷰 이름 목록을 검색합니다.|
|[C마우스 관리자::로드스테이트](#loadstate)|Windows `CMouseManager` 레지스트리에서 상태를 로드합니다.|
|[C마우스 관리자::저장 상태](#savestate)|`CMouseManager` 상태를 Windows 레지스트리에 씁니다.|
|[CMouse 관리자::세트커맨드포블클크](#setcommandfordblclk)|제공된 명령과 제공된 뷰를 연결합니다.|

## <a name="remarks"></a>설명

클래스는 `CMouseManager` 개체의 `CView` 컬렉션을 유지 관리합니다. 각 보기는 이름과 ID로 식별됩니다. 이러한 보기는 **사용자 지정** 대화 상자에 표시됩니다. 사용자는 **사용자 지정** 대화 상자를 통해 모든 보기와 연결된 명령을 변경할 수 있습니다. 연결된 명령은 사용자가 해당 보기를 두 번 클릭할 때 실행됩니다. 코딩 관점에서 이를 지원하려면 WM_LBUTTONDBLCLK 메시지를 처리하고 해당 `CView` 개체에 대한 코드에서 [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) 함수를 호출해야 합니다.

개체를 `CMouseManager` 수동으로 만들지 않아야 합니다. 응용 프로그램의 프레임워크에 의해 만들어집니다. 또한 사용자가 응용 프로그램을 종료할 때 자동으로 소멸됩니다. 응용 프로그램에 대한 마우스 관리자에 대한 포인터를 얻으려면 [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)로 전화하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxmousemanager.h

## <a name="cmousemanageraddview"></a><a name="addview"></a>C마우스 관리자::추가 보기

사용자 지정 마우스 동작을 지원 하기 위해 [CMouseManager 클래스와](../../mfc/reference/cmousemanager-class.md) [CView](../../mfc/reference/cview-class.md) 개체를 등록 합니다.

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>매개 변수

*아이뷰아이드*<br/>
【인】 보기 ID입니다.

*uiViewNameResId*<br/>
【인】 뷰 이름을 참조하는 리소스 문자열 ID입니다.

*uiIconId*<br/>
【인】 뷰 아이콘 ID입니다.

*Iid*<br/>
【인】 보기 ID입니다.

*lpszViewName*<br/>
【인】 뷰 이름입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용자 지정 마우스 동작을 지원하려면 뷰를 `CMouseManager` 개체에 등록해야 합니다. 클래스에서 파생된 `CView` 모든 개체는 마우스 관리자에 등록할 수 있습니다. 보기와 연결된 문자열과 아이콘은 **사용자 지정** 대화 상자의 **마우스** 탭에 표시됩니다.

*iViewId* 및 *iId와*같은 보기 ID를 만들고 유지 관리하는 것은 프로그래머의 책임입니다.

사용자 지정 마우스 동작을 제공하는 방법에 대한 자세한 내용은 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)을 참조하십시오.

### <a name="example"></a>예제

다음 예제에서는 `CMouseManager` 클래스에서 `CWinAppEx::GetMouseManager` 메서드와 메서드를 사용 하 여 `AddView` 개체에 `CMouseManager` 대 한 포인터를 검색 하는 방법을 보여 줍니다. 이 코드 조각은 상태 [컬렉션 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a>C마우스 매니저::GetViewDblClickCommand

사용자가 제공된 보기 내에서 두 번 클릭할 때 실행되는 명령을 반환합니다.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>매개 변수

*Iid*<br/>
【인】 뷰 ID입니다.

### <a name="return-value"></a>Return Value

뷰가 명령과 연결되어 있는 경우 명령 식별자입니다. 그렇지 않으면 0.

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a>C마우스 매니저::겟뷰아이콘

뷰 ID와 연결된 아이콘을 검색합니다.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>매개 변수

*아이뷰아이드*<br/>
【인】 뷰 ID입니다.

### <a name="return-value"></a>Return Value

성공하면 아이콘 리소스 식별자; 그렇지 않으면 0.

### <a name="remarks"></a>설명

[CMouseManager::AddView](#addview)을 사용하여 뷰가 처음 등록되지 않은 경우 이 메서드가 실패합니다.

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a>C마우스 매니저::GetViewIdByName

뷰 이름과 연결된 뷰 ID를 검색합니다.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
【인】 뷰 이름입니다.

### <a name="return-value"></a>Return Value

뷰 ID가 성공하면 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 [CMouseManager::AddView](#addview)를 사용 하 여 등록 된 보기를 통해 검색 합니다.

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a>C마우스 관리자::GetView 이름

등록된 모든 뷰 이름 목록을 검색합니다.

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>매개 변수

*목록이름*<br/>
【아웃】 개체에 `CStringList` 대한 참조입니다.

### <a name="remarks"></a>설명

이 메서드는 `listOfNames` [CMouseManager::AddView를](#addview)사용 하 여 등록 된 모든 뷰의 이름으로 매개 변수를 채웁니다.

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a>C마우스 관리자::로드스테이트

레지스트리에서 [CMouseManager 클래스의](../../mfc/reference/cmousemanager-class.md) 상태를 로드합니다.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 레지스트리 키의 경로입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

레지스트리에서 로드된 상태 정보에는 등록된 보기, 뷰 식별자 및 관련 명령이 포함됩니다. 매개 변수 *lpszProfileName이* NULL인 경우 `CMouseManager` 이 함수는 [CWinAppEx 클래스에서](../../mfc/reference/cwinappex-class.md)제어하는 기본 레지스트리 위치에서 데이터를 로드합니다.

대부분의 경우 이 함수를 직접 호출할 필요가 없습니다. 작업 영역 초기화 프로세스의 일부로 호출됩니다. 작업 영역 초기화 프로세스에 대한 자세한 내용은 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)를 참조하십시오.

## <a name="cmousemanagersavestate"></a><a name="savestate"></a>C마우스 관리자::저장 상태

[CMouseManager 클래스의](../../mfc/reference/cmousemanager-class.md) 상태를 레지스트리에 기록합니다.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 레지스트리 키의 경로입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

레지스트리에 기록된 상태 정보에는 등록된 모든 보기, 뷰 식별자 및 관련 명령이 포함됩니다. 매개 변수 *lpszProfileName이* NULL인 경우 `CMouseManager` 이 함수는 [CWinAppEx 클래스에서](../../mfc/reference/cwinappex-class.md)제어하는 기본 레지스트리 위치에 데이터를 씁니다.

대부분의 경우 이 함수를 직접 호출할 필요가 없습니다. 작업 영역 직렬화 프로세스의 일부로 호출됩니다. 작업 영역 직렬화 프로세스에 대한 자세한 내용은 [CWinAppEx:SaveState](../../mfc/reference/cwinappex-class.md#savestate)를 참조하십시오.

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a>CMouse 관리자::세트커맨드포블클크

사용자 지정 명령을 마우스 관리자에 처음 등록된 뷰와 연결합니다.

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*아이뷰아이드*<br/>
【인】 뷰 식별자입니다.

*uiCmd*<br/>
【인】 명령 식별자입니다.

### <a name="remarks"></a>설명

사용자 지정 명령을 뷰와 연결하려면 먼저 [CMouseManager::AddView](#addview)를 사용하여 뷰를 등록해야 합니다. 메서드는 `AddView` 뷰 식별자를 입력 매개 변수로 사용해야 합니다. 뷰를 등록한 후 에 `CMouseManager::SetCommandForDblClk` 제공한 동일한 뷰 식별자 입력 `AddView`매개 변수로 호출할 수 있습니다. 그런 다음 사용자가 등록된 보기에서 마우스를 두 번 클릭하면 응용 프로그램은 *uiCmd로* 표시된 명령을 실행합니다. 사용자 지정 마우스 동작을 지원하려면 마우스 관리자에 등록된 뷰를 사용자 지정해야 합니다. 사용자 지정 마우스 동작에 대한 자세한 내용은 [키보드 및 마우스 사용자 지정](../keyboard-and-mouse-customization.md)을 참조하십시오.

*uiCmd가* 0으로 설정되면 지정된 뷰가 더 이상 명령과 연결되지 않습니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)<br/>
[키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)
