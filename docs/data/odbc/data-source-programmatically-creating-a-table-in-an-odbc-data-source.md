---
title: ODBC 데이터 원본에서 프로그래밍 방식으로 테이블 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 6cf26cad7fe39f374daf371902525087b446658c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358832"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성

이 항목에서는 클래스의 `ExecuteSQL` 멤버 함수를 사용하여 CREATE `CDatabase` **TABLE** SQL 문이 포함된 문자열을 함수에 전달하는 데이터 원본에 대한 테이블을 만드는 방법을 설명합니다.

MFC의 ODBC 데이터 원본에 대한 일반 정보는 [데이터 원본(ODBC)을](../../data/odbc/data-source-odbc.md)참조하십시오. 주제 [데이터 원본: ODBC 데이터 원본을 프로그래밍 방식으로 구성하는](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) 것은 데이터 원본 만들기에 대해 설명합니다.

데이터 원본이 설정된 경우 `ExecuteSQL` 멤버 함수및 CREATE **TABLE** SQL 문을 사용하여 테이블을 쉽게 만들 수 있습니다. 예를 들어 `CDatabase` 다음 MFC `myDB`코드를 사용하여 테이블을 만들 수 있습니다.

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

이 코드 예제에서는 유지 관리되는 `myDB`Microsoft Access 데이터 원본 연결에서 "OFFICES"라는 테이블을 만듭니다. 테이블에는 "OfficeID" 및 "OfficeName" 두 필드가 포함되어 있습니다.

> [!NOTE]
> **CREATE TABLE** SQL 문에 지정된 필드 유형은 사용 중인 ODBC 드라이버에 따라 다를 수 있습니다. Microsoft 쿼리 프로그램(Visual C++ 1.5와 함께 배포)은 데이터 원본에 사용할 수 있는 필드 유형을 검색하는 한 가지 방법입니다. Microsoft 쿼리에서 **파일**클릭 Table_Definition **클릭하고**데이터 원본에서 테이블을 선택하고 **콤보 유형** 상자에 표시된 형식을 확인합니다. 인덱스를 만들기 위해 SQL 구문도 있습니다.

## <a name="see-also"></a>참고 항목

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)
