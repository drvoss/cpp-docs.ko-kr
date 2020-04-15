---
title: 'MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC applications [C++], without views
- documents [C++], applications without
- ODBC applications [C++]
- document/view architecture [C++], in databases
- files [C++], MFC
- database classes [C++], MFC
- CRecordView class, using in database applications
- database applications [C++], without views
- database applications [C++], application wizard options
- application wizards [C++], creating database applications
- ODBC [C++], file support in database applications
- ODBC applications [C++], without documents
- database applications [C++], without documents
- user interface [C++], drawing information
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
ms.openlocfilehash: c914a449b73e7da876d2e05b894c016b53881c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360665"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: 문서 및 뷰를 이용하지 않는 데이터베이스 클래스 사용

데이터베이스 응용 프로그램에서 프레임워크의 문서/뷰 아키텍처를 사용하지 않을 수 있습니다. 이 토픽에서는 다음 내용을 설명합니다.

- 문서 직렬화와 같은 [문서를 사용할 필요가 없는 경우](#_core_when_you_don.92.t_need_documents)

- [응용 프로그램 마법사 옵션은](#_core_appwizard_options_for_documents_and_views) 직렬화 없이 문서 관련 **파일** 메뉴 명령(예: **새**것, **열기,** **저장**및 **저장)이**없는 응용 프로그램을 지원합니다.

- [최소한의 문서를 사용하는 응용 프로그램으로 작업하는 방법](#_core_applications_with_minimal_documents).

- [문서 나 보기없이 응용 프로그램을 구성하는 방법](#_core_applications_with_no_document).

## <a name="when-you-do-not-need-documents"></a><a name="_core_when_you_don.92.t_need_documents"></a>문서가 필요하지 않은 경우

일부 응용 프로그램에는 문서의 고유한 개념이 있습니다. 이러한 응용 프로그램은 일반적으로 **파일 열기** 명령을 통해 저장소에서 메모리로 파일의 전부 또는 대부분을 로드합니다. 파일 **저장** 또는 **저장** 명령을 사용하여 업데이트된 파일을 저장소에 한 번에 다시 씁니다. 사용자가 보는 것은 데이터 파일입니다.

그러나 일부 응용 프로그램 범주는 문서가 필요하지 않습니다. 데이터베이스 응용 프로그램은 트랜잭션 측면에서 작동합니다. 응용 프로그램은 데이터베이스에서 레코드를 선택하고 사용자에게 한 번에 하나씩 제공합니다. 사용자가 보는 것은 일반적으로 메모리에 있는 유일한 레코드일 수 있는 단일 현재 레코드입니다.

응용 프로그램에 데이터를 저장하기 위한 문서가 필요하지 않은 경우 프레임워크의 문서/뷰 아키텍처의 일부 또는 전부를 사용하지 않도록 할 수 있습니다. 얼마나 많은 분배는 선호하는 접근 방식에 따라 다릅니다. 다음을 수행할 수 있습니다.

- 최소한의 문서를 사용하여 데이터 원본에 대한 연결을 저장하지만 직렬화와 같은 일반 문서 기능을 사용하지 않습니다. 이 기능은 데이터의 여러 뷰를 원하고 모든 뷰를 동기화하고 한 번에 모두 업데이트하려는 경우에 유용합니다.

- 뷰를 사용하는 대신 직접 그리는 프레임 창을 사용합니다. 이 경우 문서를 생략하고 프레임 창 개체에 데이터 또는 데이터 연결을 저장합니다.

## <a name="application-wizard-options-for-documents-and-views"></a><a name="_core_appwizard_options_for_documents_and_views"></a>문서 및 보기에 대한 응용 프로그램 마법사 옵션

MFC 응용 프로그램 마법사에는 다음 표에 나열된 **데이터베이스 지원 선택에**몇 가지 옵션이 있습니다. MFC 응용 프로그램 마법사를 사용하여 응용 프로그램을 만드는 경우 이러한 모든 옵션은 문서 및 뷰가 있는 응용 프로그램을 생성합니다. 일부 옵션은 불필요한 문서 기능을 생략하는 문서 및 보기를 제공합니다. 자세한 내용은 [데이터베이스 지원, MFC 응용 프로그램 마법사를](../mfc/reference/database-support-mfc-application-wizard.md)참조하십시오.

|옵션|보기|문서|
|------------|----------|--------------|
|**없음**|`CView`에서 파생됩니다.|데이터베이스 지원을 제공하지 않습니다. 기본 옵션입니다.<br /><br /> [응용 프로그램 유형, MFC 응용 프로그램 마법사](../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서/보기 아키텍처 지원** 옵션을 선택하면 **파일** 메뉴에서 직렬화 및 **새로**시작됨, **열기,** **저장**및 **저장** 명령을 비롯한 전체 문서 지원을 받을 수 있습니다. [문서가 없는 응용 프로그램을](#_core_applications_with_no_document)참조하십시오.|
|**헤더 파일만**|`CView`에서 파생됩니다.|응용 프로그램에 대한 기본 데이터베이스 지원 수준을 제공합니다.<br /><br /> Afxdb.h가 포함되어 있습니다. 링크 라이브러리를 추가하지만 데이터베이스별 클래스를 만들지는 않습니다. 나중에 레코드 집합을 만들고 레코드를 검사하고 업데이트하는 데 사용할 수 있습니다.|
|**파일 지원이 없는 데이터베이스 보기**|에서 파생`CRecordView`|문서 지원을 제공하지만 직렬화 지원은 없습니다. 문서는 레코드 집합을 저장하고 여러 뷰를 조정할 수 있습니다. 직렬화 또는 **새**, **열기**, **저장**및 **Save As** 명령을 지원하지 않습니다. [최소한의 문서로 응용 프로그램을](#_core_applications_with_minimal_documents)참조하십시오. 데이터베이스 뷰를 포함하는 경우 데이터의 원본을 지정해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 링크 라이브러리, 레코드 보기 및 레코드 집합을 포함합니다. (응용 프로그램 [유형, MFC 응용](../mfc/reference/application-type-mfc-application-wizard.md) 프로그램 마법사 페이지에서 선택한 **문서/보기 아키텍처 지원** 옵션이 있는 응용 프로그램에만 사용할 수 있습니다.)|
|**파일 지원이 있는 데이터베이스 보기**|에서 파생`CRecordView`|직렬화 및 문서 관련 **파일** 메뉴 명령을 포함하여 전체 문서 지원을 제공합니다. 데이터베이스 응용 프로그램은 일반적으로 파일별로 가기보다는 레코드단위로 작동하므로 직렬화가 필요하지 않습니다. 그러나 직렬화에 특히 사용할 수 있습니다. [최소한의 문서로 응용 프로그램을](#_core_applications_with_minimal_documents)참조하십시오. 데이터베이스 뷰를 포함하는 경우 데이터의 원본을 지정해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 링크 라이브러리, 레코드 보기 및 레코드 집합을 포함합니다. (응용 프로그램 [유형, MFC 응용](../mfc/reference/application-type-mfc-application-wizard.md) 프로그램 마법사 페이지에서 선택한 **문서/보기 아키텍처 지원** 옵션이 있는 응용 프로그램에만 사용할 수 있습니다.)|

직렬화및 직렬화에 대한 대체 용도에 대한 대안에 대한 설명은 [직렬화: 직렬화 와 데이터베이스 입력/출력을 참조하십시오.](../mfc/serialization-serialization-vs-database-input-output.md)

## <a name="applications-with-minimal-documents"></a><a name="_core_applications_with_minimal_documents"></a>최소한의 문서가 있는 응용 프로그램

MFC 응용 프로그램 마법사에는 양식 기반 데이터 액세스 응용 프로그램을 지원하는 두 가지 옵션이 있습니다. 각 옵션은 `CRecordView`-파생 뷰 클래스와 문서를 만듭니다. 문서에서 나가는 내용이 다릅니다.

### <a name="document-without-file-support"></a><a name="_core_a_document_without_file_support"></a>파일 지원이 없는 문서

문서 직렬화가 필요하지 않은 경우 파일 지원 없이 응용 프로그램 마법사 데이터베이스 **옵션 데이터베이스 보기를** 선택합니다. 이 문서는 다음과 같은 유용한 용도로 사용됩니다.

- `CRecordset` 개체를 저장하기에 편리한 장소입니다.

   이 사용은 일반적인 문서 개념과 유사합니다: 문서는 데이터를 저장합니다(또는 이 경우 레코드 집합) 뷰는 문서의 보기입니다.

- 응용 프로그램에서 여러 보기(예: 여러 레코드 보기)를 제공하는 경우 문서는 뷰 조정을 지원합니다.

   여러 뷰에 동일한 데이터가 표시되는 경우 `CDocument::UpdateAllViews` 멤버 함수를 사용하여 뷰가 데이터를 변경할 때 모든 뷰에 대한 업데이트를 조정할 수 있습니다.

일반적으로 간단한 양식 기반 응용 프로그램에이 옵션을 사용 합니다. 응용 프로그램 마법사는 이러한 응용 프로그램에 대한 편리한 구조를 자동으로 지원합니다.

### <a name="document-with-file-support"></a><a name="_core_a_document_with_file_support"></a>파일 지원이 있는 문서

문서 **관련** 파일 메뉴 명령 및 문서 직렬화에 대한 대체 용도가 있는 경우 파일 지원을 사용하는 응용 프로그램 마법사 데이터베이스 **보기를** 선택합니다. 프로그램의 데이터 액세스 부분의 경우 [파일 지원 없이](#_core_a_document_without_file_support)문서에 설명된 것과 동일한 방식으로 문서를 사용할 수 있습니다. 예를 들어 문서의 직렬화 기능을 사용하여 사용자의 기본 설정 또는 기타 유용한 정보를 저장하는 직렬화된 사용자 프로필 문서를 읽고 쓸 수 있습니다. 자세한 내용은 [직렬화: 직렬화 와 데이터베이스 입력/출력](../mfc/serialization-serialization-vs-database-input-output.md)을 참조하십시오.

응용 프로그램 마법사는 이 옵션을 지원하지만 문서를 직렬화하는 코드를 작성해야 합니다. 직렬화된 정보를 문서 데이터 멤버에 저장합니다.

## <a name="applications-with-no-document"></a><a name="_core_applications_with_no_document"></a>문서가 없는 응용 프로그램

문서 나 뷰를 사용하지 않는 응용 프로그램을 작성할 수도 있습니다. 문서가 없으면 프레임 창 클래스 또는 `CRecordset` 응용 프로그램 클래스에 데이터(예: 개체)를 저장할 수 있습니다. 추가 요구 사항은 응용 프로그램이 사용자 인터페이스를 제공하는지 여부에 따라 달라집니다.

### <a name="database-support-with-a-user-interface"></a><a name="_core_database_support_with_a_user_interface"></a>사용자 인터페이스를 갖춘 데이터베이스 지원

콘솔 명령줄 인터페이스 를 제외한 사용자 인터페이스가 있는 경우 응용 프로그램은 뷰가 아닌 프레임 창의 클라이언트 영역으로 직접 그립니다. 이러한 응용 프로그램은 `CRecordView`을 `CFormView`사용하거나 `CDialog` 기본 사용자 인터페이스에 사용하지 `CDialog` 않지만 일반적으로 일반 대화 상자에 사용됩니다.

### <a name="writing-applications-without-documents"></a><a name="_core_writing_applications_without_documents"></a>문서 없이 응용 프로그램 작성

응용 프로그램 마법사는 문서 없이 응용 프로그램 만들기를 `CWinApp`지원하지 않으므로 사용자 고유의 파생 클래스를 작성하고 필요한 경우 a `CFrameWnd` 또는 `CMDIFrameWnd` 클래스를 만들어야 합니다. 응용 `CWinApp::InitInstance` 프로그램 개체를 다음과 같이 재정의하고 선언합니다.

```cpp
CYourNameApp theApp;
```

프레임워크는 여전히 메시지 맵 메커니즘 및 기타 여러 기능을 제공합니다.

### <a name="database-support-separate-from-the-user-interface"></a><a name="_core_database_support_separate_from_the_user_interface"></a>데이터베이스 지원 사용자 인터페이스와 별개

일부 응용 프로그램에는 사용자 인터페이스가 필요하거나 최소한의 인터페이스만 필요합니다. 예를 들어 다음과 같은 것을 작성한다고 가정합니다.

- 다른 응용 프로그램(클라이언트)이 응용 프로그램과 데이터 원본 간에 데이터를 특수 처리하기 위해 호출하는 중간 데이터 액세스 개체입니다.

- 한 데이터베이스 형식에서 다른 데이터베이스 형식으로 데이터를 이동하거나 계산을 수행하고 일괄 처리를 수행하는 응용 프로그램과 같이 사용자 개입 없이 데이터를 처리하는 응용 프로그램입니다.

개체를 소유하는 `CRecordset` 문서가 없기 때문에 -derive된 응용 프로그램 `CWinApp`클래스에 포함된 데이터 멤버로 저장하려고 할 수 있습니다. 대안은 다음과 같습니다.

- 영구 `CRecordset` 객체를 전혀 유지하지 않습니다. 레코드 집합 클래스 생성자에게 NULL을 전달할 수 있습니다. 이 경우 프레임워크는 레코드 `CDatabase` 집합의 `GetDefaultConnect` 멤버 함수의 정보를 사용하여 임시 개체를 만듭니다. 이것은 가장 가능성이 높은 대체 방법입니다.

- 개체를 `CRecordset` 전역 변수로 만듭니다. 이 변수는 재정의에서 동적으로 만드는 레코드 집합 `CWinApp::InitInstance` 개체에 대한 포인터여야 합니다. 이렇게 하면 프레임워크가 초기화되기 전에 개체를 생성하지 않습니다.

- 문서 또는 뷰의 컨텍스트 내에서와 마찬가지로 레코드 집합 개체를 사용 합니다. 응용 프로그램 또는 프레임 창 개체의 멤버 함수에 레코드 집합을 만듭니다.

## <a name="see-also"></a>참고 항목

[MFC 데이터베이스 클래스](../data/mfc-database-classes-odbc-and-dao.md)
