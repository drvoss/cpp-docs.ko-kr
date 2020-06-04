---
title: '데이터 소스: 연결 관리(ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
ms.openlocfilehash: 107a5e20b70f67be74b6e6f861bd539446e9d4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374524"
---
# <a name="data-source-managing-connections-odbc"></a>데이터 소스: 연결 관리(ODBC)

이 토픽은 MFC ODBC 클래스에 적용됩니다.

이 토픽에서는 다음 내용을 설명합니다.

- [데이터 원본을 구성하는 방법](#_core_configuring_a_data_source).

- [다중 사용자 환경이 데이터 원본 및 해당 레코드 집합에 미치는 영향](#_core_working_in_a_multiuser_environment).

- [데이터 원본에 대한 연결 문자열을 일반화하는 이유](#_core_generalizing_the_connection_string).

- [데이터 원본에 연결하는 방법](#_core_connecting_to_a_specific_data_source).

- [데이터 원본에서 연결을 끊는 방법](#_core_disconnecting_from_a_data_source).

- [CDatabase 개체를 다시 사용하는 방법](#_core_reusing_a_cdatabase_object).

데이터 원본에 연결한다는 것은 데이터에 액세스하기 위해 DBMS와의 통신을 설정하는 것을 의미합니다. ODBC 드라이버를 통해 응용 프로그램의 데이터 원본에 연결할 때 드라이버는 로컬 또는 네트워크를 통해 연결합니다.

ODBC 드라이버가 있는 모든 데이터 원본에 연결할 수 있습니다. 응용 프로그램의 사용자는 데이터 원본에 대해 동일한 ODBC 드라이버를 가져야 합니다. ODBC 드라이버 재배포에 대한 자세한 내용은 [ODBC 구성 요소를 고객에게 재배포하는 것을](../../data/odbc/redistributing-odbc-components-to-your-customers.md)참조하십시오.

## <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a>데이터 원본 구성

ODBC 관리자는 데이터 원본을 구성하는 데 사용됩니다. 설치 후 ODBC 관리자를 사용하여 데이터 원본을 추가하거나 제거할 수도 있습니다. 응용 프로그램을 만들 때 ODBC 관리자에게 사용자를 지시하여 데이터 원본을 추가하도록 하거나 직접 ODBC 설치 호출을 통해 응용 프로그램에 이 기능을 빌드할 수 있습니다. 자세한 내용은 [ODBC 관리자](../../data/odbc/odbc-administrator.md)를 참조하십시오.

Excel 파일을 데이터 원본으로 사용할 수 있으며 파일이 등록되어 **데이터 원본 선택** 대화 상자에 표시되도록 파일을 구성해야 합니다.

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Excel 파일을 데이터 원본으로 사용하려면

1. ODBC 데이터 원본 관리자로 파일을 구성합니다.

1. 파일 **DSN** 탭에서 **추가를**클릭합니다.

1. 새 **데이터 원본 만들기** 대화 상자에서 Excel 드라이버를 선택한 다음 **다음을 클릭합니다.**

1. **찾아보기를**클릭하고 날짜 원본으로 사용할 파일 이름을 선택합니다.

> [!NOTE]
> .xls 파일을 보려면 드롭다운 메뉴에서 **모든 파일을** 선택해야 할 수 있습니다.

1. **다음**을 클릭하고 **마침**을 클릭합니다.

1. **ODBC Microsoft Excel 설치 설정** 대화 상자에서 데이터베이스 버전 및 통합 문서를 선택합니다.

## <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a>다중 사용자 환경에서 작업

여러 사용자가 데이터 원본에 연결되어 있는 경우 레코드 집합에서 데이터를 조작하는 동안 데이터를 변경할 수 있습니다. 마찬가지로 변경 사항은 다른 사용자의 레코드 집합에 영향을 줄 수 있습니다. 자세한 내용은 [레코드 집합: 레코드 집합 업데이트 레코드(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [트랜잭션(ODBC)을](../../data/odbc/transaction-odbc.md)참조하세요.

## <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a>연결 문자열 일반화

마법사는 기본 연결 문자열을 사용하여 데이터 원본에 대한 연결을 설정합니다. 응용 프로그램을 개발하는 동안 이 연결을 사용하여 테이블과 열을 볼 수 있습니다. 그러나 이 기본 연결 문자열은 응용 프로그램을 통해 데이터 원본에 대한 사용자의 연결에 적합하지 않을 수 있습니다. 예를 들어 해당 데이터 원본과 해당 위치에 대한 경로는 응용 프로그램 개발에 사용되는 경로와 다를 수 있습니다. 이 경우 [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) 멤버 함수를 보다 일반적인 방식으로 다시 구현하고 마법사 구현을 폐기해야 합니다. 예를 들어 다음 방법 중 하나를 사용합니다.

- ODBC 관리자를 사용하여 연결 문자열을 등록하고 관리합니다.

- 연결 문자열을 편집하고 데이터 원본 이름을 제거합니다. 프레임워크는 ODBC를 데이터 원본으로 제공합니다. 런타임에 ODBC는 데이터 원본 이름 및 기타 필요한 연결 정보를 묻는 대화 상자를 표시합니다.

- 데이터 원본 이름만 제공합니다. ODBC는 필요한 경우 사용자 ID와 암호를 요청합니다. 예를 들어 일반화하기 전에 연결 문자열은 다음과 같습니다.

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   이 연결 문자열은 Windows NT 통합 보안을 사용하는 신뢰할 수 있는 연결을 지정합니다. 암호를 하드 코딩하거나 빈 암호를 지정하지 않으면 주요 보안 약점이 발생하므로 피해야 합니다. 대신 사용자 ID와 암호를 쿼리하도록 새 연결 문자열을 제공할 `GetDefaultConnect` 수 있습니다.

    ```cpp
    // User must select data source and supply user ID and password:
        return "ODBC;";
    // User ID and password required:
        return "ODBC;DSN=mydb;";
    // Password required (myuserid must be replaced with a valid user ID):
        return "ODBC;DSN=mydb;UID=myuserid;";
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";
    ```

## <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a>특정 데이터 원본에 연결

특정 데이터 원본에 연결하려면 데이터 원본이 [이미 ODBC 관리자로](../../data/odbc/odbc-administrator.md)구성되어 있어야 합니다.

#### <a name="to-connect-to-a-specific-data-source"></a>특정 데이터 원본에 연결하려면

1. 개체를 `CDatabase` 생성합니다.

1. 해당 `OpenEx` 함수 `Open` 또는 멤버 함수를 호출합니다.

데이터 원본을 마법사로 지정한 데이터 원본이 아닌 경우 지정하는 방법에 대한 자세한 내용은 [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) *에서 MFC 참조에서*열립니다.

## <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a>데이터 원본연결 해제

의 멤버 함수를 호출하기 `Close` 전에 열려 있는 레코드 집합을 닫아야 합니다. `CDatabase` 닫으려는 `CDatabase` 개체와 연결된 레코드 집합에서 보류 `AddNew` `Edit` 중인 또는 문이 취소되고 보류 중인 모든 트랜잭션이 롤백됩니다.

#### <a name="to-disconnect-from-a-data-source"></a>데이터 원본에서 연결을 끊려면

1. 개체의 `CDatabase` [닫기](../../mfc/reference/cdatabase-class.md#close) 멤버 함수를 호출합니다.

1. 객체를 다시 사용하지 않으려면 오브젝트를 삭제합니다.

## <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a>CDatabase 개체 재사용

개체연결을 끊은 `CDatabase` 후 동일한 데이터 원본에 다시 연결하거나 다른 데이터 원본에 연결하는 데 사용할 지 여부를 다시 사용할 수 있습니다.

#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase 개체를 다시 사용하려면

1. 개체의 원래 연결을 닫습니다.

1. 개체를 파괴하는 대신 해당 `OpenEx` `Open` 개체 또는 멤버 함수를 다시 호출합니다.

## <a name="see-also"></a>참고 항목

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[데이터 소스: 데이터 소스의 스키마 확인(ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[C레코드 집합 클래스](../../mfc/reference/crecordset-class.md)
