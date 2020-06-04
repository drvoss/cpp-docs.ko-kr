---
title: 컨트롤 막대
ms.date: 11/04/2016
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
ms.openlocfilehash: ceae20c89d9a6d3f4393f838b3594938107785f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353579"
---
# <a name="control-bars"></a>컨트롤 막대

"컨트롤 막대"는 도구 모음, 상태 표시줄 및 대화 상자 막대의 일반 이름입니다. MFC `CToolBar`클래스 `CStatusBar` `CDialogBar`는 `COleResizeBar`공통 `CReBar` 기능을 구현하는 [클래스 CControlBar에서](../mfc/reference/ccontrolbar-class.md)파생됩니다.

컨트롤 막대는 사용자가 옵션을 선택하거나 명령을 실행하거나 프로그램 정보를 가져올 수 있는 컨트롤 행을 표시하는 창입니다. 컨트롤 막대 유형에는 도구 모음, 대화 상자 막대 및 상태 표시줄이 포함됩니다.

- 동급 [CToolBar의](../mfc/reference/ctoolbar-class.md) 도구 모음

- 상태 표시줄, 클래스 [CStatusBar](../mfc/reference/cstatusbar-class.md)

- 대화 상자 막대, 클래스 [CDialogBar](../mfc/reference/cdialogbar-class.md)

- 철근, 클래스 [CReBar](../mfc/reference/crebar-class.md)

> [!IMPORTANT]
> MFC 버전 4.0을 참조하면 도구 모음, 상태 표시줄 및 도구 설명은 MFC와 관련된 이전 구현 대신 *comctl32.dll에* 구현된 시스템 기능을 사용하여 구현됩니다. MFC 버전 6.0에서는 `CReBar`comctl32.dll 기능도 래핑하여 추가되었습니다.

컨트롤 바 유형에 대한 간략한 소개는 다음과 같습니다. 자세한 내용은 아래 링크를 참조하십시오.

## <a name="control-bars"></a>컨트롤 막대

컨트롤 바는 빠른 한 단계 명령 작업을 제공하여 프로그램의 유용성을 크게 향상시킵니다. 클래스는 `CControlBar` 모든 도구 모음, 상태 표시줄 및 대화 상자 막대의 공통 기능을 제공합니다. `CControlBar`은 컨트롤 막대를 상위 프레임 창에 배치하는 기능을 제공합니다. 컨트롤 막대는 일반적으로 상위 프레임 창의 자식 창이므로 프레임 창의 클라이언트 보기 또는 MDI 클라이언트에 대한 "형제"입니다. 컨트롤-막대 개체는 부모 창의 클라이언트 사각형에 대한 정보를 사용하여 자체 위치를 지정합니다. 그런 다음 클라이언트 보기 또는 MDI 클라이언트 창이 클라이언트 창의 나머지 부분을 채우게 되도록 부모의 나머지 클라이언트 창 사각형을 변경합니다.

> [!NOTE]
> 컨트롤 막대의 단추에 **COMMAND** 또는 **UPDATE_COMMAND_UI** 처리기가 없는 경우 프레임워크는 자동으로 단추를 비활성화합니다.

## <a name="toolbars"></a>도구 모음

도구 모음은 명령을 수행하는 비트매핑 단추 행을 표시하는 컨트롤 모음입니다. 도구 모음 단추를 누르는 것은 메뉴 항목을 선택하는 것과 같습니다. 해당 메뉴 항목의 ID가 도구 모음 단추와 동일한 경우 메뉴 항목에 매핑된 동일한 처리기를 호출합니다. 단추는 푸시 버튼, 라디오 단추 또는 확인란으로 표시되고 동작하도록 구성할 수 있습니다. 도구 모음은 일반적으로 프레임 창의 맨 위에 정렬되지만 MFC 도구 모음은 부모 창의 모든 면에 "도킹"하거나 자체 미니 프레임 창에 부동할 수 있습니다. 도구 모음은 또한 "부동"할 수 있으며 크기를 변경하고 마우스로 드래그 할 수 있습니다. 사용자가 도구 모음의 단추 위로 마우스를 이동할 때 도구 모음에 도구 설명이 표시될 수도 있습니다. 도구 설명은 단추의 용도를 간략하게 설명하는 작은 팝업 창입니다.

> [!NOTE]
> MFC 버전 4.0에서 클래스 [CToolBar는](../mfc/reference/ctoolbar-class.md) Windows 도구 모음 공통 컨트롤을 사용합니다. A에는 `CToolBar` [CToolBarCtrl이](../mfc/reference/ctoolbarctrl-class.md)포함되어 있습니다. 그러나 이전 도구 모음은 여전히 지원됩니다. [도구 모음](../mfc/mfc-toolbar-implementation.md)을 참조하십시오.

## <a name="status-bars"></a>상태 표시줄

상태 표시줄은 텍스트 출력 창 또는 "표시기"를 포함하는 컨트롤 막대입니다. 출력 창은 일반적으로 메시지 줄 및 상태 표시기로 사용됩니다. 메시지 줄 예제에는 MFC 응용 프로그램 마법사에서 만든 기본 상태 표시줄의 맨 왼쪽창에서 선택한 메뉴 또는 도구 모음 명령을 간략하게 설명하는 명령 도움말 메시지 줄이 포함됩니다. 상태 표시기 예제에는 스크롤 잠금, NUM 잠금 및 기타 키가 포함됩니다. 상태 표시줄은 일반적으로 프레임 창의 맨 아래에 정렬됩니다. 클래스 [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 클래스 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)을 참조하십시오.

## <a name="dialog-bars"></a>대화 상자 모음

대화 상자 막대는 모덜리스 대화 상자의 기능이 있는 대화 상자-템플릿 리소스를 기반으로 하는 컨트롤 막대입니다. 대화 막대에는 Windows, 사용자 지정 또는 ActiveX 컨트롤이 포함될 수 있습니다. 대화 상자에서와 마찬가지로 사용자는 컨트롤 간에 탭할 수 있습니다. 대화 상자 막대는 프레임 창의 위쪽, 아래쪽, 왼쪽 또는 오른쪽에 정렬할 수 있으며 자체 프레임 창에 부동시킬 수도 있습니다. 클래스 [CDialogBar](../mfc/reference/cdialogbar-class.md)를 참조하십시오.

## <a name="rebars"></a>리바

[철근은](../mfc/using-crebarctrl.md) 철근 컨트롤에 대한 도킹, 레이아웃, 상태 및 지속성 정보를 제공하는 컨트롤 막대입니다. 철근 개체에는 편집 상자, 도구 모음 및 목록 상자를 비롯한 다양한 하위 창(일반적으로 다른 컨트롤)이 포함될 수 있습니다. 철근 객체는 지정된 비트맵 위에 자식 창을 표시할 수 있습니다. 그리퍼 바를 클릭하거나 드래그하여 자동으로 또는 수동으로 크기를 조정할 수 있습니다. 클래스 [CReBar를](../mfc/reference/crebar-class.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
