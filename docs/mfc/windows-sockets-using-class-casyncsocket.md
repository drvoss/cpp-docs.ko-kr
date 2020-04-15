---
title: 'Windows 소켓: CAsyncSocket 클래스 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: d3fc32d9da54d9cf8c79e9e5de45b81c2ef64a6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371965"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows 소켓: CAsyncSocket 클래스 사용

이 문서에서는 클래스 [CAsyncSocket을](../mfc/reference/casyncsocket-class.md)사용하는 방법에 대해 설명합니다. 이 클래스는 Windows 소켓 API를 매우 낮은 수준으로 캡슐화합니다. `CAsyncSocket`네트워크 통신을 자세히 알고 있지만 네트워크 이벤트 알림을 위해 콜백의 편리함을 원하는 프로그래머가 사용할 수 있습니다. 이 가정을 기반으로 이 문서에서는 기본 지침만 제공합니다. MFC 응용 `CAsyncSocket` 프로그램에서 여러 네트워크 프로토콜을 쉽게 처리할 수 있지만 유연성을 희생하지 않으려는 경우 Windows Sockets를 쉽게 사용할 수 있습니다. 또한 보다 일반적인 대체 클래스 `CSocket`모델을 사용하는 것보다 직접 통신을 프로그래밍하여 효율성을 높일 수 있다고 생각할 수도 있습니다.

`CAsyncSocket`*MFC 참조에*설명되어 있습니다. Visual C++는 Windows SDK에 있는 Windows 소켓 사양도 제공합니다. 자세한 내용은 귀하에게 맡입니다. Visual C++는 에 대한 `CAsyncSocket`샘플 응용 프로그램을 제공하지 않습니다.

네트워크 통신에 대해 잘 알고 있지 않고 간단한 솔루션을 원한다면 클래스 `CArchive` [CSocket을](../mfc/reference/csocket-class.md) 개체와 함께 사용하십시오. 자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용을](../mfc/windows-sockets-using-sockets-with-archives.md) 참조하십시오.

이 문서에서는 다음 내용을 설명합니다.

- `CAsyncSocket` 개체 만들기 및 사용

- [CAsync소켓에 대한 귀하의 책임](#_core_your_responsibilities_with_casyncsocket).

## <a name="creating-and-using-a-casyncsocket-object"></a><a name="_core_creating_and_using_a_casyncsocket_object"></a>CAsyncSocket 개체 만들기 및 사용

#### <a name="to-use-casyncsocket"></a>CAsync소켓을 사용하려면

1. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 개체를 구성 하고 기본 **SOCKET** 핸들을 만드는 개체를 사용 합니다.

   소켓 생성은 2단계 구조의 MFC 패턴을 따릅니다.

   다음은 그 예입니다.

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     또는

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   위의 첫 번째 생성자는 스택에 개체를 `CAsyncSocket` 만듭니다. 두 번째 생성자는 `CAsyncSocket` 힙에 a를 만듭니다. 위의 첫 번째 [호출 만들기는](../mfc/reference/casyncsocket-class.md#create) 기본 매개 변수를 사용하여 스트림 소켓을 만듭니다. 두 `Create` 번째 호출은 지정된 포트 및 주소가 있는 데이터그램 소켓을 만듭니다. (두 버전 `Create` 중 하나를 구성 방법으로 사용할 수 있습니다.)

   매개 변수는 `Create` 다음과 같습니다.

   - "포트": 짧은 정수입니다.

      서버 소켓의 경우 포트를 지정해야 합니다. 클라이언트 소켓의 경우 일반적으로 Windows 소켓에서 포트를 선택할 수 있는 이 매개 변수의 기본값을 수락합니다.

   - 소켓 유형: **SOCK_STREAM** SOCK_STREAM(기본값) 또는 **SOCK_DGRAM.**

   - "ftp.microsoft.com" 또는 "128.56.22.8"과 같은 소켓 "주소"입니다.

      네트워크의 인터넷 프로토콜(IP) 주소입니다. 이 매개 변수의 기본값은 항상 의존할 것입니다.

   "포트" 및 "소켓 주소"라는 용어는 [Windows 소켓: 포트 및 소켓 주소에 설명되어 있습니다.](../mfc/windows-sockets-ports-and-socket-addresses.md)

1. 소켓이 클라이언트인 경우 [CAsyncSocket::Connect를](../mfc/reference/casyncsocket-class.md#connect)사용하여 소켓 개체를 서버 소켓에 연결합니다.

     또는

   소켓이 서버인 경우 클라이언트의 연결 시도에 대해 소켓이 수신 대기를 시작하도록 [설정합니다(CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)포함). 연결 요청을 받으면 [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)로 수락합니다.

   연결을 수락한 후 암호 유효성 검사와 같은 작업을 수행할 수 있습니다.

    > [!NOTE]
    >  멤버 `Accept` 함수는 비어 `CSocket` 있는 새 개체를 매개 변수로 참조합니다. 을 호출하기 `Accept`전에 이 개체를 생성해야 합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙니다. 이 새 `Create` 소켓 개체를 호출하지 마십시오. 예를 들어 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md)를 참조하십시오.

1. Windows Sockets API 기능을 캡슐화하는 `CAsyncSocket` 개체의 멤버 함수를 호출하여 다른 소켓과의 통신을 수행합니다.

   *MFC 참조에서*Windows 소켓 사양 및 클래스 [CAsyncSocket을](../mfc/reference/casyncsocket-class.md) 참조하십시오.

1. 개체를 `CAsyncSocket` 삭제합니다.

   스택에서 소켓 개체를 만든 경우 포함 함수가 범위를 벗어날 때 해당 소멸자가 호출됩니다. 힙에서 소켓 개체를 만든 경우 **새** 연산자사용으로 **삭제** 연산자가 개체를 삭제해야 합니다.

   소멸자는 개체를 파괴하기 전에 개체의 [Close](../mfc/reference/casyncsocket-class.md#close) 멤버 함수를 호출합니다.

코드에서 이 시퀀스의 예는 `CSocket` (실제로 개체에 대 한) [참조 Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md).

## <a name="your-responsibilities-with-casyncsocket"></a><a name="_core_your_responsibilities_with_casyncsocket"></a>CAsync소켓에 대한 귀하의 책임

[클래스 CAsyncSocket의](../mfc/reference/casyncsocket-class.md)개체를 만들 때 개체는 Windows **SOCKET** 핸들을 캡슐화 하 고 해당 핸들에 작업을 제공 합니다. 을 사용할 `CAsyncSocket`때 API를 직접 사용하는 경우 발생할 수 있는 모든 문제를 처리해야 합니다. 다음은 그 예입니다.

- "차단" 시나리오.

- 송신 및 수신 컴퓨터 간의 바이트 순서 차이입니다.

- 유니코드 와 다바이트 문자 집합(MBCS) 문자열 간에 변환

이러한 용어 및 추가 정보의 정의에 대 한 Windows [소켓을 참조: 차단](../mfc/windows-sockets-blocking.md), [윈도우 소켓: 바이트 순서,](../mfc/windows-sockets-byte-ordering.md) [창 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md).

이러한 문제에도 `CAsycnSocket` 불구하고 응용 프로그램에 얻을 수 있는 모든 유연성과 제어가 필요한 경우 클래스가 적합한 선택일 수 있습니다. 그렇지 않은 경우 클래스를 `CSocket` 대신 사용하는 것이 좋습니다. `CSocket`많은 세부 정보를 숨깁니다: 호출을 차단하는 동안 Windows 메시지를 `CArchive`펌핑하고 바이트 순서 차이 및 문자열 변환을 관리하는 에 대한 액세스를 제공합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고 항목

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
