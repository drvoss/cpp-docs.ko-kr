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
ms.openlocfilehash: 5a8fb7bf07ec631869075c5977dcec468143ad56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366284"
---
# <a name="mfc-internet-programming-basics"></a>MFC 인터넷 프로그래밍 기본 사항

Microsoft는 클라이언트 및 서버 응용 프로그램을 모두 프로그래밍하기 위한 많은 API를 제공합니다. 많은 새로운 응용 프로그램이 인터넷을 위해 작성되고 있으며 기술, 브라우저 기능 및 보안 옵션이 변경됨에 따라 새로운 유형의 응용 프로그램이 작성됩니다. 브라우저는 클라이언트 컴퓨터에서 실행되어 월드 와이드 웹에 대한 액세스를 제공하고 텍스트, 그래픽, ActiveX 컨트롤 및 문서가 포함된 HTML 페이지를 표시합니다. 서버는 FTP, HTTP 및 고퍼 서비스를 제공하고 CGI를 사용하여 서버 확장 응용 프로그램을 실행합니다. 사용자 지정 응용 프로그램은 정보를 검색하고 인터넷에서 데이터를 제공할 수 있습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

![클라이언트 및 서버 응용 프로그램](../mfc/media/vc38bq1.gif "클라이언트 및 서버 응용 프로그램")

MFC는 인터넷 프로그래밍을 지원하는 클래스를 제공합니다. [COleControl](../mfc/reference/colecontrol-class.md) 및 [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) 및 관련 MFC 클래스를 사용하여 ActiveX 컨트롤 및 활성 문서를 작성할 수 있습니다. [CInternetSession,](../mfc/reference/cinternetsession-class.md) [CFtpConnection](../mfc/reference/cftpconnection-class.md)및 [CAsyncMonikerFile과](../mfc/reference/casyncmonikerfile-class.md) 같은 MFC 클래스를 사용하여 FTP, HTTP 및 고퍼와 같은 인터넷 프로토콜을 사용하여 파일 및 정보를 검색할 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

- [인터넷 관련 MFC 클래스](../mfc/internet-related-mfc-classes.md)

- [항목별 인터넷 정보](../mfc/internet-information-by-topic.md)

- [작업별 인터넷 정보](../mfc/internet-information-by-task.md)

- [인터넷의 액티브 기술](../mfc/active-technology-on-the-internet.md)

- [WinInet 기본 사항](../mfc/wininet-basics.md)

- [HTML 기본 사항](../mfc/html-basics.md)

## <a name="related-sections"></a>관련 단원

- [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)

- [인터넷의 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32 인터넷 확장명(WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)

- [애플리케이션 디자인 선택](../mfc/application-design-choices.md)

- [MFC 애플리케이션 작성](../mfc/writing-mfc-applications.md)

- [인터넷 애플리케이션 테스트](../mfc/testing-internet-applications.md)

- [인터넷 보안](../mfc/internet-security-cpp.md)

- [DHTML 컨트롤에 대한 ATL 지원](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>자세한 내용은 웹 사이트

Microsoft 인터넷 기술에 대한 자세한 내용은 [MSDN(Microsoft 개발자 네트워크)](https://go.microsoft.com/fwlink/p/?linkid=56322) 웹 사이트를 참조하십시오. (링크는 예고 없이 변경될 수 있습니다.)

개발자를 위한 이 웹 사이트에는 Microsoft 개발 도구 및 기술 사용에 대한 정보와 최근 및 향후 컨퍼런스에 대한 주요 설명이 포함되어 있습니다. 이 페이지에서 .NET 및 XML 개발자 센터를 비롯한 많은 관련 개발자 사이트로 이동할 수 있습니다. 또한 베타 SDK 및 샘플을 다운로드 할 수 있습니다.

[W3C(월드 와이드 웹 컨소시엄)는](https://go.microsoft.com/fwlink/p/?linkid=37125) HTML, HTTP, CGI 및 기타 월드 와이드 웹 기술에 대한 사양을 게시합니다.

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>더 많은 인터넷 도움말

Windows SDK의 OLE 섹션에는 OLE 프로그래밍에 대한 추가 정보가 포함되어 있습니다. 이 정보는 MFC 클래스가 아닌 Win32 WinInet 함수를 직접 사용하는 것에 대한 세부 정보를 제공합니다. 또한 인터넷 기술에 대한 개요 정보도 포함되어 있습니다.
