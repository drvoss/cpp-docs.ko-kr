---
title: 애플리케이션 디자인 선택
ms.date: 09/12/2019
helpviewer_keywords:
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
ms.openlocfilehash: 89f3e5c108de1cf7b3b73a33a08e2c50b1333c92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374638"
---
# <a name="application-design-choices"></a>애플리케이션 디자인 선택

이 문서에서는 인터넷을 프로그래밍할 때 고려해야 할 몇 가지 디자인 문제에 대해 설명합니다.

이 문서에서 다루는 주제는 다음과 같습니다.

- [인트라넷 대 인터넷](#_core_intranet_versus_internet)

- [클라이언트 또는 서버 응용 프로그램](#_core_client_or_server_application)

- [웹 페이지](#_core_the_web_page)

- [브라우저 또는 독립 실행형 응용 프로그램](#_core_browser_or_standalone)

- [인터넷에서 COM](#_core_com_on_the_internet)

- [클라이언트 데이터 다운로드 서비스](#_core_client_data_download_services)

지금 프로그램 작성을 시작할 준비가 되면 [MFC 응용 프로그램 작성을](../mfc/writing-mfc-applications.md)참조하십시오.

## <a name="intranet-versus-internet"></a><a name="_core_intranet_versus_internet"></a>인트라넷 대 인터넷

많은 응용 프로그램은 인터넷에서 실행되며 브라우저와 인터넷에 액세스할 수 있는 모든 사용자가 액세스할 수 있습니다. 또한 기업은 TCP/IP 프로토콜 및 웹 브라우저를 사용하는 회사 전체 네트워크인 인트라넷을 구현하고 있습니다. 인트라넷은 회사 전체 정보를 쉽게 업그레이드할 수 있는 중앙 소스를 제공합니다. 소프트웨어 업그레이드, 설문조사 제공 및 표 매기기, 고객 지원 및 정보 제공에 사용할 수 있습니다. 다음 표에서는 인터넷과 인트라넷의 기능을 비교합니다.

|인터넷|Intranet|
|--------------|--------------|
|낮은 대역폭|높은 대역폭|
|데이터 및 시스템의 보안 감소|데이터 및 시스템에 대한 제어된 액세스|
|최소한의 콘텐츠 제어|콘텐츠의 높은 제어|

## <a name="client-or-server-application"></a><a name="_core_client_or_server_application"></a>클라이언트 또는 서버 응용 프로그램

응용 프로그램은 클라이언트 컴퓨터 또는 서버 컴퓨터에서 실행할 수 있습니다. 응용 프로그램은 서버에 저장한 다음 인터넷을 통해 다운로드하여 클라이언트 컴퓨터에서 실행할 수도 있습니다. MFC WinInet 클래스는 클라이언트 응용 프로그램에서 파일을 다운로드하는 데 사용됩니다. MFC 및 비동기 모니커 클래스는 파일을 다운로드하고 속성을 제어하는 데 사용됩니다. ActiveX 컨트롤 및 활성 문서에 대한 클래스는 클라이언트 응용 프로그램 및 서버에서 다운로드하여 클라이언트에서 실행되는 응용 프로그램에 사용됩니다.

## <a name="the-web-page-html-active-documents-activex-controls"></a><a name="_core_the_web_page"></a>웹 페이지: HTML, 활성 문서, ActiveX 컨트롤

Microsoft는 웹 페이지에서 콘텐츠를 제공하는 여러 가지 방법을 제공합니다. 웹 페이지는 개체 태그와 같은 표준 HTML 또는 HTML 확장을 사용하여 ActiveX 컨트롤과 같은 동적 콘텐츠를 제공할 수 있습니다.

웹 브라우저는 일반적으로 HTML 페이지를 표시합니다. 활성 문서는 COM 지원 브라우저의 간단한 포인트 앤 클릭 인터페이스에 응용 프로그램의 데이터를 표시할 수도 있습니다. Active 문서 서버는 자체 메뉴와 도구 모음을 사용하여 전체 클라이언트 영역에 문서, 전체 프레임을 표시할 수 있습니다.

작성하는 ActiveX 컨트롤은 서버에서 비동기적으로 다운로드하여 웹 페이지에 표시할 수 있습니다. VBScript와 같은 스크립팅 언어를 사용하여 서버에 정보를 보내기 전에 클라이언트 측 유효성 검사를 수행할 수 있습니다.

## <a name="browser-or-stand-alone-application"></a><a name="_core_browser_or_standalone"></a>브라우저 또는 독립 실행형 응용 프로그램

HTML 페이지에 포함된 ActiveX 컨트롤과 브라우저에서 볼 수 있는 활성 문서 서버를 작성할 수 있습니다. 웹 서버에서 ISAPI 응용 프로그램을 실행하기 위한 요청을 제출하는 버튼이 포함된 HTML 페이지를 작성할 수 있습니다. 브라우저 응용 프로그램을 사용하지 않고 인터넷 프로토콜을 사용하여 파일을 다운로드하고 사용자에게 정보를 표시하는 독립 실행형 응용 프로그램을 작성할 수 있습니다.

## <a name="com-on-the-internet"></a><a name="_core_com_on_the_internet"></a>인터넷에서 COM

ActiveX 컨트롤, 활성 문서 및 비동기 모니커는 모두 COM(구성 요소 개체 모델) 기술을 사용합니다.

ActiveX 컨트롤은 인터넷 사이트의 문서 및 페이지에 동적 콘텐츠를 제공합니다. COM을 사용하면 활성 문서를 사용하여 ActiveX 컨트롤 및 전체 프레임 문서를 작성할 수 있습니다.

비동기 모니커는 데이터를 다운로드하는 증분 또는 점진적 수단을 포함하여 인터넷 환경에서 컨트롤이 잘 수행될 수 있도록 하는 기능을 제공합니다. 또한 컨트롤은 동시에 데이터를 비동기적으로 검색할 수 있는 다른 컨트롤에서도 잘 작동해야 합니다.

## <a name="client-data-download-services"></a><a name="_core_client_data_download_services"></a>클라이언트 데이터 다운로드 서비스

클라이언트로 데이터를 전송하는 데 도움이 되는 두 가지 API 집합은 WinInet 및 비동기 모니커입니다. HTML 페이지에 큰 .gif 및 .avi 파일 및 ActiveX 컨트롤이 있는 경우 비동기 모니커를 사용하거나 WinInet을 비동기적으로 사용하여 비동기적으로 다운로드하여 사용자에 대한 응답성을 높일 수 있습니다.

인터넷에서 일반적인 작업은 데이터를 전송하는 것입니다. Active 기술을 이미 사용하고 있는 경우(예: ActiveX 컨트롤이 있는 경우) 비동기 모니커를 사용하여 다운로드할 때 데이터를 점진적으로 렌더링할 수 있습니다. WinInet을 사용하여 HTTP, FTP 및 고퍼와 같은 일반적인 인터넷 프로토콜을 사용하여 데이터를 전송할 수 있습니다. 두 방법 모두 프로토콜 독립성을 제공하고 WinSock 및 TCP/IP를 사용하는 추상 계층을 제공합니다. 여전히 [WinSock을](../mfc/windows-sockets-in-mfc.md) 직접 사용할 수 있습니다.

다음 표에는 MFC를 사용하여 인터넷을 통해 데이터를 전송하는 몇 가지 방법이 요약되어 있습니다.

|이 프로토콜 사용|이러한 조건에서|이러한 클래스 사용|
|-----------------------|----------------------------|-------------------------|
|[비동기 모니커를 사용하여 인터넷 다운로드](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX 컨트롤 및 모든 인터넷 프로토콜을 사용하는 비동기 전송용.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP 및 고퍼용 인터넷 프로토콜용. 데이터는 동기 또는 비동기적으로 전송될 수 있으며 시스템 전체 캐시에 저장됩니다.|[CInternetSession,](../mfc/reference/cinternetsession-class.md) [CFtpFileFind,](../mfc/reference/cftpfilefind-class.md) [CGopherFileFind,](../mfc/reference/cgopherfilefind-class.md)그리고 더 많은.|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|최대의 효율성과 제어를 위해. 소켓 및 TCP/IP 프로토콜에 대한 이해가 필요합니다.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>참고 항목

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 인터넷 확장명(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷의 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)
