---
title: AFX 메시지
ms.date: 11/04/2016
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
ms.openlocfilehash: b4ed86c11d3c5b5f1ce38e3146533109f3a6b00d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363592"
---
# <a name="afx-messages"></a>AFX 메시지

이러한 메시지는 MFC에서 사용됩니다.

## <a name="messages"></a>메시지

다음 표에는 MFC 라이브러리에 사용되는 메시지가 나열됩니다.

||||||
|-|-|-|-|-|
|메시지|Description|【인】 *wParam*|*lParam* (달리 명시되지 않는 한 모든 매개 변수는 [in]입니다.)|Return Value|
|AFX_WM_ACCGETOBJECT|사용되지 않습니다.|사용되지 않습니다.|해당 사항 없음|해당 사항 없음|
|AFX_WM_ACCGETSTATE|내게 필요한 옵션 지원에 사용됩니다. 이 메시지를 `CMFCPopupMenu` 현재 `CMFCRibbonPanelMenu` 요소의 상태를 검색하거나 검색합니다.|메뉴 단추 또는 구분 기호일 수 있는 요소인덱스입니다.|사용되지 않습니다.|요소 상태입니다. 인덱스가 유효하지 않은 경우 -1, 메뉴 단추에 특별한 특성이 없는 경우 0입니다. 그렇지 않으면 다음 플래그의 조합입니다.<br /><br /> TBBS_DISABLED — 항목이 비활성화됨<br /><br /> TBBS_CHECKED — 항목이 선택됨<br /><br /> TBBS_BUTTON — 이 아이템은 표준 푸시버튼입니다.<br /><br /> TBBS_PRESSED — 버튼을 누른 경우<br /><br /> TBBS_INDETERMINATE — 정의되지 않은 상태<br /><br /> TBBS_SEPARATOR - 메뉴 버튼이 아닌 이 요소는 다른 메뉴 항목 간의 구분을 형성합니다.|
|AFX_WM_CHANGE_ACTIVE_TAB|프레임워크는 이 메시지를 식재 가능한 컨트롤 막대 컨트롤로 보냅니다. 사용자가 활성 탭을 `CMFCTabCtrl` 변경할 때 개체에서 알림을 수신하려면 이 메시지를 처리합니다.|탭의 인덱스입니다.|사용되지 않습니다.|비영점.|
|AFX_WM_CHANGE_CURRENT_FOLDER|프레임워크는 사용자가 현재 폴더를 `CMFCShellListCtrl` 변경했을 때의 부모에게 이 메시지를 보냅니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_CHANGEVISUALMANAGER|프레임워크는 사용자가 현재 Visual Manager를 변경할 때 이 메시지를 모든 프레임 창으로 보냅니다. 이 메시지에 대한 응답으로 프레임 창은 해당 영역을 다시 계산하고 필요에 따라 다른 매개 변수를 조정합니다. 이 이벤트에 대한 알림을 받아야 하는 경우 응용 프로그램에서 AFX_WM_CHANGEVISUALMANAGER 메시지를 처리할 수 있습니다. 이 이벤트의 프레임워크의 내부`OnChangeVisualManager`처리가 이루어지도록 기본 클래스 처리기 () 를 호출해야 합니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_CHANGING_ACTIVE_TAB|개체의 `CMFCTabCtrl` 상위로 전송됩니다.  사용자가 탭을 재설정할 때 `CMFCTabCtrl` 개체로부터 알림을 받으려면 이 메시지를 처리합니다.|활성화 중인 탭의 인덱스입니다.|사용되지 않습니다.|비영점.|
|AFX_WM_CHECKEMPTYMINIFRAME|내부 전용입니다.|해당 사항 없음|해당 사항 없음|해당 사항 없음|
|AFX_WM_CREATETOOLBAR|사용자 `CMFCToolBarsListPropertyPage` 지정 프로세스 중에 새 도구 모음을 만들 때 전송됩니다. 이 메시지를 처리하여 사용자 지정 CMFCToolBar 파생 개체를 인스턴스화할 수 있습니다. 이 메시지를 처리하고 고유한 도구 모음을 만드는 경우 기본 처리기에 대한 호출을 생략합니다.|사용되지 않습니다.|도구 모음의 이름이 포함된 문자열에 대한 포인터입니다.|새로 만든 도구 모음에 대한 포인터입니다. NULL은 도구 모음 만들기가 취소되었지만 있음을 나타냅니다.|
|AFX_WM_CUSTOMIZEHELP|사용자가 `CMFCToolbarCustomize Dialog` **도움말** 단추 또는 F1 키를 누를 때 사용자 지정 속성 시트에서 기본 프레임 창으로 전송됩니다.|사용자 지정 속성 시트의 활성 페이지를 지정합니다.|`CMFCToolbarCustomize Dialog` 개체에 대한 포인터입니다.|단계 없음.|
|AFX_WM_CUSTOMIZETOOLBAR|이 `CMFCToolbarCustomize Dialog` 메시지를 보내 사용자가 새 도구 모음을 만들고 있음을 부모 프레임에 알립니다.|사용자 지정이 시작되면 TRUE, 사용자 지정이 완료되면 FALSE입니다.|사용되지 않습니다.|단계 없음.|
|AFX_WM_DELETETOOLBAR|사용자가 사용자 지정 모드에서 도구 모음을 삭제하려고 할 때 기본 프레임 창으로 전송됩니다.<br /><br /> 사용자가 사용자 지정 모드에서 도구 모음을 삭제할 때 이 메시지를 처리하여 추가 작업을 수행합니다. 또한 도구 모음을 삭제하는 기본 처리기()를`OnToolbarDelete`호출해야 합니다. 기본 처리기는 도구 모음을 삭제할 수 있는지 여부를 나타내는 값을 반환합니다.|사용되지 않습니다.|삭제할 `CMFCToolBar` 개체에 대한 포인터입니다.|도구 모음을 삭제할 수 없는 경우 0이 아닙니다. 그렇지 않으면 0.|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton`이 메시지를 기본 프레임 창으로 보내 문서 색상을 검색합니다.|사용되지 않습니다.|【인, 아웃】 개체에 `CList<COLORREF, COLORREF>` 대한 포인터입니다.|단계 없음.|
|AFX_WM_GETDRAGBOUNDS|내부 전용입니다.|해당 사항 없음|해당 사항 없음|해당 사항 없음|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|사용자가 리본 목록 항목을 강조 실행할 때 기본 프레임 창으로 전송됩니다.|강조 표시된 항목의 인덱스|에 대한 포인터`CMFCBaseRibbonElement`|사용되지 않습니다.|
|AFX_WM_ON_AFTER_SHELL_COMMAND|사용자가 셸 명령 `CMFCShellListCtrl` `CMFCShellTreeCtrl` 실행이 끝나면 부모 또는 컨트롤로 전송됩니다.|사용자가 실행한 명령의 ID|사용되지 않습니다.|응용 프로그램이 이 메시지를 처리하는 경우 0을 반환해야 합니다.|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|프레임워크는 팝업 메뉴를 표시하기 전에 이 메시지를 리본의 부모에게 보냅니다. 이 메시지를 처리하고 팝업 메뉴를 언제든지 수정할 수 있습니다.|사용되지 않습니다.|에 대한 포인터`CMFCBaseRibbonElement`|사용되지 않습니다.|
|AFX_WM_ON_CANCELTABMOVE|내부 전용입니다.|해당 사항 없음|해당 사항 없음||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|프레임워크는 사용자가 활성 리본 제어 범주를 변경할 때 이 메시지를 메인 프레임으로 보냅니다.|사용되지 않습니다.|범주가 `CMFCRibbonBar` 변경된 포인터입니다.|사용되지 않습니다.|
|AFX_WM_ON_CLOSEPOPUPWINDOW|프레임워크는 이 메시지를 보내 창이 닫히려는 `CMFCDesktopAlertWnd` 것을 소유자에게 알립니다.|사용되지 않습니다.|개체에 `CMFCDesktopAlertWnd` 대한 포인터입니다.|사용되지 않습니다.|
|AFX_WM_ON_DRAGCOMPLETE|내부 전용입니다.|해당 사항 없음|해당 사항 없음|해당 사항 없음|
|AFX_WM_ON_GET_TAB_TOOLTIP|사용자 지정 도구 설명이 활성화된 경우 탭 창이 탭에 대한 도구 설명이 표시될 때 기본 프레임 창으로 전송됩니다.|사용되지 않습니다.|구조에 대한 `CMFCTabToolTipInfo` 포인터입니다.|사용되지 않습니다.|
|AFX_WM_ON_HSCROLL|재조정 가능한 컨트롤 바 컨트롤로 전송됩니다. 탭된 위젯 가로 `CMFCTabCtrl` 스크롤 막대에서 스크롤 이벤트가 발생할 때 개체에서 알림을 수신하도록 이 메시지를 처리합니다.|낮은 순서의 단어는 사용자의 스크롤 요청을 나타내는 스크롤 막대 값을 지정합니다.  자세한 내용은 이 항목 뒷부분에 나오는 표를 참조하십시오.|사용되지 않습니다.|비영점.|
|AFX_WM_ON_MOVE_TAB|사용자가 탭을 새 위치로 드래그하면 탭된 창의 상위로 전송됩니다.|원래 위치에 있는 탭의 0기반 인덱스입니다.|【아웃】 새 위치에 있는 탭의 0기반 인덱스입니다.|단계 없음.|
|AFX_WM_ON_MOVETABCOMPLETE|내부 전용입니다.|해당 사항 없음|해당 사항 없음|해당 사항 없음|
|AFX_WM_ON_MOVETOTABGROUP|사용자가 한 탭 그룹에서 다른 탭된 그룹에서 MDI 자식 창을 이동할 때 기본 프레임 창으로 전송됩니다.|MDI 자식 창이 제거된 탭된 창()`CMFCTabCtrl`핸들입니다.|【아웃】 MDI 자식 창이 삽입된 탭된 창()`CMFCTabCtrl`핸들입니다.|무시됩니다.|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|사용자가 컨트롤 막대의 캡션에서 `CDockablePane` **닫기** 단추를 클릭할 때의 부모에게 전송됩니다.|사용되지 않습니다.|사용자가 **닫기** 단추를 클릭한 도킹 창에 대한 포인터입니다.|창을 닫을 수 없는 경우 TRUE입니다. 그렇지 않으면 거짓.|
|AFX_WM_ON_RENAME_TAB|사용자가 편집 가능한 탭의 이름을 바꾼 후 탭된 창의 상위로 전송됩니다.|이름이 변경된 탭의 0기반 인덱스입니다.|【아웃】 새 탭 이름이 포함된 문자열에 대한 포인터입니다.|응용 프로그램이 이 메시지를 처리하는 경우 0이 아닙니다. 프레임워크는 에 대한 `CMFCBaseTabCtrl::SetTabLabel`호출을 억제합니다.  0이 반환되면 `CMFCBaseTabCtrl::SetTabLabel` 프레임워크에서 호출됩니다.|
|AFX_WM_ON_RIBBON_CUSTOMIZE|사용자가 사용자 지정을 시작할 때 상위 프레임으로 전송됩니다. 사용자 지정 대화 상자를 표시하려는 경우 이 메시지를 처리합니다.|사용되지 않습니다.|사용자 지정할 리본 컨트롤에 대한 포인터입니다.|응용 프로그램이 이 메시지를 처리하고 자체 사용자 지정 대화 상자를 표시하는 경우 Nonzero입니다. 응용 프로그램이 0을 반환하면 프레임워크에 기본 제공 사용자 지정 대화 상자가 표시됩니다.|
|AFX_WM_ON_TABGROUPMOUSEMOVE|내부 전용입니다.|해당 사항 없음|해당 사항 없음|해당 사항 없음|
|AFX_WM_POSTSETPREVIEWFRAME|사용자가 인쇄 미리 보기 모드를 변경했다는 것을 주 프레임에 알리기 위해 전송됩니다.|TRUE는 인쇄 미리 보기 모드가 설정되어 있음을 나타냅니다. FALSE는 인쇄 미리 보기 모드가 꺼져 있음을 나타냅니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_PROPERTY_CHANGED|사용자가 선택한 속성의 값을 변경할`CMFCPropertyGridCtrl`때 속성 그리드 컨트롤 () 의 소유자에게 전송됩니다.|속성 목록의 제어 ID입니다.|변경된 속성()`CMFCPropertyGridProperty`포인터입니다.|사용되지 않습니다.|
|AFX_WM_RESETCONTEXTMENU|사용자가 사용자 지정 하는 동안 컨텍스트 메뉴를 재설정 하면 기본 프레임 창으로 전송 됩니다.|컨텍스트 메뉴의 리소스 ID입니다.|현재 컨텍스트 메뉴에 대한 `CMFCPopupMenu`포인터입니다.|사용되지 않습니다.|
|AFX_WM_RESETKEYBOARD|사용자가 사용자 지정 하는 동안 모든 키보드 가속기를 재설정 하면 프레임 창에 이 메시지를 보냅니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETMENU|사용자가 사용자 지정 하는 동안 응용 프로그램 프레임 메뉴를 다시 설정 할 때 프레임 소유자 (프레임 창)에 이 메시지를 보냅니다.|메뉴 리소스 ID입니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETPROMPT|사용자가 대화 상자 사용자 지정 도구 모음에서 도구 모음을 재설정할 때 프레임워크는 이 메시지를 보냅니다. 기본 처리기에는 사용자가 도구 모음을 재설정할지 여부를 묻는 메시지 상자가 표시됩니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETTOOLBAR|`CMFCToolBar` 도구 모음이 리소스에서 로드된 원래 상태로 복원될 때 개체는 이 메시지를 보냅니다. 이 메시지를 처리하여 `CMFCToolbarButton`클래스에서 파생된 도구 모음 단추를 다시 삽입합니다. 자세한 내용은 `CMFCToolbarComboBoxButton`을 참조하세요.|상태가 복원된 도구 모음의 리소스 ID입니다.|사용되지 않습니다.|단계 없음.|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton`개체는 사용자가 일반 메뉴 단추를 클릭할 때 소유자에게 이 메시지를 보냅니다. 사용자가 단추를 클릭할 `CMFCToolbarMenuButton` 때 팝업 메뉴를 표시하는 데 사용할 때마다 이 메시지를 처리합니다.|메시지를 보내는 단추의 명령 ID입니다.|커서의 화면 좌표를 조정합니다. 낮은 순서의 단어는 x 좌표를 지정합니다. 높은 순서의 단어는 y 좌표를 지정합니다.|사용되지 않습니다.|
|AFX_WM_TOOLBARMENU|사용자가 마우스 포인터가 창의 클라이언트 또는 비 클라이언트 영역에 있는 동안 마우스의 오른쪽 단추를 해제할 때 기본 프레임 창으로 전송됩니다.|사용되지 않습니다.|마우스 포인터의 화면 좌표를 조정합니다. 낮은 순서의 단어는 x 좌표를 지정합니다. 높은 순서의 단어는 y 좌표를 지정합니다.|응용 프로그램이 이 메시지를 처리하는 경우 0입니다. 그렇지 않으면 영하지 않습니다.|
|AFX_WM_UPDATETOOLTIPS|모든 도구 설명 소유자에게 전송되어 해당 도구 설명 컨트롤을 다시 만들어야 함을 나타냅니다.|이 메시지를 처리해야 하는 컨트롤 유형입니다. 가능한 값 목록은 이 항목의 후반부표를 참조하십시오.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog`사용자가 **도움말** 단추를 클릭하거나 **도움말** 캡션 단추 또는 F1 키를 클릭하여 도움말 모드로 들어가면 이 메시지가 부모 프레임으로 전송됩니다.|사용되지 않습니다.|의 인스턴스에 대한 `CMFCWindowsManagerDialog`포인터입니다.|사용되지 않습니다.|

다음 표는 AFX_WM_HSCROLL 메서드의 *lParam* 매개 변수의 낮은 단어에 대 한 값을 보여 주어 있습니다.

|||
|-|-|
|값|의미|
|SB_ENDSCROLL|사용자가 스크롤을 종료합니다.|
|SB_LEFT|사용자가 왼쪽 위로 스크롤합니다.|
|SB_RIGHT|사용자가 오른쪽 아래로 스크롤합니다.|
|SB_LINELEFT|사용자가 한 단위로 왼쪽으로 스크롤합니다.|
|SB_LINERIGHT|사용자가 한 단위로 오른쪽으로 스크롤합니다.|
|SB_PAGELEFT|사용자가 창 너비로 왼쪽으로 스크롤합니다.|
|SB_PAGERIGHT|사용자가 창 너비별로 오른쪽으로 스크롤합니다.|
|SB_THUMBPOSITION|사용자가 스크롤 상자(엄지 손가락)를 드래그하고 마우스 단추를 해제했습니다. 높은 순서의 단어는 끌기 작업의 끝에 있는 스크롤 상자의 위치를 나타냅니다.|
|SB_THUMBTRACK|사용자가 스크롤 상자를 끌고 있습니다. AFX_WM_ON_HSCROLL 메시지는 사용자가 마우스 단추를 해제할 때까지 이 값으로 반복적으로 전송됩니다. 높은 순서의 단어는 스크롤 상자가 드래그된 위치를 나타냅니다.|

> [!NOTE]
> *lParam* 매개 변수의 높은 차수 단어는 낮은 차수 단어가 SB_THUMBPOSITION 또는 SB_THUMBTRACK 경우 스크롤 상자의 현재 위치를 지정합니다. 그렇지 않으면 이 단어가 사용되지 않습니다.

다음 표에는 AFX_WM_UPDATETOOLTIPS 메시지의 *lParam* 매개 변수에 대한 플래그 값이 나열됩니다.

|||
|-|-|
|플래그|값|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>참고 항목

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
