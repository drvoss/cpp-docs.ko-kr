---
title: ODBC 데이터 원본에서 프로그래밍 방식으로 테이블 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
ms.openlocfilehash: 25c975560d6a73ce67294d97830b2f5bec9cd635
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213280"
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>데이터 소스: ODBC 데이터 소스에서 프로그래밍 방식으로 테이블 작성

이 항목에서는 `CDatabase`클래스의 `ExecuteSQL` 멤버 함수를 사용 하 여 데이터 원본에 대 한 테이블을 만들고 **CREATE TABLE** SQL 문이 포함 된 문자열을 함수에 전달 하는 방법에 대해 설명 합니다.

MFC의 ODBC 데이터 원본에 대 한 일반 정보는 [데이터 원본 (odbc)](../../data/odbc/data-source-odbc.md)을 참조 하세요. 항목 [데이터 원본: 프로그래밍 방식으로 ODBC 데이터 소스를 구성](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) 하는 방법에 대해서는 데이터 원본 만들기를 설명 합니다.

데이터 원본을 설정 하면 `ExecuteSQL` 멤버 함수와 **CREATE TABLE** SQL 문을 사용 하 여 테이블을 쉽게 만들 수 있습니다. 예를 들어 `myDB`라는 `CDatabase` 개체가 있는 경우 다음 MFC 코드를 사용 하 여 테이블을 만들 수 있습니다.

```
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",
                         OfficeName TEXT(10))");
```

이 코드 예제에서는 `myDB`에 의해 유지 관리 되는 Microsoft Access 데이터 원본 연결에서 "사무실" 이라는 테이블을 만듭니다. 테이블에는 "OfficeName Id" 및 "" 라는 두 개의 필드가 있습니다.

> [!NOTE]
>  **CREATE TABLE** SQL 문에 지정 된 필드 형식은 사용 하는 ODBC 드라이버에 따라 달라질 수 있습니다. Visual C++ 1.5와 함께 배포되는 Microsoft Query 프로그램을 사용하면 데이터 소스에 대해 사용할 수 있는 필드 형식을 알 수 있습니다. Microsoft Query에서 **파일**, **Table_Definition**을 차례로 클릭 하 고 데이터 원본에서 테이블을 선택 하 고 **유형** 콤보 상자에 표시 된 유형을 확인 합니다. 인덱스를 작성하기 위한 SQL 구문도 있습니다.

## <a name="see-also"></a>참고 항목

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)
