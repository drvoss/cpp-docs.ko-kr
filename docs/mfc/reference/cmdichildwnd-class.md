---
title: CMDI차일드 클래스
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: a547a21b96d035f507e749aeb19f891175498d5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754568"
---
# <a name="cmdichildwnd-class"></a>CMDI차일드 클래스

창 관리 멤버와 함께 Windows MDI(다중 문서 인터페이스) 자식 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMDIChildWnd:::CMDIChildWnd](#cmdichildwnd)|`CMDIChildWnd` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMDIChildWnd::만들기](#create)|`CMDIChildWnd` 개체와 연결된 Windows MDI 자식 창을 만듭니다.|
|[CMDIChildWnd:::겟MDI프레임](#getmdiframe)|MDI 클라이언트 창의 상위 MDI 프레임을 반환합니다.|
|[CMDIChildWnd:::MDIActivate](#mdiactivate)|이 MDI 자식 창을 활성화합니다.|
|[CMDIChildWnd:::MDIDestroy](#mdidestroy)|이 MDI 자식 창을 삭제합니다.|
|[CMDIChildWnd::MDI극대화](#mdimaximize)|이 MDI 자식 창을 최대화합니다.|
|[CMDIChildWnd:::MDIRestore](#mdirestore)|이 MDI 자식 창을 최대화 또는 최소화된 크기에서 복원합니다.|
|[CMDIChildWnd::세트핸들](#sethandles)|메뉴 및 가속기 리소스에 대한 핸들을 설정합니다.|

## <a name="remarks"></a>설명

MDI 자식 창은 MDI 자식 창이 데스크톱이 아닌 MDI 프레임 창 안에 표시된다는 점을 제외하면 일반적인 프레임 창과 비슷합니다. MDI 자식 창에는 자체 메뉴 모음이 없지만 대신 MDI 프레임 창의 메뉴를 공유합니다. 프레임워크는 현재 활성 MDI 자식 창을 나타내도록 MDI 프레임 메뉴를 자동으로 변경합니다.

응용 프로그램에 대한 유용한 MDI 자식 창을 `CMDIChildWnd`만들려면 에서 클래스를 파생합니다. 파생 클래스에 멤버 변수를 추가하여 응용 프로그램에 특정한 데이터를 저장합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.

MDI 자식 창을 구성하는 방법에는 세 가지가 있습니다.

- 을 사용하여 `Create`직접 구성합니다.

- 을 사용하여 `LoadFrame`직접 구성합니다.

- 문서 템플릿을 통해 간접적으로 구성합니다.

호출하거나 `Create` `LoadFrame`, C++ **새** 연산자사용을 사용하여 힙에서 프레임 창 개체를 생성해야 합니다. 호출하기 `Create` 전에 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 글로벌 함수에 창 클래스를 등록하여 프레임의 아이콘 및 클래스 스타일을 설정할 수도 있습니다.

멤버 `Create` 함수를 사용하여 프레임의 생성 매개변수를 즉각적인 인수로 전달합니다.

`LoadFrame`은 보다 `Create`적은 인수를 필요로 하며 대신 프레임의 캡션, 아이콘, 액셀러레이터 테이블 및 메뉴를 포함하여 리소스에서 대부분의 기본 값을 검색합니다. `LoadFrame`에 액세스할 수 있도록 이러한 모든 리소스에는 동일한 리소스 ID(예: IDR_MAINFRAME)가 있어야 합니다.

개체에 `CMDIChildWnd` 뷰와 문서가 포함된 경우 프로그래머가 직접 작성하지 않고 프레임워크에 의해 간접적으로 만들어집니다. 개체는 `CDocTemplate` 프레임 작성, 포함된 뷰 작성 및 뷰를 해당 문서에 연결하도록 오케스트레이션합니다. `CDocTemplate` 생성자의 매개 변수는 관련된 `CRuntimeClass` 세 클래스(문서, 프레임 및 뷰)를 지정합니다. `CRuntimeClass` 개체는 사용자가 지정한 경우(예: 파일 새 명령 또는 MDI 창 새 명령을 사용 하 여) 새 프레임을 동적으로 만드는 프레임프레임에 대 한 프레임에서 사용 됩니다.

위의 RUNTIME_CLASS 메커니즘이 올바르게 `CMDIChildWnd` 작동하려면 프레임 창 클래스를 DECLARE_DYNCREATE 함께 선언해야 합니다.

클래스는 `CMDIChildWnd` `CFrameWnd`기본 구현의 대부분을 상속합니다. 이러한 기능에 대한 자세한 목록은 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명을 참조하십시오. 클래스에는 `CMDIChildWnd` 다음과 같은 추가 기능이 있습니다.

- `CMultiDocTemplate` 클래스와 함께 동일한 `CMDIChildWnd` 문서 템플릿의 여러 개체가 동일한 메뉴를 공유하여 Windows 시스템 리소스를 절약합니다.

- 현재 활성 MDI 자식 창 메뉴는 MDI 프레임 창의 메뉴를 완전히 대체하며 현재 활성 MDI 자식 창의 캡션이 MDI 프레임 창의 캡션에 추가됩니다. MDI 프레임 창과 함께 구현되는 MDI 자식 창 함수의 추가 `CMDIFrameWnd` 예는 클래스 설명을 참조하십시오.

C++ **delete** 연산자사용을 사용하여 프레임 창을 파괴하지 마십시오. 대신 `CWnd::DestroyWindow`를 사용하세요. 구현은 `CFrameWnd` `PostNcDestroy` 창이 소멸될 때 C++ 개체를 삭제합니다. 사용자가 프레임 창을 닫으면 기본 `OnClose` 처리기가 `DestroyWindow`호출합니다.

자세한 `CMDIChildWnd`내용은 프레임 [창](../../mfc/frame-windows.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd:::CMDIChildWnd

개체를 생성하기 위해 호출합니다. `CMDIChildWnd`

```
CMDIChildWnd();
```

### <a name="remarks"></a>설명

호출하여 `Create` 표시되는 창을 만듭니다.

### <a name="example"></a>예제

  [CMDIChildWnd::Create에](#create)대한 예제를 참조하십시오.

## <a name="cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd::만들기

이 멤버 함수를 호출하여 Windows MDI 자식 `CMDIChildWnd` 창을 만들고 개체에 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
Windows [클래스(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조)의 이름을 지정하는 null 종료된 문자 문자열을 가리킵니다. 클래스 이름은 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 글로벌 함수에 등록된 모든 이름일 수 있습니다. 표준에 `CMDIChildWnd`대해 NULL이어야 합니다.

*lpszWindowName*<br/>
창 이름을 나타내는 null 종료된 문자 문자열을 가리킵니다. 제목 표시줄의 텍스트로 사용됩니다.

*dwStyle*<br/>
창 [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 특성을 지정합니다. WS_CHILD 스타일이 필요합니다.

*rect*<br/>
창의 크기와 위치를 포함합니다. 이 `rectDefault` 값을 통해 Windows는 새 `CMDIChildWnd`의 크기와 위치를 지정할 수 있습니다.

*pParentWnd*<br/>
창의 부모를 지정합니다. NULL이면 기본 응용 프로그램 창이 사용됩니다.

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조를 지정합니다. 이 매개 변수는 NULL일 수 있습니다.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

현재 활성 MDI 자식 프레임 창은 상위 프레임 창의 캡션을 결정할 수 있습니다. 이 기능은 자식 프레임 창의 FWS_ADDTOTITLE 스타일 비트를 해제하여 비활성화됩니다.

프레임워크는 사용자 명령에 대한 응답으로 이 멤버 함수를 호출하여 자식 창을 만들고 프레임워크는 *pContext* 매개 변수를 사용하여 자식 창을 응용 프로그램에 올바르게 연결합니다. 호출할 `Create`때 *pContextNULL일* 수 있습니다.

### <a name="example"></a>예제

예제 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>예제

예제 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd:::겟MDI프레임

이 함수를 호출하여 MDI 부모 프레임을 반환합니다.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Return Value

MDI 부모 프레임 창에 대한 포인터입니다.

### <a name="remarks"></a>설명

반환된 프레임은 두 부모에서 `CMDIChildWnd` 제거되며 `CMDIChildWnd` 개체를 관리하는 MDICLIENT 형식창의 부모입니다. [GetParent](../../mfc/reference/cwnd-class.md#getparent) 멤버 함수를 호출하여 `CMDIChildWnd` 개체의 즉각적인 MDICLIENT `CWnd` 부모를 임시 포인터로 반환합니다.

### <a name="example"></a>예제

  [CMDIFrameWnd::MDISetMenu에](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)대한 예제를 참조하십시오.

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd:::MDIActivate

MDI 프레임 창과 독립적으로 MDI 자식 창을 활성화하려면 이 멤버 함수를 호출합니다.

```cpp
void MDIActivate();
```

### <a name="remarks"></a>설명

프레임이 활성화되면 마지막으로 활성화된 자식 창도 활성화됩니다.

### <a name="example"></a>예제

  [CMDIFrameWnd::GetWindowMenuPopup에](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)대한 예제를 참조하십시오.

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd:::MDIDestroy

이 멤버 함수를 호출하여 MDI 자식 창을 삭제합니다.

```cpp
void MDIDestroy();
```

### <a name="remarks"></a>설명

멤버 함수는 프레임 창에서 자식 창의 제목을 제거하고 자식 창을 비활성화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd::MDI극대화

이 멤버 함수를 호출하여 MDI 자식 창을 최대화합니다.

```cpp
void MDIMaximize();
```

### <a name="remarks"></a>설명

자식 창이 최대화되면 Windows는 크기를 조정하여 클라이언트 영역이 프레임 창의 클라이언트 영역을 채웁니다. Windows는 사용자가 자식 창을 복원하거나 닫을 수 있도록 자식 창의 컨트롤 메뉴를 프레임의 메뉴 모음에 배치하고 자식 창의 제목을 프레임 창 제목에 추가합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd:::MDIRestore

이 멤버 함수를 호출하여 MDI 자식 창을 최대화 또는 최소화된 크기에서 복원합니다.

```cpp
void MDIRestore();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd::세트핸들

메뉴 및 가속기 리소스에 대한 핸들을 설정합니다.

```cpp
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>매개 변수

*Hmenu*<br/>
메뉴 리소스의 핸들입니다.

*하셀 (것)과 같은*<br/>
가속기 리소스의 핸들입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 MDI 자식 창 개체에서 사용하는 메뉴 및 가속기 리소스를 설정합니다.

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 스냅폭스](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd 클래스](../../mfc/reference/cmdiframewnd-class.md)
