---
title: '데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성'
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: ba0224d166795b34d636ace610265e115209e49c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358867"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>데이터 소스: 프로그래밍 방식으로 ODBC 데이터 소스 구성

이 항목에서는 ODBC(개방형 데이터베이스 연결) 데이터 원본 이름을 프로그래밍 방식으로 구성하는 방법을 설명합니다. 이렇게 하면 사용자가 ODBC 관리자 또는 다른 프로그램을 명시적으로 사용하여 데이터 원본 이름을 지정하지 않고도 데이터에 액세스할 수 있습니다.

일반적으로 사용자는 ODBC 관리자를 실행하여 관련 데이터베이스 관리 시스템(DBMS)이 이 작업을 지원하는 경우 데이터 원본을 만듭니다.

ODBC 관리자를 통해 Microsoft Access ODBC 데이터 원본을 만들 때 기존 .mdb 파일을 선택하거나 새 .mdb 파일을 만들 수 있습니다. MFC ODBC 응용 프로그램에서 .mdb 파일을 만드는 프로그래밍 방식은 없습니다. 따라서 응용 프로그램에서 데이터를 Microsoft Access 데이터 원본(.mdb 파일)에 배치하도록 요구하는 경우 필요할 때마다 사용하거나 복사할 수 있는 빈 .mdb 파일을 사용하려고 할 수 있습니다.

그러나 많은 DBMS를 사용하면 프로그래밍 방식의 데이터 원본을 만들 수 있습니다. 일부 데이터 원본은 데이터베이스에 대한 디렉터리 사양을 유지 관리합니다. 즉, 디렉터리는 데이터 원본이고 데이터 원본 내의 각 테이블은 별도의 파일에 저장됩니다(dBASE의 경우 각 테이블은 .dbf 파일입니다). Microsoft Access 및 SQL Server와 같은 다른 ODBC 데이터베이스의 드라이버는 데이터 원본을 설정하기 전에 몇 가지 특정 기준을 충족해야 합니다. 예를 들어 SQL Server ODBC 드라이버를 사용할 때는 SQL Server 컴퓨터를 설정해야 합니다.

## <a name="sqlconfigdatasource-example"></a><a name="_core_sqlconfigdatasource_example"></a>SQLConfig데이터 소스 예제

다음 예제에서는 `::SQLConfigDataSource` ODBC API 함수를 사용하여 새 Excel 데이터 원본이라는 새 Excel 데이터 원본을 만듭니다.

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

데이터 원본은 실제로 디렉터리(C:\EXCELDIR)입니다. 이 디렉터리가 있어야 합니다. Excel 드라이버는 디렉터리를 데이터 원본및 파일로 개별 테이블(.xls 파일당 하나의 테이블)으로 사용합니다.

테이블 만들기에 대한 자세한 내용은 [데이터 원본: 프로그래밍 방식으로 ODBC 데이터 원본에서 테이블 만들기](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)를 참조하십시오.

다음 정보는 ODBC API 함수에 전달해야 `::SQLConfigDataSource` 하는 매개 변수에 대해 설명합니다. 을 `::SQLConfigDataSource`사용하려면 Odbcinst.h 헤더 파일을 포함하고 Odbcinst.lib 가져오기 라이브러리를 사용해야 합니다. 또한 Odbccp32.dll은 런타임(또는 16비트의 Odbcinst.dll)에 경로에 있어야 합니다.

ODBC 관리자 또는 유사한 유틸리티를 사용하여 ODBC 데이터 원본 이름을 만들 수 있습니다. 그러나 경우에 따라 사용자가 별도의 유틸리티를 실행하지 않고도 액세스 권한을 얻으려면 응용 프로그램에서 직접 데이터 원본 이름을 만드는 것이 좋습니다.

ODBC 관리자(일반적으로 제어판에 설치)는 Windows 레지스트리에 항목을 배치하여 새 데이터 원본을 만듭니다(또는 Odbc.ini 파일에서 16비트). ODBC 드라이버 관리자는 이 파일을 쿼리하여 데이터 원본에 대한 필요한 정보를 가져옵니다. 에 대한 호출을 제공해야 하므로 레지스트리에 배치해야 하는 정보를 아는 것이 `::SQLConfigDataSource`중요합니다.

이 정보를 사용하지 `::SQLConfigDataSource`않고 레지스트리에 직접 쓸 수 있지만, 그렇게 하는 모든 응용 프로그램은 드라이버 관리자가 데이터를 유지 관리하는 데 사용하는 현재 기술에 의존합니다. ODBC 드라이버 관리자에 대한 이후 개정에서 데이터 원본에 대한 레코드 를 다른 방식으로 유지하는 것을 구현하는 경우 이 기술을 사용하는 모든 응용 프로그램이 손상됩니다. 일반적으로 API 함수가 제공될 때 사용하는 것이 좋습니다. 예를 들어 `::SQLConfigDataSource` 함수가 Odbc.ini 파일이나 레지스트리에 올바르게 기록되기 때문에 함수를 사용하는 경우 코드는 16비트에서 32비트로 이식가능합니다.

## <a name="sqlconfigdatasource-parameters"></a><a name="_core_sqlconfigdatasource_parameters"></a>SQLConfigData소스 매개 변수

다음은 함수의 매개 변수에 대해 `::SQLConfigDataSource` 설명합니다. 대부분의 정보는 Visual C++ 버전 1.5 이상과 함께 제공되는 ODBC API *프로그래머의 참조에서* 가져옵니다.

### <a name="function-prototype"></a><a name="_core_function_prototype"></a>기능 프로토타입

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>설명

#### <a name="parameters-and-usage"></a><a name="_core_parameters_and_usage"></a>매개 변수 및 사용법

*hwndParent*<br/>
ODBC 드라이버 관리자 또는 특정 ODBC 드라이버가 새 데이터 원본에 대한 추가 정보를 얻기 위해 만드는 대화 상자의 소유자로 지정된 창입니다. *lpszAttributes* 매개 변수가 충분한 정보를 제공하지 않으면 대화 상자가 나타납니다. *hwndParent* 매개 변수는 NULL일 수 있습니다.

*lpsz드라이버*<br/>
드라이버 설명입니다. 이 이름은 DLL(실제 드라이버 이름)이 아니라 사용자에게 표시되는 이름입니다.

*lpsz속성*<br/>
"키 이름=value" 형식의 특성 목록입니다. 이러한 문자열은 목록 끝에 두 개의 연속된 null 종단이 있는 null 종기로 구분됩니다. 이러한 특성은 주로 새 데이터 원본의 레지스트리로 이동하는 기본 드라이버 관련 항목입니다. 이 함수에 대한 ODBC API 참조에서 언급되지 않은 중요한 키 중 하나는 새 데이터 원본의 이름을 지정하는 "DSN"("데이터 원본 이름")입니다. 나머지 항목은 새 데이터 원본의 드라이버에 따라 다릅니다. 드라이버가 새 값에 대한 대화 상자를 사용자에게 표시할 수 있으므로 모든 항목을 제공할 필요는 없는 경우가 많습니다. *(hwndParent를* NULL로 설정하여 이를 발생시도록 합니다.) 사용자에게 프롬프트가 지정되지 않도록 기본값을 명시적으로 제공할 수 있습니다.

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC 관리자를 사용하여 lpszDriver 매개 변수에 대한 드라이버 설명을 확인하려면

1. ODBC 관리자를 실행합니다.

1. **추가**를 클릭합니다.

이렇게 하면 설치된 드라이버 목록과 해당 설명이 표시됩니다. 이 설명을 *lpszDriver* 매개 변수로 사용합니다. 설명에 있는 경우 파일 이름 확장자 및 괄호를 포함하여 "Excel 파일(*.xls)"과 같은 전체 설명을 사용합니다.

또는 레지스트리 키 "ODBC 드라이버"(또는 Odbc.ini의 [ODBC 드라이버] 섹션)에서 모든 드라이버 항목 및 설명 목록을 포함하는 레지스트리(또는 16비트의 경우 Odbcinst.ini 파일)를 검사할 수 있습니다.

*lpszAttributes* 매개 변수에 대 한 키 이름 및 값을 찾는 한 가지 방법은 이미 구성 된 데이터 원본에 대 한 Odbc.ini 파일을 검사 하는 것입니다 (아마도 ODBC 관리자에 의해 구성 된 것).

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>lpszAttributes 매개 변수에 대한 키 이름 및 값을 찾으려면

1. Windows 레지스트리 편집기(또는 16비트의 경우 Odbc.ini 파일을 엽니다)를 실행합니다.

1. 다음 중 하나를 사용하여 ODBC 데이터 원본 정보를 찾습니다.

   - 32비트의 경우 키 **HKEY_CURRENT_USER\Software\ODBC\ODBC를 찾습니다. **왼쪽 창에 있는 INI\ODBC 데이터 원본입니다.

      오른쪽 창에는 양식의 항목이 나열됩니다: "pub: REG_SZ:*\<데이터 원본 이름>", * * \<데이터 원본 이름>* 이미 사용하려는 드라이버에 대 한 원하는 설정으로 구성 된 데이터 원본입니다. SQL Server와 같은 원하는 데이터 원본을 선택합니다. 문자열 "pub:" 다음항목은 *lpszAttributes* 매개 변수에 사용할 키 이름과 값입니다.

   - 16비트의 경우*\<[데이터 원본 이름>]로 *표시된 Odbc.ini 파일에서 섹션을 찾습니다.

      이 줄 다음의 줄은 "keyname=value" 양식입니다. *lpszAttributes* 매개 변수에서 사용할 항목입니다.

사용할 특정 드라이버에 대한 설명서를 검토할 수도 있습니다. ODBC 관리자를 실행하여 액세스할 수 있는 드라이버에 대한 온라인 도움말에서 유용한 정보를 찾을 수 있습니다. 이러한 도움말 파일은 일반적으로 Windows NT, Windows 3.1 또는 Windows 95용 WINDOWS\SYSTEM 디렉토리에 배치됩니다.

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC 드라이버에 대한 온라인 도움말을 얻으려면

1. ODBC 관리자를 실행합니다.

1. **추가**를 클릭합니다.

1. 드라이버 이름을 선택합니다.

1. **확인**을 클릭합니다.

ODBC 관리자가 특정 드라이버에 대한 새 데이터 원본을 만들기 위한 정보를 표시하면 **도움말 을 클릭합니다.** 그러면 일반적으로 드라이버 사용과 관련된 중요한 정보가 포함된 특정 드라이버에 대한 도움말 파일이 열립니다.

## <a name="see-also"></a>참고 항목

[데이터 소스(ODBC)](../../data/odbc/data-source-odbc.md)
