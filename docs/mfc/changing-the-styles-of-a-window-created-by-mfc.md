---
title: MFC에서 만든 창 스타일 변경
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
ms.openlocfilehash: 221092eb25a4f044cda5b379d6774659d9e9d2d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374588"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC에서 만든 창 스타일 변경

`WinMain` 해당 버전의 함수에서 MFC는 여러 표준 창 클래스를 등록합니다. 일반적으로 MFC를 `WinMain`편집하지 않으므로 이 함수는 MFC 기본 창 스타일을 변경할 수 없습니다. 이 문서에서는 기존 응용 프로그램에서 미리 등록된 창 클래스의 스타일을 변경하는 방법을 설명합니다.

## <a name="changing-styles-in-a-new-mfc-application"></a><a name="_core_changing_styles_in_a_new_mfc_application"></a>새 MFC 응용 프로그램에서 스타일 변경

Visual C++ 2.0 이상을 사용하는 경우 응용 프로그램을 만들 때 응용 프로그램 마법사에서 기본 창 스타일을 변경할 수 있습니다. 응용 프로그램 마법사의 사용자 인터페이스 기능 페이지에서 기본 프레임 창 및 MDI 자식 창에 대한 스타일을 변경할 수 있습니다. 두 창 유형 중 하나에 대해 프레임 두께(굵거나 얇은)와 다음 중 하나를 지정할 수 있습니다.

- 창에 최소화 또는 최대화 컨트롤이 있는지 여부입니다.

- 창이 처음에 최소화, 최대화 또는 둘 다 나타나는지 여부입니다.

주 프레임 창의 경우 창에 시스템 메뉴가 있는지 여부를 지정할 수도 있습니다. MDI 자식 창의 경우 창이 스플리터 창을 지원하는지 여부를 지정할 수 있습니다.

## <a name="changing-styles-in-an-existing-application"></a><a name="_core_changing_styles_in_an_existing_application"></a>기존 응용 프로그램의 스타일 변경

기존 응용 프로그램에서 창 특성을 변경하는 경우 이 문서의 나머지 부분에 있는 지침을 따릅니다.

응용 프로그램 마법사로 만든 프레임워크 응용 프로그램에서 사용하는 기본 창 특성을 변경하려면 창의 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 가상 멤버 함수를 재정의합니다. `PreCreateWindow`응용 프로그램이 일반적으로 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) 클래스에서 내부적으로 관리하는 생성 프로세스에 액세스할 수 있습니다. 프레임워크는 `PreCreateWindow` 창을 만들기 직전에 호출합니다. `PreCreateWindow`에 전달 된 [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) 구조를 수정 하 여 응용 프로그램 창을 만드는 데 사용 하는 특성을 변경할 수 있습니다. 예를 들어 창에서 캡션을 사용하지 않도록 하려면 다음 비트별 작업을 사용합니다.

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md) 샘플 응용 프로그램은 창 특성을 변경하기 위한 이 기술을 보여 줍니다. 응용 프로그램이 변경되는 `PreCreateWindow`항목에 따라 함수의 기본 클래스 구현을 호출해야 할 수 있습니다.

다음 설명에서는 SDI 사례와 [MDI 사례를](#_core_the_mdi_case)다룹니다.

## <a name="the-sdi-case"></a><a name="_core_the_sdi_case"></a>SDI 케이스

단일 문서 인터페이스(SDI) 응용 프로그램에서 프레임워크의 기본 창 스타일은 **WS_OVERLAPPEDWINDOW** **FWS_ADDTOTITLE** 스타일의 조합입니다. **FWS_ADDTOTITLE** 프레임 워크창의 캡션에 문서 제목을 추가 하도록 지시 하는 MFC 관련 스타일입니다. SDI 응용 프로그램의 창 특성을 변경하려면 `PreCreateWindow` 응용 프로그램 마법사 이름에서 `CFrameWnd` `CMainFrame`파생된 클래스의 함수를 재정의합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

이 코드는 최소화 및 최대화 버튼 없이 상당한 테두리 없이 주 프레임 창을 만듭니다. 창은 처음에 화면의 가운데에 있습니다.

## <a name="the-mdi-case"></a><a name="_core_the_mdi_case"></a>MDI 케이스

여러 문서 인터페이스(MDI) 응용 프로그램에서 자식 창의 창 스타일을 변경하려면 조금 더 많은 작업이 필요합니다. 기본적으로 응용 프로그램 마법사로 만든 MDI 응용 프로그램은 MFC에 정의된 기본 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 클래스를 사용합니다. MDI 자식 창의 창 스타일을 변경하려면 프로젝트에서 새 `CMDIChildWnd` 클래스를 파생하고 프로젝트의 모든 참조를 `CMDIChildWnd` 새 클래스에 대한 참조로 바꿔야 합니다. 대부분의 경우 응용 프로그램에서 `CMDIChildWnd` 유일한 참조는 응용 프로그램의 `InitInstance` 멤버 함수에 있습니다.

MDI 응용 프로그램에 사용되는 기본 창 스타일은 **WS_CHILD,** **WS_OVERLAPPEDWINDOW**및 **FWS_ADDTOTITLE** 스타일의 조합입니다. MDI 응용 프로그램의 자식 창의 창 특성을 변경하려면 에서 파생된 클래스의 `CMDIChildWnd` [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 함수를 재정의합니다. 다음은 그 예입니다.

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

이 코드는 최대화 버튼 없이 MDI 자식 창을 만듭니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [윈도우 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

- [창 스타일](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>참고 항목

[프레임 창 스타일](../mfc/frame-window-styles-cpp.md)
