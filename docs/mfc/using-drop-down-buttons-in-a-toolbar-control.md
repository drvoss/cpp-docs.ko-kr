---
title: 도구 모음 컨트롤에서 드롭다운 단추 사용
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: 0bc4df4c07ec4b8bc5b488925cbb140609302186
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365060"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>도구 모음 컨트롤에서 드롭다운 단추 사용

도구 모음에는 표준 푸시 버튼 외에도 드롭다운 버튼이 있을 수 있습니다. 드롭다운 버튼은 일반적으로 아래쪽 화살표가 부착되어 있는 것으로 표시됩니다.

> [!NOTE]
> TBSTYLE_EX_DRAWDDARROWS 확장 스타일이 설정된 경우에만 연결된 아래쪽 화살표가 나타납니다.

사용자가 이 화살표(또는 화살표가 없는 경우 단추 자체)를 클릭하면 도구 모음 컨트롤의 상위 사용자에게 TBN_DROPDOWN 알림 메시지가 전송됩니다. 그런 다음 이 알림을 처리하고 팝업 메뉴를 표시할 수 있습니다. 인터넷 익스플로러의 동작과 유사합니다.

다음 절차에서는 팝업 메뉴를 사용하여 드롭다운 도구 모음 단추를 구현하는 방법을 보여 줍니다.

### <a name="to-implement-a-drop-down-button"></a>드롭다운 단추를 구현하려면

1. `CToolBarCtrl` 개체가 만들어지면 다음 코드를 사용하여 TBSTYLE_EX_DRAWDDARROWS 스타일을 설정합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. 새[(삽입 버튼](../mfc/reference/ctoolbarctrl-class.md#insertbutton) 또는 추가 [버튼)](../mfc/reference/ctoolbarctrl-class.md#addbuttons)또는 드롭 다운 버튼이 될 기존[(SetButtonInfo)](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)버튼에 대한 TBSTYLE_DROPDOWN 스타일을 설정합니다. 다음 예제에서는 개체의 기존 단추를 `CToolBarCtrl` 수정하는 것을 보여 줍니다.

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. 도구 모음 개체의 상위 클래스에 TBN_DROPDOWN 처리기를 추가합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. 새 처리기에서 적절한 팝업 메뉴를 표시합니다. 다음 코드는 한 가지 방법을 보여 줍니다.

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>참고 항목

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
