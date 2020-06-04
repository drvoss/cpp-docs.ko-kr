---
title: 'Windows 소켓: 바이트 순서 지정'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: 50548202483c4d9d4471ad2c600270c4df4503e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371051"
---
# <a name="windows-sockets-byte-ordering"></a>Windows 소켓: 바이트 순서 지정

이 문서 및 두 개의 참조 문서에서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다. 이 문서에서는 바이트 순서를 다룹니다. 다른 문제는 문서에서 다룹니다: [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md) 및 [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md).

[클래스 CAsyncSocket을](../mfc/reference/casyncsocket-class.md)사용하거나 파생하는 경우 이러한 문제를 직접 관리해야 합니다. [클래스 CSocket에서](../mfc/reference/csocket-class.md)사용 하거나 파생 하는 경우 MFC 당신을 위해 그들을 관리 합니다.

## <a name="byte-ordering"></a>바이트 순서 지정

컴퓨터 아키텍처마다 다른 바이트 순서를 사용하여 데이터를 저장합니다. 예를 들어 인텔 기반 컴퓨터는 매킨토시(모토로라) 컴퓨터의 역순으로 데이터를 저장합니다. "리틀 엔디안"이라고 하는 인텔 바이트 순서는 네트워크 표준 "빅 엔디안" 순서의 반대입니다. 다음 표는 이러한 용어에 대해 설명합니다.

### <a name="big--and-little-endian-byte-ordering"></a>빅 및 리틀 엔디안 바이트 주문

|바이트 순서 지정|의미|
|-------------------|-------------|
|빅 엔디안|가장 중요한 바이트는 단어의 왼쪽 끝에 있습니다.|
|리틀 엔디안|가장 중요한 바이트는 단어의 오른쪽 끝에 있습니다.|

일반적으로 네트워크를 통해 보내고 받는 데이터에 대한 바이트 순서 변환에 대해 걱정할 필요는 없지만 바이트 주문을 변환해야 하는 상황이 있습니다.

## <a name="when-you-must-convert-byte-orders"></a>바이트 주문을 변환해야 하는 경우

다음과 같은 상황에서 바이트 주문을 변환해야 합니다.

- 다른 컴퓨터로 보내는 데이터와 는 달리 네트워크에서 해석해야 하는 정보를 전달하고 있습니다. 예를 들어 네트워크가 이해해야 하는 포트와 주소를 전달할 수 있습니다.

- 통신하는 서버 응용 프로그램은 MFC 응용 프로그램이 아닙니다(소스 코드가 없습니다). 이렇게 하면 두 컴퓨터가 동일한 바이트 순서를 공유하지 않는 경우 바이트 주문 변환이 요구됩니다.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>바이트 주문을 변환할 필요가 없는 경우

다음과 같은 상황에서 바이트 주문을 변환하는 작업을 방지할 수 있습니다.

- 양쪽 끝의 컴퓨터는 바이트를 교환하지 않을 수 있으며 두 컴퓨터는 동일한 바이트 순서를 사용합니다.

- 통신하는 서버는 MFC 응용 프로그램입니다.

- 통신하는 서버에 대한 소스 코드가 있으므로 바이트 주문을 변환해야 하는지 여부를 명시적으로 알 수 있습니다.

- 서버를 MFC로 이식할 수 있습니다. 이 작업을 수행하는 것은 매우 쉬우며 일반적으로 더 작고 빠른 코드입니다.

[CAsyncSocket으로](../mfc/reference/casyncsocket-class.md)작업하는 경우 필요한 바이트 순서 변환을 직접 관리해야 합니다. Windows 소켓은 "큰 Endian" 바이트 순서 모델을 표준화하 고이 순서와 다른 순서 사이 변환 하는 기능을 제공 합니다. 그러나 [CSocket에서](../mfc/reference/csocket-class.md)사용하는 `CArchive` [CArchive는](../mfc/reference/carchive-class.md)반대("little-Endian") 순서를 사용하지만 바이트 순서 변환의 세부 정보를 처리합니다. 응용 프로그램에서 이 표준 순서를 사용하거나 Windows Sockets 바이트 순서 변환 함수를 사용하면 코드를 보다 이식성이 높일 수 있습니다.

MFC 소켓을 사용하기에 이상적인 경우는 통신의 양 끝을 작성하는 경우입니다. FTP 서버와 같은 비 MFC 응용 프로그램과 통신하는 응용 프로그램을 작성하는 경우 Windows 소켓 변환 루틴 **ntohs,** **ntohl,** **htons**및 **htonl을**사용하여 아카이브 개체에 데이터를 전달하기 전에 바이트 교환을 직접 관리해야 할 수 있습니다. MFC가 아닌 응용 프로그램과 통신하는 데 사용되는 이러한 함수의 예는 이 문서의 후반부에서 나타납니다.

> [!NOTE]
> 통신의 다른 쪽 끝이 MFC 응용 프로그램이 아닌 경우 수신기가 이를 처리할 `CObject` 수 없으므로 아카이브에서 파생된 C++ 개체를 스트리밍하지 않아야 합니다. [Windows 소켓: 아카이브가 있는 소켓 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

바이트 주문에 대한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows 소켓 사양을 참조하십시오.

## <a name="a-byte-order-conversion-example"></a>바이트 순서 변환 예제

다음 예제에서는 아카이브를 사용하는 `CSocket` 개체에 대한 직렬화 함수를 보여 주습니다. 또한 Windows 소켓 API에서 바이트 순서 변환 함수를 사용하는 방법을 보여 줍니다.

이 예제에서는 소스 코드에 액세스할 수 없는 MFC 서버 가 아닌 응용 프로그램과 통신하는 클라이언트를 작성하는 시나리오를 제공합니다. 이 시나리오에서는 MFC 가 아닌 서버가 표준 네트워크 바이트 순서를 사용한다고 가정해야 합니다. 반대로 MFC 클라이언트 응용 프로그램은 `CArchive` `CSocket` 개체가 있는 `CArchive` 개체를 사용하고 네트워크 표준과 반대되는 "little-Endian" 바이트 순서를 사용합니다.

통신하려는 MFC가 아닌 서버에 다음과 같은 메시지 패킷에 대해 설정된 프로토콜이 있다고 가정합니다.

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC 용어에서 다음과 같이 표시됩니다.

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

C++에서 **구조체는** 기본적으로 클래스와 동일합니다. 구조에는 `Message` 위에서 선언한 멤버 함수와 `Serialize` 같은 멤버 함수가 있을 수 있습니다. 멤버 `Serialize` 함수는 다음과 같습니다.

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

이 예제에서는 한쪽 끝에 있는 비 MFC 서버 응용 프로그램의 바이트 순서와 다른 쪽 끝에 MFC 클라이언트 `CArchive` 응용 프로그램에서 사용되는 바이트 순서 간에 명확한 불일치가 있기 때문에 데이터의 바이트 순서 변환을 요구합니다. 이 예제에서는 Windows Sockets가 제공하는 몇 가지 바이트 순서 변환 함수를 보여 줍니다. 다음 표는 이러한 함수에 대해 설명합니다.

### <a name="windows-sockets-byte-order-conversion-functions"></a>윈도우 소켓 바이트 순서 변환 기능

|함수|용도|
|--------------|-------------|
|**ntohs**|16비트 수량을 네트워크 바이트 순서에서 호스트 바이트 순서(빅 엔디안에서 리틀 엔디안)로 변환합니다.|
|**ntohl**|네트워크 바이트 순서에서 호스트 바이트 순서(빅 엔디안에서 리틀 엔디안)로 32비트 수량을 변환합니다.|
|**Htons**|호스트 바이트 순서에서 네트워크 바이트 순서(리틀 엔디안에서 빅 엔디안)로 16비트 수량을 변환합니다.|
|**호른 ("요")**|호스트 바이트 순서에서 네트워크 바이트 순서(리틀 엔디안에서 빅 엔디안)로 32비트 수량을 변환합니다.|

이 예제의 또 다른 점은 통신의 다른 쪽 끝에 있는 소켓 응용 프로그램이 MFC가 아닌 응용 프로그램인 경우 다음과 같은 작업을 수행하지 않아야 한다는 것입니다.

`ar << pMsg;`

여기서 `pMsg` 클래스에서 `CObject`파생된 C++ 개체에 대한 포인터입니다. 이렇게 하면 개체와 연결된 추가 MFC 정보가 전송되고 서버는 MFC 응용 프로그램인 경우와 마찬가지로 이를 이해하지 못합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
