---
title: C소켓 파일 클래스
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 83810a05925e5c8302240b61d95c131fdd78b426
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318167"
---
# <a name="csocketfile-class"></a>C소켓 파일 클래스

Windows 소켓을 통해 네트워크에서 데이터를 보내고 받는 데 사용되는 `CFile` 개체입니다.

## <a name="syntax"></a>구문

```
class CSocketFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C소켓 파일::C소켓 파일](#csocketfile)|`CSocketFile` 개체를 생성합니다.|

## <a name="remarks"></a>설명

이 목적을 `CSocketFile` 위해 객체를 객체에 `CSocket` 첨부할 수 있습니다. 또한 일반적으로 개체를 `CSocketFile` `CArchive` 개체에 연결하여 MFC 직렬화를 사용하여 데이터 송수신을 단순화할 수도 있습니다.

데이터를 직렬화(전송)하기 위해 개체에 데이터를 `CSocketFile` 쓰기 위해 멤버 함수를 `CSocket` 호출하는 아카이브에 삽입합니다. 데이터를 역직렬화(수신)하려면 아카이브에서 추출합니다. 이렇게 하면 아카이브가 `CSocketFile` 멤버 함수를 호출하여 `CSocket` 개체에서 데이터를 읽습니다.

> [!TIP]
> 여기에 `CSocketFile` 설명된 대로 사용하는 것 외에도 기본 클래스와 마찬가지로 독립 실행형 파일 개체로 `CFile`사용할 수 있습니다. 모든 아카이브 `CSocketFile` 기반 MFC 직렬화 기능에서도 사용할 수 있습니다. 모든 `CSocketFile` `CFile`기능을 지원하지 는 않으므로 일부 기본 MFC serialize 함수는 `CSocketFile`와 호환되지 않습니다. 이것은 특히 클래스의 `CEditView` 사실이다. 다음을 `CEditView` 사용하여 `CArchive` `CSocketFile` `CEditView::SerializeRaw`개체에 연결된 개체를 통해 데이터를 직렬화하려고 시도해서는 안 됩니다. 대신 `CEditView::Serialize` 사용합니다. 함수는 `SerializeRaw` 파일 개체에 없는 와 `Seek` `CSocketFile` 같은 함수를 갖습니다.

와 함께 `CArchive` `CSocketFile` `CSocket`사용할 때 요청된 바이트 `CSocket::Receive` 양을 기다리는 루프(by `PumpMessages(FD_READ)`by)가 들어오는 상황이 발생할 수 있습니다. 이는 Windows 소켓에서 FD_READ 알림당 하나의 recv `CSocketFile` 호출만 허용하지만 `CSocket` FD_READ 대해 여러 recv 호출을 허용하기 때문입니다. 읽을 데이터가 없을 때 FD_READ 받으면 응용 프로그램이 중단됩니다. 다른 FD_READ 얻지 못하면 응용 프로그램이 소켓을 통해 통신을 중지합니다.

이 문제를 다음과 같이 해결할 수 있습니다. 소켓 `OnReceive` 클래스의 메서드에서 소켓에서 읽을 `Serialize` 것으로 예상되는 데이터가 하나의 TCP 패킷(네트워크 미디어의 최대 전송 단위( 일반적으로 최소 1096바이트)을 초과할 때 메시지 클래스의 메서드를 호출하기 전에 호출합니다. `CAsyncSocket::IOCtl(FIONREAD, ...)` 사용 가능한 데이터의 크기가 필요 하지 않은 경우 모든 데이터가 수신될 때까지 기다린 다음 읽기 작업을 시작합니다.

다음 `m_dwExpected` 예제에서는 사용자가 수신할 것으로 예상되는 대략적인 바이트 수입니다. 코드의 다른 위치에 선언한다고 가정합니다.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

자세한 내용은 MFC , Windows [소켓의 Windows 소켓:](../../mfc/windows-sockets-in-mfc.md) [아카이브가 있는 소켓 사용](../../mfc/windows-sockets-using-sockets-with-archives.md)및 Windows 소켓 2 [API를](/windows/win32/WinSock/windows-sockets-start-page-2)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a>C소켓 파일::C소켓 파일

`CSocketFile` 개체를 생성합니다.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>매개 변수

*p소켓*<br/>
개체에 연결할 소켓입니다. `CSocketFile`

*b아카이브호환*<br/>
파일 개체가 개체와 함께 사용할지 `CArchive` 여부를 지정합니다. 독립 실행형 개체와 마찬가지로 `CSocketFile` 독립 실행형 `CFile` 방식으로 개체를 사용하려는 경우에만 FALSE를 전달합니다. 이 플래그는 `CArchive` `CSocketFile` 개체에 연결된 개체가 읽기 위해 버퍼를 관리하는 방법을 변경합니다.

### <a name="remarks"></a>설명

개체가 범위를 벗어나거나 삭제될 때 개체의 소멸자는 소켓 개체에서 자신을 분리합니다.

> [!NOTE]
> A는 `CSocketFile` `CArchive` 개체가 없는 (제한된) 파일로도 사용할 수 있습니다. 기본적으로 `CSocketFile` 생성자의 *bArchiveCompatible* 매개 변수는 TRUE입니다. 이렇게 하면 파일 개체가 아카이브와 함께 사용할 수 있도록 지정됩니다. 아카이브없이 파일 개체를 사용하려면 *bArchiveCompatible* 매개 변수에서 FALSE를 전달합니다.

"아카이브 호환" 모드에서 개체는 `CSocketFile` 더 나은 성능을 제공하고 "교착 상태"의 위험을 줄입니다. 교착 상태는 송신 소켓과 수신 소켓이 서로 대기하거나 공통 리소스를 기다리는 경우에 발생합니다. 개체가 `CFile` 개체와 `CArchive` 함께 `CSocketFile` 작업하는 경우 이 상황이 발생할 수 있습니다. 을 `CFile`사용하면 요청한 바이트보다 적은 바이트를 수신하는 경우 파일의 끝에 도달했다고 가정할 수 있습니다.

그러나 `CSocketFile`을 사용하면 데이터는 메시지 기반입니다. 버퍼에 여러 메시지가 포함될 수 있으므로 요청된 바이트 수보다 적게 받는 것은 파일끝을 의미하지 않습니다. 이 경우 응용 프로그램은 을 사용 `CFile`하 여 차단 하지 않습니다 및 버퍼가 비어 있을 때까지 버퍼에서 메시지를 계속 읽을 수 있습니다. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) 함수는 이러한 경우 아카이브 버퍼의 상태를 모니터링하는 데 유용합니다.

사용 `CSocketFile`방법에 대한 자세한 내용은 Windows 소켓: 아카이브 및 Windows 소켓이 [있는 소켓 사용: 아카이브를](../../mfc/windows-sockets-using-sockets-with-archives.md) [사용하는 소켓 예제](../../mfc/windows-sockets-example-of-sockets-using-archives.md)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsync소켓 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[C소켓 클래스](../../mfc/reference/csocket-class.md)
