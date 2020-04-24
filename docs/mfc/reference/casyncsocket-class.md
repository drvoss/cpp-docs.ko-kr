---
title: CAsync소켓 클래스
ms.date: 09/03/2019
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
ms.openlocfilehash: e384be534bdbb355554c28383e9e214e9084f217
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753023"
---
# <a name="casyncsocket-class"></a>CAsync소켓 클래스

네트워크 통신의 끝점인 Windows 소켓을 나타냅니다.

## <a name="syntax"></a>구문

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CAsync 소켓::CAsync소켓](#casyncsocket)|`CAsyncSocket` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CAsync 소켓::수락](#accept)|소켓의 연결을 허용합니다.|
|[CAsync 소켓::비동기 선택](#asyncselect)|소켓에 대한 이벤트 알림을 요청합니다.|
|[CAsync 소켓::연결](#attach)|소켓 핸들을 개체에 `CAsyncSocket` 연결합니다.|
|[CAsync 소켓::바인딩](#bind)|로컬 주소를 소켓과 연결합니다.|
|[CAsync 소켓::닫기](#close)|소켓을 닫습니다.|
|[CAsync 소켓::연결](#connect)|피어 소켓에 대한 연결을 설정합니다.|
|[CAsyncSocket::Create](#create)|소켓을 만듭니다.|
|[CAsync소켓::D에타치](#detach)|개체에서 소켓 핸들을 `CAsyncSocket` 분리합니다.|
|[CAsync 소켓::에서 핸들](#fromhandle)|소켓 핸들이 `CAsyncSocket` 주어진 개체에 대한 포인터를 반환합니다.|
|[CAsync 소켓::GetLastError](#getlasterror)|실패한 마지막 작업에 대한 오류 상태를 가져옵니다.|
|[CAsync소켓::GetPeerName](#getpeername)|소켓이 연결된 피어 소켓의 주소를 가져옵니다.|
|[CAsync소켓::GetPeerNameEx](#getpeernameex)|소켓이 연결된 피어 소켓의 주소를 가져옵니다(IPv6 주소 처리).|
|[CAsync 소켓:::GetSockName](#getsockname)|소켓의 로컬 이름을 가져옵니다.|
|[CAsync소켓:::GetsockNameEx](#getsocknameex)|소켓의 로컬 이름을 가져옵니다(IPv6 주소 처리).|
|[CAsync소켓:::GetSockOpt](#getsockopt)|소켓 옵션을 검색합니다.|
|[CAsync소켓:::IOCtl](#ioctl)|소켓의 모드를 제어합니다.|
|[CAsync 소켓::듣기](#listen)|들어오는 연결 요청을 수신하는 소켓을 설정합니다.|
|[CAsync 소켓::수신](#receive)|소켓에서 데이터를 수신합니다.|
|[CAsync 소켓::수신에서](#receivefrom)|데이터그램을 수신하고 원본 주소를 저장합니다.|
|[CAsync 소켓::수신FromEx](#receivefromex)|데이터그램을 수신하고 원본 주소(IPv6 주소 처리)를 저장합니다.|
|[CAsync 소켓::보내기](#send)|데이터를 연결된 소켓으로 전송합니다.|
|[CAsync소켓::SendTo](#sendto)|데이터를 특정 대상으로 보냅니다.|
|[CAsync소켓::센드토엑스](#sendtoex)|데이터를 특정 대상으로 보냅니다(IPv6 주소 처리).|
|[CAsync소켓::SetSockOpt](#setsockopt)|소켓 옵션을 설정합니다.|
|[CAsync소켓::종료](#shutdown)|소켓에서 `Send` 비활성화 `Receive` 및/또는 통화를 비활성화합니다.|
|[CASync소켓::소켓](#socket)|소켓 핸들을 할당합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[CAsync 소켓::에 수락](#onaccept)|을 호출하여 `Accept`보류 중인 연결 요청을 수락할 수 있음을 수신 대기 소켓에 지정합니다.|
|[CAsync 소켓::온클로즈](#onclose)|연결된 소켓이 닫혔다는 것을 소켓에 지정합니다.|
|[CAsync 소켓::온커넥트](#onconnect)|연결 소켓에 연결 시도가 성공적으로 또는 오류되었는지 여부에 관계없이 완료되었는지 를 지정합니다.|
|[CAsync소켓::OnOutOfBandData](#onoutofbanddata)|수신 소켓에 대역 외 데이터가 소켓에서 읽을 수 있음을 알수 있습니다(일반적으로 긴급 메시지).|
|[CAsync 소켓:::수신](#onreceive)|을 호출하여 `Receive`검색할 데이터가 있음을 수신 대기 소켓에 지정합니다.|
|[CAsync소켓::온센드](#onsend)|을 호출하여 `Send`데이터를 보낼 수 있음을 소켓에 지정합니다.|

### <a name="public-operators"></a>Public 연산자

|속성|Description|
|----------|-----------------|
|[CAsync소켓::연산자 =](#operator_eq)|개체에 새 값을 `CAsyncSocket` 할당합니다.|
|[CAsync 소켓::연산자 소켓](#operator_socket)|이 연산자를 사용하여 개체의 SOCKET 핸들을 검색합니다. `CAsyncSocket`|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CAsync 소켓::m_hSocket](#m_hsocket)|이 `CAsyncSocket` 개체에 연결된 SOCKET 핸들을 나타냅니다.|

## <a name="remarks"></a>설명

클래스는 `CAsyncSocket` Windows 소켓 함수 API를 캡슐화하여 MFC와 함께 Windows 소켓을 사용하려는 프로그래머에게 개체 지향 추상화를 제공합니다.

이 클래스는 네트워크 통신을 이해한다는 가정을 기반으로 합니다. 차단, 바이트 순서 차이 및 유니코드와 다바이트 문자 집합(MBCS) 문자열 간의 변환을 처리해야 합니다. 이러한 문제를 관리하는 보다 편리한 인터페이스를 원한다면 [클래스 CSocket](../../mfc/reference/csocket-class.md)을 참조하십시오.

개체를 `CAsyncSocket` 사용 하려면 해당 생성자 호출 한 다음 [Create](#create) 함수를 `SOCKET`호출 하여 허용된 소켓을 제외하고 기본 소켓 핸들(type)을 만듭니다. 서버 소켓의 경우 [Listen](#listen) 멤버 함수를 호출하고 클라이언트 소켓은 [Connect](#connect) 멤버 함수를 호출합니다. 서버 소켓은 연결 요청을 받을 때 [Accept](#accept) 함수를 호출해야 합니다. 나머지 `CAsyncSocket` 함수를 사용하여 소켓 간의 통신을 수행합니다. 완료 시 힙에 `CAsyncSocket` 생성된 오브젝트를 파괴합니다. 소멸자가 자동으로 [Close](#close) 함수를 호출합니다. SOCKET 데이터 형식은 Windows [소켓: 백그라운드 문서에 설명되어 있습니다.](../../mfc/windows-sockets-background.md)

> [!NOTE]
> 정적으로 연결된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 `AfxSocketInit` 사용하는 경우 소켓을 사용하여 소켓 라이브러리를 초기화하는 각 스레드를 호출해야 합니다. 기본적으로 기본 `AfxSocketInit` 스레드에서만 호출됩니다.

자세한 내용은 [Windows 소켓: 클래스 CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) 및 관련 문서 사용 및 [Windows 소켓 2 API를](/windows/win32/WinSock/windows-sockets-start-page-2)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

## <a name="casyncsocketaccept"></a><a name="accept"></a>CAsync 소켓::수락

이 멤버 함수를 호출하여 소켓의 연결을 수락합니다.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>매개 변수

*r커넥티드 소켓*<br/>
연결에 사용할 수 있는 새 소켓을 식별하는 참조입니다.

*lpSockAddr*<br/>
네트워크에 알려진 연결 소켓의 주소를 수신하는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다. *lpSockAddr* 인수의 정확한 형식은 소켓을 만들 때 설정된 주소 패밀리에 의해 결정됩니다. *lpSockAddr* 및/또는 *lpSockAddrLen이* NULL과 같으면 허용된 소켓의 원격 주소에 대한 정보가 반환되지 않습니다.

*lp삭아드렌*<br/>
*바이트로 lpSockAddr의* 주소 길이에 대한 포인터입니다. *lpSockAddrLen값* 결과 매개 변수: 그것은 처음에 *lpSockAddr에*의해 가리키는 공간의 양을 포함 해야 합니다. 반환시 반환된 주소의 실제 길이(바이트)가 포함됩니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수가 너무 [작습니다(SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조의 크기보다 작음).

- WSAEINPROGRESS 차단 윈도우 소켓 호출이 진행 중입니다.

- WSAEINVAL은 `Listen` 수락하기 전에 호출되지 않았습니다.

- WSAEMFILE 대기열은 수락할 항목시 비어 있으며 사용 가능한 설명자가 없습니다.

- WSAENOBUFS 버퍼 공간을 사용할 수 없습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOpNOTSUPP 참조된 소켓은 연결 지향 서비스를 지원하는 형식이 아닙니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되며 허용될 연결이 없습니다.

### <a name="remarks"></a>설명

이 루틴은 보류 중인 연결 큐에서 첫 번째 연결을 추출하고 이 소켓과 동일한 속성을 가진 새 소켓을 만들고 *rConnectedSocket에*연결합니다. 큐에 보류 중인 연결이 없는 `Accept` 경우 `GetLastError` 0을 반환하고 오류를 반환합니다. 허용되는 *소켓(rConnectedSocket)은* 더 많은 연결을 수락하는 데 사용할 수 없습니다. 원래 소켓은 열려 있고 듣고 있는 상태로 유지됩니다.

인수 *lpSockAddr는* 통신 계층에 알려진 연결 소켓의 주소로 채워지는 결과 매개 변수입니다. `Accept`SOCK_STREAM 같은 연결 기반 소켓 유형에 사용됩니다.

## <a name="casyncsocketasyncselect"></a><a name="asyncselect"></a>CAsync 소켓::비동기 선택

이 멤버 함수를 호출하여 소켓에 대한 이벤트 알림을 요청합니다.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>매개 변수

*l이벤트*<br/>
응용 프로그램에 관심이 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- FD_READ 읽기 준비에 대한 알림을 받고 싶습니다.

- FD_WRITE 데이터를 읽을 수 있을 때 알림을 받고 싶습니다.

- FD_OOB 대역 외 데이터의 도착에 대한 알림을 받고 싶습니다.

- FD_ACCEPT 들어오는 연결에 대한 알림을 받고 싶습니다.

- FD_CONNECT 연결 결과에 대한 알림을 받고 싶습니다.

- FD_CLOSE 피어에 의해 소켓이 닫혔을 때 알림을 받고 싶습니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEINVAL 지정된 매개 변수 중 하나가 유효하지 않음을 나타냅니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

### <a name="remarks"></a>설명

이 함수는 소켓에 대해 호출되는 MFC 콜백 알림 함수를 지정하는 데 사용됩니다. `AsyncSelect`이 소켓을 비차단 모드로 자동으로 설정합니다. 자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

## <a name="casyncsocketattach"></a><a name="attach"></a>CAsync 소켓::연결

이 멤버 함수를 호출하여 *hSocket* 핸들을 개체에 연결합니다. `CAsyncSocket`

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>매개 변수

*h소켓*<br/>
소켓에 대한 핸들이 포함되어 있습니다.

*l이벤트*<br/>
응용 프로그램에 관심이 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- FD_READ 읽기 준비에 대한 알림을 받고 싶습니다.

- FD_WRITE 데이터를 읽을 수 있을 때 알림을 받고 싶습니다.

- FD_OOB 대역 외 데이터의 도착에 대한 알림을 받고 싶습니다.

- FD_ACCEPT 들어오는 연결에 대한 알림을 받고 싶습니다.

- FD_CONNECT 연결 결과에 대한 알림을 받고 싶습니다.

- FD_CLOSE 피어에 의해 소켓이 닫혔을 때 알림을 받고 싶습니다.

### <a name="return-value"></a>Return Value

함수가 성공하는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

SOCKET 핸들은 개체의 [m_hSocket](#m_hsocket) 데이터 멤버에 저장됩니다.

## <a name="casyncsocketbind"></a><a name="bind"></a>CAsync 소켓::바인딩

이 멤버 함수를 호출하여 로컬 주소를 소켓과 연결합니다.

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*n소켓 포트*<br/>
소켓 응용 프로그램을 식별하는 포트입니다.

*lpsz소켓 주소*<br/>
네트워크 주소, "128.56.22.8"과 같은 점선 숫자입니다. 이 매개 변수에 대한 `CAsyncSocket` NULL 문자열을 전달하면 인스턴스가 모든 네트워크 인터페이스에서 클라이언트 작업을 수신 절영해야 합니다.

*lpSockAddr*<br/>
이 소켓에 할당할 주소가 포함된 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다.

*n삭아드렌*<br/>
*lpSockAddr의* 주소 길이입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 다음 목록에서는 반환될 수 있는 몇 가지 오류를 다룹니다. 전체 목록은 Windows [소켓 오류 코드를](/windows/win32/winsock/windows-sockets-error-codes-2)참조하십시오.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEADDRINUSE 지정된 주소가 이미 사용 중입니다. [(setSockOpt에서](#setsockopt)SO_REUSEADDR 소켓 옵션을 참조하십시오.)

- WSAEFAULT *nSockAddrLen* 인수가 너무 [작습니다(SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조의 크기보다 작음).

- WSAEINPROGRESS 차단 윈도우 소켓 호출이 진행 중입니다.

- WSAEAFNOSUPPORT 지정된 주소 패밀리는 이 포트에서 지원되지 않습니다.

- WSAEINVAL 소켓이 이미 주소에 바인딩되어 있습니다.

- WSAENOBUFS 사용 가능한 버퍼가 충분하지 않고 연결이 너무 많습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

이 루틴은 후속 `Connect` 또는 `Listen` 호출 전에 연결되지 않은 데이터그램 또는 스트림 소켓에 사용됩니다. 연결 요청을 수락하기 전에 수신 대기 서버 소켓은 포트 번호를 선택하고 을 `Bind`호출하여 Windows 소켓에 알려야 합니다. `Bind`이름 없는 소켓에 로컬 이름을 할당하여 소켓의 로컬 연결(호스트 주소/포트 번호)을 설정합니다.

## <a name="casyncsocketcasyncsocket"></a><a name="casyncsocket"></a>CAsync 소켓::CAsync소켓

빈 소켓 개체를 생성합니다.

```
CAsyncSocket();
```

### <a name="remarks"></a>설명

개체를 생성한 후 해당 `Create` 멤버 함수를 호출하여 SOCKET 데이터 구조를 만들고 해당 주소를 바인딩해야 합니다. Windows 소켓 통신의 서버 쪽에서는 수신 대기 소켓이 호출에 사용할 `Accept` 소켓을 만들 `Create` 때 해당 소켓을 호출하지 않습니다.

## <a name="casyncsocketclose"></a><a name="close"></a>CAsync 소켓::닫기

소켓을 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

이 함수는 소켓 설명기를 해제하여 WSAENOTSOCK 오류로 소켓에 대한 추가 참조가 실패합니다. 기본 소켓에 대한 마지막 참조인 경우 연결된 이름 정보 및 큐에 대기중인 데이터가 삭제됩니다. 소켓 개체의 소멸자가 `Close` 호출합니다.

의 `CAsyncSocket` `CSocket`경우 의미 `Close` 체계는 SO_LINGER 소켓 옵션및 SO_DONTLINGER 영향을 받습니다. 자세한 내용은 멤버 함수를 `GetSockOpt`참조하십시오.

## <a name="casyncsocketconnect"></a><a name="connect"></a>CAsync 소켓::연결

이 멤버 함수를 호출하여 연결되지 않은 스트림 또는 데이터그램 소켓에 대한 연결을 설정합니다.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*lpszHostAddress*<br/>
이 개체가 연결된 소켓의 네트워크 주소: "ftp.microsoft.com"와 같은 컴퓨터 이름 또는 "128.56.22.8"과 같은 점선 번호입니다.

*n호스트포트*<br/>
소켓 응용 프로그램을 식별하는 포트입니다.

*lpSockAddr*<br/>
연결된 소켓의 주소를 포함하는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다.

*n삭아드렌*<br/>
*lpSockAddr의* 주소 길이입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. WSAEWOULDBLOCK의 오류 코드를 나타내고 응용 프로그램이 재정의 가능한 콜백을 사용하는 경우 연결 `OnConnect` 작업이 완료되면 응용 프로그램에 메시지가 표시됩니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEADDRINUSE 지정된 주소가 이미 사용 중입니다.

- WSAEINPROGRESS 차단 윈도우 소켓 호출이 진행 중입니다.

- WSAEADDRNOTAVAIL 지정된 주소를 로컬 컴퓨터에서 사용할 수 없습니다.

- 지정된 패밀리의 WSAEAFNOSUPPORT 주소는 이 소켓과 함께 사용할 수 없습니다.

- WSAEConnREFUSED 연결 시도가 거부되었습니다.

- WSAEDADDRREQ 대상 주소가 필요합니다.

- WSAEFAULT *nSockAddrLen* 인수가 올바르지 않습니다.

- WSAEInval 잘못된 호스트 주소입니다.

- WSAEISCONN 소켓이 이미 연결되어 있습니다.

- WSAEMFILE 더 이상 파일 설명자는 사용할 수 없습니다.

- WSAENETUNREACH 현재 이 호스트에서 네트워크에 연결할 수 없습니다.

- WSAENOBUFS 버퍼 공간을 사용할 수 없습니다. 소켓을 연결할 수 없습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAETIMEDOUT 연결을 설정하지 않고 시간 시간이 시간 지정된 연결을 시도합니다.

- WSAEWOULDBLOCK 소켓이 비차단으로 표시되어 있으며 연결을 즉시 완료할 수 없습니다.

### <a name="remarks"></a>설명

소켓이 언바운드인 경우 고유 값은 시스템에 의해 로컬 연결에 할당되고 소켓은 바운드로 표시됩니다. 이름 구조의 주소 필드가 모두 0이면 `Connect` 0이 반환됩니다. 확장 오류 정보를 얻으려면 `GetLastError` 멤버 함수를 호출합니다.

스트림 소켓(유형 SOCK_STREAM)의 경우 외부 호스트에 활성 연결이 시작됩니다. 소켓 호출이 성공적으로 완료되면 소켓이 데이터를 보내고 받을 준비가 된 것입니다.

데이터그램 소켓(SOCK_DGRAM 유형)의 경우 후속 `Send` 및 `Receive` 호출에 사용되는 기본 대상이 설정됩니다.

## <a name="casyncsocketcreate"></a><a name="create"></a>CAsync 소켓::만들기

소켓 `Create` 개체를 생성한 후 멤버 함수를 호출하여 Windows 소켓을 만들고 연결합니다.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>매개 변수

*n소켓 포트*<br/>
Windows 소켓이 포트를 선택하도록 하려면 소켓과 함께 사용할 잘 알려진 포트 또는 0입니다.

*n소켓 유형*<br/>
SOCK_STREAM 또는 SOCK_DGRAM.

*l이벤트*<br/>
응용 프로그램에 관심이 있는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- FD_READ 읽기 준비에 대한 알림을 받고 싶습니다.

- FD_WRITE 작성 준비 에 대한 알림을 받고 싶습니다.

- FD_OOB 대역 외 데이터의 도착에 대한 알림을 받고 싶습니다.

- FD_ACCEPT 들어오는 연결에 대한 알림을 받고 싶습니다.

- FD_CONNECT 완료된 연결 알림을 받고 싶습니다.

- FD_CLOSE 소켓 폐쇄 알림을 받고 싶습니다.

*lpszSockAddress*<br/>
연결된 소켓의 네트워크 주소를 포함하는 문자열에 대한 포인터로, "128.56.22.8"과 같은 점선 번호입니다. 이 매개 변수에 대한 `CAsyncSocket` NULL 문자열을 전달하면 인스턴스가 모든 네트워크 인터페이스에서 클라이언트 작업을 수신 절영해야 합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEAFNO지원 지정된 주소 패밀리는 지원되지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEMFILE 더 이상 파일 설명자는 사용할 수 없습니다.

- WSAENOBUFS 버퍼 공간을 사용할 수 없습니다. 소켓을 만들 수 없습니다.

- WSAEPROTONOSUPPORT 지정된 포트가 지원되지 않습니다.

- WSAEPROTOTYPE 지정된 포트가 이 소켓에 대해 잘못된 형식입니다.

- WSAESOCKTNOSUPPORT 지정된 소켓 유형은 이 주소 패밀리에서 지원되지 않습니다.

### <a name="remarks"></a>설명

`Create`[소켓을](#socket) 호출하고 성공하면 [바인딩을](#bind) 호출하여 지정된 주소에 소켓을 바인딩합니다. 다음 소켓 유형이 지원됩니다.

- SOCK_STREAM 연속적으로 신뢰할 수 있는 전이중 바이트 스트림을 제공합니다. 인터넷 주소 패밀리에 대 한 전송 제어 프로토콜 (TCP)를 사용 합니다.

- SOCK_DGRAM 고정된(일반적으로 작은) 최대 길이의 연결되지 않고 신뢰할 수 없는 패킷인 데이터그램을 지원합니다. 인터넷 주소 패밀리에 UDP(사용자 데이터그램 프로토콜)를 사용합니다.

    > [!NOTE]
    >  멤버 `Accept` 함수는 비어 `CSocket` 있는 새 개체를 매개 변수로 참조합니다. 을 호출하기 `Accept`전에 이 개체를 생성해야 합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙납니다. 이 새 `Create` 소켓 개체를 호출하지 마십시오.

> [!IMPORTANT]
> `Create`스레드가 안전하지 **않습니다.**  다른 스레드에서 동시에 호출할 수 있는 다중 스레드 환경에서 호출하는 경우 뮤텍스 또는 다른 동기화 잠금으로 각 호출을 보호해야 합니다.

스트림 및 데이터그램 소켓에 대한 자세한 내용은 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md) 및 [Windows 소켓: 포트 및 소켓 주소 및](../../mfc/windows-sockets-ports-and-socket-addresses.md) Windows 소켓 2 [API](/windows/win32/WinSock/windows-sockets-start-page-2)문서를 참조하십시오.

## <a name="casyncsocketdetach"></a><a name="detach"></a>CAsync소켓::D에타치

이 멤버 함수를 호출하여 *m_hSocket* 데이터 멤버의 SOCKET `CAsyncSocket` 핸들을 개체에서 분리하고 *m_hSocket* NULL로 설정합니다.

```
SOCKET Detach();
```

## <a name="casyncsocketfromhandle"></a><a name="fromhandle"></a>CAsync 소켓::에서 핸들

개체에 대한 `CAsyncSocket` 포인터를 반환합니다.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*h소켓*<br/>
소켓에 대한 핸들이 포함되어 있습니다.

### <a name="return-value"></a>Return Value

*hSocket에* `CAsyncSocket` 연결된 개체가 없는 `CAsyncSocket` 경우 개체에 대한 포인터 또는 NULL.

### <a name="remarks"></a>설명

SOCKET 핸들이 지정되면 `CAsyncSocket` 개체가 핸들에 연결되지 않은 경우 멤버 함수는 NULL을 반환합니다.

## <a name="casyncsocketgetlasterror"></a><a name="getlasterror"></a>CAsync 소켓::GetLastError

이 멤버 함수를 호출하여 실패한 마지막 작업에 대한 오류 상태를 가져옵니다.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Return Value

반환 값은 이 스레드에서 수행한 마지막 Windows Sockets API 루틴에 대한 오류 코드를 나타냅니다.

### <a name="remarks"></a>설명

특정 멤버 함수가 오류가 발생했음을 `GetLastError` 나타내면 적절한 오류 코드를 검색하기 위해 호출해야 합니다. 적용 가능한 오류 코드 목록은 개별 멤버 함수 설명을 참조하십시오.

오류 코드에 대한 자세한 내용은 [Windows 소켓 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)를 참조하십시오.

## <a name="casyncsocketgetpeername"></a><a name="getpeername"></a>CAsync소켓::GetPeerName

이 멤버 함수를 호출하여 이 소켓이 연결된 피어 소켓의 주소를 가져옵니다.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*r피어 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r피어 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

*lpSockAddr*<br/>
피어 소켓의 이름을 받는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다.

*lp삭아드렌*<br/>
*바이트로 lpSockAddr의* 주소 길이에 대한 포인터입니다. 반환시, *lpSockAddrLen* 인수는 바이트로 반환 *된 lpSockAddr의* 실제 크기를 포함합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수는 충분히 크지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 호출이 진행 중입니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

IPv6 주소를 처리하려면 [CAsyncSocket::GetPeerNameEx](#getpeernameex)를 사용합니다.

## <a name="casyncsocketgetpeernameex"></a><a name="getpeernameex"></a>CAsync소켓::GetPeerNameEx

이 멤버 함수를 호출하여 이 소켓이 연결된 피어 소켓의 주소를 가져옵니다(IPv6 주소 처리).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>매개 변수

*r피어 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r피어 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수는 충분히 크지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 호출이 진행 중입니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

이 함수는 이전 프로토콜뿐만 아니라 IPv6 주소를 처리한다는 점을 제외하면 [CAsyncSocket::GetPeerName과](#getpeername) 동일합니다.

## <a name="casyncsocketgetsockname"></a><a name="getsockname"></a>CAsync 소켓:::GetSockName

이 멤버 함수를 호출하여 소켓의 로컬 이름을 가져옵니다.

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*r소켓 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r소켓 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

*lpSockAddr*<br/>
소켓의 주소를 받는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다.

*lp삭아드렌*<br/>
*바이트로 lpSockAddr의* 주소 길이에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수는 충분히 크지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEINVAL 소켓이 있는 `Bind`주소에 바인딩되지 않았습니다.

### <a name="remarks"></a>설명

이 호출은 `Connect` `Bind` 첫 번째 호출을 수행하지 않고 호출이 수행된 경우에 특히 유용합니다. 이 호출은 시스템에서 설정한 로컬 연결을 확인할 수 있는 유일한 수단을 제공합니다.

IPv6 주소를 처리하려면 [CAsyncSocket::GetSockNameEx를](#getsocknameex) 사용합니다.

## <a name="casyncsocketgetsocknameex"></a><a name="getsocknameex"></a>CAsync소켓:::GetsockNameEx

이 멤버 함수를 호출하여 소켓의 로컬 이름을 가져옵니다(IPv6 주소 처리).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>매개 변수

*r소켓 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r소켓 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수는 충분히 크지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEINVAL 소켓이 있는 `Bind`주소에 바인딩되지 않았습니다.

### <a name="remarks"></a>설명

이 호출은 이전 프로토콜뿐만 아니라 IPv6 주소를 처리한다는 점을 제외하면 [CAsyncSocket::GetSockName과](#getsockname) 동일합니다.

이 호출은 `Connect` `Bind` 첫 번째 호출을 수행하지 않고 호출이 수행된 경우에 특히 유용합니다. 이 호출은 시스템에서 설정한 로컬 연결을 확인할 수 있는 유일한 수단을 제공합니다.

## <a name="casyncsocketgetsockopt"></a><a name="getsockopt"></a>CAsync소켓:::GetSockOpt

이 멤버 함수를 호출하여 소켓 옵션을 검색합니다.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>매개 변수

*n옵션 이름*<br/>
값을 검색할 소켓 옵션입니다.

*lp옵션값*<br/>
요청된 옵션의 값을 반환할 버퍼에 대한 포인터입니다. 선택한 옵션과 연결된 값이 버퍼 *lpOptionValue*에서 반환됩니다. *lpOptionLen으로* 가리키는 정수는 원래 이 버퍼의 크기를 바이트로 포함해야 합니다. 반환할 때 반환되는 값의 크기로 설정됩니다. SO_LINGER 경우, 이것은 구조의 `LINGER` 크기가 될 것입니다. 다른 모든 옵션의 경우 옵션에 따라 BOOL 또는 **int의**크기가 됩니다. 비고 섹션에서 옵션 및 해당 크기 목록을 참조하십시오.

*lpOptionLen*<br/>
*바이트의 lpOptionValue* 버퍼 크기에 대 한 포인터입니다.

*n레벨*<br/>
옵션이 정의된 수준입니다. 지원되는 수준은 SOL_SOCKET 및 IPPROTO_TCP.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 옵션을 함께 설정하지 `SetSockOpt`않은 `GetSockOpt` 경우 옵션의 기본값을 반환합니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpOptionLen* 인수가 잘못되었습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOPROTOOPT 이 옵션은 알 수 없거나 지원되지 않습니다. 특히 SO_BROADCAST SOCK_STREAM 형식의 소켓에서는 지원되지 않지만 SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER 및 SO_OOBINLINE 형식 SOCK_DGRAM 소켓에서는 지원되지 않습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

`GetSockOpt`모든 형식의 소켓과 연결된 소켓 옵션의 현재 값을 모든 상태에서 검색하고 결과를 *lpOptionValue*에 저장합니다. 옵션은 패킷 라우팅, 대역 외 데이터 전송 등과 같은 소켓 작업에 영향을 미칩니다.

다음 옵션은 에 `GetSockOpt`대해 지원됩니다. Type은 *lpOptionValue*에서 해결되는 데이터 유형을 식별합니다. TCP_NODELAY 옵션은 레벨 IPPROTO_TCP 사용합니다. 다른 모든 옵션은 레벨 SOL_SOCKET 사용합니다.

|값|Type|의미|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|소켓이 대기 중입니다.|
|SO_BROADCAST|BOOL|소켓은 브로드캐스트 메시지의 전송을 위해 구성된다.|
|SO_DEBUG|BOOL|디버깅이 활성화되어 있습니다.|
|SO_DONTLINGER|BOOL|true이면 SO_LINGER 옵션이 비활성화됩니다.|
|SO_DONTROUTE|BOOL|라우팅이 비활성화되었습니다.|
|SO_ERROR|**int**|오류 상태를 검색하고 지우기.|
|SO_KEEPALIVE|BOOL|Keep-alives가 전송되고 있습니다.|
|SO_LINGER|`struct LINGER`|현재 느린 옵션을 반환합니다.|
|SO_OOBINLINE|BOOL|대역 외 데이터가 일반 데이터 스트림에서 수신되고 있습니다.|
|SO_RCVBUF|int|수신에 대한 버퍼 크기입니다.|
|SO_REUSEADDR|BOOL|소켓은 이미 사용 중인 주소에 바인딩할 수 있습니다.|
|SO_SNDBUF|**int**|송신의 버퍼 크기입니다.|
|SO_TYPE|**int**|소켓의 유형(예: SOCK_STREAM)입니다.|
|Tcp_nodelay|BOOL|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|

지원되지 않는 버클리 소프트웨어 배포(BSD) 옵션은 다음과 같습니다. `GetSockOpt`

|값|Type|의미|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|낮은 워터 마크를 받습니다.|
|SO_RCVTIMEO|**int**|시간 시간을 받습니다.|
|SO_SNDLOWAT|**int**|낮은 워터 마크를 보냅니다.|
|SO_SNDTIMEO|**int**|시간 시간을 보냅니다.|
|IP_OPTIONS||IP 헤더에서 옵션을 가져옵니다.|
|TCP_MAXSEG|**int**|TCP 최대 세그먼트 크기를 가져옵니다.|

지원되지 않는 옵션을 호출하면 `GetSockOpt` WSAENOPROTOOPT에서 오류 코드가 `GetLastError`반환됩니다.

## <a name="casyncsocketioctl"></a><a name="ioctl"></a>CAsync소켓:::IOCtl

이 멤버 함수를 호출하여 소켓 모드를 제어합니다.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>매개 변수

*lCommand*<br/>
소켓에서 수행할 명령입니다.

*lp인수*<br/>
*lCommand에*대 한 매개 변수에 대 한 포인터입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEINVAL *lCommand는* 유효한 명령이 아니거나 *lpArgument가* *lCommand에*허용되는 매개 변수가 아니거나 명령이 제공된 소켓 유형에 적용되지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

이 루틴은 모든 상태의 모든 소켓에서 사용할 수 있습니다. 프로토콜 및 통신 하위 시스템과 는 별개로 소켓과 관련된 운영 매개 변수를 얻거나 검색하는 데 사용됩니다. 지원되는 명령은 다음과 같습니다.

- FIONBIO 소켓에서 비차단 모드를 활성화하거나 비활성화합니다. *lpArgument* 매개 변수는 `DWORD`비차단 모드를 사용하도록 설정하면 0이 아닌 에서 를 가리키며 비활성화할 경우 0을 가리킵니다. 소켓에서 발급된 경우 `AsyncSelect` 소켓을 다시 `IOCtl` 차단 모드로 설정하는 데 사용하려는 시도는 WSAEINVAL에서 실패합니다. 소켓을 다시 차단 모드로 설정하고 WSAEINVAL 오류를 방지하려면 `AsyncSelect` 응용 `AsyncSelect` 프로그램이 먼저 0과 동일한 *lEvent* 매개 변수를 호출하여 비활성화한 다음 을 호출해야 `IOCtl`합니다.

- FIONREAD 이 소켓에서 한 번의 `Receive` 호출로 읽을 수 있는 최대 바이트 수를 확인합니다. *lpArgument* 매개 변수는 `DWORD` 결과를 `IOCtl` 저장하는 지점을 가리킵니다. 이 소켓이 SOCK_STREAM 경우 FIONREAD는 단일에서 `Receive`읽을 수 있는 총 데이터 양을 반환합니다. 이는 일반적으로 소켓에 큐에 대기된 데이터의 총 양과 동일합니다. 이 소켓이 SOCK_DGRAM 형식인 경우 FIONREAD는 소켓에 큐에 대기된 첫 번째 데이터그램의 크기를 반환합니다.

- SIOCATMARK 모든 대역 외 데이터를 읽었는지 여부를 결정합니다. 이는 대역 외 데이터(SO_OOBINLINE)의 인라인 수신을 위해 구성된 형식 SOCK_STREAM 소켓에만 적용됩니다. 대역 외 데이터가 읽기를 기다리지 않으면 작업이 0이 아닌 것으로 반환됩니다. 그렇지 않으면 0을 반환하고 다음 `Receive` 또는 `ReceiveFrom` 소켓에서 수행된 데이터는 "mark" 앞에 있는 데이터의 일부 또는 전부를 검색합니다. 응용 프로그램은 SIOCATMARK 작업을 사용하여 데이터가 남아 있는지 여부를 결정해야 합니다. "긴급"(대역 외) 데이터 앞에 정상적인 데이터가 있으면 순서대로 수신됩니다. (a `Receive` 또는 `ReceiveFrom` 동일한 호출에서 대역 외 및 일반 데이터를 혼합하지 않습니다.) *lpArgument* 매개 변수는 `DWORD` 결과를 `IOCtl` 저장하는 지점을 가리킵니다.

이 함수는 버클리 `ioctl()` 소켓에 사용되는 하위 집합입니다. 특히 FIOASYNC와 동등한 명령은 없으며 SIOCATMARK는 지원되는 유일한 소켓 수준 명령입니다.

## <a name="casyncsocketlisten"></a><a name="listen"></a>CAsync 소켓::듣기

들어오는 연결 요청을 수신하려면 이 멤버 함수를 호출합니다.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>매개 변수

*n연결 백로그*<br/>
보류 중인 연결의 큐가 증가할 수 있는 최대 길이입니다. 유효한 범위는 1에서 5까지입니다.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEADDRINUSE 사용 중 주소에서 수신을 위해 시도되었습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEINVAL 소켓이 바인딩되지 `Bind` 않았거나 이미 연결되어 있습니다.

- WSAEISCONN 소켓이 이미 연결되어 있습니다.

- WSAEMFILE 더 이상 파일 설명자는 사용할 수 없습니다.

- WSAENOBUFS 버퍼 공간을 사용할 수 없습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOpNOTSUPP 참조된 소켓은 작업을 지원하는 형식이 `Listen` 아닙니다.

### <a name="remarks"></a>설명

연결을 허용하기 위해 소켓은 `Create`에서 먼저 만들어집니다.에서 들어오는 연결에 대한 백로그가 `Listen` `Accept`지정되고 연결은 을 사용하여 수락됩니다. `Listen`연결을 지원하는 소켓, 즉 형식 SOCK_STREAM 소켓에만 적용됩니다. 이 소켓은 들어오는 연결을 승인하고 프로세스에 의해 수락 대기 중인 대기 중인 "수동" 모드로 전환됩니다.

이 함수는 일반적으로 한 번에 두 개 이상의 연결 요청을 가질 수 있는 서버(또는 연결을 수락하려는 모든 응용 프로그램)에서 사용됩니다.

`Listen`사용 가능한 포트(설명자)가 없을 때 합리적으로 계속 작동하려고 시도합니다. 큐가 비워질 때까지 연결을 허용합니다. 포트를 사용할 수 있게 `Listen` 되면 `Accept` 나중에 현재 또는 가장 최근의 "백로그"로 큐를 호출하거나 리필하고 들어오는 연결에 대한 수신 수신 을 다시 시작합니다.

## <a name="casyncsocketm_hsocket"></a><a name="m_hsocket"></a>CAsync 소켓::m_hSocket

이 `CAsyncSocket` 개체에 의해 캡슐화된 소켓에 대한 SOCKET 핸들을 포함합니다.

```
SOCKET m_hSocket;
```

## <a name="casyncsocketonaccept"></a><a name="onaccept"></a>CAsync 소켓::에 수락

[수락](#accept) 멤버 함수를 호출하여 보류 중인 연결 요청을 수락할 수 있음을 수신 대기 소켓에 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnAccept` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

### <a name="remarks"></a>설명

자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

## <a name="casyncsocketonclose"></a><a name="onclose"></a>CAsync 소켓::온클로즈

프레임워크에서 호출하여 연결된 소켓이 프로세스에 의해 닫혀 있음을 이 소켓에 알립니다.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnClose` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAECONNRESET 연결이 원격 측에 의해 재설정되었습니다.

- WSAECONNABORTED 시간 시간 또는 기타 오류로 인해 연결이 중단되었습니다.

### <a name="remarks"></a>설명

자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

## <a name="casyncsocketonconnect"></a><a name="onconnect"></a>CAsync 소켓::온커넥트

이 연결 소켓에 연결 시도가 성공적으로 또는 오류되었는지 여부에 관계없이 완료되었음을 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnConnect` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAEADDRINUSE 지정된 주소가 이미 사용 중입니다.

- WSAEADDRNOTAVAIL 지정된 주소를 로컬 컴퓨터에서 사용할 수 없습니다.

- 지정된 패밀리의 WSAEAFNOSUPPORT 주소는 이 소켓과 함께 사용할 수 없습니다.

- WSAEConnREFUSED 연결 시도는 강제로 거부되었습니다.

- WSAEDADDRREQ 대상 주소가 필요합니다.

- WSAEFAULT *lpSockAddrLen* 인수가 올바르지 않습니다.

- WSAEINVAL 소켓이 이미 주소에 바인딩되어 있습니다.

- WSAEISCONN 소켓이 이미 연결되어 있습니다.

- WSAEMFILE 더 이상 파일 설명자는 사용할 수 없습니다.

- WSAENETUNREACH 현재 이 호스트에서 네트워크에 연결할 수 없습니다.

- WSAENOBUFS 버퍼 공간을 사용할 수 없습니다. 소켓을 연결할 수 없습니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다.

- WSAENOTSOCK 설명자는 소켓이 아닌 파일입니다.

- WSAETIMEDOUT 연결을 설정하지 않고 시간 시간이 시간 지정된 연결을 시도합니다.

### <a name="remarks"></a>설명

> [!NOTE]
> [CSocket에서](../../mfc/reference/csocket-class.md)알림 `OnConnect` 함수는 호출되지 않습니다. 연결의 경우 연결이 `Connect`완료될 때 반환되는 을 호출하기만 하면 됩니다(성공적으로 또는 오류). 연결 알림을 처리하는 방법은 MFC 구현 세부 정보입니다.

자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

## <a name="casyncsocketonoutofbanddata"></a><a name="onoutofbanddata"></a>CAsync소켓::OnOutOfBandData

송신 소켓에 보낼 대역 외 데이터가 있음을 수신 소켓에 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnOutOfBandData` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

### <a name="remarks"></a>설명

대역 외 데이터는 SOCK_STREAM 형식의 연결된 각 소켓 쌍과 연결된 논리적으로 독립적인 채널입니다. 채널은 일반적으로 긴급 데이터를 전송하는 데 사용됩니다.

MFC는 대역 외 데이터를 지원하지만 `CAsyncSocket` 클래스 사용자는 데이터를 사용하지 않는 것이 좋습니다. 더 쉬운 방법은 이러한 데이터를 전달하기 위한 두 번째 소켓을 만드는 것입니다. 대역 외 데이터에 대한 자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

## <a name="casyncsocketonreceive"></a><a name="onreceive"></a>CAsync 소켓:::수신

멤버 함수를 호출하여 검색할 수 있는 버퍼에 데이터가 있음을 이 `Receive` 소켓에 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnReceive` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

### <a name="remarks"></a>설명

자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

## <a name="casyncsocketonsend"></a><a name="onsend"></a>CAsync소켓::온센드

이제 멤버 함수를 호출하여 데이터를 보낼 수 있음을 `Send` 소켓에 알리기 위해 프레임워크에서 호출합니다.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓의 최신 오류입니다. 다음 오류 코드는 `OnSend` 멤버 함수에 적용됩니다.

- **0** 함수가 성공적으로 실행되었습니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

### <a name="remarks"></a>설명

자세한 내용은 [Windows 소켓: 소켓 알림을](../../mfc/windows-sockets-socket-notifications.md)참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

## <a name="casyncsocketoperator-"></a><a name="operator_eq"></a>CAsync소켓::연산자 =

개체에 새 값을 `CAsyncSocket` 할당합니다.

```cpp
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
기존 `CAsyncSocket` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

이 함수를 호출하여 `CAsyncSocket` 기존 `CAsyncSocket` 개체를 다른 개체에 복사합니다.

## <a name="casyncsocketoperator-socket"></a><a name="operator_socket"></a>CAsync 소켓::연산자 소켓

이 연산자를 사용하여 개체의 SOCKET 핸들을 검색합니다. `CAsyncSocket`

```
operator SOCKET() const;
```

### <a name="return-value"></a>Return Value

성공하면 SOCKET 개체의 핸들; 그렇지 않으면 NULL이 됩니다.

### <a name="remarks"></a>설명

핸들을 사용하여 Windows API를 직접 호출할 수 있습니다.

## <a name="casyncsocketreceive"></a><a name="receive"></a>CAsync 소켓::수신

이 멤버 함수를 호출하여 소켓에서 데이터를 수신합니다.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대한 버퍼입니다.

*n부플렌*<br/>
바이트로 *lpBuf의* 길이입니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_PEEK 들어오는 데이터를 엿볼 수 있습니다. 데이터는 버퍼에 복사되지만 입력 큐에서 제거되지 않습니다.

- 대역 외 데이터를 MSG_OOB 처리합니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `Receive` 수신된 바이트 수를 반환합니다. 연결이 닫히면 0을 반환합니다. 그렇지 않으면 SOCKET_ERROR 값이 반환되고 [GetLastError](#getlasterror)를 호출하여 특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 0 `Receive` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 `Receive` 작업이 차단됩니다.

- WSAEMSGSIZE 데이터그램이 너무 커서 지정된 버퍼에 맞지 않고 잘렸습니다.

- WSAEINVAL 소켓이 바인딩되지 `Bind`않았습니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

### <a name="remarks"></a>설명

이 함수는 연결된 스트림 또는 데이터그램 소켓에 사용되며 들어오는 데이터를 읽는 데 사용됩니다.

SOCK_STREAM 형식의 소켓의 경우 제공된 버퍼 크기까지 현재 사용할 수 있는 많은 정보가 반환됩니다. 소켓이 대역 외 데이터(소켓 옵션 SO_OOBINLINE)의 인라인 수신을 위해 구성되었으며 대역 외 데이터가 읽지 않은 경우 대역 외 데이터만 반환됩니다. 응용 프로그램은 `IOCtlSIOCATMARK` 옵션 또는 [OnOutOfBandData를](#onoutofbanddata) 사용하여 더 이상 대역 외 데이터를 읽을 수 있는지 여부를 결정할 수 있습니다.

데이터그램 소켓의 경우 첫 번째 큐에 대기된 데이터그램에서 제공된 버퍼 크기까지 데이터가 추출됩니다. 데이터그램이 제공된 버퍼보다 큰 경우 버퍼는 데이터그램의 첫 번째 부분으로 채워지고, 초과 `Receive` 데이터가 손실되고, WSAEMSGSIZE로 설정된 오류 코드로 SOCKET_ERROR 값을 반환합니다. 소켓에서 들어오는 데이터를 사용할 수 없는 경우 WSAEWOULDBLOCK으로 설정된 오류 코드와 함께 SOCKET_ERROR 값이 반환됩니다. [OnReceive](#onreceive) 콜백 함수를 사용하여 더 많은 데이터가 도착하는 시기를 결정할 수 있습니다.

소켓이 SOCK_STREAM 유형이고 원격 측이 연결을 정상적으로 종료한 `Receive` 경우 0바이트가 수신된 즉시 완료됩니다. 연결이 재설정되면 WSAECONNRESET 오류가 발생하면 a가 `Receive` 실패합니다.

`Receive`[CAsyncSocket::OnReceive가](#onreceive) 호출될 때마다 한 번만 호출해야 합니다.

### <a name="example"></a>예제

  [CAsyncSocket::OnReceive](#onreceive)에 대한 예제를 참조하십시오.

## <a name="casyncsocketreceivefrom"></a><a name="receivefrom"></a>CAsync 소켓::수신에서

이 멤버 함수를 호출하여 데이터그램을 수신하고 소스 주소를 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조 또는 *rSocketAddress에*저장합니다.

```
int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);

int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대한 버퍼입니다.

*n부플렌*<br/>
바이트로 *lpBuf의* 길이입니다.

*r소켓 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r소켓 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

*lpSockAddr*<br/>
반환 시 소스 주소를 보유 하는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대 한 포인터입니다.

*lp삭아드렌*<br/>
*바이트의 lpSockAddr에서* 소스 주소의 길이에 대 한 포인터입니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_PEEK 들어오는 데이터를 엿볼 수 있습니다. 데이터는 버퍼에 복사되지만 입력 큐에서 제거되지 않습니다.

- 대역 외 데이터를 MSG_OOB 처리합니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `ReceiveFrom` 수신된 바이트 수를 반환합니다. 연결이 닫히면 0을 반환합니다. 그렇지 않으면 SOCKET_ERROR 값이 반환되고 를 호출하여 `GetLastError`특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수가 잘못되었습니다: *lpSockAddr* 버퍼가 너무 작아서 피어 주소를 수용할 수 없습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEINVAL 소켓이 바인딩되지 `Bind`않았습니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다(SOCK_STREAM 만).

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 0 `ReceiveFrom` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 `ReceiveFrom` 작업이 차단됩니다.

- WSAEMSGSIZE 데이터그램이 너무 커서 지정된 버퍼에 맞지 않고 잘렸습니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

### <a name="remarks"></a>설명

이 함수는 (연결된) 소켓에서 들어오는 데이터를 읽고 데이터가 전송된 주소를 캡처하는 데 사용됩니다.

IPv6 주소를 처리하려면 [CAsyncSocket::ReceiveFromEx](#receivefromex)를 사용합니다.

SOCK_STREAM 형식의 소켓의 경우 제공된 버퍼 크기까지 현재 사용할 수 있는 많은 정보가 반환됩니다. 소켓이 대역 외 데이터(소켓 옵션 SO_OOBINLINE)의 인라인 수신을 위해 구성되었으며 대역 외 데이터가 읽지 않은 경우 대역 외 데이터만 반환됩니다. 응용 프로그램은 이 `IOCtlSIOCATMARK` 옵션을 `OnOutOfBandData` 사용하거나 대역 외 데이터를 더 이상 읽을 수 있는지 여부를 결정할 수 있습니다. SOCK_STREAM 소켓에 대해 *lpSockAddr* 및 *lpSockAddrLen* 매개 변수는 무시됩니다.

데이터그램 소켓의 경우 첫 번째 큐에 대기된 데이터그램에서 제공된 버퍼 크기까지 데이터가 추출됩니다. 데이터그램이 제공된 버퍼보다 큰 경우 버퍼는 메시지의 첫 번째 부분으로 채워지고 초과 `ReceiveFrom` 데이터가 손실되고 WSAEMSGSIZE로 설정된 오류 코드로 SOCKET_ERROR 값을 반환합니다.

*lpSockAddr가* 0이 아닌 경우 소켓이 SOCK_DGRAM 형식인 경우 데이터를 보낸 소켓의 네트워크 주소가 해당 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조로 복사됩니다. *lpSockAddrLen에* 의해 가리키는 값은이 구조의 크기로 초기화되고 반환시 수정되어 거기에 저장된 주소의 실제 크기를 나타냅니다. 소켓에서 들어오는 데이터를 사용할 수 없는 `ReceiveFrom` 경우 소켓이 비차단되지 않는 한 호출은 데이터가 도착할 때까지 기다립니다. 이 경우 SOCKET_ERROR 값은 WSAEWOULDBLOCK으로 설정된 오류 코드와 함께 반환됩니다. `OnReceive` 콜백을 사용하여 더 많은 데이터가 도착하는 시기를 결정할 수 있습니다.

소켓이 SOCK_STREAM 유형이고 원격 측이 연결을 정상적으로 종료한 `ReceiveFrom` 경우 0바이트가 수신된 즉시 완료됩니다.

## <a name="casyncsocketreceivefromex"></a><a name="receivefromex"></a>CAsync 소켓::수신FromEx

이 멤버 함수를 호출하여 데이터그램을 수신하고 소스 주소를 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조 또는 *rSocketAddress(IPv6* 주소 처리)에 저장합니다.

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대한 버퍼입니다.

*n부플렌*<br/>
바이트로 *lpBuf의* 길이입니다.

*r소켓 주소*<br/>
점선 `CString` 번호 IP 주소를 받는 개체에 대한 참조입니다.

*r소켓 포트*<br/>
포트를 저장하는 UINT를 참조합니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_PEEK 들어오는 데이터를 엿볼 수 있습니다. 데이터는 버퍼에 복사되지만 입력 큐에서 제거되지 않습니다.

- 대역 외 데이터를 MSG_OOB 처리합니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `ReceiveFromEx` 수신된 바이트 수를 반환합니다. 연결이 닫히면 0을 반환합니다. 그렇지 않으면 SOCKET_ERROR 값이 반환되고 를 호출하여 `GetLastError`특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpSockAddrLen* 인수가 잘못되었습니다: *lpSockAddr* 버퍼가 너무 작아서 피어 주소를 수용할 수 없습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEINVAL 소켓이 바인딩되지 `Bind`않았습니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다(SOCK_STREAM 만).

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 0 `ReceiveFromEx` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 `ReceiveFromEx` 작업이 차단됩니다.

- WSAEMSGSIZE 데이터그램이 너무 커서 지정된 버퍼에 맞지 않고 잘렸습니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

### <a name="remarks"></a>설명

이 함수는 (연결된) 소켓에서 들어오는 데이터를 읽고 데이터가 전송된 주소를 캡처하는 데 사용됩니다.

이 함수는 이전 프로토콜뿐만 아니라 IPv6 주소를 처리한다는 점을 제외하면 [CAsyncSocket::ReceiveFrom와](#receivefrom) 동일합니다.

SOCK_STREAM 형식의 소켓의 경우 제공된 버퍼 크기까지 현재 사용할 수 있는 많은 정보가 반환됩니다. 소켓이 대역 외 데이터(소켓 옵션 SO_OOBINLINE)의 인라인 수신을 위해 구성되었으며 대역 외 데이터가 읽지 않은 경우 대역 외 데이터만 반환됩니다. 응용 프로그램은 이 `IOCtlSIOCATMARK` 옵션을 `OnOutOfBandData` 사용하거나 대역 외 데이터를 더 이상 읽을 수 있는지 여부를 결정할 수 있습니다. SOCK_STREAM 소켓에 대해 *lpSockAddr* 및 *lpSockAddrLen* 매개 변수는 무시됩니다.

데이터그램 소켓의 경우 첫 번째 큐에 대기된 데이터그램에서 제공된 버퍼 크기까지 데이터가 추출됩니다. 데이터그램이 제공된 버퍼보다 큰 경우 버퍼는 메시지의 첫 번째 부분으로 채워지고 초과 `ReceiveFromEx` 데이터가 손실되고 WSAEMSGSIZE로 설정된 오류 코드로 SOCKET_ERROR 값을 반환합니다.

*lpSockAddr가* 0이 아닌 경우 소켓이 SOCK_DGRAM 형식인 경우 데이터를 보낸 소켓의 네트워크 주소가 해당 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조로 복사됩니다. *lpSockAddrLen에* 의해 가리키는 값은이 구조의 크기로 초기화되고 반환시 수정되어 거기에 저장된 주소의 실제 크기를 나타냅니다. 소켓에서 들어오는 데이터를 사용할 수 없는 `ReceiveFromEx` 경우 소켓이 비차단되지 않는 한 호출은 데이터가 도착할 때까지 기다립니다. 이 경우 SOCKET_ERROR 값은 WSAEWOULDBLOCK으로 설정된 오류 코드와 함께 반환됩니다. `OnReceive` 콜백을 사용하여 더 많은 데이터가 도착하는 시기를 결정할 수 있습니다.

소켓이 SOCK_STREAM 유형이고 원격 측이 연결을 정상적으로 종료한 `ReceiveFromEx` 경우 0바이트가 수신된 즉시 완료됩니다.

## <a name="casyncsocketsend"></a><a name="send"></a>CAsync 소켓::보내기

연결된 소켓에 데이터를 보내려면 이 멤버 함수를 호출합니다.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터를 포함하는 버퍼입니다.

*n부플렌*<br/>
*lpBuf의* 데이터 길이(바이트)입니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_DONTROUTE 데이터가 라우팅대상이 되어서는 안 되도록 지정합니다. Windows 소켓 공급자는 이 플래그를 무시하도록 선택할 수 있습니다.

- MSG_OOB 대역 외 데이터(SOCK_STREAM만)를 보냅니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `Send` 전송된 총 문자 수를 반환합니다. *(nBufLen으로*표시된 숫자보다 적을 수 있습니다.) 그렇지 않으면 SOCKET_ERROR 값이 반환되고 [GetLastError](#getlasterror)를 호출하여 특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEACCES 요청된 주소가 브로드캐스트 주소이지만 적절한 플래그가 설정되지 않았습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEFAULT *lpBuf* 인수가 사용자 주소 공간의 유효한 부분에 없습니다.

- WSAENETRESET Windows 소켓 구현에서 연결을 삭제했기 때문에 연결을 재설정해야 합니다.

- WSAENOBUFS Windows 소켓 구현은 버퍼 교착 상태를 보고합니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 1 `Send` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 요청된 작업이 차단됩니다.

- WSAEMSGSIZE 소켓은 SOCK_DGRAM 유형이며 데이터그램은 Windows 소켓 구현에서 지원하는 최대값보다 큽합니다.

- WSAEINVAL 소켓이 바인딩되지 `Bind`않았습니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

### <a name="remarks"></a>설명

`Send`은 연결된 스트림 또는 데이터그램 소켓에 나가는 데이터를 작성하는 데 사용됩니다. 데이터그램 소켓의 경우 [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 구조의 `iMaxUdpDg` 요소에 의해 반환되는 기본 서브넷의 최대 IP 패킷 크기를 초과하지 `AfxSocketInit`않도록 주의해야 합니다. 데이터가 기본 프로토콜을 원자적으로 전달하기에 너무 길면 WSAEMSGSIZE 오류가 `GetLastError`반환되고 데이터가 전송되지 않습니다.

데이터그램 소켓의 경우 a를 `Send` 성공적으로 완료해도 데이터가 성공적으로 전달되었음을 나타내지는 않습니다.

SOCK_STREAM `CAsyncSocket` 형식의 개체에서 작성된 바이트 수는 로컬 호스트와 외부 호스트의 버퍼 가용성에 따라 1에서 요청된 길이 사이일 수 있습니다.

### <a name="example"></a>예제

  [CAsyncSocket::OnSend](#onsend)에 대한 예제를 참조하십시오.

## <a name="casyncsocketsendto"></a><a name="sendto"></a>CAsync소켓::SendTo

이 멤버 함수를 호출하여 특정 대상으로 데이터를 보냅니다.

```
int SendTo(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);

int SendTo(
    const void* lpBuf,
    int nBufLen,
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터를 포함하는 버퍼입니다.

*n부플렌*<br/>
*lpBuf의* 데이터 길이(바이트)입니다.

*n호스트포트*<br/>
소켓 응용 프로그램을 식별하는 포트입니다.

*lpszHostAddress*<br/>
이 개체가 연결된 소켓의 네트워크 주소: "ftp.microsoft.com"와 같은 컴퓨터 이름 또는 "128.56.22.8"과 같은 점선 번호입니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_DONTROUTE 데이터가 라우팅대상이 되어서는 안 되도록 지정합니다. Windows 소켓 공급자는 이 플래그를 무시하도록 선택할 수 있습니다.

- MSG_OOB 대역 외 데이터(SOCK_STREAM만)를 보냅니다.

*lpSockAddr*<br/>
대상 소켓의 주소를 포함하는 [SOCKADDR](/windows/win32/winsock/sockaddr-2) 구조에 대한 포인터입니다.

*n삭아드렌*<br/>
*lpSockAddr의* 주소 길이입니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `SendTo` 전송된 총 문자 수를 반환합니다. *(nBufLen으로*표시된 숫자보다 적을 수 있습니다.) 그렇지 않으면 SOCKET_ERROR 값이 반환되고 [GetLastError](#getlasterror)를 호출하여 특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEACCES 요청된 주소가 브로드캐스트 주소이지만 적절한 플래그가 설정되지 않았습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEFAULT *lpBuf* 또는 *lpSockAddr* 매개 변수는 사용자 주소 공간의 일부가 아니거나 *lpSockAddr* 인수가 너무 작습니다(SOCKADDR 구조의 크기보다 작음). [SOCKADDR](/windows/win32/winsock/sockaddr-2)

- WSAEINVAL 호스트 이름이 잘못되었습니다.

- WSAENETRESET Windows 소켓 구현에서 연결을 삭제했기 때문에 연결을 재설정해야 합니다.

- WSAENOBUFS Windows 소켓 구현은 버퍼 교착 상태를 보고합니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다(SOCK_STREAM 만).

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 1 `SendTo` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 요청된 작업이 차단됩니다.

- WSAEMSGSIZE 소켓은 SOCK_DGRAM 유형이며 데이터그램은 Windows 소켓 구현에서 지원하는 최대값보다 큽합니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

- WSAEADDRNOTAVAIL 지정된 주소를 로컬 컴퓨터에서 사용할 수 없습니다.

- 지정된 패밀리의 WSAEAFNOSUPPORT 주소는 이 소켓과 함께 사용할 수 없습니다.

- WSAEDADDRREQ 대상 주소가 필요합니다.

- WSAENETUNREACH 현재 이 호스트에서 네트워크에 연결할 수 없습니다.

### <a name="remarks"></a>설명

`SendTo`데이터그램 또는 스트림 소켓에 사용되며 소켓에 나가는 데이터를 작성하는 데 사용됩니다. 데이터그램 소켓의 경우 `iMaxUdpDg` [AfxSocketInit에서](../../mfc/reference/application-information-and-management.md#afxsocketinit)작성한 [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 구조의 요소에 의해 제공되는 기본 서브넷의 최대 IP 패킷 크기를 초과하지 않도록 주의해야 합니다. 데이터가 너무 길어 기본 프로토콜을 원자적으로 전달하지 못하면 WSAEMSGSIZE 오류가 반환되고 데이터가 전송되지 않습니다.

a를 `SendTo` 성공적으로 완료했다고 해서 데이터가 성공적으로 전달되었음을 나타내는 것은 아닙니다.

`SendTo`SOCK_DGRAM 소켓에서만 *사용되며, lpSockAddr* 매개 변수로 식별된 특정 소켓에 데이터그램을 보냅니다.

브로드캐스트를 SOCK_DGRAM 만 보내려면 *lpSockAddr* 매개 변수의 주소는 INADDR_BROADCAST 특수 IP 주소(Windows 소켓 헤더 파일 WINSOCK에 정의됨)를 사용하여 구성해야 합니다. H) 의도된 포트 번호와 함께. 또는 *lpszHostAddress* 매개 변수가 NULL이면 소켓이 브로드캐스트용으로 구성됩니다. 일반적으로 브로드캐스트 데이터그램이 조각화가 발생할 수 있는 크기를 초과하는 것은 바람직하지 않으며, 이는 데이터그램의 데이터 부분(헤더 제외)이 512바이트를 초과해서는 안 된다는 것을 의미합니다.

IPv6 주소를 처리하려면 [CAsyncSocket::SendToEx](#sendtoex)를 사용합니다.

## <a name="casyncsocketsendtoex"></a><a name="sendtoex"></a>CAsync소켓::센드토엑스

이 멤버 함수를 호출하여 특정 대상(IPv6 주소 처리)으로 데이터를 보냅니다.

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터를 포함하는 버퍼입니다.

*n부플렌*<br/>
*lpBuf의* 데이터 길이(바이트)입니다.

*n호스트포트*<br/>
소켓 응용 프로그램을 식별하는 포트입니다.

*lpszHostAddress*<br/>
이 개체가 연결된 소켓의 네트워크 주소: "ftp.microsoft.com"와 같은 컴퓨터 이름 또는 "128.56.22.8"과 같은 점선 번호입니다.

*nFlags*<br/>
호출이 이루어지는 방식을 지정합니다. 이 함수의 의미 체계는 소켓 옵션과 *nFlags* 매개 변수에 의해 결정됩니다. 후자는 다음 값 중 어느 값을 C++ **OR** 연산자와 결합하여 생성됩니다.

- MSG_DONTROUTE 데이터가 라우팅대상이 되어서는 안 되도록 지정합니다. Windows 소켓 공급자는 이 플래그를 무시하도록 선택할 수 있습니다.

- MSG_OOB 대역 외 데이터(SOCK_STREAM만)를 보냅니다.

### <a name="return-value"></a>Return Value

오류가 발생하지 않으면 `SendToEx` 전송된 총 문자 수를 반환합니다. *(nBufLen으로*표시된 숫자보다 적을 수 있습니다.) 그렇지 않으면 SOCKET_ERROR 값이 반환되고 [GetLastError](#getlasterror)를 호출하여 특정 오류 코드를 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEACCES 요청된 주소가 브로드캐스트 주소이지만 적절한 플래그가 설정되지 않았습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEFAULT *lpBuf* 또는 *lpSockAddr* 매개 변수는 사용자 주소 공간의 일부가 아니거나 *lpSockAddr* 인수가 너무 작습니다(SOCKADDR 구조의 크기보다 작음). [SOCKADDR](/windows/win32/winsock/sockaddr-2)

- WSAEINVAL 호스트 이름이 잘못되었습니다.

- WSAENETRESET Windows 소켓 구현에서 연결을 삭제했기 때문에 연결을 재설정해야 합니다.

- WSAENOBUFS Windows 소켓 구현은 버퍼 교착 상태를 보고합니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다(SOCK_STREAM 만).

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정되었지만 소켓이 SOCK_STREAM 형식이 아닙니다.

- WSAESHUTDOWN 소켓이 종료되었습니다. *nHow가* 1 `SendToEx` 또는 2로 `ShutDown` 설정된 경우 호출된 후에는 소켓을 호출할 수 없습니다.

- WSAEWOULDBLOCK 소켓은 비차단으로 표시되고 요청된 작업이 차단됩니다.

- WSAEMSGSIZE 소켓은 SOCK_DGRAM 유형이며 데이터그램은 Windows 소켓 구현에서 지원하는 최대값보다 큽합니다.

- WSAECONNABORTED 가상 회로는 시간 시간 또는 기타 오류로 인해 중단되었습니다.

- WSAECONNRESET 가상 회로가 원격 측에 의해 재설정되었습니다.

- WSAEADDRNOTAVAIL 지정된 주소를 로컬 컴퓨터에서 사용할 수 없습니다.

- 지정된 패밀리의 WSAEAFNOSUPPORT 주소는 이 소켓과 함께 사용할 수 없습니다.

- WSAEDADDRREQ 대상 주소가 필요합니다.

- WSAENETUNREACH 현재 이 호스트에서 네트워크에 연결할 수 없습니다.

### <a name="remarks"></a>설명

이 메서드는 [CAsyncSocket::SendToIPv6](#sendto) 주소와 이전 프로토콜을 처리한다는 점을 제외하면 동일합니다.

`SendToEx`데이터그램 또는 스트림 소켓에 사용되며 소켓에 나가는 데이터를 작성하는 데 사용됩니다. 데이터그램 소켓의 경우 `iMaxUdpDg` [AfxSocketInit에서](../../mfc/reference/application-information-and-management.md#afxsocketinit)작성한 [WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata) 구조의 요소에 의해 제공되는 기본 서브넷의 최대 IP 패킷 크기를 초과하지 않도록 주의해야 합니다. 데이터가 너무 길어 기본 프로토콜을 원자적으로 전달하지 못하면 WSAEMSGSIZE 오류가 반환되고 데이터가 전송되지 않습니다.

a를 `SendToEx` 성공적으로 완료했다고 해서 데이터가 성공적으로 전달되었음을 나타내는 것은 아닙니다.

`SendToEx`SOCK_DGRAM 소켓에서만 *사용되며, lpSockAddr* 매개 변수로 식별된 특정 소켓에 데이터그램을 보냅니다.

브로드캐스트를 SOCK_DGRAM 만 보내려면 *lpSockAddr* 매개 변수의 주소는 INADDR_BROADCAST 특수 IP 주소(Windows 소켓 헤더 파일 WINSOCK에 정의됨)를 사용하여 구성해야 합니다. H) 의도된 포트 번호와 함께. 또는 *lpszHostAddress* 매개 변수가 NULL이면 소켓이 브로드캐스트용으로 구성됩니다. 일반적으로 브로드캐스트 데이터그램이 조각화가 발생할 수 있는 크기를 초과하는 것은 바람직하지 않으며, 이는 데이터그램의 데이터 부분(헤더 제외)이 512바이트를 초과해서는 안 된다는 것을 의미합니다.

## <a name="casyncsocketsetsockopt"></a><a name="setsockopt"></a>CAsync소켓::SetSockOpt

이 멤버 함수를 호출하여 소켓 옵션을 설정합니다.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>매개 변수

*n옵션 이름*<br/>
값을 설정할 소켓 옵션입니다.

*lp옵션값*<br/>
요청된 옵션의 값이 제공되는 버퍼에 대한 포인터입니다.

*n옵션렌*<br/>
*바이트의 lpOptionValue* 버퍼의 크기입니다.

*n레벨*<br/>
옵션이 정의된 수준입니다. 지원되는 수준은 SOL_SOCKET 및 IPPROTO_TCP.

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEFAULT *lpOptionValue* 프로세스 주소 공간의 유효한 부분에 없습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAEInVAL *nLevel이* 잘못되었거나 *lpOptionValue의* 정보가 유효하지 않습니다.

- WSAENETRESET 연결이 설정되면 시간이 SO_KEEPALIVE.

- WSAENOPROTOOPT 이 옵션은 알 수 없거나 지원되지 않습니다. 특히 SO_BROADCAST 형식 SOCK_STREAM 소켓에서는 지원되지 않지만 SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER 및 SO_OOBINLINE 형식 SOCK_DGRAM 소켓에서는 지원되지 않습니다.

- SO_KEEPALIVE 설정되면 WSAENOTCONN 연결이 재설정되었습니다.

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

`SetSockOpt`모든 상태의 소켓과 연결된 소켓 옵션의 현재 값을 설정합니다. 옵션은 여러 프로토콜 수준에 존재할 수 있지만 이 사양은 최상위 "소켓" 수준에 있는 옵션만 정의합니다. 옵션은 일반 데이터 스트림에서 신속한 데이터를 수신하는지 여부, 소켓에서 브로드캐스트 메시지를 보낼 수 있는지 여부 등과 같은 소켓 작업에 영향을 미칩니다.

소켓 옵션에는 기능 또는 동작을 사용하거나 사용하지 않도록 설정하는 부울 옵션과 정수 값 또는 구조가 필요한 옵션의 두 가지 유형이 있습니다. 부울 옵션을 활성화하려면 *lpOptionValue가* 영하지 않은 정수를 가리킵니다. 옵션을 비활성화하려면 *lpOptionValue는* 0과 같은 정수를 가리킵니다. *nOptionLen* 부울 `sizeof(BOOL)` 옵션에 대 한 동일 해야 합니다. 다른 옵션의 경우 *lpOptionValue는* 옵션에 대해 원하는 값을 포함하는 정수 또는 구조를 가리키고 *nOptionLen은* 정수 또는 구조의 길이입니다.

SO_LINGER 보내지 않은 데이터가 소켓에 큐에 대기하고 `Close` 소켓을 닫기 위해 함수가 호출될 때 수행된 작업을 제어합니다.

기본적으로 소켓은 이미 사용 중인 로컬 주소에 바인딩할 수 [없습니다(바인드](#bind)참조). 그러나 경우에 따라 이러한 방식으로 주소를 "재사용"하는 것이 바람직할 수 있습니다. 모든 연결은 로컬 주소와 원격 주소의 조합으로 고유하게 식별되므로 원격 주소가 다른 한 두 개의 소켓이 동일한 로컬 주소에 바인딩되는 데 문제가 없습니다.

원하는 주소가 다른 소켓에서 `Bind` 이미 사용 중이므로 소켓에 대한 호출을 허용하지 않아야 한다는 Windows 소켓 구현을 알리려면 응용 프로그램은 `Bind` 호출을 실행하기 전에 소켓에 대한 SO_REUSEADDR 소켓 옵션을 설정해야 합니다. 이 옵션은 `Bind` 호출 시에만 해석됩니다: 따라서 기존 주소에 바인딩되지 않는 소켓에서 옵션을 설정하고 `Bind` 호출 후 옵션을 설정하거나 재설정하는 것은 이 소켓이나 다른 소켓에 영향을 미치지 않습니다.

응용 프로그램은 Windows 소켓 구현에서 SO_KEEPALIVE 소켓 옵션을 켜서 TCP(전송 제어 프로토콜) 연결에서 "유지"패킷을 사용하도록 요청할 수 있습니다. Windows 소켓 구현은 keep-alives 사용을 지원할 필요가 없습니다. "keep-alives"의 결과로 연결이 끊어지면 오류 코드 WSAENETRESET이 소켓에서 진행 중인 모든 호출로 반환되고 WSAENOTCONN에서 후속 호출이 실패합니다.

TCP_NODELAY 옵션은 Nagle 알고리즘을 사용하지 않도록 설정합니다. Nagle 알고리즘은 전체 크기 패킷을 보낼 수 있을 때까지 승인되지 않은 전송 데이터를 버퍼링하여 호스트가 보내는 작은 패킷 수를 줄이는 데 사용됩니다. 그러나 일부 응용 프로그램의 경우 이 알고리즘은 성능을 저하시킬 수 있으며 TCP_NODELAY 사용하여 해제할 수 있습니다. TCP_NODELAY 설정하면 네트워크 성능에 심각한 부정적인 영향을 미칠 수 있으므로 응용 프로그램 작성기는 TCP_NODELAY 설정해서는 안 됩니다. TCP_NODELAY 레벨 IPPROTO_TCP 사용하는 유일한 지원되는 소켓 옵션입니다. 다른 모든 옵션은 레벨 SOL_SOCKET 사용합니다.

일부 Windows 소켓 구현은 응용 프로그램에서 SO_DEBUG 옵션을 설정한 경우 출력 디버그 정보를 제공합니다.

다음 옵션은 에 `SetSockOpt`대해 지원됩니다. Type은 *lpOptionValue*에서 해결되는 데이터 유형을 식별합니다.

|값|Type|의미|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|소켓에서 브로드캐스트 메시지를 전송할 수 있습니다.|
|SO_DEBUG|BOOL|디버깅 정보를 기록합니다.|
|SO_DONTLINGER|BOOL|보내지 않은 `Close` 데이터가 전송될 때까지 기다리는 것을 차단하지 마십시오. 이 옵션을 설정하면 SO_LINGER `l_onoff` 0으로 설정하면 됩니다.|
|SO_DONTROUTE|BOOL|라우팅 하지 마십시오: 인터페이스에 직접 보냅니다.|
|SO_KEEPALIVE|BOOL|keep-alives를 보내십시오.|
|SO_LINGER|`struct LINGER`|보내지 `Close` 않은 데이터가 있는 경우 계속 남아 있습니다.|
|SO_OOBINLINE|BOOL|일반 데이터 스트림에서 대역 외 데이터를 수신합니다.|
|SO_RCVBUF|**int**|수신에 대한 버퍼 크기를 지정합니다.|
|SO_REUSEADDR|BOOL|소켓을 이미 사용 중인 주소에 바인딩할 수 있습니다. (바인딩 [Bind](#bind)참조.)|
|SO_SNDBUF|**int**|송신에 대한 버퍼 크기를 지정합니다.|
|Tcp_nodelay|BOOL|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|

지원되지 않는 버클리 소프트웨어 배포(BSD) 옵션은 다음과 같습니다. `SetSockOpt`

|값|Type|의미|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|소켓이 대기 중입니다.|
|SO_ERROR|**int**|오류 상태를 얻고 지우십시오.|
|SO_RCVLOWAT|**int**|낮은 워터 마크를 받습니다.|
|SO_RCVTIMEO|**int**|수신 시간 제한|
|SO_SNDLOWAT|**int**|낮은 워터 마크를 보냅니다.|
|SO_SNDTIMEO|**int**|시간 시간을 보냅니다.|
|SO_TYPE|**int**|소켓의 유형입니다.|
|IP_OPTIONS||IP 헤더의 옵션 필드를 설정합니다.|

## <a name="casyncsocketshutdown"></a><a name="shutdown"></a>CAsync소켓::종료

이 멤버 함수를 호출하여 소켓에서 송신, 수신 또는 둘 다 비활성화합니다.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>매개 변수

*Nhow*<br/>
다음 을 사용하여 더 이상 허용되지 않는 작업 유형을 설명하는 플래그입니다.

- **수신 = 0**

- **전송 = 1**

- **둘 다 = 2**

### <a name="return-value"></a>Return Value

함수가 성공하면 0이 아닙니다. 그렇지 않으면 0이고 특정 오류 코드는 [GetLastError](#getlasterror)를 호출하여 검색할 수 있습니다. 이 멤버 함수에는 다음 오류가 적용됩니다.

- WSANOTINITIALISD 성공적인 [AfxSocketInit이](../../mfc/reference/application-information-and-management.md#afxsocketinit) API를 사용하기 전에 발생해야합니다.

- WSAENETDOWN Windows 소켓 구현에서 네트워크 하위 시스템이 실패한 것을 발견했습니다.

- WSAEInval *nHow가* 잘못되었습니다.

- WSAEINPROGRESS 차단 윈도우 소켓 작업이 진행 중입니다.

- WSAENOTCONN 소켓이 연결되어 있지 않습니다(SOCK_STREAM 만).

- WSAENOTSOCK 설명자는 소켓이 아닙니다.

### <a name="remarks"></a>설명

`ShutDown`수신, 전송 또는 둘 다 비활성화하는 모든 유형의 소켓에 사용됩니다. *nHow가* 0이면 소켓의 후속 수신이 허용되지 않습니다. 이는 하위 프로토콜 계층에는 영향을 주지 않습니다.

TCP(전송 제어 프로토콜)의 경우 TCP 창이 변경되지 않으며 창이 소진될 때까지 들어오는 데이터가 허용되지만 승인되지는 않습니다. UDP(사용자 데이터그램 프로토콜)의 경우 들어오는 데이터그램이 수락되고 큐에 대기됩니다. 어떤 경우에도 ICMP 오류 패킷이 생성되지 않습니다. *nHow가* 1이면 후속 송신이 허용되지 않습니다. TCP 소켓의 경우 FIN이 전송됩니다. *nHow* to 2로 설정하면 위에서 설명한 대로 송신및 수신을 모두 비활성화할 수 없습니다.

소켓을 `ShutDown` 닫지 않으며 소켓에 연결된 리소스가 호출될 `Close` 때까지 해제되지 않습니다. 응용 프로그램은 종료된 후 소켓을 다시 사용할 수 있는 것에 의존해서는 안 됩니다. 특히 Windows 소켓 구현은 이러한 소켓의 `Connect` 사용을 지원할 필요가 없습니다.

### <a name="example"></a>예제

  [CAsyncSocket::OnReceive](#onreceive)에 대한 예제를 참조하십시오.

## <a name="casyncsocketsocket"></a><a name="socket"></a>CASync소켓::소켓

소켓 핸들을 할당합니다.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>매개 변수

*n소켓 유형*<br/>
또는 `SOCK_DGRAM`를 `SOCK_STREAM` 지정합니다.

*l이벤트*<br/>
응용 프로그램에 관심이 있는 네트워크 이벤트의 조합을 지정하는 비트 마스크입니다.

- `FD_READ`: 독서 준비 에 대한 알림을 받고 싶습니다.

- `FD_WRITE`: 작성 준비 에 대한 알림을 받고 싶습니다.

- `FD_OOB`: 대역 외 데이터의 도착 알림을 받고 싶습니다.

- `FD_ACCEPT`: 들어오는 연결에 대한 알림을 받고 싶습니다.

- `FD_CONNECT`: 완료된 연결 알림을 받고 싶습니다.

- `FD_CLOSE`: 소켓 폐쇄 알림을 받고 싶습니다.

*n 프로토콜 유형*<br/>
표시된 주소 패밀리에 특정한 소켓과 함께 사용할 프로토콜입니다.

*n주소 형식*<br/>
패밀리 사양을 해결합니다.

### <a name="return-value"></a>Return Value

성공하면 `TRUE`를 반환하고 실패하면 `FALSE`를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 소켓 핸들을 할당합니다. [CAsyncSocket::바인딩을](#bind) 호출하지 않으므로 지정된 주소에 소켓을 바인딩하려면 `Bind` 나중에 호출하여 지정된 주소에 소켓을 바인딩해야 합니다. [CAsyncSocket::SetSockOpt를](#setsockopt) 사용하여 바인딩되기 전에 소켓 옵션을 설정할 수 있습니다.

## <a name="see-also"></a>참조

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[C소켓 클래스](../../mfc/reference/csocket-class.md)<br/>
[C소켓 파일 클래스](../../mfc/reference/csocketfile-class.md)
