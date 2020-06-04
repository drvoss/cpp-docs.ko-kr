---
title: CStatusBarCtrl 개체에서 도구 설명 사용
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 29d326c708743424686d616bbaf172ccd72481ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374701"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체에서 도구 설명 사용

상태 표시줄 컨트롤에 대한 도구 `CStatusBarCtrl` 설명을 사용하려면 SBT_TOOLTIPS 스타일로 개체를 만듭니다.

> [!NOTE]
> 개체를 `CStatusBar` 사용하여 상태 표시줄을 구현하는 경우 `CStatusBar::CreateEx` 이 함수를 사용합니다. 포함된 `CStatusBarCtrl` 객체에 대한 추가 스타일을 지정할 수 있습니다.

개체가 `CStatusBarCtrl` 성공적으로 만들어지면 [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) 및 [CStatusBarCtrl::GetTipText를](../mfc/reference/cstatusbarctrl-class.md#gettiptext) 사용하여 특정 창에 대한 팁 텍스트를 설정하고 검색합니다.

공구 팁이 설정되면 부품에 아이콘과 텍스트가 없거나 부품 내부에 모든 텍스트를 표시할 수 없는 경우에만 표시됩니다. 도구 설명은 간단한 모드에서 지원되지 않습니다.

## <a name="see-also"></a>참고 항목

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
