---
title: C소켓 클래스
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: 730bea34354b008d641ecc28e7368f79efad12a7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751160"
---
# <a name="csocket-class"></a>C소켓 클래스

에서 `CAsyncSocket`파생 된 Windows 소켓 API의 캡슐화를 상속 하 고 `CAsyncSocket` 개체보다 더 높은 수준의 추상화를 나타냅니다.

## <a name="syntax"></a>구문

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C소켓:::C소켓](#csocket)|`CSocket` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C소켓:::연결](#attach)|SOCKET 핸들을 개체에 `CSocket` 연결합니다.|
|[C소켓::취소차단호출](#cancelblockingcall)|현재 진행 중인 차단 호출을 취소합니다.|
|[C소켓::만들기](#create)|소켓을 만듭니다.|
|[C소켓:::에서 핸들](#fromhandle)|SOCKET 핸들이 `CSocket` 주어진 개체에 대한 포인터를 반환합니다.|
|[C소켓::차단](#isblocking)|차단 호출이 진행 중인지 여부를 확인합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C소켓::메시지 보류 중](#onmessagepending)|차단 호출이 완료될 때까지 기다리는 동안 보류 중인 메시지를 처리하도록 호출됩니다.|

## <a name="remarks"></a>설명

`CSocket`데이터 송수신을 관리하고 있습니다. `CSocketFile` `CArchive`

개체는 `CSocket` 또한 `CArchive`의 동기 작업에 필수적인 차단을 제공합니다. `Receive`을 `Send`클릭하는 `ReceiveFrom` `SendTo`함수(예: " `Accept` 및 모든 `CAsyncSocket`상속됨)는 `WSAEWOULDBLOCK` 에서 `CSocket`오류를 반환하지 않습니다. 대신 이러한 함수는 작업이 완료될 때까지 기다립니다. 또한 원래 호출은 이러한 함수 중 하나가 차단되는 동안 호출되는 경우 `CancelBlockingCall` WSAEINTR 오류로 종료됩니다.

개체를 `CSocket` 사용 하려면 생성자 호출 `Create` 한 다음 호출 하여 기본 SOCKET 핸들 (SOCKET 형식)을 만듭니다. 스트림 소켓을 `Create` 만드는 기본 매개 변수이지만 `CArchive` 개체가 있는 소켓을 사용하지 않는 경우 매개 변수를 지정하여 데이터그램 소켓을 만들거나 특정 포트에 바인딩하여 서버 소켓을 만들 수 있습니다. 클라이언트 측과 `Accept` 서버 `Connect` 측에서 사용하여 클라이언트 소켓에 연결합니다. 그런 다음 `CSocketFile` 개체를 만들고 `CSocket` `CSocketFile` 생성자의 개체에 연결합니다. 그런 다음 `CArchive` 전송할 개체와 데이터 수신을 위한 개체를 만든 `CSocketFile` 다음 `CArchive` 생성자의 개체와 연결합니다. 통신이 완료되면 에서 `CArchive`및 `CSocketFile` `CSocket` 개체를 삭제합니다. SOCKET 데이터 형식은 Windows [소켓: 백그라운드 문서에 설명되어 있습니다.](../../mfc/windows-sockets-background.md)

와 함께 `CArchive` `CSocketFile` `CSocket`사용할 때 요청된 바이트 `CSocket::Receive` 양을 기다리는 루프(by `PumpMessages(FD_READ)`by)가 들어오는 상황이 발생할 수 있습니다. 이는 Windows 소켓에서 FD_READ 알림당 하나의 recv `CSocketFile` 호출만 허용하지만 `CSocket` FD_READ 대해 여러 recv 호출을 허용하기 때문입니다. 읽을 데이터가 없을 때 FD_READ 받으면 응용 프로그램이 중단됩니다. 다른 FD_READ 얻지 못하면 응용 프로그램이 소켓을 통해 통신을 중지합니다.

이 문제를 다음과 같이 해결할 수 있습니다. 소켓 `OnReceive` 클래스의 메서드에서 소켓에서 읽을 `Serialize` 것으로 예상되는 데이터가 하나의 TCP 패킷(네트워크 미디어의 최대 전송 단위( 일반적으로 최소 1096바이트)을 초과할 때 메시지 클래스의 메서드를 호출하기 전에 호출합니다. `CAsyncSocket::IOCtl(FIONREAD, ...)` 사용 가능한 데이터의 크기가 필요 하지 않은 경우 모든 데이터가 수신될 때까지 기다린 다음 읽기 작업을 시작합니다.

다음 `m_dwExpected` 예제에서는 사용자가 수신할 것으로 예상되는 대략적인 바이트 수입니다. 코드의 다른 위치에 선언한다고 가정합니다.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
> 정적으로 연결된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 `AfxSocketInit` 사용하는 경우 소켓을 사용하여 소켓 라이브러리를 초기화하는 각 스레드를 호출해야 합니다. 기본적으로 기본 `AfxSocketInit` 스레드에서만 호출됩니다.

자세한 내용은 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓 : 아카이브가있는 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md)사용 , Windows 소켓 : [아카이브가있는 소켓 작업](../../mfc/windows-sockets-how-sockets-with-archives-work.md)방법 , Windows 소켓 : 작업 [시퀀스](../../mfc/windows-sockets-sequence-of-operations.md), [Windows 소켓 : 아카이브를 사용하는 소켓의 예](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

## <a name="csocketattach"></a><a name="attach"></a>C소켓:::연결

이 멤버 함수를 `hSocket` 호출하여 `CSocket` 핸들을 개체에 연결합니다.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*h소켓*<br/>
소켓에 대한 핸들이 포함되어 있습니다.

### <a name="return-value"></a>Return Value

함수가 성공하는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

SOCKET 핸들은 개체의 [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) 데이터 멤버에 저장됩니다.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

## <a name="csocketcancelblockingcall"></a><a name="cancelblockingcall"></a>C소켓::취소차단호출

현재 진행 중인 차단 호출을 취소하려면 이 멤버 함수를 호출합니다.

```cpp
void CancelBlockingCall();
```

### <a name="remarks"></a>설명

이 함수는 이 소켓에 대한 미해결 차단 작업을 취소합니다. WSAEINTR 오류로 원래 차단 호출이 가능한 한 빨리 종료됩니다.

차단 `Connect` 작업의 경우 Windows Sockets 구현은 가능한 한 빨리 차단 호출을 종료하지만 연결이 완료되고 재설정되거나 시간 만료될 때까지 소켓 리소스를 해제하지 못할 수 있습니다. 이는 응용 프로그램이 즉시 새 소켓을 열려거나(사용 가능한 소켓이 없는 경우) 동일한 피어에 연결하려고 하는 경우에만 눈에 띄게 될 수 있습니다.

소켓을 확정되지 `Accept` 않은 상태로 둘 수 있는 이외의 작업을 취소할 수 있습니다. 응용 프로그램이 소켓에서 차단 작업을 취소하는 경우 다른 작업이 일부 Windows 소켓 구현에서 작동할 `Close`수 있지만 응용 프로그램이 소켓에서 수행할 수 있는 작업에 종속될 수 있는 유일한 작업은 호출입니다. 응용 프로그램에 대한 최대 이식성을 원하는 경우 취소 후 수행 작업에 의존하지 않도록 주의해야 합니다.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketcreate"></a><a name="create"></a>C소켓::만들기

Windows 소켓을 만들고 연결하려면 소켓 개체를 생성한 후 멤버 **만들기** 함수를 호출합니다.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>매개 변수

*n소켓 포트*<br/>
MFC가 포트를 선택하려는 경우 소켓과 함께 사용할 특정 포트 또는 0입니다.

*n소켓 유형*<br/>
SOCK_STREAM 또는 SOCK_DGRAM.

*lpsz소켓 주소*<br/>
연결된 소켓의 네트워크 주소를 포함하는 문자열에 대한 포인터로, "128.56.22.8"과 같은 점선 번호입니다. 이 매개 변수에 대한 `CSocket` NULL 문자열을 전달하면 인스턴스가 모든 네트워크 인터페이스에서 클라이언트 작업을 수신 절영해야 합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0을 호출하여 특정 오류 `GetLastError`코드를 검색할 수 있습니다.

### <a name="remarks"></a>설명

`Create`그런 `Bind` 다음 지정된 주소에 소켓을 바인딩하기 위해 호출합니다. 다음 소켓 유형이 지원됩니다.

- SOCK_STREAM 시퀀스, 신뢰할 수 있는 양방향 연결 기반 바이트 스트림을 제공합니다. 인터넷 주소 패밀리에 대 한 전송 제어 프로토콜 (TCP)를 사용 합니다.

- SOCK_DGRAM 고정된(일반적으로 작은) 최대 길이의 연결되지 않고 신뢰할 수 없는 버퍼인 데이터그램을 지원합니다. 인터넷 주소 패밀리에 UDP(사용자 데이터그램 프로토콜)를 사용합니다. 이 옵션을 사용하려면 개체와 함께 소켓을 `CArchive` 사용해서는 안 됩니다.

    > [!NOTE]
    >  멤버 `Accept` 함수는 비어 `CSocket` 있는 새 개체를 매개 변수로 참조합니다. 을 호출하기 `Accept`전에 이 개체를 생성해야 합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙납니다. 이 새 `Create` 소켓 개체를 호출하지 마십시오.

스트림 및 데이터그램 소켓에 대한 자세한 내용은 [Windows 소켓: 배경,](../../mfc/windows-sockets-background.md) [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md)및 Windows [소켓: 아카이브가 있는 소켓 사용](../../mfc/windows-sockets-using-sockets-with-archives.md)문서를 참조하십시오.

## <a name="csocketcsocket"></a><a name="csocket"></a>C소켓:::C소켓

`CSocket` 개체를 생성합니다.

```
CSocket();
```

### <a name="remarks"></a>설명

시공 후에는 멤버 `Create` 함수를 호출해야 합니다.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketfromhandle"></a><a name="fromhandle"></a>C소켓:::에서 핸들

개체에 대한 `CSocket` 포인터를 반환합니다.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*h소켓*<br/>
소켓에 대한 핸들이 포함되어 있습니다.

### <a name="return-value"></a>Return Value

*hSocket에* `CSocket` 연결된 개체가 없는 `CSocket` 경우 개체에 대한 포인터 또는 NULL.

### <a name="remarks"></a>설명

SOCKET 핸들이 지정되면 `CSocket` 개체가 핸들에 연결되지 않은 경우 멤버 함수는 NULL을 반환하고 임시 개체를 만들지 않습니다.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketisblocking"></a><a name="isblocking"></a>C소켓::차단

이 멤버 함수를 호출하여 차단 호출이 진행 중인지 확인합니다.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Return Value

소켓이 차단되는 경우 0이 아닌 경우; 그렇지 않으면 0.

### <a name="remarks"></a>설명

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="csocketonmessagepending"></a><a name="onmessagepending"></a>C소켓::메시지 보류 중

이 멤버 함수를 재정의하여 Windows에서 특정 메시지를 찾고 소켓에서 응답합니다.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Return Value

메시지가 처리된 경우 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 고급 재정의 할 수 있습니다.

소켓이 `OnMessagePending` Windows 메시지를 펌핑하는 동안 프레임워크가 호출되어 응용 프로그램에 대한 관심 있는 메시지를 처리할 수 있습니다. 사용 `OnMessagePending`방법의 예는 [Windows 소켓: 소켓 클래스에서 파생](../../mfc/windows-sockets-deriving-from-socket-classes.md)되는 문서를 참조 합니다.

자세한 내용은 [Windows 소켓: 아카이브가 있는 소켓 사용.](../../mfc/windows-sockets-using-sockets-with-archives.md)

## <a name="see-also"></a>참조

[CAsync소켓 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsync소켓 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[C소켓 파일 클래스](../../mfc/reference/csocketfile-class.md)
