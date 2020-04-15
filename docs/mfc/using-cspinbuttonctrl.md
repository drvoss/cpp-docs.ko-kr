---
title: CSpinButtonCtrl 사용
ms.date: 11/04/2016
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: 6f72601d3813f36e4a99b9ab04f2e9383c58df94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366477"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl 사용

*스핀 버튼* *컨트롤(업다운* 컨트롤이라고도 함)은 사용자가 클릭하여 값을 조정할 수 있는 화살표 쌍을 제공합니다. 이 값을 현재 *위치라고*합니다. 위치는 스핀 버튼 범위 내에 유지됩니다. 사용자가 위쪽 화살표를 클릭하면 위치가 최대값으로 이동합니다. 사용자가 아래쪽 화살표를 클릭하면 위치가 최소값으로 이동합니다.

스핀 버튼 컨트롤은 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) 클래스에 의해 MFC로 표시됩니다.

> [!NOTE]
> 기본적으로 스핀 버튼의 범위는 최대 값이 0(0)으로 설정되고 최소값은 100으로 설정됩니다. 최대값이 최소값보다 적기 때문에 위쪽 화살표를 클릭하면 위치가 줄어들고 아래쪽 화살표를 클릭하면 화살표가 증가합니다. [CSpinButtonCtrl::SetRange를](../mfc/reference/cspinbuttonctrl-class.md#setrange) 사용하여 이러한 값을 조정합니다.

일반적으로 현재 위치는 컴패니언 컨트롤에 표시됩니다. 도우미 컨트롤을 버디 *창이라고*합니다. 스핀 단추 컨트롤의 그림은 Windows SDK의 [업다운 컨트롤 을](/windows/win32/Controls/up-down-controls) 참조하십시오.

Visual Studio에서 스핀 컨트롤 및 편집 컨트롤 버디 창을 만들려면 먼저 편집 컨트롤을 대화 상자 또는 창으로 드래그한 다음 스핀 컨트롤을 드래그합니다. 스핀 컨트롤을 선택하고 **자동 버디** 및 **설정 버디 정수** 속성을 **True로**설정합니다. 또한 **정렬** 속성을 설정합니다. **오른쪽 정렬이** 가장 일반적입니다. 이러한 설정을 사용하면 편집 컨트롤이 탭 순서의 편집 컨트롤 바로 앞에 있기 때문에 편집 컨트롤이 버디 창으로 설정됩니다. 편집 컨트롤은 정수를 표시하고 스핀 컨트롤은 편집 컨트롤의 오른쪽에 포함됩니다. 선택적으로 [CSpinButtonCtrl:SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 메서드를 사용하여 스핀 컨트롤의 유효한 범위를 설정할 수 있습니다. 데이터를 직접 교환하기 때문에 스핀 컨트롤과 버디 창 간에 통신할 필요가 없습니다. 스핀 컨트롤을 사용하여 창 또는 대화 상자 시퀀스를 페이징한 다음 UDN_DELTAPOS 메시지에 대한 처리기를 추가하고 사용자 지정 작업을 수행합니다.

## <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [스핀 단추 스타일](../mfc/spin-button-styles.md)

- [스핀 단추 멤버 함수](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>참고 항목

[컨트롤](../mfc/controls-mfc.md)
