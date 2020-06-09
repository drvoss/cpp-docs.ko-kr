---
title: Messages
ms.date: 11/04/2016
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
ms.openlocfilehash: f36dab679a2e41910b2445a7dab36f5786081563
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624276"
---
# <a name="messages"></a>Messages

`Run`클래스의 멤버 함수에 있는 메시지 루프는 `CWinApp` 다양 한 이벤트에 의해 생성 된 대기 중인 메시지를 검색 합니다. 예를 들어 사용자가 마우스를 클릭 하면 마우스 왼쪽 단추를 누르고 마우스 왼쪽 단추를 놓을 때 WM_LBUTTONUP WM_LBUTTONDOWN와 같은 몇 가지 마우스 관련 메시지가 전송 됩니다. 프레임 워크의 응용 프로그램 메시지 루프 구현에서는 메시지를 적절 한 창에 디스패치합니다.

메시지 [범주](message-categories.md)에는 메시지의 중요 한 범주가 설명 되어 있습니다.

## <a name="see-also"></a>참고 항목

[프레임워크의 메시지 및 명령](messages-and-commands-in-the-framework.md)
