---
title: MFC의 Windows 소켓
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 8e5562b028d3d9b7cba4b47716b63fd1392c514f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371092"
---
# <a name="windows-sockets-in-mfc"></a>MFC의 Windows 소켓

> [!NOTE]
> MFC는 윈도우 소켓 1을 지원하지만 [윈도우 소켓 2를](/windows/win32/WinSock/windows-sockets-start-page-2)지원하지 않습니다 . 윈도우 소켓 2 처음 윈도우 98와 함께 제공 및 윈도우 2000에 포함 된 버전입니다.

MFC는 두 개의 MFC 클래스에 구현된 Windows 소켓으로 네트워크 통신 프로그램을 작성하기 위한 두 가지 모델을 제공합니다. 이 문서에서는 이러한 모델에 대해 설명하고 MFC 소켓 지원에 대한 자세한 내용을 설명합니다. "소켓"은 통신의 끝점입니다: 응용 프로그램이 네트워크를 통해 다른 Windows Sockets 응용 프로그램과 통신하는 개체입니다.

소켓 개념에 대한 설명을 포함하여 Windows 소켓에 대한 자세한 내용은 [Windows 소켓: 배경](../mfc/windows-sockets-background.md)을 참조하십시오.

## <a name="sockets-programming-models"></a><a name="_core_sockets_programming_models"></a>소켓 프로그래밍 모델

두 개의 MFC Windows 소켓 프로그래밍 모델은 다음 클래스에서 지원됩니다.

- `CAsyncSocket`

   이 클래스는 Windows 소켓 API를 캡슐화합니다. [CAsyncSocket은](../mfc/reference/casyncsocket-class.md) 네트워크 프로그래밍을 알고 소켓 API에 직접 프로그래밍의 유연성을 원하지만 네트워크 이벤트 알림을 위한 콜백 기능의 편리함을 원하는 프로그래머를 위한 것입니다. C++에서 사용하기 위해 개체 지향 양식의 소켓을 패키징하는 것 이외에 이 클래스가 제공하는 유일한 추가 추상화는 특정 소켓 관련 Windows 메시지를 콜백으로 변환하는 것입니다. 자세한 내용은 [Windows 소켓: 소켓 알림을](../mfc/windows-sockets-socket-notifications.md)참조하십시오.

- `CSocket`

   에서 `CAsyncSocket`파생 된이 클래스는 MFC [CArchive](../mfc/reference/carchive-class.md) 개체를 통해 소켓작업을 위한 상위 수준의 추상화를 제공합니다. 아카이브가 있는 소켓을 사용하는 것은 MFC의 파일 직렬화 프로토콜을 사용하는 것과 매우 유사합니다. 이렇게 하면 모델보다 사용하기가 더 쉽습니다. `CAsyncSocket` [CSocket은](../mfc/reference/csocket-class.md) Windows 소켓 API를 `CAsyncSocket` 캡슐화하는 많은 멤버 함수를 상속합니다. 이러한 기능 중 일부를 사용하고 일반적으로 소켓 프로그래밍을 이해해야 합니다. 그러나 `CSocket` 원시 API 또는 클래스를 `CAsyncSocket`사용하여 직접 수행해야 하는 통신의 여러 측면을 관리합니다. 가장 중요한 `CSocket` 것은 의 동기 작업에 `CArchive`필수적인 차단(Windows 메시지의 백그라운드 처리 포함)을 제공한다는 것입니다.

생성 및 `CSocket` `CAsyncSocket` 사용 및 개체는 Windows 소켓: 아카이브 및 Windows [소켓이 있는 소켓 사용:](../mfc/windows-sockets-using-sockets-with-archives.md) [클래스 CAsyncSocket 사용](../mfc/windows-sockets-using-class-casyncsocket.md).

## <a name="windows-sockets-dlls"></a><a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>윈도우 소켓 DLL

마이크로소프트 윈도 운영 체제 는 윈도우 소켓 동적 링크 라이브러리 (DLL)를 제공합니다. Visual C++는 적절한 헤더 파일 및 라이브러리와 Windows 소켓 사양을 제공합니다.

Windows 소켓에 대한 자세한 내용은 다음을 참조하십시오.

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows 소켓: 소켓 알림](../mfc/windows-sockets-socket-notifications.md)

- [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)

- [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)

- [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)

- [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>참고 항목

[Windows 소켓](../mfc/windows-sockets.md)
