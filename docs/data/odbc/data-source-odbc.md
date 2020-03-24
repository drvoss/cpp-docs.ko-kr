---
title: 데이터 소스(ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: ed9eeb8f5ef0d53846761062cf2c6575d2eaf9e6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213305"
---
# <a name="data-source-odbc"></a>데이터 소스(ODBC)

이 항목은 MFC ODBC 클래스에 적용됩니다.

데이터베이스 용어로 데이터 원본은 특정 데이터 집합, 데이터에 액세스 하는 데 필요한 정보 및 데이터 원본 이름을 사용 하 여 설명할 수 있는 데이터 원본의 위치입니다. 클래스 [CDatabase](../../mfc/reference/cdatabase-class.md)로 작업 하려면 ODBC (Open Database Connectivity) 관리자를 통해 구성한 데이터 원본 이어야 합니다. 데이터 원본의 예로는 네트워크를 통해 Microsoft SQL Server에서 실행 되는 원격 데이터베이스 또는 로컬 디렉터리의 Microsoft Access 파일이 있습니다. 응용 프로그램에서 ODBC 드라이버가 있는 모든 데이터 원본에 액세스할 수 있습니다.

응용 프로그램에서 한 번에 하나 이상의 데이터 소스를 활성화 하 여 한 번에 `CDatabase` 개체로 나타낼 수 있습니다. 모든 데이터 원본에 대 한 동시 연결을 여러 개 사용할 수도 있습니다. 설치한 드라이버 및 ODBC 드라이버의 기능에 따라 원격 및 로컬 데이터 원본에 연결할 수 있습니다. 데이터 원본 및 ODBC 관리자에 대 한 자세한 내용은 [odbc](../../data/odbc/odbc-basics.md) 및 [odbc 관리자](../../data/odbc/odbc-administrator.md)를 참조 하십시오.

다음 항목에서는 데이터 원본에 대해 자세히 설명 합니다.

- [데이터 소스: 연결 관리(ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [데이터 소스: 데이터 소스의 스키마 확인(ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>참고 항목

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)
