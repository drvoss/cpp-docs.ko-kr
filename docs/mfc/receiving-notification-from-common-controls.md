---
title: 공용 컨트롤에서 알림 받기
ms.date: 11/04/2016
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
ms.openlocfilehash: 9205facb5ec4e2491308020d9667a27ab8deb96b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371790"
---
# <a name="receiving-notification-from-common-controls"></a>공용 컨트롤에서 알림 받기

일반적인 컨트롤은 사용자의 입력과 같은 이벤트가 컨트롤에서 발생할 때 부모 창에 알림 메시지를 보내는 자식 창입니다.

응용 프로그램은 이러한 알림 메시지를 사용하여 사용자가 수행하려는 작업을 결정합니다. 대부분의 일반적인 컨트롤은 알림 메시지를 WM_NOTIFY 메시지로 보냅니다. Windows 컨트롤은 대부분의 알림 메시지를 WM_COMMAND 메시지로 보냅니다. [CWnd::OnNotify는](../mfc/reference/cwnd-class.md#onnotify) WM_NOTIFY 메시지의 처리기입니다. 마찬가지로 `CWnd::OnCommand`디스패치의 `OnNotify` 구현은 메시지 맵에서 처리하기 `OnCmdMsg` 위한 알림 메시지를 전달합니다. 알림 처리를 위한 메시지 맵 항목은 ON_NOTIFY. 자세한 내용은 [기술 참고 61: ON_NOTIFY 및 WM_NOTIFY 메시지를](../mfc/tn061-on-notify-and-wm-notify-messages.md)참조하십시오.

또는 파생 클래스는 "메시지 리플렉션"을 사용하여 자체 알림 메시지를 처리할 수 있습니다. 자세한 내용은 [기술 참고 62: Windows 컨트롤에 대한 메시지 반사를](../mfc/tn062-message-reflection-for-windows-controls.md)참조하십시오.

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>알림 메시지에서 커서 위치 검색

경우에 따라 공통 컨트롤에서 특정 알림 메시지를 수신할 때 커서의 현재 위치를 확인하는 것이 유용합니다. 예를 들어 공통 컨트롤이 NM_RCLICK 알림 메시지를 수신할 때 현재 커서 위치를 확인하는 것이 좋습니다.

호출하여 `CWnd::GetCurrentMessage`이 작업을 수행하는 간단한 방법이 있습니다. 그러나 이 메서드는 메시지를 보낸 시점의 커서 위치만 검색합니다. 메시지가 전송된 이후 커서가 이동되었을 수 있으므로 `CWnd::GetCursorPos` 현재 커서 위치를 얻으려면 호출해야 합니다.

> [!NOTE]
> `CWnd::GetCurrentMessage`메시지 처리기 내에서만 호출해야 합니다.

알림 메시지 처리기의 본문에 다음 코드를 추가합니다(이 예에서는 NM_RCLICK).

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

이 시점에서 마우스 커서 위치는 개체에 `cursorPos` 저장됩니다.

## <a name="see-also"></a>참고 항목

[컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
