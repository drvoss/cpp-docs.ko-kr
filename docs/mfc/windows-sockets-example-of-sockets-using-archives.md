---
title: 'Windows 소켓: 아카이브를 사용하는 소켓의 예'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
ms.openlocfilehash: 253a65430ae230fbc4deeb9bd5288f28237310d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371082"
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows 소켓: 아카이브를 사용하는 소켓의 예

이 문서에서는 [클래스 CSocket을](../mfc/reference/csocket-class.md)사용하는 예제를 제공합니다. 이 예제는 `CArchive` 소켓을 통해 데이터를 직렬화하는 개체를 사용합니다. 파일과 문서 직렬화가 아닙니다.

다음 예제에서는 아카이브를 사용하여 개체를 통해 `CSocket` 데이터를 보내고 받는 방법을 보여 줍니다. 이 예제는 응용 프로그램의 두 인스턴스(동일한 컴퓨터 또는 네트워크의 다른 컴퓨터)가 데이터를 교환하도록 설계되었습니다. 한 인스턴스는 다른 인스턴스가 수신하고 승인하는 데이터를 보냅니다. 두 응용 프로그램 중 하나가 교환을 시작할 수 있으며 서버 역할을 하거나 다른 응용 프로그램에 대한 클라이언트 역할을 할 수 있습니다. 다음 함수는 응용 프로그램의 뷰 클래스에 정의되어 있습니다.

[!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]

이 예제에서 가장 중요한 점은 해당 구조가 MFC `Serialize` 함수와 유사하다는 것입니다. 멤버 `PacketSerialize` 함수는 **else** 절이 있는 **if** 문으로 구성됩니다. 함수는 두 개의 [CArchive](../mfc/reference/carchive-class.md) 참조를 매개 변수로 수신합니다: *arData* 및 *arAck*. *arData* 아카이브 개체가 저장(전송)하도록 설정된 경우 **if** 분기가 실행됩니다. 그렇지 않으면 *arData가* 로드(수신)를 위해 설정된 경우 함수는 **else** 분기를 취합니다. MFC의 직렬화에 대한 자세한 내용은 [직렬화를](../mfc/how-to-make-a-type-safe-collection.md)참조하십시오.

> [!NOTE]
> *arAck* 아카이브 개체는 *arData의*반대로 가정됩니다. *arData가* 전송용인 경우 *arAck이* 수신하고 반대가 true입니다.

송신의 경우 예제 함수는 데모를 위해 임의의 데이터를 생성할 때마다 지정된 횟수동안 반복됩니다. 응용 프로그램은 파일과 같은 일부 소스에서 실제 데이터를 가져옵니다. *arData* 아카이브의 삽입 연산자**<<**()는 세 개의 연속된 데이터 청크 스트림을 보내는 데 사용됩니다.

- 데이터의 특성을 지정하는 "헤더"(이 경우 *bValue* 변수의 값과 전송될 복사본 수).

   이 예제에서 두 항목 모두 임의로 생성됩니다.

- 지정된 데이터 복사본 수입니다.

   내부 **for** 루프는 지정된 횟수에 *대해 bValue를* 보냅니다.

- 수신기가 사용자에게 표시하는 *strText라는* 문자열입니다.

수신의 경우 이 함수는 아카이브의 추출 연산자()를**>>** 사용하여 아카이브에서 데이터를 가져옵니다. 수신 응용 프로그램은 수신한 데이터를 확인하고 최종 "수신됨" 메시지를 표시한 다음 전송 응용 프로그램이 표시할 "Sent"라는 메시지를 다시 보냅니다.

이 통신 모델에서 *strText* 변수에서 보낸 메시지인 "Received"라는 단어는 통신의 다른 쪽 끝에 표시하기 위한 것이므로 수신 사용자에게 특정 수의 데이터 패킷이 수신되었음을 지정합니다. 수신자는 원래 발신자의 화면에 표시하기 위해 "Sent"라는 유사한 문자열로 회신합니다. 두 문자열을 모두 수신하면 통신이 성공했음을 나타냅니다.

> [!CAUTION]
> 설정된(MFC 이외) 서버와 통신하도록 MFC 클라이언트 프로그램을 작성하는 경우 아카이브를 통해 C++ 개체를 전송하지 마십시오. 서버가 보내려는 개체의 종류를 이해하는 MFC 응용 프로그램이 아니면 개체를 수신하고 역직렬화할 수 없습니다. [Windows 소켓: 바이트 순서문서의](../mfc/windows-sockets-byte-ordering.md) 예로는 이 유형의 통신이 표시됩니다.

자세한 내용은 Windows 소켓 사양을 참조하십시오: **htonl,** **htons,** **ntohl,** **ntohs**. 또한 자세한 내용은 다음을 참조하십시오.

- [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[C아카이브::저장](../mfc/reference/carchive-class.md#isstoring)<br/>
[C보관:운영자 <<](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[C보관:운영자 >>](../mfc/reference/carchive-class.md#operator_lt_lt)<br/>
[CArchive::Flush](../mfc/reference/carchive-class.md#flush)<br/>
[CObject::직렬화](../mfc/reference/cobject-class.md#serialize)
