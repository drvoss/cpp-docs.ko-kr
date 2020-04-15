---
title: 목록 컨트롤 스타일 변경
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 5f45e0549c3fc0f5747f8dd12a6310fafd7dd7bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370809"
---
# <a name="changing-list-control-styles"></a>목록 컨트롤 스타일 변경

목록[컨트롤(CListCtrl)을](../mfc/reference/clistctrl-class.md)만든 후 언제든지 목록 컨트롤의 창 스타일을 변경할 수 있습니다. 창 스타일을 변경하면 컨트롤에서 사용하는 뷰의 종류가 변경됩니다. 예를 들어 탐색기를 에뮬레이트하려면 아이콘 보기, 목록 보기 등 서로 다른 보기 간에 컨트롤을 전환하기 위한 메뉴 항목 또는 도구 모음 단추를 제공할 수 있습니다.

예를 들어 사용자가 메뉴 항목을 선택하면 [GetWindowLong을](/windows/win32/api/winuser/nf-winuser-getwindowlongw) 호출하여 컨트롤의 현재 스타일을 검색한 다음 [SetWindowLong을](/windows/win32/api/winuser/nf-winuser-setwindowlongw) 호출하여 스타일을 재설정할 수 있습니다. 자세한 내용은 Windows SDK의 [목록 보기 컨트롤 사용을](/windows/win32/Controls/using-list-view-controls) 참조하십시오.

사용 가능한 스타일은 [만들기](../mfc/reference/clistctrl-class.md#create)에 나열됩니다. 스타일은 **LVS_ICON**, **LVS_SMALLICON**, **LVS_LIST**및 **LVS_REPORT** 네 개의 목록 컨트롤 뷰를 지정합니다.

## <a name="extended-styles"></a>확장 스타일

목록 컨트롤에 대한 표준 스타일 외에도 확장 스타일이라고 하는 다른 집합이 있습니다. Windows SDK의 [확장 목록 보기 스타일에서](/windows/win32/Controls/extended-list-view-styles) 설명하는 이러한 스타일은 목록 컨트롤의 동작을 사용자 지정하는 다양한 유용한 기능을 제공합니다. 특정 스타일(예: 호버 선택)의 동작을 구현하려면 [CListCtrl::SetExtendedStyle을](../mfc/reference/clistctrl-class.md#setextendedstyle)호출하여 필요한 스타일을 전달합니다. 다음 예제에서는 함수 호출을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> 호버 선택작업을 수행하려면 **LVS_EX_ONECLICKACTIVATE** 또는 **LVS_EX_TWOCLICKACTIVATE** 켜져 있어야 합니다.

## <a name="see-also"></a>참고 항목

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
