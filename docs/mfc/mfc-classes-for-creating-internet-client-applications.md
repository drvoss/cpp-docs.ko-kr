---
title: 인터넷 클라이언트 애플리케이션을 만들기 위한 MFC 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: 578fd5b72e6c04610aa862f1a6631895a32a9bfe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358215"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>인터넷 클라이언트 애플리케이션을 만들기 위한 MFC 클래스

MFC는 인터넷 클라이언트 응용 프로그램을 작성하기 위한 다음과 같은 클래스 및 전역 함수를 제공합니다. 들여쓰기는 클래스가 위에 있는 들여쓰기되지 않은 클래스에서 파생된다는 것을 나타냅니다. `CGopherFile`및 `CHttpFile` `CInternetFile`예를 들어 에서 파생됩니다. 이러한 클래스와 전역 함수는 AFXINET에서 선언됩니다. H, `CFileFind`AFX에서 선언되는 를 제외합니다. H.

## <a name="classes"></a>클래스

- [CInternetSession](../mfc/reference/cinternetsession-class.md)

- [CInternetConnection](../mfc/reference/cinternetconnection-class.md)

  - [CFtpConnection](../mfc/reference/cftpconnection-class.md)

  - [CGopherConnection](../mfc/reference/cgopherconnection-class.md)

  - [CHttpConnection](../mfc/reference/chttpconnection-class.md)

- [CInternetFile](../mfc/reference/cinternetfile-class.md)

  - [CGopherFile](../mfc/reference/cgopherfile-class.md)

  - [CHttpFile](../mfc/reference/chttpfile-class.md)

- [CFileFind](../mfc/reference/cfilefind-class.md)

  - [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)

  - [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)

- [CGopherLocator](../mfc/reference/cgopherlocator-class.md)

- [CInternetException](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>글로벌 기능

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>참고 항목

[Win32 인터넷 확장명(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet 클래스를 사용하여 인터넷 클라이언트 애플리케이션 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
