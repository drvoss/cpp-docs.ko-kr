---
title: 헤더 컨트롤 및 목록 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 53dd6f1a7878d82a7f7ac48dd7082d791323941b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370467"
---
# <a name="header-control-and-list-control"></a>헤더 컨트롤 및 목록 컨트롤

대부분의 경우 [CListCtrl](../mfc/reference/clistctrl-class.md) 또는 [CListView](../mfc/reference/clistview-class.md) 개체에 포함된 헤더 컨트롤을 사용합니다. 그러나 [CView-파생](../mfc/reference/cview-class.md)개체에서 열이나 행에 정렬된 데이터 조작과 같이 별도의 헤더 제어 개체가 바람직한 경우가 있습니다. 이러한 경우 포함된 헤더 컨트롤의 모양과 기본 동작을 보다 세중하게 제어해야 합니다.

헤더 컨트롤이 표준 기본 동작을 제공하려는 일반적인 경우 [CListCtrl](../mfc/reference/clistctrl-class.md) 또는 [CListView를](../mfc/reference/clistview-class.md) 대신 사용할 수 있습니다. 목록 `CListCtrl` 보기 공통 컨트롤에 포함된 기본 헤더 컨트롤의 기능을 원하는 경우에 사용합니다. 뷰 개체에 포함된 기본 헤더 컨트롤의 기능을 원할 때 [CListView를](../mfc/reference/clistview-class.md) 사용합니다.

> [!NOTE]
> 이러한 컨트롤에는 **LVS_REPORT** 스타일을 사용하여 목록 보기 컨트롤을 만든 경우에만 기본 제공 헤더 컨트롤이 포함됩니다.

대부분의 경우 포함된 목록 보기 컨트롤의 스타일을 변경하여 포함된 헤더 컨트롤의 모양을 수정할 수 있습니다. 또한 헤더 컨트롤에 대한 정보는 상위 목록 뷰 컨트롤의 멤버 함수를 통해 얻을 수 있습니다. 그러나 포함된 헤더 컨트롤의 특성 및 스타일에 대한 완전한 제어 및 액세스의 경우 헤더 제어 개체에 대한 포인터를 가져오는 것이 좋습니다.

포함된 헤더 제어 개체는 각 `CListCtrl` 클래스의 `CListView` `GetHeaderCtrl` 멤버 함수를 호출하거나 호출하여 액세스할 수 있습니다. 다음 코드에서 이 과정을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [헤더 컨트롤이 있는 이미지 목록 사용](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>참고 항목

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
