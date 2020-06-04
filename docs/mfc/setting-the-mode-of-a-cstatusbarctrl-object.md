---
title: CStatusBarCtrl 개체의 모드 설정
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: e09a7bd274c44df2da48bbc007a95802fadd8cf0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365413"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체의 모드 설정

`CStatusBarCtrl` 개체에 대한 두 가지 모드가 있습니다: 단순 및 비단순. 대부분의 경우 상태 표시줄 컨트롤에는 텍스트 및 아이콘 또는 아이콘과 함께 하나 이상의 부분이 있습니다. 이를 단순하지 않은 모드라고 합니다. 이 모드에 대한 자세한 내용은 [CStatusBarCtrl 개체의 부품 초기화를](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)참조하십시오.

그러나 한 줄의 텍스트만 표시해야 하는 경우가 있습니다. 이 경우 간단한 모드로 충분합니다. `CStatusBarCtrl` 개체의 모드를 단순으로 변경하려면 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) 멤버 함수를 호출합니다. 상태 표시줄 컨트롤이 단순 모드로 설정되면 `SetText` 멤버 함수를 호출하여 255를 *nPane* 매개 변수의 값으로 전달하여 텍스트를 설정합니다.

[IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) 함수를 사용하여 개체가 `CStatusBarCtrl` 어떤 모드인지 확인할 수 있습니다.

> [!NOTE]
> 상태 표시줄 개체가 단순하지 않은 개체에서 단순으로 변경되거나 그 반대로 변경되는 경우 창이 즉시 다시 그려지고 해당하는 경우 정의된 부품이 자동으로 복원됩니다.

## <a name="see-also"></a>참고 항목

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
