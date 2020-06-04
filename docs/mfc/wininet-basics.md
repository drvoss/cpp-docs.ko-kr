---
title: WinInet 기본 사항
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: b989e5c3df63ee7b5129d01468a0f869772ed286
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367332"
---
# <a name="wininet-basics"></a>WinInet 기본 사항

WinInet을 사용하여 FTP 지원을 추가하여 응용 프로그램 내에서 파일을 다운로드하고 업로드할 수 있습니다. [OnStatusCallback을](../mfc/reference/cinternetsession-class.md#onstatuscallback) 재정의하고 *dwContext* 매개 변수를 사용하여 파일을 검색하고 다운로드할 때 사용자에게 진행 률 정보를 제공할 수 있습니다.

이 문서에는 다음 항목이 포함되어 있습니다.

- [매우 간단한 브라우저 만들기](#_core_create_a_very_simple_browser)

- [웹 페이지 다운로드](#_core_download_a_web_page)

- [FTP a 파일](#_core_ftp_a_file)

- [고퍼 디렉토리 검색](#_core_retrieve_a_gopher_directory)

- [파일을 전송하는 동안 진행 률 정보 표시](#_core_display_progress_information_while_transferring_files)

아래 코드 발췌는 간단한 브라우저를 만들고, 웹 페이지를 다운로드하고, 파일을 FTP하고, 고퍼 파일을 검색하는 방법을 보여 줍니다. 완전한 예제로 의도된 것이 아니며 모두 예외 처리를 포함하지는 않습니다.

WinInet에 대한 자세한 내용은 [Win32 인터넷 확장(WinInet)을](../mfc/win32-internet-extensions-wininet.md)참조하십시오.

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a>매우 간단한 브라우저 만들기

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a>웹 페이지 다운로드

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a>FTP a 파일

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a>고퍼 디렉토리 검색

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>온스테이콜백 사용

WinInet 클래스를 사용하는 경우 응용 프로그램의 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체의 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 멤버를 사용하여 상태 정보를 검색할 수 있습니다. 사용자 고유의 `CInternetSession` 개체를 파생하고 재정의하고 `OnStatusCallback`상태 콜백을 사용하도록 `OnStatusCallback` 설정하면 MFC는 해당 인터넷 세션의 모든 활동에 대한 진행률 정보를 사용하여 함수를 호출합니다.

단일 세션이 여러 연결을 지원할 수 있으므로(수명 동안 여러 `OnStatusCallback` 개의 서로 다른 작업을 수행할 수 있음) 특정 연결 또는 트랜잭션을 사용하여 각 상태 변경을 식별하는 메커니즘이 필요합니다. 이 메커니즘은 WinInet 지원 클래스의 많은 멤버 함수에 제공된 컨텍스트 ID 매개 변수에 의해 제공됩니다. 이 매개 변수는 항상 **DWORD** 형식이며 항상 *dwContext*.

특정 인터넷 개체에 할당된 컨텍스트는 개체가 `OnStatusCallback` `CInternetSession` 개체의 멤버에서 발생하는 활동을 식별하는 데만 사용됩니다. 호출은 `OnStatusCallback` 여러 매개 변수를 수신합니다. 이러한 매개 변수는 함께 작동하여 응용 프로그램에서 어떤 트랜잭션 및 연결에 대해 진행이 이루어졌는지 알려줍니다.

개체를 `CInternetSession` 만들 때 *dwContext* 매개 변수를 생성자로 지정할 수 있습니다. `CInternetSession`자체는 컨텍스트 ID를 사용하지 않습니다. 대신, 명시적으로 자신의 컨텍스트 ID를 얻지 않는 **모든 InternetConnection-파생**된 개체에 컨텍스트 ID를 전달 합니다. 그런 다음 `CInternetConnection` 다른 컨텍스트 ID를 명시적으로 `CInternetFile` 지정하지 않으면 해당 개체가 만든 개체에 컨텍스트 ID를 전달합니다. 반면에 고유한 특정 컨텍스트 ID를 지정하면 개체와 해당 작업이 해당 컨텍스트 ID와 연결됩니다. 컨텍스트 아이디를 사용하여 함수에서 어떤 상태 정보가 제공되는지 `OnStatusCallback` 식별할 수 있습니다.

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a>파일을 전송하는 동안 진행 률 정보 표시

예를 들어 파일을 읽기 위해 FTP 서버와의 연결을 만들고 HTTP 서버에 연결하여 웹 페이지를 얻는 응용 프로그램을 작성하는 경우 `CInternetSession` 개체, `CInternetConnection` 두 개체(하나는 `CFtpSession` a이고 다른 `CHttpSession`하나는 a) 및 두 개체(각 `CInternetFile` 연결에 대해 하나씩)가 됩니다. *dwContext* 매개 변수에 대한 기본값을 사용한 경우 FTP 연결의 진행률을 나타내는 호출과 HTTP 연결의 `OnStatusCallback` 진행률을 나타내는 호출을 구분할 수 없습니다. 에서 나중에 테스트할 수 있는 *dwContext* ID를 `OnStatusCallback`지정하면 콜백을 생성한 작업을 알 수 있습니다.

## <a name="see-also"></a>참고 항목

[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 인터넷 확장명(WinInet)](../mfc/win32-internet-extensions-wininet.md)
