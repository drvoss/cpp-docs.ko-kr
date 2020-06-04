---
title: CMFC리본미니툴바 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 5e5ac6c923640b7584d89a9c6f75d941deadddf3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754086"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFC리본미니툴바 클래스

상황별 팝업 도구 모음을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|기본 생성자입니다.|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonMiniToolBar::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|( `CMFCPopupMenu::IsRibbonMiniToolBar`을 재정의합니다.)|
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|도구 모음에 표시되는 명령의 목록을 설정합니다.|
|[CMFCRibbonMiniToolBar::Show](#show)|지정된 화면 좌표에 미니 도구 모음을 표시합니다.|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|상황에 맞는 메뉴와 함께 미니 도구 모음을 표시합니다.|

## <a name="remarks"></a>설명

미니 도구 모음은 일반적으로 사용자가 문서에서 개체를 선택한 후에 표시됩니다. 예를 들어 사용자가 문서 작성 프로그램에서 텍스트 블록을 선택하고 나면 애플리케이션은 텍스트 서식 지정 명령이 포함된 미니 도구 모음을 표시합니다.

마우스 포인터가 미니 도구 모음의 범위를 벗어나면 미니 도구 모음은 투명해집니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본미니툴바.h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a>CMFC리본미니툴바::설정 명령

도구 모음에 표시되는 명령의 목록을 설정합니다.

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>매개 변수

*pRibbonBar*<br/>
【인】 미니 도구 모음에서 표시할 단추를 검색하는 리본 막대입니다.

*lstCommands*<br/>
【인】 미니 도구 모음에 표시할 명령 목록입니다. 모든 리본 범주가 검색되어 관련 단추를 찾습니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 미니 도구 모음에 표시할 명령 목록을 설정합니다.

### <a name="example"></a>예제

다음 예제에서는 `SetCommands` `CMFCRibbonMiniToolBar` 클래스의 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 MS [Office 2007 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a>CMFC리본미니툴바::쇼

지정된 화면 좌표에 미니 도구 모음을 표시합니다.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 화면 좌표에서 미니 도구 모음의 수평 위치를 지정합니다.

*Y*<br/>
【인】 화면 좌표에서 미니 도구 모음의 수직 위치를 지정합니다.

### <a name="return-value"></a>Return Value

미니 도구 모음이 성공적으로 표시된 경우 TRUE; 그렇지 않으면 false입니다.

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a>CMFC리본미니툴바::쇼위드컨텍스트메뉴

상황에 맞는 메뉴와 함께 미니 도구 모음을 표시합니다.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
【인】 화면 좌표에서 컨텍스트 메뉴의 가로 위치를 지정합니다.

*Y*<br/>
【인】 화면 좌표에서 컨텍스트 메뉴의 세로 위치를 지정합니다.

*uiMenuResID*<br/>
【인】 표시할 컨텍스트 메뉴의 리소스 ID를 지정합니다.

*pWnd소유자*<br/>
【인】 컨텍스트 메뉴에서 메시지를 받는 창을 식별합니다.

### <a name="return-value"></a>Return Value

컨텍스트 메뉴가 성공적으로 표시되는 경우 TRUE입니다. 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 상황에 맞는 메뉴가 있는 미니 도구 모음을 표시합니다. 컨텍스트 메뉴는 미니 도구 모음 아래에 15픽셀 아래에 배치됩니다.

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a>CMFC리본미니툴바::이맥락메뉴모드

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a>CMFC리본미니툴바::이리본미니툴바

자세한 내용은 Visual Studio 설치의 **\\VC\\atlmfc\\src mfc** 폴더에 있는 소스 코드를 참조하십시오.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
