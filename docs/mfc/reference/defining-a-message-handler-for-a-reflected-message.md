---
title: 리플렉트된 메시지의 메시지 처리기 정의
ms.date: 09/07/2019
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: f7f90d3347ac61abcfcb48e77ef39aa2626ae5c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365861"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>리플렉트된 메시지의 메시지 처리기 정의

새 MFC 컨트롤 클래스를 만든 후에는 메시지 처리기를 정의할 수 있습니다. 반영된 메시지 처리기를 사용하면 컨트롤 클래스가 부모가 메시지를 받기 전에 자체 메시지를 처리할 수 있습니다. MFC [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 기능을 사용하여 컨트롤에서 부모 창으로 메시지를 보낼 수 있습니다.

예를 들어 이 기능을 사용하면 부모 창에 의존하지 않고 자체적으로 다시 그리는 목록 상자를 만들 수 있습니다(소유자가 그려집니다). 반영된 메시지에 대한 자세한 내용은 [반영된 메시지 처리를](../../mfc/handling-reflected-messages.md)참조하십시오.

동일한 기능을 사용하여 [ActiveX 컨트롤을](../../mfc/activex-controls-on-the-internet.md) 만들려면 ActiveX 컨트롤에 대한 프로젝트를 만들어야 합니다.

> [!NOTE]
> 아래 설명된 대로 클래스 마법사를 사용하여 ActiveX 컨트롤에 대해 반사된 메시지(OCM_*메시지)를*추가할 수 없습니다. 이러한 메시지를 수동으로 추가해야 합니다.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-class-wizard"></a>클래스 마법사에서 반사된 메시지에 대한 메시지 처리기를 정의하려면

1. MFC 프로젝트에 목록, 철근 컨트롤, 도구 모음 또는 트리 컨트롤과 같은 컨트롤을 추가합니다.

1. 클래스 보기에서 컨트롤 클래스의 이름을 클릭합니다.

1. 클래스 [마법사에서](mfc-class-wizard.md)컨트롤 클래스 이름이 **클래스 이름** 목록에 나타납니다.

1. **메시지** 탭을 클릭하여 컨트롤에 추가할 수 있는 Windows 메시지를 표시합니다.

1. 처리기를 정의할 반사된 메시지를 선택합니다. 반사된 메시지는 등가 기호(=)로 표시됩니다.

1. 클래스 마법사의 오른쪽 열에 있는 셀을 클릭하여 처리기의 \<제안된 이름을 *>HandlerName*을 추가합니다. (예를 들어 **= WM_CTLCOLOR** 메시지 \<처리기는 **ctlColor에**>추가하는 것을 제안합니다.

1. 수락할 권장 이름을 클릭합니다. 처리기가 프로젝트에 추가됩니다.

1. 메시지 처리기를 편집하거나 삭제하려면 4~7단계를 반복합니다. 처리기 이름이 포함된 셀을 클릭하여 해당 작업을 편집 또는 삭제하고 클릭합니다.

## <a name="see-also"></a>참고 항목

[함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[코드 마법사에서 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
