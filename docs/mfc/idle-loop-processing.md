---
title: 유휴 루프 처리
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
ms.openlocfilehash: 9579d4bb8768b0227453af401d6fdc8a8bd482b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376004"
---
# <a name="idle-loop-processing"></a>유휴 루프 처리

많은 응용 프로그램이 "백그라운드에서" 긴 처리를 수행합니다. 경우에 따라 성능 고려 사항은 이러한 작업에 대해 멀티스레딩을 사용하는 것을 지시합니다. 스레드에는 추가 개발 오버헤드가 포함되므로 MFC가 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) 함수에서 수행하는 유휴 시간 작업과 같은 간단한 작업에는 권장되지 않습니다. 이 문서에서는 유휴 처리에 중점을 둡니다. 멀티스레딩에 대한 자세한 내용은 [다중 스레딩 항목을](../parallel/multithreading-support-for-older-code-visual-cpp.md)참조하십시오.

일부 종류의 백그라운드 처리는 사용자가 응용 프로그램과 상호 작용하지 않는 간격 동안 적절하게 수행됩니다. Microsoft Windows 운영 체제용으로 개발된 응용 프로그램에서 응용 프로그램은 긴 프로세스를 여러 개의 작은 조각으로 분할하여 유휴 시간 처리를 수행할 수 있습니다. 각 조각을 처리 한 후 응용 프로그램은 [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) 루프를 사용하여 Windows에 실행 제어를 생성합니다.

이 문서에서는 응용 프로그램에서 유휴 처리를 수행하는 두 가지 방법을 설명합니다.

- MFC의 기본 메시지 루프에서 **PeekMessage를** 사용 하 여.

- 응용 프로그램의 다른 위치에 다른 **PeekMessage** 루프를 포함합니다.

## <a name="peekmessage-in-the-mfc-message-loop"></a><a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC 메시지 루프의 엿보기 메시지

MFC로 개발된 응용 프로그램에서 클래스의 `CWinThread` 기본 메시지 루프에는 [PeekMessage](/windows/win32/api/winuser/nf-winuser-peekmessagew) Win32 API를 호출하는 메시지 루프가 포함되어 있습니다. 이 루프는 `OnIdle` 메시지 `CWinThread` 간의 멤버 함수도 호출합니다. 응용 프로그램은 함수를 재정의하여 이 `OnIdle` 유휴 시간에 메시지를 처리할 수 있습니다.

> [!NOTE]
> `Run`및 `OnIdle`특정 다른 멤버 함수는 이제 `CWinThread` 클래스가 `CWinApp`아닌 클래스의 멤버입니다. `CWinApp`는 `CWinThread`에서 파생됩니다.

유휴 처리 수행에 대한 자세한 내용은 *MFC 참조의* [OnIdle을](../mfc/reference/cwinthread-class.md#onidle) 참조하십시오.

## <a name="peekmessage-elsewhere-in-your-application"></a><a name="_core_peekmessage_elsewhere_in_your_application"></a>응용 프로그램의 다른 곳에서 엿보기 메시지

응용 프로그램에서 유휴 처리를 수행하는 또 다른 방법은 함수 중 하나에 메시지 루프를 포함합니다. 이 메시지 루프는 [CWinThread::Run에서](../mfc/reference/cwinthread-class.md#run)발견되는 MFC의 기본 메시지 루프와 매우 유사합니다. 즉, MFC로 개발된 응용 프로그램의 이러한 루프는 주 메시지 루프와 동일한 많은 기능을 수행해야 합니다. 다음 코드 조각은 MFC와 호환되는 메시지 루프를 작성하는 것을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]

함수에 포함된 이 코드는 유휴 처리가 있는 한 반복됩니다. 해당 루프 내에서 중첩 루프는 반복적으로 호출합니다. `PeekMessage` 해당 호출이 zero가 아닌 값을 반환하는 `CWinThread::PumpMessage` 한 루프는 일반 메시지 변환 및 디스패치를 수행하기 위해 호출합니다. 문서화되지 않았지만 `PumpMessage` Visual C++ 설치의 \atlmfc\src\mfc 디렉토리에서 ThrdCore.Cpp 파일에서 소스 코드를 검사할 수 있습니다.

내부 루프가 끝나면 외부 루프는 하나 이상의 호출을 `OnIdle`사용하여 유휴 처리를 수행합니다. 첫 번째 호출은 MFC의 목적입니다. 자신의 백그라운드 작업을 `OnIdle` 수행하도록 추가 호출을 수행할 수 있습니다.

유휴 처리 수행에 대한 자세한 내용은 MFC 라이브러리 참조의 [OnIdle을](../mfc/reference/cwinthread-class.md#onidle) 참조하십시오.

## <a name="see-also"></a>참고 항목

[일반 MFC 항목](../mfc/general-mfc-topics.md)
