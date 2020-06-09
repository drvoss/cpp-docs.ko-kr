---
title: MFC 인터넷 프로그래밍 기본 사항
ms.date: 11/19/2018
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
ms.openlocfilehash: 3265bffb393eeff1d8a04a41357e2b138aa0ebf7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615567"
---
# <a name="mfc-internet-programming-basics"></a>MFC 인터넷 프로그래밍 기본 사항

Microsoft는 클라이언트 및 서버 응용 프로그램을 모두 프로그래밍 하기 위한 많은 Api를 제공 합니다. 인터넷을 위해 많은 새로운 응용 프로그램을 작성 하 고, 기술, 브라우저 기능 및 보안 옵션이 변경 됨에 따라 새로운 유형의 응용 프로그램이 작성 됩니다. 브라우저는 클라이언트 컴퓨터에서 실행 되며, World Wide Web에 대 한 액세스를 제공 하 고 텍스트, 그래픽, ActiveX 컨트롤 및 문서를 포함 하는 HTML 페이지를 표시 합니다. 서버는 FTP, HTTP 및 gopher 서비스를 제공 하 고 CGI를 사용 하 여 서버 확장 응용 프로그램을 실행 합니다. 사용자 지정 응용 프로그램은 인터넷에서 정보를 검색 하 고 데이터를 제공할 수 있습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 하지 않아야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX Controls](activex-controls.md)을 참조 하세요.

![클라이언트 및 서버 응용 프로그램](../mfc/media/vc38bq1.gif "클라이언트 및 서버 응용 프로그램")

MFC는 인터넷 프로그래밍을 지 원하는 클래스를 제공 합니다. [COleControl](reference/colecontrol-class.md) 및 [CDOCOBJECTSERVER](reference/cdocobjectserver-class.md) 및 관련 MFC 클래스를 사용 하 여 ActiveX 컨트롤 및 활성 문서를 작성할 수 있습니다. [Cinternetsession](reference/cinternetsession-class.md), [CCAsyncMonikerFile connection](reference/cftpconnection-class.md)및 [CAsyncMonikerFile](reference/casyncmonikerfile-class.md) 와 같은 MFC 클래스를 사용 하 여 FTP, HTTP, gopher 등의 인터넷 프로토콜을 사용 하 여 파일 및 정보를 검색할 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

- [인터넷 관련 MFC 클래스](internet-related-mfc-classes.md)

- [항목별 인터넷 정보](internet-information-by-topic.md)

- [작업별 인터넷 정보](internet-information-by-task.md)

- [인터넷의 액티브 기술](active-technology-on-the-internet.md)

- [WinInet 기본 사항](wininet-basics.md)

- [HTML 기본 사항](html-basics.md)

## <a name="related-sections"></a>관련 단원

- [인터넷의 ActiveX 컨트롤](activex-controls-on-the-internet.md)

- [인터넷의 비동기 모니커](asynchronous-monikers-on-the-internet.md)

- [Win32 인터넷 확장명(WinInet)](win32-internet-extensions-wininet.md)

- [MFC 인터넷 프로그래밍 작업](mfc-internet-programming-tasks.md)

- [애플리케이션 디자인 선택](application-design-choices.md)

- [MFC 애플리케이션 작성](writing-mfc-applications.md)

- [인터넷 애플리케이션 테스트](testing-internet-applications.md)

- [인터넷 보안](internet-security-cpp.md)

- [DHTML 컨트롤에 대한 ATL 지원](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>자세한 내용은 웹 사이트를

Microsoft 인터넷 기술에 대 한 자세한 내용은 [MSDN (Microsoft Developer Network)](https://go.microsoft.com/fwlink/p/?linkid=56322) 웹 사이트를 참조 하십시오. 링크는 예 고 없이 변경 될 수 있습니다.

개발자를 위한이 웹 사이트에는 Microsoft 개발 도구 및 기술 사용에 대 한 정보와 최근 및 예정 된 회의에 대 한 주요 스토리가 포함 되어 있습니다. 이 페이지에서 .NET 및 XML 개발자 센터를 비롯 한 많은 관련 개발자 사이트로 이동할 수 있습니다. 베타 Sdk 및 샘플을 다운로드할 수도 있습니다.

[W3C (World Wide Web 컨소시엄)](https://go.microsoft.com/fwlink/p/?linkid=37125) 는 HTML, HTTP, CGI 및 기타 World Wide Web 기술에 대 한 사양을 게시 합니다.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>추가 인터넷 도움말

Windows SDK OLE 섹션에는 OLE 프로그래밍에 대 한 추가 정보가 포함 되어 있습니다. 이 정보는 MFC 클래스가 아니라 Win32 WinInet 함수를 직접 사용 하는 방법에 대 한 자세한 정보를 제공 합니다. 또한 인터넷 기술에 대 한 개요 정보도 포함 되어 있습니다.
