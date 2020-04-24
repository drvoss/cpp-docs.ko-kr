---
title: CMDIFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: d5c9bc12e6c3f0ab4742a940547087c9742caf73
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754552"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd 클래스

창 관리 멤버와 함께 Windows MDI(다중 문서 인터페이스) 프레임 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMDIFrameWnd:::CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMDIFrameWnd::만들기 클라이언트](#createclient)|이에 `CMDIFrameWnd`대한 Windows MDICLIENT 창을 만듭니다. 의 멤버 `OnCreate` 함수에 `CWnd`의해 호출됩니다.|
|[CMDIFrameWnd::만들기새로운 아이](#createnewchild)|새 자식 창을 만듭니다.|
|[CMDIFrameWnd:::겟윈도우메뉴팝업](#getwindowmenupopup)|창 팝업 메뉴를 반환합니다.|
|[CMDIFrameWnd:::MDI활성화](#mdiactivate)|다른 MDI 자식 창을 활성화합니다.|
|[CMDIFrameWnd:::MDI캐스케이드](#mdicascade)|모든 하위 창을 계단식 형식으로 정렬합니다.|
|[CMDIFrameWnd:::MDIGetActive](#mdigetactive)|자식이 최대화되었는지 여부를 나타내는 플래그와 함께 현재 활성 MDI 자식 창을 검색합니다.|
|[CMDIFrameWnd::MDIIcon정렬](#mdiiconarrange)|최소화된 모든 문서 자식 창을 정렬합니다.|
|[CMDIFrameWnd::MDI극대화](#mdimaximize)|MDI 자식 창을 최대화합니다.|
|[CMDIFrameWnd:::MDI다음](#mdinext)|현재 활성 하위 창 바로 뒤에 자식 창을 활성화하고 현재 활성 하위 창을 다른 모든 하위 창 뒤에 배치합니다.|
|[CMDIFrameWnd:::MDIPrev](#mdiprev)|이전 하위 창을 활성화하고 현재 활성 하위 창을 바로 뒤에 배치합니다.|
|[CMDIFrameWnd:::MDI복원](#mdirestore)|MDI 자식 창을 최대화 또는 최소화된 크기에서 복원합니다.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI 프레임 창, 창 팝업 메뉴 또는 둘 다의 메뉴를 바꿉습니다.|
|[CMDIFrameWnd::MDITile](#mditile)|모든 자식 창을 타일 형식으로 정렬합니다.|

## <a name="remarks"></a>설명

응용 프로그램에 대한 유용한 MDI 프레임 창을 만들려면 에서 `CMDIFrameWnd`클래스를 파생합니다. 파생 클래스에 멤버 변수를 추가하여 응용 프로그램에 특정한 데이터를 저장합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.

의 만들기 또는 [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) 멤버 함수를 호출하여 MDI 프레임 창을 생성할 수 있습니다. [Create](../../mfc/reference/cframewnd-class.md#create) `CFrameWnd`

호출하거나 `Create` `LoadFrame`, C++ **새** 연산자사용을 사용하여 힙에서 프레임 창 개체를 생성해야 합니다. 호출하기 `Create` 전에 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 글로벌 함수에 창 클래스를 등록하여 프레임의 아이콘 및 클래스 스타일을 설정할 수도 있습니다.

멤버 `Create` 함수를 사용하여 프레임의 생성 매개변수를 즉각적인 인수로 전달합니다.

`LoadFrame`은 보다 `Create`적은 인수를 필요로 하며 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 포함하여 리소스에서 대부분의 기본 값을 검색합니다. `LoadFrame`에 액세스하려면 이러한 모든 리소스에 동일한 리소스 ID(예: IDR_MAINFRAME)가 있어야 합니다.

에서 `MDIFrameWnd` 파생되지만 `CFrameWnd`에서 파생된 프레임 창 `CMDIFrameWnd` 클래스는 을 `DECLARE_DYNCREATE`사용할 필요가 없습니다.

클래스는 `CMDIFrameWnd` `CFrameWnd`기본 구현의 대부분을 상속합니다. 이러한 기능에 대한 자세한 목록은 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명을 참조하십시오. 클래스에는 `CMDIFrameWnd` 다음과 같은 추가 기능이 있습니다.

- MDI 프레임 창은 MDICLIENT 창을 관리하여 컨트롤 막대와 함께 재배치합니다. MDI 클라이언트 창은 MDI 자식 프레임 창의 직접 상위 입니다. 사용자가 MDI 클라이언트 영역을 `CMDIFrameWnd` 스크롤할 수 있도록 주 프레임 창이 아닌 MDI 클라이언트 창에 적용되는 WS_HSCROLL 및 WS_VSCROLL 창 스타일입니다(예: Windows 프로그램 관리자).

- MDI 프레임 창은 활성 MDI 자식 창이 없을 때 메뉴 모음으로 사용되는 기본 메뉴를 소유합니다. 활성 MDI 자식이 있는 경우 MDI 프레임 창의 메뉴 모음이 자동으로 MDI 자식 창 메뉴로 대체됩니다.

- MDI 프레임 창이 있는 경우 현재 MDI 자식 창과 함께 작동합니다. 예를 들어 명령 메시지는 MDI 프레임 창 앞에 현재 활성 MDI 자식에 위임됩니다.

- MDI 프레임 창에는 다음과 같은 표준 Window 메뉴 명령에 대한 기본 처리기가 있습니다.

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- MDI 프레임 창에는 ID_WINDOW_NEW 구현하여 현재 문서에 새 프레임과 보기를 만듭니다. 응용 프로그램은 이러한 기본 명령 구현을 재정의하여 MDI 창 처리를 사용자 지정할 수 있습니다.

C++ **delete** 연산자사용을 사용하여 프레임 창을 파괴하지 마십시오. 대신 `CWnd::DestroyWindow`를 사용하세요. 구현은 `CFrameWnd` `PostNcDestroy` 창이 소멸될 때 C++ 개체를 삭제합니다. 사용자가 프레임 창을 닫으면 기본 `OnClose` 처리기가 `DestroyWindow`호출합니다.

자세한 `CMDIFrameWnd`내용은 프레임 [창](../../mfc/frame-windows.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd:::CMDIFrameWnd

`CMDIFrameWnd` 개체를 생성합니다.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>설명

또는 `LoadFrame` `Create` 멤버 함수를 호출하여 표시되는 MDI 프레임 창을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd::만들기 클라이언트

`CMDIChildWnd` 개체를 관리하는 MDI 클라이언트 창을 만듭니다.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>매개 변수

*lp창조*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) 구조에 대한 긴 포인터입니다.

*p윈도우 메뉴*<br/>
창 팝업 메뉴에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

멤버 함수를 직접 재정의하는 `OnCreate` 경우 이 멤버 함수를 호출해야 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd::만들기새로운 아이

새 자식 창을 만듭니다.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>매개 변수

*pClass*<br/>
만들 자식 창의 런타임 클래스입니다.

*n 리소스*<br/>
하위 창과 연결된 공유 리소스의 ID입니다.

*Hmenu*<br/>
자식 창의 메뉴입니다.

*하셀 (것)과 같은*<br/>
자식 창의 가속기입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 MDI 프레임 창의 자식 창을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd:::겟윈도우메뉴팝업

이 멤버 함수를 호출하여 "Window"(MDI 창 관리를 위한 메뉴 항목이 있는 팝업 메뉴)라는 현재 팝업 메뉴에 대한 핸들을 얻습니다.

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>매개 변수

*hMenuBar*<br/>
현재 메뉴 모음입니다.

### <a name="return-value"></a>Return Value

창 팝업 메뉴가 있는 경우; 그렇지 않으면 NULL.

### <a name="remarks"></a>설명

기본 구현은 ID_WINDOW_NEW 및 ID_WINDOW_TILE_HORZ 같은 표준 Window 메뉴 명령을 포함하는 팝업 메뉴를 찾습니다.

표준 메뉴 명령 아이디를 사용하지 않는 Window 메뉴가 있는 경우 이 멤버 함수를 재정의합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd:::MDI활성화

다른 MDI 자식 창을 활성화합니다.

```cpp
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>매개 변수

*pWnd활성화*<br/>
활성화할 MDI 자식 창을 가리킵니다.

### <a name="remarks"></a>설명

이 멤버 함수는 활성화 중인 자식 창과 비활성화되는 자식 창 모두에 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) 메시지를 보냅니다.

사용자가 마우스 나 키보드를 사용하여 MDI 자식 창으로 포커스를 변경하는 경우 전송되는 것과 동일한 메시지입니다.

> [!NOTE]
> MDI 자식 창은 MDI 프레임 창과 독립적으로 활성화됩니다. 프레임이 활성화되면 마지막으로 활성화된 자식 창이 활성 창 프레임 및 캡션 막대를 그리는 [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) 메시지를 전송하지만 다른 WM_MDIACTIVATE 메시지가 수신되지 는 않습니다.

### <a name="example"></a>예제

[CMDIFrameWnd::GetWindowMenuPopup에](#getwindowmenupopup)대한 예제를 참조하십시오.

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd:::MDI캐스케이드

모든 MDI 자식 창을 계단식 형식으로 정렬합니다.

```cpp
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
계단식 플래그를 지정합니다. 비활성화된 MDI 자식 창이 계단식으로 배열되는 것을 방지하는 MDITILE_SKIPDISABLED 다음과 같은 플래그만 지정할 수 있습니다.

### <a name="remarks"></a>설명

매개 변수가 `MDICascade`없는 의 첫 번째 버전은 비활성화된 창을 포함하여 모든 MDI 자식 창을 계단식으로 배열합니다. 두 번째 버전은 *선택적으로 nType* 매개 변수에 대한 MDITILE_SKIPDISABLED 지정하는 경우 비활성화된 MDI 자식 창을 계단식으로 캐스케이드하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd:::MDIGetActive

자식 창이 최대화되었는지 여부를 나타내는 플래그와 함께 현재 활성 MDI 자식 창을 검색합니다.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>매개 변수

*pbMaximized*<br/>
BOOL 반환 값에 대한 포인터입니다. 창이 최대화되면 반환 시 TRUE로 설정합니다. 그렇지 않으면 거짓.

### <a name="return-value"></a>Return Value

활성 MDI 자식 창에 대한 포인터입니다.

### <a name="example"></a>예제

[CMDIChildWnd::MDI최대화에](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)대한 예제를 참조하십시오.

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIcon정렬

최소화된 모든 문서 자식 창을 정렬합니다.

```cpp
void MDIIconArrange();
```

### <a name="remarks"></a>설명

최소화되지 않은 자식 창에는 영향을 주지 않습니다.

### <a name="example"></a>예제

[CMDIFrameWnd::MDICascade에](#mdicascade)대한 예제를 참조하십시오.

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd::MDI극대화

지정된 MDI 자식 창을 최대화합니다.

```cpp
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
최대화할 창을 가리킵니다.

### <a name="remarks"></a>설명

자식 창이 최대화되면 Windows는 클라이언트 영역이 클라이언트 창을 채우도록 크기를 조정합니다. Windows는 사용자가 자식 창을 복원하거나 닫을 수 있도록 자식 창의 컨트롤 메뉴를 프레임의 메뉴 모음에 배치합니다. 또한 자식 창의 제목을 프레임 창 제목에 추가합니다.

현재 활성 MDI 자식 창이 최대화될 때 다른 MDI 자식 창이 활성화되면 Windows는 현재 활성 자식을 복원하고 새로 활성화된 자식 창을 최대화합니다.

### <a name="example"></a>예제

[CMDIChildWnd::MDI최대화에](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)대한 예제를 참조하십시오.

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd:::MDI다음

현재 활성 하위 창 바로 뒤에 자식 창을 활성화하고 현재 활성 하위 창을 다른 모든 하위 창 뒤에 배치합니다.

```cpp
void MDINext();
```

### <a name="remarks"></a>설명

현재 활성 MDI 자식 창이 최대화되면 멤버 함수는 현재 활성 자식을 복원하고 새로 활성화된 자식을 최대화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd:::MDIPrev

이전 하위 창을 활성화하고 현재 활성 하위 창을 바로 뒤에 배치합니다.

```cpp
void MDIPrev();
```

### <a name="remarks"></a>설명

현재 활성 MDI 자식 창이 최대화되면 멤버 함수는 현재 활성 자식을 복원하고 새로 활성화된 자식을 최대화합니다.

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd:::MDI복원

MDI 자식 창을 최대화 또는 최소화된 크기에서 복원합니다.

```cpp
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
복원할 창을 가리킵니다.

### <a name="example"></a>예제

[CMDIChildWnd::MDIRestore에](../../mfc/reference/cmdichildwnd-class.md#mdirestore)대한 예제를 참조하십시오.

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu

MDI 프레임 창, 창 팝업 메뉴 또는 둘 다의 메뉴를 바꿉습니다.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>매개 변수

*p프레임 메뉴*<br/>
새 프레임 창 메뉴의 메뉴를 지정합니다. NULL이면 메뉴가 변경되지 않습니다.

*p윈도우 메뉴*<br/>
새 창 팝업 메뉴의 메뉴를 지정합니다. NULL이면 메뉴가 변경되지 않습니다.

### <a name="return-value"></a>Return Value

이 메시지로 대체된 프레임 창 메뉴에 대한 포인터입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.

### <a name="remarks"></a>설명

호출 `MDISetMenu`후 응용 프로그램은 메뉴 모음을 `CWnd` 업데이트하기 위해 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) 멤버 함수를 호출해야 합니다.

이 호출이 창 팝업 메뉴를 대체하는 경우 MDI 자식 창 메뉴 항목이 이전 창 메뉴에서 제거되고 새 창 팝업 메뉴에 추가됩니다.

MDI 자식 창이 최대화되고 이 호출이 MDI 프레임 창 메뉴를 대체하면 컨트롤 메뉴 및 복원 컨트롤이 이전 프레임 창 메뉴에서 제거되고 새 메뉴에 추가됩니다.

프레임워크를 사용하여 MDI 자식 창을 관리하는 경우 이 멤버 함수를 호출하지 마십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd::MDITile

모든 자식 창을 타일 형식으로 정렬합니다.

```cpp
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
타일링 플래그를 지정합니다. 이 매개 변수는 다음 플래그 중 하나일 수 있습니다.

- MDITILE_HORIZONTAL 하나의 창이 다른 창 위에 표시되도록 타일 MDI 자식 창입니다.

- MDITILE_SKIPDISABLED 비활성화된 MDI 자식 창이 바둑판식으로 배열되지 않도록 합니다.

- MDITILE_VERTICAL 하나의 창이 다른 옆에 표시되도록 타일 MDI 자식 창입니다.

### <a name="remarks"></a>설명

`MDITile`의 첫 번째 버전은 매개 변수가 없는 Windows 버전 3.1 이상에서 창을 세로로 바이라고 합니다. 두 번째 버전은 *nType* 매개 변수의 값에 따라 창을 세로 또는 수평으로 타일로 바릅니다.

### <a name="example"></a>예제

[CMDIFrameWnd::MDICascade에](#mdicascade)대한 예제를 참조하십시오.

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CMDI차일드 클래스](../../mfc/reference/cmdichildwnd-class.md)
