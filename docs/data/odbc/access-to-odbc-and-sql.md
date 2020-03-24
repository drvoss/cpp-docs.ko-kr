---
title: ODBC 및 SQL 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 0b590ce9309cbbe95285001cc5befe70a1d1961f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213332"
---
# <a name="access-to-odbc-and-sql"></a>ODBC 및 SQL 액세스

Microsoft Foundation Class 라이브러리에는 많은 Windows API 함수가 캡슐화되어 있으며 프로그래머가 Windows API 함수를 직접 호출할 수도 있습니다. 데이터베이스 클래스는 ODBC API와 비교할 때 동일한 유연성을 제공합니다. 데이터베이스 클래스를 이용하면 ODBC 사용과 관련된 복잡한 문제를 피할 수 있는 반면 프로그램의 어디서나 ODBC API 함수를 직접 호출할 수도 있습니다.

마찬가지로 데이터베이스 클래스를 사용 하면 [sql](../../data/odbc/sql.md)에서 많은 작업을 수행할 필요가 없지만 원하는 경우 sql을 직접 사용할 수 있습니다. 레코드 집합을 열 때 사용자 지정 SQL 문 또는 기본 명령문의 설정 부분을 전달하여 레코드 집합 개체를 사용자 지정할 수 있습니다. 또한 [CDatabase](../../mfc/reference/cdatabase-class.md)클래스의 [executesql](../../mfc/reference/cdatabase-class.md#executesql) 멤버 함수를 사용 하 여 SQL 호출을 직접 수행할 수 있습니다.

자세한 내용은 odbc [: ODBC API 함수 직접 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 및 [Sql: sql 직접 호출 (odbc)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)을 참조 하세요.

## <a name="see-also"></a>참고 항목

[ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)
