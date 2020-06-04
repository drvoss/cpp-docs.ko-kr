---
title: 애플리케이션 마법사로 만든 프레임 창 클래스
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
ms.openlocfilehash: c17ba2b6dd79e8e62baa29bba403c136d16a0d95
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077531"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>애플리케이션 마법사로 만든 프레임 창 클래스

응용 프로그램, 문서 및 뷰 클래스 외에도 **새 프로젝트** 대화 상자에서 새 MFC 프로젝트를 만들 때 응용 프로그램 마법사는 응용 프로그램의 주 프레임 창에 대해 파생 프레임 창 클래스를 만듭니다. 클래스는 기본적으로 `CMainFrame` 호출 되며,이를 포함 하는 파일의 이름은 MAINFRM.CPP입니다. H 및 MAINFRM.CPP. .CPP.

응용 프로그램이 SDI 인 경우 `CMainFrame` 클래스는 [CFrameWnd](../mfc/reference/cframewnd-class.md)클래스에서 파생 됩니다.

응용 프로그램이 MDI 인 경우 `CMainFrame`는 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)클래스에서 파생 됩니다. 이 경우 `CMainFrame`는 메뉴, 도구 모음 및 상태 표시줄을 포함 하는 주 프레임을 구현 합니다. 응용 프로그램 마법사는 새로운 문서 프레임 창 클래스를 파생 하지 않습니다. 대신 [CMDIChildWnd 클래스](../mfc/reference/cmdichildwnd-class.md)의 기본 구현을 사용 합니다. MFC 프레임 워크는 각 뷰 (`CScrollView`, `CEditView`, `CTreeView`, `CListView`등)를 포함 하는 자식 창을 만들어 응용 프로그램에 필요한 형식입니다. 문서 프레임 창을 사용자 지정 해야 하는 경우 새 문서 프레임 창 클래스를 만들 수 있습니다 ( [클래스 추가](../ide/adding-a-class-visual-cpp.md)참조).

도구 모음을 지원 하도록 선택 하는 경우 클래스에는 [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [cstatusbar](../mfc/reference/cstatusbar-class.md) 형식의 멤버 변수를 포함 하 고 두 개의 [컨트롤 막대](../mfc/control-bars.md)를 초기화 하는 `OnCreate` 메시지 처리기 함수를 사용할 수도 있습니다.

이러한 프레임 창 클래스는 생성 된 대로 작동 하지만 기능을 향상 시키려면 멤버 변수와 멤버 함수를 추가 해야 합니다. 창 클래스에서 다른 Windows 메시지를 처리 하도록 할 수도 있습니다. 자세한 내용은 [MFC에서 만든 창의 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[프레임 창 클래스](../mfc/frame-window-classes.md)<br/>
[MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../build/reference/mfc-program-or-control-source-and-header-files.md)
