---
title: 도구 모음 도구 설명
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: 1762931b75734801659fd6271377260bd0473614
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373452"
---
# <a name="toolbar-tool-tips"></a>도구 모음 도구 설명

도구 팁은 마우스를 단추 위에 잠시 배치할 때 도구 모음 단추의 목적에 대한 간단한 설명을 제공하는 작은 팝업 창입니다. 도구 모음이 있는 응용 프로그램 마법사를 사용하여 응용 프로그램을 만들 면 도구 설명 지원이 제공됩니다. 이 문서에서는 응용 프로그램 마법사에서 만든 도구 설명 부및 응용 프로그램에 도구 설명 지원을 추가하는 방법에 대해 설명합니다.

이 문서에서는 다음 내용을 설명합니다.

- [도구 팁 활성화](#_core_activating_tool_tips)

- [플라이비 상태 표시줄 업데이트](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a>도구 팁 활성화

응용 프로그램에서 도구 팁을 활성화하려면 다음 두 가지 작업을 수행해야 합니다.

- CBRS_TOOLTIPS 스타일을 다른 스타일(예: WS_CHILD, WS_VISIBLE 및 기타 **CBRS_** 스타일)에 *dwStyle* 매개변수로 전달하여 [CToolBar::Create](../mfc/reference/ctoolbar-class.md#create) 함수 또는 [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)에 추가합니다.

- 아래 절차에서 설명한 대로 줄 바 명령에 대 한 명령줄 프롬프트를 포함 하는 문자열 리소스에 줄 바 문자('\n')로 구분된 도구 모음 팁 텍스트를 더해 두세요. 문자열 리소스는 도구 모음 단추의 ID를 공유합니다.

#### <a name="to-add-the-tool-tip-text"></a>도구 설명 텍스트를 추가하려면

1. 도구 모음 편집기에서 도구 모음을 편집하는 동안 지정된 단추에 대한 **도구 모음 단추 속성** 창을 엽니다.

1. **프롬프트** 상자에서 해당 단추의 도구 설명에 표시할 텍스트를 지정합니다.

> [!NOTE]
> 도구 모음 편집기에서 텍스트를 단추 속성으로 설정하면 문자열 리소스를 열고 편집해야 했던 이전 프로시저가 대체됩니다.

도구 설명이 활성화된 컨트롤 막대에 자식 컨트롤이 배치된 경우 컨트롤 막대는 다음 기준을 충족하는 한 컨트롤 막대의 모든 자식 컨트롤에 대한 도구 설명입니다.

- 컨트롤의 ID는 그렇지 않습니다 - 1.

- 리소스 파일의 자식 컨트롤과 동일한 ID를 가진 문자열 테이블 항목에는 도구 설명 문자열이 있습니다.

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a>플라이비 상태 표시줄 업데이트

도구 팁과 관련된 기능은 "플라이비" 상태 표시줄 업데이트입니다. 기본적으로 상태 표시줄의 메시지는 단추를 활성화할 때 특정 도구 모음 단추만 설명합니다. `CToolBar::Create`에 전달된 스타일 목록에 CBRS_FLYBY 포함하면 마우스 커서가 실제로 단추를 활성화하지 않고 도구 모음을 통과할 때 이러한 메시지를 업데이트할 수 있습니다.

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- [MFC 도구 모음 구현(도구 모음에 대한 개요 정보)](../mfc/mfc-toolbar-implementation.md)

- [도구 모음 고정 및 고정 해제](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) 및 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [도구 모음 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고 항목

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
