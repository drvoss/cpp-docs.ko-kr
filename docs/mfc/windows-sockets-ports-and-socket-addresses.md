---
title: 'Windows 소켓: 포트 및 소켓 주소'
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: 791bf07c927e80e65e0fda79fae8a50235bc2def
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371041"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows 소켓: 포트 및 소켓 주소

이 문서에서는 Windows 소켓에서 사용되는 용어 "포트" 및 "주소"에 대해 설명합니다.

## <a name="port"></a><a name="_core_port"></a>포트

포트는 서비스를 제공할 수 있는 고유한 프로세스를 식별합니다. 현재 컨텍스트에서 포트는 Windows 소켓을 지원하는 응용 프로그램과 연결됩니다. 이 아이디어는 각 Windows 소켓 응용 프로그램을 고유하게 식별하여 컴퓨터에서 동시에 두 개 이상의 Windows 소켓 응용 프로그램을 실행할 수 있도록 하는 것입니다.

특정 포트는 FTP와 같은 일반적인 서비스를 위해 예약되어 있습니다. 이러한 종류의 서비스를 제공하지 않는 한 이러한 포트를 사용하지 않아야 합니다. Windows 소켓 사양은 이러한 예약된 포트에 대해 자세히 설명합니다. 파일 WINSOCK. H는 또한 그들을 나열합니다.

Windows 소켓 DLL에서 사용 가능한 포트를 선택하도록 하려면 0을 포트 값으로 전달합니다. MFC는 소수점 이하의 포트 값을 선택합니다. [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) 멤버 함수를 호출하여 MFC가 선택한 포트 값을 검색할 수 있습니다.

## <a name="socket-address"></a><a name="_core_socket_address"></a>소켓 주소

각 소켓 개체는 네트워크의 IP(인터넷 프로토콜) 주소와 연결됩니다. 일반적으로 주소는 "ftp.microsoft.com"과 같은 컴퓨터 이름 또는 "128.56.22.8"과 같은 점선 번호입니다.

소켓을 만들려고 할 때 일반적으로 자신의 주소를 지정할 필요가 없습니다.

> [!NOTE]
> 컴퓨터에 여러 네트워크 카드가 있을 수 있습니다(또는 응용 프로그램이 이러한 컴퓨터에서 언젠가 실행될 수 있음) 각각 다른 네트워크를 나타내는 것일 수 있습니다. 그렇다면 소켓에서 사용할 네트워크 카드를 지정하기 위해 주소를 지정해야 할 수 있습니다. 이것은 고급 사용 및 가능한 이식성 문제일 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
