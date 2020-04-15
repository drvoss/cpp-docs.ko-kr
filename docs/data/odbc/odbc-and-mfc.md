---
title: ODBC 및 MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 38a625c73a17ecae4d8adc61e8c56bc4bdda67f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320076"
---
# <a name="odbc-and-mfc"></a>ODBC 및 MFC

> [!NOTE]
> MFC 데이터베이스 클래스를 사용하려면 데이터 원본에 적합한 ODBC 드라이버가 있어야 합니다. SQL 서버에 대한 마지막 마이크로 소프트 ODBC 드라이버는 [SQL 서버에 대한 마이크로 소프트 ODBC 드라이버 (13)입니다](https://www.microsoft.com/download/details.aspx?id=50420). 대부분의 데이터베이스 공급업체는 Windows용 ODBC 드라이버를 제공합니다.

이 항목에서는 MFC(Microsoft Foundation 클래스) 라이브러리의 ODBC 기반 데이터베이스 클래스의 주요 개념을 소개하고 클래스가 함께 작동하는 방식에 대한 개요를 제공합니다. ODBC 및 MFC에 대한 자세한 내용은 다음 항목을 참조하십시오.

- [데이터 소스에 연결](connecting-to-a-data-source.md)

- [레코드 선택 및 조작](selecting-and-manipulating-records.md)

- [양식에 데이터 표시 및 조작](displaying-and-manipulating-data-in-a-form.md)

- [문서 및 뷰 작업](working-with-documents-and-views.md)

- [ODBC 및 SQL 액세스](access-to-odbc-and-sql.md)

- [MFC ODBC 클래스에 대한 추가 정보](further-reading-about-the-mfc-odbc-classes.md)

ODBC를 기반으로 하는 MFC 데이터베이스 클래스는 ODBC 드라이버를 사용할 수 있는 모든 데이터베이스에 대한 액세스를 제공하도록 설계되었습니다. 클래스는 ODBC를 사용하기 때문에 응용 프로그램은 다양한 데이터 형식과 다른 로컬/원격 구성의 데이터에 액세스할 수 있습니다. 다른 DBMS(데이터베이스 관리 시스템)를 처리하기 위해 특수 대/소문자 코드를 작성할 필요가 없습니다. 사용자가 액세스하려는 데이터에 대해 적절한 ODBC 드라이버를 사용하는 한 프로그램을 사용하여 저장된 테이블에 있는 데이터를 조작할 수 있습니다.

## <a name="see-also"></a>참고 항목

[개방형 데이터베이스 연결(ODBC)](open-database-connectivity-odbc.md)
