---
title: CMiniFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: e9b91161f4207f4d2215d8777beade93617ddfac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319813"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd 클래스

일반적으로 부동 도구 모음에 있는 절반 높이의 프레임 창을 나타냅니다.

## <a name="syntax"></a>구문

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|`CMiniFrameWnd` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMiniFrameWnd::만들기](#create)|시공 `CMiniFrameWnd` 후 객체를 만듭니다.|
|[CMiniFrameWnd::만들기](#createex)|시공 `CMiniFrameWnd` 후 추가 옵션포함 객체를 만듭니다.|

## <a name="remarks"></a>설명

이 미니 프레임 창은 최소화 / 최대화 버튼이나 메뉴가 없으며 시스템 메뉴를 한 번만 클릭하면 해제된다는 점을 제외하고는 일반 프레임 창처럼 행동합니다.

개체를 `CMiniFrameWnd` 사용하려면 먼저 개체를 정의합니다. 그런 다음 멤버 [만들기](#create) 함수를 호출하여 미니 프레임 창을 표시합니다.

개체를 사용하는 `CMiniFrameWnd` 방법에 대한 자세한 내용은 [도킹 및 부동 도구 모음](../../mfc/docking-and-floating-toolbars.md)을 참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd

개체를 `CMiniFrameWnd` 생성하지만 창을 만들지는 않습니다.

```
CMiniFrameWnd();
```

### <a name="remarks"></a>설명

창을 만들려면 [CMiniFrameWnd::Create를](#create)호출합니다.

## <a name="cminiframewndcreate"></a><a name="create"></a>CMiniFrameWnd::만들기

Windows 미니 프레임 창을 만들고 개체에 `CMiniFrameWnd` 연결합니다.

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>매개 변수

*lpClassName*<br/>
Windows 클래스의 이름을 지정하는 null 종료된 문자 문자열을 가리킵니다. 클래스 이름은 전역 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 함수에 등록된 모든 이름일 수 있습니다. NULL이면 프레임워크에서 창 클래스가 등록됩니다. MFC는 기본 클래스에 다음과 같은 스타일과 특성을 제공합니다.

- 사용자가 마우스를 두 번 클릭할 때 창 프로시저에 두 번 클릭 메시지를 보내는 스타일 비트 CS_DBLCLKS 설정합니다.

- 스타일 비트를 CS_HREDRAW 설정하고 CS_VREDRAW 창크기를 변경할 때 클라이언트 영역의 내용을 다시 그려지도록 지시합니다.

- 클래스 커서를 Windows 표준 IDC_ARROW 설정합니다.

- 클래스 배경 브러시를 NULL로 설정하여 창이 배경을 지우지 않도록 합니다.

- 클래스 아이콘을 표준 흔들기 플래그 Windows 로고 아이콘으로 설정합니다.

- 창을 Windows에서 표시한 대로 기본 크기와 위치로 설정합니다.

*lp창이름*<br/>
창 이름을 포함 하는 null 종료 된 문자 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. 여기에는 표준 창 스타일과 다음 특수 스타일 중 하나 이상이 포함될 수 있습니다.

- MFS_MOVEFRAME 캡션뿐만 아니라 창의 가장자리를 클릭하여 미니 프레임 창을 이동할 수 있습니다.

- MFS_4THICKFRAME 미니 프레임 창의 크기 조정을 사용하지 않도록 설정합니다.

- MFS_SYNCACTIVE 미니 프레임 창의 활성화를 부모 창의 활성화와 동기화합니다.

- MFS_THICKFRAME 미니 프레임 창의 크기를 클라이언트 영역의 내용만큼 작게 할 수 있습니다.

- MFS_BLOCKSYSMENU 시스템 메뉴 및 컨트롤 메뉴에 대한 액세스를 비활성화하고 캡션(제목 표시줄)의 일부로 변환합니다.

가능한 창 스타일 값에 대한 설명은 [CWnd::만들기를](../../mfc/reference/cwnd-class.md#create) 참조하십시오. 미니 프레임 창에 사용되는 일반적인 조합은 WS_CAPTION&#124;WS_CAPTION WS_SYSMENU WS_POPUP&#124;.

*rect*<br/>
창의 원하는 치수를 지정하는 `RECT` 구조입니다.

*pParentWnd*<br/>
상위 창을 가리킵니다. 최상위 창에 NULL을 사용합니다.

*nID*<br/>
미니 프레임 창이 자식 창으로 만들어지면 자식 컨트롤의 식별자입니다. 그렇지 않으면 0.

### <a name="return-value"></a>Return Value

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Create`은 창의 클래스 이름과 창 이름을 초기화하고 해당 스타일 및 부모에 대한 기본값을 등록합니다.

## <a name="cminiframewndcreateex"></a><a name="createex"></a>CMiniFrameWnd::만들기

`CMiniFrameWnd` 개체를 만듭니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
`CMiniFrameWnd` 작성 중인 확장 스타일을 지정합니다. [확장된 창 스타일을](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) 창에 적용합니다.

*lpClassName*<br/>
Windows [클래스(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 구조)의 이름을 지정하는 null 종료된 문자 문자열을 가리킵니다. 클래스 이름은 전역 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 함수에 등록된 이름 또는 미리 정의된 컨트롤 클래스 이름일 수 있습니다. NULL이 아니어야 합니다.

*lp창이름*<br/>
창 이름을 포함 하는 null 종료 된 문자 문자열을 가리킵니다.

*dwStyle*<br/>
창 스타일 특성을 지정합니다. 가능한 값에 대한 설명은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 및 [CWnd::만들기를](../../mfc/reference/cwnd-class.md#create) 참조하십시오.

*rect*<br/>
*pParentWnd의*클라이언트 좌표에서 창의 크기와 위치.

*pParentWnd*<br/>
부모 창 개체를 가리킵니다.

*nID*<br/>
자식 창의 식별자입니다.

### <a name="return-value"></a>Return Value

성공에 TRUE를 반환, 실패에 FALSE.

### <a name="remarks"></a>설명

매개 `CreateEx` 변수는 WNDCLASS, 창 스타일 및 (선택적으로) 창의 초기 위치와 크기를 지정합니다. `CreateEx`또한 창의 부모(있는 경우)와 ID를 지정합니다.

실행되면 `CreateEx` Windows는 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), WM_NCCREATE [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)및 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) 메시지를 창으로 보냅니다. [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)

기본 메시지 처리를 확장하려면 에서 `CMiniFrameWnd`클래스를 파생합니다 . 예를 `OnCreate`들어 새 클래스에 필요한 초기화를 수행하려면 을 재정의합니다.

파생 클래스에 추가 기능을 추가하려면 `On` *메시지* 메시지 처리기를 추가로 재정의합니다.

WS_VISIBLE 스타일이 지정되면 Windows는 창을 활성화하고 표시하는 데 필요한 모든 메시지를 창에 보냅니다. 창 스타일이 제목 표시줄을 지정하는 경우 *lpszWindowName* 매개 변수가 가리키는 창 제목이 제목 표시줄에 표시됩니다.

*dwStyle* 매개 변수는 [창 스타일의](../../mfc/reference/styles-used-by-mfc.md#window-styles)모든 조합일 수 있습니다.

이전 스타일 팔레트 도구 상자 창은 더 이상 지원되지 않습니다. "X" 닫기 버튼이 없는 이전 스타일은 이전 버전의 Windows에서 MFC 응용 프로그램을 실행할 때 지원되었지만 Visual C++.NET에서는 더 이상 지원되지 않습니다. 이제 새 WS_EX_TOOLWINDOW 스타일만 지원됩니다. 이 스타일에 대한 설명은 [확장 창 스타일을](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)참조하십시오.

## <a name="see-also"></a>참고 항목

[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)
