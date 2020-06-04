---
title: 메시지 범주
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
ms.openlocfilehash: 686d5eef4aaa67785aa56133d820b637fbf4bb86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364749"
---
# <a name="message-categories"></a>메시지 범주

처리기를 작성하는 메시지 의 종류에는 세 가지 주요 범주가 있습니다.

1. Windows 메시지

   여기에는 WM_COMMAND 제외한 **WM_** 접두사로 시작하는 메시지가 주로 포함됩니다. Windows 메시지는 창 및 보기에서 처리됩니다. 이러한 메시지에는 메시지를 처리하는 방법을 결정하는 데 사용되는 매개 변수가 있는 경우가 많습니다.

1. 알림 제어

   여기에는 컨트롤 및 기타 자식 창에서 부모 창으로 WM_COMMAND 알림 메시지가 포함됩니다. 예를 들어 편집 컨트롤은 사용자가 편집 컨트롤에서 텍스트를 변경했을 수 있는 작업을 수행한 경우 EN_CHANGE 제어 알림 코드가 포함된 WM_COMMAND 메시지를 부모에게 보냅니다. 메시지에 대한 창의 처리기는 컨트롤의 텍스트를 검색하는 등 적절한 방법으로 알림 메시지에 응답합니다.

   프레임워크는 다른 **WM_** 메시지와 같은 제어 알림 메시지를 라우팅합니다. 그러나 한 가지 예외는 사용자가 단추를 클릭할 때 단추에서 보내는 BN_CLICKED 제어 알림 메시지입니다. 이 메시지는 특별히 명령 메시지로 처리되고 다른 명령처럼 라우팅됩니다.

1. 명령 메시지

   여기에는 메뉴, 도구 모음 단추 및 가속기 키와 같은 사용자 인터페이스 개체의 알림 메시지가 WM_COMMAND 포함됩니다. 프레임워크는 명령을 다른 메시지와 다르게 처리하며 [명령 대상에](../mfc/command-targets.md)설명된 대로 더 많은 종류의 개체에서 처리할 수 있습니다.

## <a name="windows-messages-and-control-notification-messages"></a><a name="_core_windows_messages_and_control.2d.notification_messages"></a>Windows 메시지 및 제어 알림 메시지

범주 1 및 2의 메시지 - Windows 메시지 및 제어 알림은 클래스에서 파생된 클래스의 개체인 창에서 `CWnd`처리됩니다. 여기에는 `CFrameWnd` `CMDIFrameWnd` `CMDIChildWnd` `CView`이러한 기본 클래스에서 파생된 고유의 클래스와 `CDialog`. 이러한 개체는 Windows `HWND`창에 대한 핸들을 캡슐화합니다.

## <a name="command-messages"></a><a name="_core_command_messages"></a>명령 메시지

범주 3의 메시지 - 명령 - 문서, 문서 템플릿 및 응용 프로그램 개체 자체와 같은 다양한 개체에서 창을 처리하고 볼 수 있습니다. 명령이 특정 개체에 직접 영향을 주는 경우 해당 개체가 명령을 처리하도록 하는 것이 합리적입니다. 예를 들어 파일 메뉴의 열기 명령은 응용 프로그램과 논리적으로 연결됩니다. 따라서 Open 명령의 처리기는 응용 프로그램 클래스의 멤버 함수입니다. 명령 및 명령이 개체로 라우팅되는 방법에 대한 자세한 내용은 [프레임워크가 처리기를 호출하는 방법을](../mfc/how-the-framework-calls-a-handler.md)참조하십시오.

## <a name="see-also"></a>참고 항목

[프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)
