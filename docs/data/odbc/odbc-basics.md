---
title: ODBC 기초
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
ms.openlocfilehash: 042b1ce6d12e4f4a2be57c0e2e8e01d9750f5357
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213215"
---
# <a name="odbc-basics"></a>ODBC 기초

이 항목에서는 ODBC (Open Database Connectivity)의 기본 사항을 제공 합니다.

- [ODBC가 데이터베이스 클래스와 작동 하는 방식](../../data/odbc/odbc-and-the-database-classes.md)

- [ODBC 드라이버가 다이너셋은 어떻게 작동 합니까?](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [응용 프로그램과 함께 재배포 해야 하는 ODBC 구성 요소](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

관련 항목 [odbc: Odbc 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)를 읽으려고 할 수도 있습니다.

> [!NOTE]
> ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

> [!NOTE]
> MFC ODBC 클래스는 유니코드 및 다중 스레딩을 지원 합니다. 다중 스레딩 지원에 대 한 자세한 내용은 [ODBC 클래스 및 스레드](../../data/odbc/odbc-classes-and-threads.md) 를 참조 하세요.

ODBC는 응용 프로그램에서 ODBC 드라이버가 있는 모든 데이터베이스의 데이터에 액세스할 수 있도록 하는 호출 수준 인터페이스입니다. ODBC를 사용 하 여 최종 사용자에 게 ODBC 드라이버가 있는 모든 데이터베이스에 대 한 액세스 권한이 있는 데이터베이스 응용 프로그램을 만들 수 있습니다. ODBC는 응용 프로그램이 원본 DBMS (데이터베이스 관리 시스템)와 독립적으로 사용할 수 있도록 하는 API를 제공 합니다.

ODBC는 Windows 기반 데스크톱 응용 프로그램에서 각 플랫폼용 응용 프로그램을 다시 작성 하지 않고도 여러 컴퓨팅 환경에 연결할 수 있도록 하는 WOSA (Microsoft Windows Open Services) 아키텍처의 데이터베이스 부분입니다.

ODBC의 구성 요소는 다음과 같습니다.

- ODBC API

   함수 호출 라이브러리, 오류 코드 집합 및 Dbms의 데이터에 액세스 하기 위한 표준 [SQL](../../data/odbc/sql.md) 구문입니다.

- ODBC 드라이버 관리자

   응용 프로그램을 대신 하 여 ODBC 데이터베이스 드라이버를 로드 하는 동적 연결 라이브러리 (위한 odbc32.dll)입니다. 이 DLL은 응용 프로그램에 투명 합니다.

- ODBC 데이터베이스 드라이버

   특정 Dbms에 대 한 ODBC 함수 호출을 처리 하는 Dll이 하나 이상 있습니다. 제공 된 드라이버 목록은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조 하십시오.

- [ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)

   ODBC 드라이버 관리자와 드라이버 사이에 상주 하는 동적 연결 라이브러리 (Odbccr32)로, 데이터 스크롤을 처리 합니다.

- [ODBC 관리자](../../data/odbc/odbc-administrator.md)

   응용 프로그램의 데이터 원본으로 사용할 수 있도록 DBMS를 구성 하는 데 사용 되는 도구입니다.

응용 프로그램은 dbms를 사용 하 여 직접 작업 하는 대신 DBMS 용으로 특별히 작성 된 ODBC 드라이버를 통해 작업 하 여 Dbms와의 독립성을 달성 합니다. 드라이버는 호출을 DBMS에서 사용할 수 있는 명령으로 변환 하 여 개발자의 작업을 간소화 하 고 광범위 한 데이터 원본에 사용할 수 있도록 합니다.

데이터베이스 클래스는 ODBC 드라이버가 있는 모든 데이터 원본을 지원 합니다. 예를 들어 관계형 데이터베이스, 인덱싱된 ISAM (순차 액세스 방법) 데이터베이스, Microsoft Excel 스프레드시트 또는 텍스트 파일을 포함할 수 있습니다. ODBC 드라이버는 데이터 원본에 대 한 연결을 관리 하 고 SQL은 데이터베이스에서 레코드를 선택 하는 데 사용 됩니다.

이 버전의 Visual C++에 포함된 ODBC 드라이버 목록과 추가 드라이버를 가져오는 방법에 대한 자세한 내용은 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)
