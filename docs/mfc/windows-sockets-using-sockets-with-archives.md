---
title: 'Windows 소켓: 소켓과 아카이브 함께 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: 55b4f9a5412c1447fe2b3bde10cb934b91abf008
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359960"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows 소켓: 소켓과 아카이브 함께 사용

이 문서에서는 [CSocket 프로그래밍 모델에 대해 설명합니다.](#_core_the_csocket_programming_model) 클래스 [C소켓은](../mfc/reference/csocket-class.md) 클래스 [CAsyncSocket보다](../mfc/reference/casyncsocket-class.md)더 높은 수준의 추상화로 소켓 지원을 제공합니다. `CSocket`MFC 직렬화 프로토콜 버전을 사용하여 MFC [CArchive](../mfc/reference/carchive-class.md) 개체를 통해 소켓 개체와 데이터를 전달합니다. `CSocket`은 차단을 제공하며(Windows 메시지의 백그라운드 처리 관리), 원시 API 또는 `CArchive`클래스를 사용할 경우 직접 수행해야 하는 문서의 여러 측면에 대한 관리 작업을 수행하는 `CAsyncSocket`에 액세스할 수 있게 해줍니다.

> [!TIP]
> `CSocket`의 편리한 버전으로 `CAsyncSocket` 클래스를 직접 사용할 수 있지만 가장 간단한 프로그래밍 모델은 `CSocket` 개체에 `CArchive`을 사용하는 것입니다.

아카이브가 있는 소켓의 구현이 작동하는 방식에 대한 자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓](../mfc/windows-sockets-how-sockets-with-archives-work.md)작동 방식을 참조하십시오. 예를 들어 코드는 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md) 및 [Windows 소켓: 아카이브를 사용하는 소켓의 예를](../mfc/windows-sockets-example-of-sockets-using-archives.md)참조하십시오. 소켓 클래스에서 사용자 고유의 클래스를 파생하여 얻을 수 있는 몇 가지 기능에 대한 자세한 내용은 [Windows 소켓: 소켓 클래스에서 파생을](../mfc/windows-sockets-deriving-from-socket-classes.md)참조하십시오.

> [!NOTE]
> 설정된(MFC 이외) 서버와 통신하도록 MFC 클라이언트 프로그램을 작성하는 경우 아카이브를 통해 C++ 개체를 전송하지 마십시오. 사용자가 전송하려는 개체 종류를 인식하는 MFC 애플리케이션이 아니면 개체를 수신하고 이를 역직렬화할 수 없습니다. 비 MFC 응용 프로그램과 통신하는 주제에 대한 관련 자료에 대한 자세한 내용은 [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md)문서를 참조하십시오.

## <a name="the-csocket-programming-model"></a><a name="_core_the_csocket_programming_model"></a>C소켓 프로그래밍 모델

`CSocket` 개체 사용 시에는 여러 MFC 클래스 개체를 함께 만들고 연결하는 작업이 포함됩니다. 아래의 일반 절차에서 각 단계는 각 소켓 유형에 서로 다른 작업이 필요한 3단계를 제외하고 서버 소켓과 클라이언트 소켓 모두에서 수행됩니다.

> [!TIP]
> 런타임에 서버 애플리케이션은 일반적으로 먼저 시작되어 준비되며, 클라이언트 애플리케이션이 연결을 검색할 때 이를 수신 대기합니다. 클라이언트가 연결을 시도할 때 서버가 준비되어 있지 않으면 일반적으로 사용자 애플리케이션이 나중에 연결을 다시 시도해야 합니다.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>서버 소켓과 클라이언트 소켓 사이의 통신을 설정하려면

1. [CSocket](../mfc/reference/csocket-class.md) 개체를 생성합니다.

1. 개체를 사용하여 기본 **SOCKET** 핸들을 만듭니다.

   클라이언트 `CSocket` 개체의 경우 데이터그램 소켓이 필요하지 않는 한 일반적으로 기본 매개 변수를 [사용하여 만들기](../mfc/reference/casyncsocket-class.md#create)를 사용해야 합니다. 서버 `CSocket` 개체의 경우 호출에 포트를 `Create` 지정해야 합니다.

    > [!NOTE]
    >  `CArchive`는 데이터그램 소켓에서 작동하지 않습니다. 데이터그램 소켓에 대해 `CSocket`을 사용하려는 경우에는 `CAsyncSocket`을 사용할 때와 마찬가지로, 아카이브 없이 클래스를 사용해야 합니다. 데이터그램은 안정적이지 않기 때문에(수신이 보장되지 않고 반복되거나 순서가 바뀔 수 있음), 아카이브를 통한 serialization과 호환되지 않습니다. serialization 작업은 안정적으로 그리고 순차적으로 완료할 것으로 예상됩니다. 데이터그램에 대해 `CSocket` 개체와 함께 `CArchive`을 사용하려고 시도하면 MFC 어설션이 실패합니다.

1. 소켓이 클라이언트인 경우 [CAsyncSocket::Connect를](../mfc/reference/casyncsocket-class.md#connect) 호출하여 소켓 개체를 서버 소켓에 연결합니다.

     또는

   소켓이 서버인 경우 [CAsyncSocket::Listen을](../mfc/reference/casyncsocket-class.md#listen) 호출하여 클라이언트의 연결 시도 수신 을 시작합니다. 연결 요청을 받으면 [CAsyncSocket::Accept를](../mfc/reference/casyncsocket-class.md#accept)호출하여 수락합니다.

    > [!NOTE]
    >  멤버 `Accept` 함수는 비어 `CSocket` 있는 새 개체를 매개 변수로 참조합니다. 을 호출하기 `Accept`전에 이 개체를 생성해야 합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙니다. 이 새 `Create` 소켓 개체를 호출하지 마십시오.

1. 개체와 연결되는 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체를 `CSocket` 만듭니다.

1. 데이터를 로드(수신) 또는 저장(전송)하기 위해 [CArchive](../mfc/reference/carchive-class.md) 개체를 만듭니다. 아카이브는 `CSocketFile` 개체와 연결됩니다.

   `CArchive`는 데이터그램 소켓에서 작동하지 않습니다.

1. 클라이언트 및 서버 소켓 사이에 데이터를 전달하려면 `CArchive` 개체를 사용합니다.

   특정 `CArchive` 개체는 데이터를 한 방향으로만 이동합니다. 즉, 로드(수신) 또는 저장(송신) 방향으로만 이동합니다. 일부 경우에는 데이터 송신 및 수신 확인을 위해 두 개의 `CArchive` 개체를 사용합니다.

   연결을 수락하고 아카이브를 설정한 후에는 암호 유효성 검사와 같은 작업을 수행할 수 있습니다.

1. 아카이브, 소켓 파일 및 소켓 개체를 삭제합니다.

    > [!NOTE]
    >  `CArchive` 클래스는 `IsBufferEmpty` 클래스에 사용할 수 있도록 `CSocket` 멤버 함수를 제공합니다. 예를 들어 버퍼에 여러 데이터 메시지가 포함된 경우에는 모든 항목이 읽혀지고 버퍼가 비워질 때까지 반복해야 합니다. 그렇지 않으면 수신할 데이터가 있음에 대한 다음 알림이 무기한 지연될 수 있습니다. 모든 데이터를 검색할 수 있도록 `IsBufferEmpty`를 사용합니다.

Windows [소켓: 작업 시퀀스는](../mfc/windows-sockets-sequence-of-operations.md) 예제 코드와 함께 이 프로세스의 양면을 보여 줍니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[C소켓::만들기](../mfc/reference/csocket-class.md#create)
