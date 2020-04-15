---
title: 'TN048: MFC 데이터베이스 애플리케이션에 대한 ODBC 설정 및 관리 프로그램 작성'
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: d25520c4ffc805701dfe6b51192f8078e2fa300f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365476"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: MFC 데이터베이스 애플리케이션에 대한 ODBC 설정 및 관리 프로그램 작성

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

MFC 데이터베이스 클래스를 사용하는 응용 프로그램에는 ODBC 구성 요소를 설치하는 설치 프로그램이 필요합니다. 또한 사용 가능한 드라이버에 대한 정보를 검색하고 기본 드라이버를 지정하고 데이터 원본을 구성하는 ODBC 관리 프로그램이 필요할 수도 있습니다. 이 참고 는 ODBC 설치 프로그램 API를 사용하여 이러한 프로그램을 작성하는 방법을 설명합니다.

## <a name="writing-an-odbc-setup-program"></a><a name="_mfcnotes_writing_an_odbc_setup_program"></a>ODBC 설치 프로그램 작성

MFC 데이터베이스 응용 프로그램에는 ODBC 드라이버 관리자(ODBC)가 필요합니다. DLL) 및 ODBC 드라이버가 데이터 원본에 도착할 수 있도록 합니다. 많은 ODBC 드라이버에는 추가 네트워크 및 통신 DLL이 필요합니다. 대부분의 ODBC 드라이버는 필요한 ODBC 구성 요소를 설치하는 설치 프로그램과 함께 제공됩니다. MFC 데이터베이스 클래스를 사용하는 응용 프로그램 개발자는 다음을 수행할 수 있습니다.

- ODBC 구성 요소를 설치하기 위한 드라이버 별 설정 프로그램에 의존합니다. 이렇게 하면 드라이버의 설치 프로그램을 재배포할 수 있으므로 개발자의 부분에 대한 추가 작업이 필요하지 않습니다.

- 또는 드라이버 관리자와 드라이버를 설치하는 자체 설치 프로그램을 작성할 수 있습니다.

ODBC 설치 프로그램 API를 사용하여 응용 프로그램별 설정 프로그램을 작성할 수 있습니다. 설치 프로그램 API의 기능은 ODBC 설치 프로그램 DLL - ODBCINST에 의해 구현됩니다. 16 비트 윈도우와 ODBCCP32에 DLL. Win32에 DLL. 응용 프로그램은 `SQLInstallODBC` ODBC 드라이버 관리자, ODBC 드라이버 및 필요한 번역기를 설치하는 설치 프로그램 DLL에서 호출할 수 있습니다. 그런 다음 ODBCINST에 설치된 드라이버와 번역기를 기록합니다. INI 파일(또는 NT의 레지스트리). `SQLInstallODBC`ODBC에 대한 전체 경로가 필요합니다. 설치할 드라이버 목록을 포함하고 각 드라이버를 구성하는 파일을 설명하는 INF 파일입니다. 또한 드라이버 관리자 및 번역기에 대한 유사한 정보도 포함되어 있습니다. Odbc. INF 파일은 일반적으로 드라이버 개발자가 제공합니다.

프로그램은 개별 ODBC 구성 요소를 설치할 수도 있습니다. 드라이버 관리자를 설치하려면 프로그램이 `SQLInstallDriverManager` 먼저 설치 관리자 DLL에서 호출하여 드라이버 관리자의 대상 디렉터리를 가져옵니다. 일반적으로 Windows DLL이 있는 디렉터리입니다. 그런 다음 프로그램은 ODBC의 [ODBC 드라이버 관리자] 섹션의 정보를 사용합니다. 설치 디스크에서 이 디렉토리로 드라이버 관리자 및 관련 파일을 복사하는 INF 파일입니다. 개별 드라이버를 설치하려면 프로그램이 먼저 `SQLInstallDriver` 설치 관리자 DLL에서 호출하여 ODBCINST에 드라이버 사양을 추가합니다. INI 파일(또는 NT의 레지스트리). `SQLInstallDriver`은 일반적으로 Windows DLL이 있는 디렉터리인 드라이버의 대상 디렉터리를 반환합니다. 그런 다음 프로그램은 ODBC의 드라이버 섹션에 있는 정보를 사용합니다. 설치 디스크에서 이 디렉토리에 드라이버 DLL 및 관련 파일을 복사하는 INF 파일입니다.

ODBC에 대한 자세한 내용은 INF, ODBCINST. INI 및 설치 프로그램 API를 사용하여 ODBC SDK *프로그래머의 참조,* 장 19, ODBC 소프트웨어 설치를 참조하십시오.

## <a name="writing-an-odbc-administrator"></a><a name="_mfcnotes_writing_an_odbc_administrator"></a>ODBC 관리자 쓰기

MFC 데이터베이스 응용 프로그램은 다음과 같이 다음 두 가지 방법 중 하나로 ODBC 데이터 원본을 설정하고 구성할 수 있습니다.

- ODBC 관리자(프로그램 또는 제어판 항목으로 사용 가능)를 사용합니다.

- 사용자 고유의 프로그램을 만들어 데이터 원본을 구성합니다.

데이터 원본을 구성하는 프로그램은 설치 관리자 DLL에 함수 호출을 합니다. 설치 관리자 DLL은 설치 DLL을 호출하여 데이터 원본을 구성합니다. 각 드라이버에 대해 하나의 설정 DLL이 있습니다. 드라이버 DLL 자체 또는 별도의 DLL일 수 있습니다. 설정 DLL은 드라이버가 데이터 원본과 기본 변환기에 연결해야 하는 정보를 사용자에게 프롬프트합니다(지원되는 경우). 그런 다음 설치 관리자 DLL 및 Windows API를 호출하여 이 정보를 ODBC에 기록합니다. INI 파일(또는 레지스트리).

사용자가 데이터 원본을 추가, 수정 및 삭제할 수 있는 대화 `SQLManageDataSources` 상자를 표시하려면 프로그램이 설치 관리자 DLL에서 호출합니다. 이 함수는 제어판에서 설치 관리자 DLL을 호출할 때 호출됩니다. 데이터 원본을 추가, 수정 또는 `SQLManageDataSources` `ConfigDSN` 삭제하려면 해당 데이터 원본과 연결된 드라이버에 대한 설정 DLL에서 호출합니다. 데이터 원본을 직접 추가, 수정 또는 `SQLConfigDataSource` 삭제하려면 프로그램이 설치 관리자 DLL에서 호출합니다. 프로그램은 데이터 원본의 이름과 취할 작업을 지정하는 옵션을 전달합니다. `SQLConfigDataSource`설정 `ConfigDSN` DLL에서 호출하고 에서 `SQLConfigDataSource`인수를 전달합니다.

자세한 내용은 ODBC SDK *프로그래머의 참조,* 장 23, 설치 DLL 함수 참조 및 24장 설치 관리자 DLL 함수 참조를 참조하십시오.

## <a name="see-also"></a>참고 항목

[숫자별 기술 노트](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
