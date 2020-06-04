---
title: 'Windows 소켓: 백그라운드'
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 1c4a6dc6740660d1097785578cdac355983cad18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360123"
---
# <a name="windows-sockets-background"></a>Windows 소켓: 백그라운드

이 문서에서는 Windows 소켓의 특성과 용도에 대해 설명합니다. 이 기사는 또한 :

- ["소켓"이라는 용어를 정의합니다.](#_core_definition_of_a_socket)

- [SOCKET 핸들 데이터 형식에 대해 설명합니다.](#_core_the_socket_data_type)

- [소켓에 대한 용도에 대해 설명합니다.](#_core_uses_for_sockets)

Windows 소켓 사양은 Microsoft Windows용 바이너리 호환 네트워크 프로그래밍 인터페이스를 정의합니다. Windows 소켓은 버클리 캘리포니아 대학교버클리 의 버클리 소프트웨어 배포(BSD, 릴리스 4.3)의 UNIX 소켓 구현을 기반으로 합니다. 이 사양에는 BSD 스타일 소켓 루틴과 Windows 전용 확장이 모두 포함됩니다. Windows 소켓을 사용하면 응용 프로그램이 Windows 소켓 API를 준수하는 모든 네트워크를 통해 통신할 수 있습니다. Win32에서 Windows 소켓은 스레드 안전을 제공합니다.

많은 네트워크 소프트웨어 공급업체는 전송 제어 프로토콜/인터넷 프로토콜(TCP/IP), Xerox 네트워크 시스템(XNS), 디지털 장비 회사의 DECNet 프로토콜, Novell Corporation의 인터넷 패킷 교환/시퀀싱 포장 교환(IPX/SPX) 등 네트워크 프로토콜에 따라 Windows 소켓을 지원합니다. 현재 Windows 소켓 사양은 TCP/IP에 대한 소켓 추상화를 정의하지만 모든 네트워크 프로토콜은 Windows 소켓을 구현하는 자체 버전의 DLL(동적 링크 라이브러리)을 제공하여 Windows 소켓을 준수할 수 있습니다. Windows 소켓으로 작성된 상용 응용 프로그램의 예로는 X Windows 서버, 터미널 에뮬레이터 및 전자 메일 시스템이 있습니다.

> [!NOTE]
> Windows 소켓의 목적은 기본 네트워크를 추상화하여 해당 네트워크에 대해 잘 알고 있을 필요가 없으며 응용 프로그램이 소켓을 지원하는 모든 네트워크에서 실행할 수 있도록 하는 것입니다. 따라서 이 설명서는 네트워크 프로토콜의 세부 사항에 대해 설명하지 않습니다.

Microsoft 파운데이션 클래스 라이브러리(MFC)는 두 개의 클래스를 제공하여 Windows 소켓 API로 프로그래밍을 지원합니다. 이러한 클래스 `CSocket`중 하나는 네트워크 통신 프로그래밍을 단순화하기 위해 높은 수준의 추상화를 제공합니다.

윈도우 소켓 사양, 윈도우 소켓: 마이크로소프트 윈도에서 네트워크 컴퓨팅에 대 한 오픈 인터페이스, 지금 버전 1.1, TCP/IP 커뮤니티에서 개인 및 기업의 큰 그룹에 의해 오픈 네트워킹 표준으로 개발 하 고 자유롭게 사용할 수 있습니다. 소켓 프로그래밍 모델은 인터넷 프로토콜 제품군을 사용하여 현재 하나의 "통신 도메인"을 지원합니다. 사양은 Windows SDK에서 사용할 수 있습니다.

> [!TIP]
> 소켓은 인터넷 프로토콜 제품군을 사용하기 때문에 "정보 고속도로"에서 인터넷 통신을 지원하는 응용 프로그램에 선호되는 경로입니다.

## <a name="definition-of-a-socket"></a><a name="_core_definition_of_a_socket"></a>소켓 정의

소켓은 Windows Sockets 응용 프로그램이 네트워크를 통해 데이터 패킷을 보내거나 받는 개체인 통신 끝점입니다. 소켓에는 형식이 있으며 실행 중인 프로세스와 연결되며 이름이 있을 수 있습니다. 현재 소켓은 일반적으로 인터넷 프로토콜 제품군을 사용하는 동일한 "통신 도메인"의 다른 소켓과만 데이터를 교환합니다.

소켓의 두 종류는 양방향; 양방향으로 동시에 통신할 수 있는 데이터 흐름입니다(전이중).

두 가지 소켓 유형을 사용할 수 있습니다.

- 스트림 소켓

   스트림 소켓은 레코드 경계가 없는 데이터 흐름( 바이트 스트림)을 제공합니다. 스트림은 전달되고 올바르게 순서가 정렬되고 중복되지 않을 수 있습니다.

- 데이터그램 소켓

   Datagram 소켓은 제공이 보장되지 않으며 전송되거나 중복되지 않은 순서로 정렬되지 않을 수 있는 레코드 지향 데이터 흐름을 지원합니다.

"시퀀스"는 패킷이 전송된 순서대로 전달된다는 것을 의미합니다. "중복되지 않은"은 특정 패킷을 한 번만 받는 것을 의미합니다.

> [!NOTE]
> XNS와 같은 일부 네트워크 프로토콜에서는 스트림을 바이트 스트림이 아닌 레코드 스트림으로 기록지향적일 수 있습니다. 그러나 보다 일반적인 TCP/IP 프로토콜에서 스트림은 바이트 스트림입니다. Windows 소켓은 기본 프로토콜과 독립적인 추상화 수준을 제공합니다.

이러한 유형및 어떤 종류의 소켓을 사용할지에 대한 자세한 내용은 [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md) 및 Windows [소켓: Datagram 소켓을](../mfc/windows-sockets-datagram-sockets.md)참조하십시오.

## <a name="the-socket-data-type"></a><a name="_core_the_socket_data_type"></a>소켓 데이터 유형

각 MFC 소켓 개체는 Windows 소켓 개체에 핸들을 캡슐화합니다. 이 핸들의 데이터 형식은 **SOCKET**입니다. **SOCKET** 핸들은 창과 `HWND` 유사합니다. MFC 소켓 클래스는 캡슐화된 핸들에서 작업을 제공합니다.

**SOCKET** 데이터 형식은 Windows SDK에서 자세히 설명합니다. Windows 소켓 에서 "소켓 데이터 유형 및 오류 값"을 참조하십시오.

## <a name="uses-for-sockets"></a><a name="_core_uses_for_sockets"></a>소켓에 사용

소켓은 세 개 이상의 통신 컨텍스트에서 매우 유용합니다.

- 클라이언트/서버 모델입니다.

- 메시징 응용 프로그램과 같은 피어 투 피어 시나리오입니다.

- 수신 응용 프로그램이 메시지를 함수 호출로 해석하게 하여 원격 프로시저 호출(RPC)을 만듭니다.

> [!TIP]
> MFC 소켓을 사용하기에 이상적인 경우는 통신의 양 끝을 작성하는 경우입니다. MFC가 아닌 응용 프로그램과 통신할 때 케이스를 관리하는 방법을 포함하여 이 항목에 대한 자세한 내용은 [Windows 소켓: 바이트 순서를](../mfc/windows-sockets-byte-ordering.md)참조하십시오.

자세한 내용은 Windows 소켓 사양을 참조하십시오: **ntohs,** **ntohl,** **htons,** **htonl**. 또한 다음 항목을 참조하십시오.

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
