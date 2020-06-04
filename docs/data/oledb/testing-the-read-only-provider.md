---
title: 읽기 전용 공급자 테스트
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: dc3c4ea36aa9dac64f2aa7861fd5d51927c77ecd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209505"
---
# <a name="testing-the-read-only-provider"></a>읽기 전용 공급자 테스트

공급자를 테스트 하려면 소비자가 필요 합니다. 소비자가 공급자와 일치 하는 경우에 유용 합니다. OLE DB 소비자 템플릿은 OLE DB에 대 한 씬 래퍼로, 공급자 COM 개체와 일치 합니다. 소스는 소비자 템플릿과 함께 제공 되므로 공급자를 디버그 하는 것이 쉽습니다. 소비자 템플릿은 소비자 응용 프로그램을 개발 하는 매우 작고 빠른 방법 이기도 합니다.

이 항목의 예제에서는 테스트 소비자를 위한 기본 MFC 응용 프로그램 마법사 응용 프로그램을 만듭니다. 테스트 응용 프로그램은 OLE DB 소비자 템플릿 코드가 추가 된 간단한 대화 상자입니다.

## <a name="to-create-the-test-application"></a>테스트 애플리케이션을 만들려면

1. **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.

1. **프로젝트 형식** 창에서 **설치** 된 > **Visual C++**  > **MFC/ATL** 폴더를 선택 합니다. **템플릿** 창에서 **MFC 응용 프로그램**을 선택 합니다.

1. 프로젝트 이름에 *TestProv*를 입력 한 다음 **확인**을 클릭 합니다.

   **MFC 응용 프로그램** 마법사가 나타납니다.

1. **응용 프로그램 종류** 페이지에서 **대화 상자 기반**을 선택 합니다.

1. **고급 기능** 페이지에서 **자동화**를 선택 하 고 **마침**을 클릭 합니다.

> [!NOTE]
> `CTestProvApp::InitInstance`에서 `CoInitialize`를 추가 하는 경우에는 응용 프로그램에서 자동화를 지원 하지 않아도 됩니다.

**리소스 뷰**에서 선택 하 여 **TestProv** 대화 상자 (IDD_TESTPROV_DIALOG)를 보고 편집할 수 있습니다. 대화 상자에서 행 집합의 각 문자열에 대해 하나씩 두 개의 목록 상자를 놓습니다. **Enter** 키를 눌러 두 목록 상자에 대 한 sort 속성을 해제 하 고, 목록 상자를 선택 하 고 **정렬** 속성을 **False**로 설정 하 **여+합니다** . 또한 대화 상자에 **실행** 단추를 놓고 파일을 가져옵니다. 완성 된 **TestProv** 대화 상자에는 각각 "string 1" 및 "string 2" 라는 두 개의 목록 상자가 있어야 합니다. 또한 **확인**, **취소**및 **실행** 단추가 있습니다.

대화 상자 클래스 (이 경우 TestProvDlg)에 대 한 헤더 파일을 엽니다. 헤더 파일 (클래스 선언 외부)에 다음 코드를 추가 합니다.

```cpp
////////////////////////////////////////////////////////////////////////
// TestProvDlg.h
#include <atldbcli.h>  

class CProvider
{
// Attributes
public:
   char   szField1[16];
   char   szField2[16];

   // Binding Maps
BEGIN_COLUMN_MAP(CProvider)
   COLUMN_ENTRY(1, szField1)
   COLUMN_ENTRY(2, szField2)
END_COLUMN_MAP()
};
```

코드는 행 집합에 있는 열을 정의 하는 사용자 레코드를 나타냅니다. 클라이언트는 `IAccessor::CreateAccessor`를 호출할 때 이러한 항목을 사용 하 여 바인딩할 열을 지정 합니다. 또한 OLE DB 소비자 템플릿을 사용 하면 열을 동적으로 바인딩할 수 있습니다. COLUMN_ENTRY 매크로는 PROVIDER_COLUMN_ENTRY 매크로의 클라이언트 쪽 버전입니다. 두 개의 COLUMN_ENTRY 매크로는 두 문자열의 서 수, 형식, 길이 및 데이터 멤버를 지정 합니다.

**Ctrl** 키를 누르고 **실행** 단추를 두 번 클릭 하 여 **실행** 단추에 대 한 처리기 함수를 추가 합니다. 함수에 다음 코드를 추가 합니다.

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession session;

   if (source.Open("Custom.Custom.1", NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)
      return;

   while (table.MoveNext() == S_OK)
   {
      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
   }
}
```

`CCommand`, `CDataSource`및 `CSession` 클래스는 모두 OLE DB 소비자 템플릿에 속합니다. 각 클래스는 공급자의 COM 개체를 모방 합니다. `CCommand` 개체는 헤더 파일에 선언 된 `CProvider` 클래스를 템플릿 매개 변수로 사용 합니다. `CProvider` 매개 변수는 공급자의 데이터에 액세스 하는 데 사용 하는 바인딩을 나타냅니다.

각 클래스를 여는 줄은 공급자에 각 COM 개체를 만듭니다. 공급자를 찾으려면 공급자의 `ProgID`을 사용 합니다. 시스템 레지스트리에서 또는 사용자 지정 .rgs 파일 (공급자의 디렉터리를 열고 `ProgID` 키를 검색)을 찾아 `ProgID`를 가져올 수 있습니다.

MyData .txt 파일은 `MyProv` 샘플에 포함 되어 있습니다. 고유한 파일을 만들려면 편집기를 사용 하 여 짝수 문자열을 입력 하 고 각 문자열 사이에 **enter** 키를 누릅니다. 파일을 이동 하는 경우 경로 이름을 변경 합니다.

`table.Open` 줄에서 "c:\\\samples\\\myprov\\\MyData.txt" 문자열을 전달 합니다. `Open` 호출을 한 단계씩 실행 하는 경우이 문자열이 공급자의 `SetCommandText` 메서드에 전달 되는 것을 알 수 있습니다. `ICommandText::Execute` 메서드는 해당 문자열을 사용 했습니다.

데이터를 페치 하려면 테이블에서 `MoveNext`를 호출 합니다. `MoveNext`는 `IRowset::GetNextRows`, `GetRowCount`및 `GetData` 함수를 호출 합니다. 행이 더 이상 없는 경우 (즉, 행 집합의 현재 위치가 `GetRowCount`보다 큰 경우) 루프가 종료 됩니다.

행이 더 이상 없는 경우 공급자는 DB_S_ENDOFROWSET을 반환 합니다. DB_S_ENDOFROWSET 값이 오류가 아닙니다. 데이터 인출 루프를 취소 하 고 SUCCEEDED 매크로를 사용 하지 않으려면 항상 S_OK 인지 확인 해야 합니다.

이제 프로그램을 빌드하고 테스트할 수 있습니다.

## <a name="see-also"></a>참고 항목

[단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)
